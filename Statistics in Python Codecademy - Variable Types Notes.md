# Intro To Variable Types 

Categorical variables:
- Gender
- Political groups
- Can have ranking such as: Poverty, Middle class, Upper-Middle, etc.
- Can be random such as: cat , dog, bird ( no ranking system).... email type... city 
Come in different types such as:
- nominal: names for groups
- ordinal: places in a competition 
- binary

Numeric types:
- quantities: counted or measured 
- ex. points in a game or height
- discrete: represent counts of whole numbers (int). I have 44 children in my classroom.
- continuous: can represent a whole number and decimal. I weight 194.5 lbs (float)

Binary:
- T or F
- Y or N 
- 0 or 1

Flat files aka = tablular files containing columns and rows

![image.png](attachment:image.png)

# Assessing Variable Types


```python
import pandas as pd
import os 
```


```python
os.chdir('Desktop/Practice Data')
```


```python
movies = pd.read_csv('netflix_titles.csv', index_col = 0)
```


```python
#Printing the head of the frame
movies.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>type</th>
      <th>title</th>
      <th>director</th>
      <th>cast</th>
      <th>country</th>
      <th>date_added</th>
      <th>release_year</th>
      <th>rating</th>
      <th>duration</th>
      <th>listed_in</th>
      <th>description</th>
    </tr>
    <tr>
      <th>show_id</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>s1</th>
      <td>Movie</td>
      <td>Dick Johnson Is Dead</td>
      <td>Kirsten Johnson</td>
      <td>NaN</td>
      <td>United States</td>
      <td>September 25, 2021</td>
      <td>2020</td>
      <td>PG-13</td>
      <td>90 min</td>
      <td>Documentaries</td>
      <td>As her father nears the end of his life, filmm...</td>
    </tr>
    <tr>
      <th>s2</th>
      <td>TV Show</td>
      <td>Blood &amp; Water</td>
      <td>NaN</td>
      <td>Ama Qamata, Khosi Ngema, Gail Mabalane, Thaban...</td>
      <td>South Africa</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>TV-MA</td>
      <td>2 Seasons</td>
      <td>International TV Shows, TV Dramas, TV Mysteries</td>
      <td>After crossing paths at a party, a Cape Town t...</td>
    </tr>
    <tr>
      <th>s3</th>
      <td>TV Show</td>
      <td>Ganglands</td>
      <td>Julien Leclercq</td>
      <td>Sami Bouajila, Tracy Gotoas, Samuel Jouy, Nabi...</td>
      <td>NaN</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>TV-MA</td>
      <td>1 Season</td>
      <td>Crime TV Shows, International TV Shows, TV Act...</td>
      <td>To protect his family from a powerful drug lor...</td>
    </tr>
    <tr>
      <th>s4</th>
      <td>TV Show</td>
      <td>Jailbirds New Orleans</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>TV-MA</td>
      <td>1 Season</td>
      <td>Docuseries, Reality TV</td>
      <td>Feuds, flirtations and toilet talk go down amo...</td>
    </tr>
    <tr>
      <th>s5</th>
      <td>TV Show</td>
      <td>Kota Factory</td>
      <td>NaN</td>
      <td>Mayur More, Jitendra Kumar, Ranjan Raj, Alam K...</td>
      <td>India</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>TV-MA</td>
      <td>2 Seasons</td>
      <td>International TV Shows, Romantic TV Shows, TV ...</td>
      <td>In a city of coaching centers known to train I...</td>
    </tr>
  </tbody>
</table>
</div>




```python
rating_variable_type = 'categorical'
rating_variable_type
```




    'categorical'



# Categorical Variables


```python
# Print the unique values in the country column
print(movies.country.unique())
# Set the correct value for country_variable_type
country_variable_type = 'nominal'
```

    ['United States' 'South Africa' nan 'India'
     'United States, Ghana, Burkina Faso, United Kingdom, Germany, Ethiopia'
     'United Kingdom' 'Germany, Czech Republic' 'Mexico' 'Turkey' 'Australia'
     'United States, India, France' 'Finland' 'China, Canada, United States'
     'South Africa, United States, Japan' 'Nigeria' 'Japan'
     'Spain, United States' 'France' 'Belgium' 'United Kingdom, United States'
     'United States, United Kingdom' 'France, United States' 'South Korea'
     'Spain' 'United States, Singapore' 'United Kingdom, Australia, France'
     'United Kingdom, Australia, France, United States'
     'United States, Canada' 'Germany, United States'
     'South Africa, United States' 'United States, Mexico'
     'United States, Italy, France, Japan'
     'United States, Italy, Romania, United Kingdom'
     'Australia, United States' 'Argentina, Venezuela'
     'United States, United Kingdom, Canada' 'China, Hong Kong' 'Russia'
     'Canada' 'Hong Kong' 'United States, China, Hong Kong'
     'Italy, United States' 'United States, Germany'
     'United Kingdom, Canada, United States' ', South Korea' 'Ireland'
     'India, Nepal' 'New Zealand, Australia, France, United States' 'Italy'
     'Italy, Brazil, Greece' 'Argentina' 'Jordan' 'Colombia'
     'United States, Japan' 'Belgium, United Kingdom'
     'Switzerland, United Kingdom, Australia' 'Israel, United States'
     'Canada, United States' 'Brazil' 'Argentina, Spain' 'Taiwan'
     'United States, Nigeria' 'Bulgaria, United States'
     'Spain, United Kingdom, United States' 'United States, China'
     'United States, France' 'Spain, France, United Kingdom, United States'
     ', France, Algeria' 'Poland' 'Germany'
     'France, Israel, Germany, United States, United Kingdom' 'New Zealand'
     'Saudi Arabia' 'Thailand' 'Indonesia' 'Egypt, Denmark, Germany'
     'United States, Switzerland' 'Hong Kong, Canada, United States'
     'Kuwait, United States' 'France, Canada, United States, Spain'
     'France, Netherlands, Singapore' 'France, Belgium'
     'Ireland, United States, United Kingdom' 'Egypt' 'Malaysia' 'Israel'
     'Australia, New Zealand' 'United Kingdom, Germany' 'Belgium, Netherlands'
     'South Korea, Czech Republic' 'Australia, Germany' 'Vietnam'
     'United Kingdom, Belgium' 'United Kingdom, Australia, United States'
     'France, Japan, United States'
     'United Kingdom, Germany, Spain, United States'
     'United Kingdom, United States, France, Italy'
     'United States, Germany, Canada'
     'United States, France, Italy, United Kingdom'
     'United States, United Kingdom, Germany, Hungary'
     'United States, New Zealand' 'Sweden' 'China' 'Lebanon' 'Romania'
     'Finland, Germany' 'Lebanon, Syria' 'Philippines' 'Iceland' 'Denmark'
     'United States, India' 'Philippines, Singapore, Indonesia'
     'China, United States, Canada' 'Lebanon, United Arab Emirates'
     'Canada, United States, Denmark' 'United Arab Emirates'
     'Mexico, France, Colombia' 'Netherlands' 'Germany, United States, France'
     'United States, Bulgaria'
     'United Kingdom, France, Germany, United States' 'Norway, Denmark'
     'Syria, France, Lebanon, Qatar' 'United States, Czech Republic'
     'Mauritius' 'Canada, South Africa' 'Austria' 'Mexico, Brazil'
     'Germany, France' 'Mexico, United States'
     'United Kingdom, France, Spain, United States' 'United States, Australia'
     'United States, United Kingdom, France' 'United States, Russia'
     'United States, United Kingdom, New Zealand' 'Australia, United Kingdom'
     'Canada, Nigeria, United States'
     'France, United States, United Kingdom, Canada' 'France, United Kingdom'
     'India, United Kingdom' 'Canada, United States, Mexico'
     'United Kingdom, Germany, United States'
     'Czech Republic, United Kingdom, United States' 'China, United Kingdom'
     'Italy, United Kingdom' 'China, Taiwan'
     'United States, Brazil, Japan, Spain, India'
     'United States, China, United Kingdom' 'Cameroon'
     'Lebanon, Palestine, Denmark, Qatar' 'Japan, United States'
     'Uruguay, Germany' 'Egypt, Saudi Arabia'
     'United Kingdom, France, Poland, Germany, United States'
     'Ireland, Switzerland, United Kingdom, France, United States'
     'United Kingdom, South Africa, France'
     'Ireland, United Kingdom, France, Germany' 'Russia, United States'
     'United Kingdom, United States, France' 'United Kingdom,'
     'United States, India, United Kingdom' 'Kenya' 'Spain, Argentina'
     'India, United Kingdom, France, Qatar' 'Belgium, France'
     'Argentina, Chile' 'United States, Thailand' 'Chile, Brazil'
     'United States, Colombia' 'Canada, United States, United Kingdom'
     'Uruguay' 'Luxembourg' 'United States, Cambodia, Romania' 'Bangladesh'
     'Spain, Belgium, United States'
     'United Kingdom, United States, Australia'
     'Canada, United States, France' 'Portugal, United States'
     'Portugal, Spain' 'India, United States' 'United Kingdom, Ireland'
     'United Kingdom, Spain, United States' 'Hungary, United States'
     'United States, South Korea' 'Canada, United States, Cayman Islands'
     'India, France' 'France, Canada' 'Canada, Hungary, United States'
     'Norway' 'Canada, United Kingdom, United States'
     'United Kingdom, Germany, France, United States' 'Denmark, United States'
     'Senegal' 'France, Algeria'
     'United Kingdom, Finland, Germany, United States, Australia, Japan, France, Ireland'
     'Philippines, Canada, United Kingdom, United States'
     'Ireland, France, Iceland, United States, Mexico, Belgium, United Kingdom, Hong Kong'
     'Singapore' 'Kuwait' 'United States, France, Serbia'
     'United States, Italy' 'Spain, Italy'
     'United States, Ireland, United Kingdom, India'
     'United Kingdom, Singapore' 'Hong Kong, United States'
     'United States, Malta, France, United Kingdom'
     'United States, China, Canada' 'Canada, United States, Ireland'
     'Lebanon, Canada, France' 'Japan, Canada, United States'
     'Spain, France, Canada' 'Denmark, Singapore, Canada, United States'
     'United States, France, Denmark' 'United States, China, Colombia'
     'Spain, Thailand, United States' 'Mexico, Spain'
     'Ireland, Luxembourg, Belgium' 'China, United States' 'Canada, Belgium'
     'Canada, United Kingdom'
     'Lebanon, United Arab Emirates, France, Switzerland, Germany'
     'France, Belgium, Italy' 'Lebanon, United States, United Arab Emirates'
     'Lebanon, France' 'France, Lebanon' 'France, Lebanon, United Kingdom'
     'France, Norway, Lebanon, Belgium'
     'Sweden, Czech Republic, United Kingdom, Denmark, Netherlands'
     'United States, United Kingdom, India' 'Indonesia, Netherlands'
     'Turkey, South Korea' 'Serbia, United States' 'Namibia'
     'United Kingdom, Kenya' 'United Kingdom, France, Germany, Spain'
     'United Kingdom, France, United States, Belgium, Luxembourg, China, Germany'
     'Thailand, United States' 'United States, France, Canada, Belgium'
     'United Kingdom, China' 'Germany, China, United Kingdom'
     'Australia, New Zealand, United States'
     'Hong Kong, Iceland, United States' 'France, Australia, Germany'
     'United States, Belgium, Canada, France' 'South Africa, Angola'
     'United States, Philippines'
     'United States, United Kingdom, Canada, China'
     'United States, Canada, United Kingdom' 'Turkey, United States'
     'Peru, Germany, Norway' 'Mozambique' 'Brazil, France'
     'China, Spain, South Korea, United States' 'Spain, Germany'
     'Hong Kong, China' 'France, Belgium, Luxembourg, Cambodia,'
     'United Kingdom, Australia' 'Belarus' 'Indonesia, United Kingdom'
     'Switzerland, France, Belgium, United States' 'Ghana'
     'Spain, France, Canada, United States' 'Chile, Italy'
     'United Kingdom, Nigeria' 'Chile' 'France, Egypt' 'Egypt, France'
     'France, Brazil, Spain, Belgium' 'Egypt, Algeria'
     'Canada, South Korea, United States' 'Nigeria, United Kingdom'
     'United States, France, Canada' 'Poland, United States'
     'United Arab Emirates, Jordan, Lebanon, Saudi Arabia'
     'United States, Mexico, Spain, Malta'
     'Saudi Arabia, United Arab Emirates' 'Zimbabwe'
     'United Kingdom, Germany, United Arab Emirates, New Zealand'
     'Romania, United States' 'Canada, Nigeria'
     'Saudi Arabia, Netherlands, Germany, Jordan, United Arab Emirates, United States'
     'United Kingdom, Spain' 'Finland, France'
     'United Kingdom, Germany, United States, France'
     'India, United Kingdom, China, Canada, Japan, South Korea, United States'
     'Italy, United Kingdom, France' 'United States, Mexico, Colombia'
     'Turkey, India' 'Italy, Turkey' 'United Kingdom, United States, Japan'
     'France, Belgium, United States' 'Puerto Rico, United States, Colombia'
     'Uruguay, Argentina' 'United States, United Kingdom, Japan'
     'United States, Argentina' 'United Kingdom, Italy'
     'Ireland, United Kingdom'
     'United Kingdom, France, Belgium, Canada, United States'
     'Netherlands, Germany, Denmark, United Kingdom' 'Hungary'
     'Austria, Germany' 'Taiwan, China'
     'United Kingdom, United States, Ireland' 'South Korea, United States'
     'Brazil, United Kingdom' 'Pakistan, United States'
     'Romania, France, Switzerland, Germany' 'Romania, United Kingdom'
     'France, Malta, United States' 'Cyprus'
     'United Kingdom, France, Belgium, Ireland, United States'
     'United States, Norway, Canada' 'Kenya, United States'
     'France, South Korea, Japan, United States' 'Taiwan, Malaysia'
     'Uruguay, Argentina, Germany, Spain'
     'United States, United Kingdom, France, Germany, Japan'
     'United States, France, Japan' 'United Kingdom, France, United States'
     'Spain, France, United States' 'Indonesia, South Korea, Singapore'
     'United States, Spain' 'Netherlands, Germany, Italy, Canada'
     'Spain, Germany, Denmark, United States' 'Norway, Sweden'
     'South Korea, Canada, United States, China' 'Argentina, Uruguay, Serbia'
     'France, Japan' 'Mauritius, South Africa' 'United States, Poland'
     'United Kingdom, United States, Germany, Denmark, Belgium, Japan'
     'India, Germany' 'India, United Kingdom, Canada, United States'
     'Philippines, United States' 'Romania, Bulgaria, Hungary'
     'Uruguay, Guatemala' 'France, Senegal, Belgium' 'United Kingdom, Canada'
     'Mexico, United States, Spain, Colombia' 'Canada, Norway'
     'Singapore, United States' 'Finland, Germany, Belgium'
     'United Kingdom, France' 'United States, Chile'
     'United Kingdom, Japan, United States' 'Spain, United Kingdom'
     'Argentina, United States, Mexico' 'United States, South Korea, Japan'
     'Canada, Australia' 'United Kingdom, Hungary, Australia' 'Italy, Belgium'
     'United States, United Kingdom, Germany' 'Switzerland'
     'Singapore, Malaysia'
     'France, Belgium, Luxembourg, Romania, Canada, United States'
     'South Africa, Nigeria' 'Spain, France' 'United Kingdom, Hong Kong'
     'Pakistan' 'Brazil, United States'
     'Denmark, Brazil, France, Portugal, Sweden' 'India, Turkey'
     'Malaysia, Singapore, Hong Kong' 'Philippines, Singapore'
     'Australia, Canada' 'Taiwan, China, France, United States'
     'Germany, Italy' 'Colombia, Peru, United Kingdom'
     'Thailand, China, United States' 'Argentina, United States'
     'Sweden, United States' 'Uruguay, Spain, Mexico'
     'France, Luxembourg, Canada' 'Denmark, Spain' 'Chile, Argentina'
     'United Kingdom, Belgium, Sweden' 'Canada, Brazil' 'Italy, France'
     'Canada, Germany' 'Pakistan, United Arab Emirates' 'Ghana, United States'
     'Mexico, Finland' 'United Arab Emirates, United Kingdom, India'
     'Netherlands, Belgium' 'United States, Taiwan'
     'Austria, Iraq, United States' 'United Kingdom, Malawi'
     'Paraguay, Argentina' 'United Kingdom, Russia, United States'
     'India, Pakistan' 'Indonesia, Singapore' 'Spain, Belgium'
     'Iceland, Sweden, Belgium' 'Croatia' 'Uruguay, Argentina, Spain'
     'United Kingdom, Ireland, United States'
     'Canada, Germany, France, United States' 'United Kingdom, Japan'
     'Norway, Denmark, Netherlands, Sweden' 'Hong Kong, China, United States'
     'Ireland, Canada' 'Italy, Switzerland, France, Germany'
     'Mexico, Netherlands' 'United States, Sweden' 'Germany, France, Russia'
     'France, Iran, United States' 'United Kingdom, India'
     'Russia, Poland, Serbia' 'Spain, Portugal' 'Peru' 'Mexico, Argentina'
     'United Kingdom, Canada, United States, Cayman Islands'
     'Indonesia, United States'
     'United States, Israel, United Kingdom, Canada'
     'Norway, Iceland, United States' 'Czech Republic, United States'
     'United Kingdom, India, United States' 'United Kingdom, West Germany'
     'India, Australia' 'United States,'
     'Belgium, United Kingdom, United States' 'India, Germany, Austria'
     'United States, Brazil, South Korea, Mexico, Japan, Germany'
     'Spain, Mexico' 'China, Japan' 'Argentina, France'
     'China, United States, United Kingdom'
     'France, Luxembourg, United States' 'China, United States, Australia'
     'Colombia, Mexico' 'United States, Canada, Ireland' 'Chile, Peru'
     'Argentina, Italy' 'Canada, Japan, United States'
     'United Kingdom, Canada, United States, Germany'
     'Italy, Switzerland, Albania, Poland' 'United States, Japan, Canada'
     'Cambodia' 'Italy, United States, Argentina'
     'Saudi Arabia, Syria, Egypt, Lebanon, Kuwait'
     'United States, Canada, Indonesia, United Kingdom, China, Singapore'
     'Spain, Colombia'
     'United Kingdom, South Africa, Australia, United States' 'Bulgaria'
     'Argentina, Brazil, France, Poland, Germany, Denmark'
     'United Kingdom, Spain, United States, Germany' 'Philippines, Qatar'
     'Netherlands, Belgium, Germany, Jordan'
     'United Arab Emirates, United States' 'Norway, Germany, Sweden'
     'South Korea, China' 'Georgia' 'Soviet Union, India'
     'Australia, United Arab Emirates' 'Canada, Germany, South Africa'
     'South Korea, China, United States' 'India, Soviet Union' 'India, Mexico'
     'Georgia, Germany, France' 'United Arab Emirates, Romania'
     'India, Malaysia' 'Germany, Jordan, Netherlands'
     'Turkey, France, Germany, Poland' 'Greece, United States'
     'France, United Kingdom, United States' 'Norway, Germany'
     'France, Morocco' 'Cambodia, United States' 'United States, Denmark'
     'United States, Colombia, Mexico'
     'United Kingdom, Italy, Israel, Peru, United States'
     'Argentina, Uruguay, Spain, France'
     'United Kingdom, France, United States, Belgium'
     'France, Canada, China, Cambodia'
     'United Kingdom, France, Belgium, United States' 'Chile, France'
     'Netherlands, United States' 'France, United Kingdom, India'
     'Czech Republic, Slovakia' 'Singapore, France' 'Spain, Switzerland'
     'United States, Australia, China' 'South Africa, United States, Germany'
     'United States, United Kingdom, Australia' 'Spain, Italy, Argentina'
     'Chile, Spain, Argentina, Germany' 'West Germany'
     'Austria, Czech Republic' 'Lebanon, Qatar'
     'United Kingdom, Jordan, Qatar, Iran' 'France, South Korea, Japan'
     'Israel, Germany, France' 'Canada, Japan, Netherlands'
     'United States, Hungary' 'France, Germany' 'France, Qatar'
     'United Kingdom, Germany, Canada' 'Ireland, South Africa'
     'Chile, United States, France' 'Belgium, France, Netherlands'
     'United Kingdom, Ukraine, United States'
     'Germany, Australia, France, China' 'Norway, United States'
     'United States, Bermuda, Ecuador'
     'United States, Hungary, Ireland, Canada'
     'United Kingdom, Egypt, United States'
     'United States, France, United Kingdom' 'Spain, Mexico, France'
     'United States, South Africa' 'Hong Kong, China, Singapore'
     'South Africa, China, United States' 'Denmark, France, Poland'
     'New Zealand, United Kingdom' 'Netherlands, Denmark, South Africa'
     'Iran, France' 'United Kingdom, United States, France, Germany'
     'Australia, France' 'Ireland, United Kingdom, United States'
     'United Kingdom, France, Germany' 'Canada, Luxembourg'
     'Brazil, Netherlands, United States, Colombia, Austria, Germany'
     'France, Canada, Belgium' 'Canada, France'
     'Bulgaria, United States, Spain, Canada' 'Sweden, Netherlands'
     'France, United States, Mexico'
     'Australia, United Kingdom, United Arab Emirates, Canada'
     'Australia, Armenia, Japan, Jordan, Mexico, Mongolia, New Zealand, Philippines, South Africa, Sweden, United States, Uruguay'
     'India, Iran' 'France, Belgium, Spain'
     'Denmark, Sweden, Israel, United States' 'United States, Iceland'
     'United Kingdom, Russia' 'United States, Israel, Italy, South Africa'
     'Netherlands, Denmark, France, Germany' 'South Korea, Japan'
     'United Kingdom, Pakistan' 'France, New Zealand'
     'United Kingdom, Czech Republic, United States, Germany, Bahamas'
     'China, Germany, India, United States' 'Germany, Sri Lanka'
     'United States, India, Bangladesh' 'United States, Canada, France'
     'Brazil, France, Germany' 'Germany, United States, Hong Kong, Singapore'
     'France, Germany, Switzerland'
     'Germany, France, Luxembourg, United Kingdom, United States'
     'United Kingdom, Canada, Italy' 'Czech Republic, France'
     'Taiwan, Hong Kong, United States, China' 'Germany, Australia'
     'United Kingdom, Poland, United States' 'Denmark, Zimbabwe'
     'United Kingdom, South Africa' 'Finland, Sweden, Norway, Latvia, Germany'
     'South Africa, United States, New Zealand, Canada'
     'United States, Italy, United Kingdom, Liechtenstein'
     'Denmark, France, Belgium, Italy, Netherlands, United States, United Kingdom'
     'United States, Australia, Mexico'
     'United Kingdom, Czech Republic, Germany, United States'
     'France, China, Japan, United States' 'United States, South Korea, China'
     'Germany, Belgium' 'Pakistan, Norway, United States'
     'United States, Canada, Belgium, United Kingdom' 'Venezuela'
     'Canada, France, Italy, Morocco, United States' 'Canada, Spain, France'
     'United States, Indonesia' 'Spain, France, Italy'
     'United Arab Emirates, United States, United Kingdom'
     'United Kingdom, Israel, Russia' 'Spain, Cuba' 'United States, Brazil'
     'United States, France, Mexico' 'United States, Nicaragua'
     'United Kingdom, United States, Spain, Germany, Greece, Canada'
     'Italy, Canada, France' 'United Kingdom, Denmark, Canada, Croatia'
     'Italy, Germany' 'United States, France, United Kingdom, Japan'
     'United States, United Kingdom, Denmark, Sweden'
     'United States, United Kingdom, Italy'
     'United States, France, Canada, Spain' 'Russia, United States, China'
     'United States, Canada, Germany' 'Ireland, United States'
     'United States, United Arab Emirates' 'United States, Ireland'
     'Ireland, United Kingdom, Italy, United States' 'Poland,'
     'Slovenia, Croatia, Germany, Czech Republic, Qatar'
     'Canada, United Kingdom, Netherlands' 'United States, Spain, Germany'
     'India, Japan' 'China, South Korea, United States'
     'United Kingdom, France, Belgium' 'Canada, Ireland, United States'
     'United Kingdom, United States, Dominican Republic'
     'United States, Senegal' 'Germany, United Kingdom, United States'
     'South Africa, Germany, Netherlands, France'
     'Canada, United States, United Kingdom, France, Luxembourg'
     'Ireland, United States, France' 'Germany, United States, Canada'
     'United Kingdom, Germany, Canada, United States'
     'United States, France, Canada, Lebanon, Qatar'
     'Netherlands, Belgium, United Kingdom, United States'
     'France, Belgium, China, United States' 'United States, Chile, Israel'
     'United Kingdom, Norway, Denmark, Germany, Sweden'
     'Norway, Denmark, Sweden' 'China, India, Nepal'
     'Colombia, Mexico, United States' 'United Kingdom, South Korea'
     'Denmark, China' 'United States, Greece, Brazil' 'South Korea, France'
     'United States, Australia, Samoa, United Kingdom'
     'Germany, United Kingdom' 'Argentina, Chile, Peru' 'Turkey, Azerbaijan'
     'Poland, West Germany' 'Germany, United States, Sweden' 'Canada, Spain'
     'United States, Cambodia' 'United States, Greece'
     'Norway, United Kingdom, France, Ireland' 'United Kingdom, Poland'
     'Israel, Sweden, Germany, Netherlands' 'Switzerland, France'
     'Italy, India' 'United States, Botswana'
     'Chile, Argentina, France, Spain, United States'
     'United States, India, South Korea, China'
     'Denmark, Germany, Belgium, United Kingdom, France'
     'Denmark, Germany, Belgium, United Kingdom, France, Sweden'
     'France, Switzerland, Spain, United States, United Arab Emirates'
     'Brazil, India, China, United States'
     'Denmark, France, United States, Sweden' 'Australia, Iraq'
     'China, Morocco, Hong Kong' 'Canada, United States, Germany'
     'United Kingdom, Thailand' 'Venezuela, Colombia'
     'Colombia, United States' 'France, Germany, Czech Republic, Belgium'
     'Switzerland, Vatican City, Italy, Germany, France'
     'Portugal, France, Poland, United States'
     'United States, New Zealand, Japan'
     'United States, Netherlands, Japan, France' 'India, Switzerland'
     'Canada, India' 'United States, Morocco' 'Singapore, Japan, France'
     'Canada, Mexico, Germany, South Africa'
     'United Kingdom, United States, Canada'
     'Germany, France, United States, Canada, United Kingdom'
     'United States, Uruguay' 'India, Canada'
     'Ireland, Canada, United Kingdom, United States'
     'United States, Germany, Australia' 'Australia, France, Ireland'
     'Australia, India' 'United States, United Kingdom, Canada, Japan'
     'Sweden, United Kingdom, Finland' 'Hong Kong, Taiwan'
     'United States, United Kingdom, Spain, South Korea' 'Guatemala' 'Ukraine'
     'Italy, South Africa, West Germany, Australia, United States'
     'United States, Germany, United Kingdom, Australia'
     'Italy, France, Switzerland' 'Canada, France, United States'
     'Switzerland, United States' 'Thailand, Canada, United States'
     'China, Hong Kong, United States' 'United Kingdom, New Zealand'
     'Czech Republic, United Kingdom, France'
     'Australia, United Kingdom, Canada' 'Jamaica, United States'
     'Australia, United Kingdom, United States, New Zealand, Italy, France'
     'France, United States, Canada'
     'United Kingdom, France, Canada, Belgium, United States'
     'Denmark, United Kingdom, Sweden' 'United States, Hong Kong'
     'United States, Kazakhstan'
     'Argentina, France, United States, Germany, Qatar'
     'United States, Germany, United Kingdom'
     'United States, Germany, United Kingdom, Italy'
     'United States, New Zealand, United Kingdom' 'Finland, United States'
     'Spain, France, Uruguay' 'France, Canada, United States'
     'United States, Canada, China'
     'Ireland, Canada, Luxembourg, United States, United Kingdom, Philippines, India'
     'United States, Czech Republic, United Kingdom' 'Israel, Germany'
     'Mexico, France'
     'Israel, Germany, Poland, Luxembourg, Belgium, France, United States'
     'Austria, United States' 'United Kingdom, Lithuania'
     'United States, Greece, United Kingdom'
     'United Kingdom, China, United States, India'
     'United States, Sweden, Norway' 'United Kingdom, United States, Morocco'
     'United States, United Kingdom, Morocco' 'Spain, Canada, United States'
     'United States, India, United Arab Emirates'
     'United Kingdom, Canada, France, United States' 'India, Germany, France'
     'Belgium, Ireland, Netherlands, Germany, Afghanistan'
     'France, Canada, Italy, United States, China'
     'Ireland, United Kingdom, Greece, France, Netherlands'
     'Denmark, Indonesia, Finland, Norway, United Kingdom, Israel, France, United States, Germany, Netherlands'
     'New Zealand, United States'
     'United States, Australia, South Africa, United Kingdom'
     'United States, Germany, Mexico'
     'Somalia, Kenya, Sudan, South Africa, United States'
     'United States, Canada, Japan, Panama' 'United Kingdom, Spain, Belgium'
     'Serbia, South Korea, Slovenia'
     'Denmark, United Kingdom, South Africa, Sweden, Belgium'
     'Germany, Canada, United States'
     'Ireland, Canada, United States, United Kingdom'
     'New Zealand, United Kingdom, Australia'
     'United Kingdom, Australia, Canada, United States'
     'Germany, United States, Italy' 'United States, Venezuela'
     'United Kingdom, Canada, Japan'
     'United Kingdom, United States, Czech Republic'
     'United Kingdom, China, United States' 'United Kingdom, Brazil, Germany'
     'United Kingdom, Namibia, South Africa, Zimbabwe, United States'
     'Canada, United States, India, United Kingdom'
     'Switzerland, United Kingdom, United States'
     'United Kingdom, India, Sweden'
     'United States, Brazil, India, Uganda, China'
     'Peru, United States, United Kingdom'
     'Germany, United States, United Kingdom, Canada'
     'Canada, India, Thailand, United States, United Arab Emirates'
     'United States, East Germany, West Germany'
     'France, Netherlands, South Africa, Finland'
     'Egypt, Austria, United States' 'Russia, Spain'
     'Croatia, Slovenia, Serbia, Montenegro' 'Japan, Canada'
     'United States, France, South Korea, Indonesia'
     'United Arab Emirates, Jordan']



```python
# Set the correct value for release_year_variable_type
release_year_variable_type = 'discrete'
print(release_year_variable_type)

# Set the correct value for duration_variable_type
cast_count_variable_type = 'discrete'
print(cast_count_variable_type)
```

    discrete
    discrete


# The Pandas Category Data Type


```python
# Change the data type of `rating` to category
#Sets the movies in order according to the sequence you put the ratings in 
movies['rating'] = pd.Categorical(movies['rating'], ['NR', 'G','PG','PG-13','R'] ,ordered=True)
```

# One-Hot Encoding


Another way of encoding categorical variables is called One-Hot Encoding (OHE). With OHE, we essentially create a new binary variable for each of the categories within our original variable. This technique is useful when managing nominal variables because it encodes the variable without creating an order among the categories.

![image.png](attachment:image.png)

Notice that when using pd.get_dummies(), we are effectively creating a new dataframe that contains a different set of variables to the original dataframe.


```python
#Assigns a new binary variable to 2 category values 
pd.get_dummies(data=movies, columns=['type'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>title</th>
      <th>director</th>
      <th>cast</th>
      <th>country</th>
      <th>date_added</th>
      <th>release_year</th>
      <th>rating</th>
      <th>duration</th>
      <th>listed_in</th>
      <th>description</th>
      <th>type_Movie</th>
      <th>type_TV Show</th>
    </tr>
    <tr>
      <th>show_id</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>s1</th>
      <td>Dick Johnson Is Dead</td>
      <td>Kirsten Johnson</td>
      <td>NaN</td>
      <td>United States</td>
      <td>September 25, 2021</td>
      <td>2020</td>
      <td>PG-13</td>
      <td>90 min</td>
      <td>Documentaries</td>
      <td>As her father nears the end of his life, filmm...</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>s2</th>
      <td>Blood &amp; Water</td>
      <td>NaN</td>
      <td>Ama Qamata, Khosi Ngema, Gail Mabalane, Thaban...</td>
      <td>South Africa</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>NaN</td>
      <td>2 Seasons</td>
      <td>International TV Shows, TV Dramas, TV Mysteries</td>
      <td>After crossing paths at a party, a Cape Town t...</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>s3</th>
      <td>Ganglands</td>
      <td>Julien Leclercq</td>
      <td>Sami Bouajila, Tracy Gotoas, Samuel Jouy, Nabi...</td>
      <td>NaN</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>NaN</td>
      <td>1 Season</td>
      <td>Crime TV Shows, International TV Shows, TV Act...</td>
      <td>To protect his family from a powerful drug lor...</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>s4</th>
      <td>Jailbirds New Orleans</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>NaN</td>
      <td>1 Season</td>
      <td>Docuseries, Reality TV</td>
      <td>Feuds, flirtations and toilet talk go down amo...</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>s5</th>
      <td>Kota Factory</td>
      <td>NaN</td>
      <td>Mayur More, Jitendra Kumar, Ranjan Raj, Alam K...</td>
      <td>India</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>NaN</td>
      <td>2 Seasons</td>
      <td>International TV Shows, Romantic TV Shows, TV ...</td>
      <td>In a city of coaching centers known to train I...</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>s8803</th>
      <td>Zodiac</td>
      <td>David Fincher</td>
      <td>Mark Ruffalo, Jake Gyllenhaal, Robert Downey J...</td>
      <td>United States</td>
      <td>November 20, 2019</td>
      <td>2007</td>
      <td>R</td>
      <td>158 min</td>
      <td>Cult Movies, Dramas, Thrillers</td>
      <td>A political cartoonist, a crime reporter and a...</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>s8804</th>
      <td>Zombie Dumb</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>July 1, 2019</td>
      <td>2018</td>
      <td>NaN</td>
      <td>2 Seasons</td>
      <td>Kids' TV, Korean TV Shows, TV Comedies</td>
      <td>While living alone in a spooky town, a young g...</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>s8805</th>
      <td>Zombieland</td>
      <td>Ruben Fleischer</td>
      <td>Jesse Eisenberg, Woody Harrelson, Emma Stone, ...</td>
      <td>United States</td>
      <td>November 1, 2019</td>
      <td>2009</td>
      <td>R</td>
      <td>88 min</td>
      <td>Comedies, Horror Movies</td>
      <td>Looking to survive in a world taken over by zo...</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>s8806</th>
      <td>Zoom</td>
      <td>Peter Hewitt</td>
      <td>Tim Allen, Courteney Cox, Chevy Chase, Kate Ma...</td>
      <td>United States</td>
      <td>January 11, 2020</td>
      <td>2006</td>
      <td>PG</td>
      <td>88 min</td>
      <td>Children &amp; Family Movies, Comedies</td>
      <td>Dragged from civilian life, a former superhero...</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>s8807</th>
      <td>Zubaan</td>
      <td>Mozez Singh</td>
      <td>Vicky Kaushal, Sarah-Jane Dias, Raaghav Chanan...</td>
      <td>India</td>
      <td>March 2, 2019</td>
      <td>2015</td>
      <td>NaN</td>
      <td>111 min</td>
      <td>Dramas, International Movies, Music &amp; Musicals</td>
      <td>A scrappy but poor boy worms his way into a ty...</td>
      <td>1</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>8807 rows × 12 columns</p>
</div>




```python
movies.dtypes
```




    type              object
    title             object
    director          object
    cast              object
    country           object
    date_added        object
    release_year       int64
    rating          category
    duration          object
    listed_in         object
    description       object
    dtype: object




```python
movies['release_year'].astype(float)
```




    show_id
    s1       2020.0
    s2       2021.0
    s3       2021.0
    s4       2021.0
    s5       2021.0
              ...  
    s8803    2007.0
    s8804    2018.0
    s8805    2009.0
    s8806    2006.0
    s8807    2015.0
    Name: release_year, Length: 8807, dtype: float64




```python
'hello'
```




    'hello'




```python

```
