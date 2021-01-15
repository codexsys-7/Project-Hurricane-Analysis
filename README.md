# Project-Hurricane-Analysis
The Project is all about organizing, manipulating and viewing the data(HURRICANE_DATA) ,This is a project where we write several functions that organize and manipulate data about Category 5 Hurricanes, the strongest hurricanes as rated by their wind speed. Each one of these functions will use a number of parameters, conditionals, lists, dictionaries, string manipulation, and return statements.

# Below is the code Regarding the Project.
#names of hurricanes
names = ['Cuba I', 'San Felipe II Okeechobee', 'Bahamas', 'Cuba II', 'CubaBrownsville', 'Tampico', 'Labor Day', 'New England', 'Carol', 'Janet', 'Carla', 'Hattie', 'Beulah', 'Camille', 'Edith', 'Anita', 'David', 'Allen', 'Gilbert', 'Hugo', 'Andrew', 'Mitch', 'Isabel', 'Ivan', 'Emily', 'Katrina', 'Rita', 'Wilma', 'Dean', 'Felix', 'Matthew', 'Irma', 'Maria', 'Michael']

# Months of hurricanes
months = ['October', 'September', 'September', 'November', 'August', 'September', 'September', 'September', 'September', 'September', 'September', 'October', 'September', 'August', 'September', 'September', 'August', 'August', 'September', 'September', 'August', 'October', 'September', 'September', 'July', 'August', 'September', 'October', 'August', 'September', 'October', 'September', 'September', 'October']

# Years of hurricanes
years = [1924, 1928, 1932, 1932, 1933, 1933, 1935, 1938, 1953, 1955, 1961, 1961, 1967, 1969, 1971, 1977, 1979, 1980, 1988, 1989, 1992, 1998, 2003, 2004, 2005, 2005, 2005, 2005, 2007, 2007, 2016, 2017, 2017, 2018]

# Maximum sustained winds (mph) of hurricanes
max_sustained_winds = [165, 160, 160, 175, 160, 160, 185, 160, 160, 175, 175, 160, 160, 175, 160, 175, 175, 190, 185, 160, 175, 180, 165, 165, 160, 175, 180, 185, 175, 175, 165, 180, 175, 160]

# Areas affected by each hurricane
areas_affected = [['Central America', 'Mexico', 'Cuba', 'Florida', 'The Bahamas'], ['Lesser Antilles', 'The Bahamas', 'United States East Coast', 'Atlantic Canada'], ['The Bahamas', 'Northeastern United States'], ['Lesser Antilles', 'Jamaica', 'Cayman Islands', 'Cuba', 'The Bahamas', 'Bermuda'], ['The Bahamas', 'Cuba', 'Florida', 'Texas', 'Tamaulipas'], ['Jamaica', 'Yucatn Peninsula'], ['The Bahamas', 'Florida', 'Georgia', 'The Carolinas', 'Virginia'], ['Southeastern United States', 'Northeastern United States', 'Southwestern Quebec'], ['Bermuda', 'New England', 'Atlantic Canada'], ['Lesser Antilles', 'Central America'], ['Texas', 'Louisiana', 'Midwestern United States'], ['Central America'], ['The Caribbean', 'Mexico', 'Texas'], ['Cuba', 'United States Gulf Coast'], ['The Caribbean', 'Central America', 'Mexico', 'United States Gulf Coast'], ['Mexico'], ['The Caribbean', 'United States East coast'], ['The Caribbean', 'Yucatn Peninsula', 'Mexico', 'South Texas'], ['Jamaica', 'Venezuela', 'Central America', 'Hispaniola', 'Mexico'], ['The Caribbean', 'United States East Coast'], ['The Bahamas', 'Florida', 'United States Gulf Coast'], ['Central America', 'Yucatn Peninsula', 'South Florida'], ['Greater Antilles', 'Bahamas', 'Eastern United States', 'Ontario'], ['The Caribbean', 'Venezuela', 'United States Gulf Coast'], ['Windward Islands', 'Jamaica', 'Mexico', 'Texas'], ['Bahamas', 'United States Gulf Coast'], ['Cuba', 'United States Gulf Coast'], ['Greater Antilles', 'Central America', 'Florida'], ['The Caribbean', 'Central America'], ['Nicaragua', 'Honduras'], ['Antilles', 'Venezuela', 'Colombia', 'United States East Coast', 'Atlantic Canada'], ['Cape Verde', 'The Caribbean', 'British Virgin Islands', 'U.S. Virgin Islands', 'Cuba', 'Florida'], ['Lesser Antilles', 'Virgin Islands', 'Puerto Rico', 'Dominican Republic', 'Turks and Caicos Islands'], ['Central America', 'United States Gulf Coast (especially Florida Panhandle)']]

# Damages (USD($)) of hurricanes
damages = ['Damages not recorded', '100M', 'Damages not recorded', '40M', '27.9M', '5M', 'Damages not recorded', '306M', '2M', '65.8M', '326M', '60.3M', '208M', '1.42B', '25.4M', 'Damages not recorded', '1.54B', '1.24B', '7.1B', '10B', '26.5B', '6.2B', '5.37B', '23.3B', '1.01B', '125B', '12B', '29.4B', '1.76B', '720M', '15.1B', '64.8B', '91.6B', '25.1B']

# Deaths for each hurricane
deaths = [90,4000,16,3103,179,184,408,682,5,1023,43,319,688,259,37,11,2068,269,318,107,65,19325,51,124,17,1836,125,87,45,133,603,138,3057,74]


#Function to print the updated damages list by using string parsing and converting "M":1000000,"B":1000000000...
print("FUNCTION TO CONVERT M:1000000, B:1000000000 FLOAT VALUES. ")
dam=[]
def hurr_damage(damages):
  conversion={"M":1000000,"B":1000000000}
  for i in damages:
    if i == "Damages not recorded":
      dam.append(i)
    elif i[-1] == "M":
      #dam1=float(i[:-1]) * 1000000
      dam1=float(i[:-1]) * conversion["M"]
      dam.append(dam1)
    elif i[-1] == "B":
      #dam2=float(i[:-1]) * 1000000000
      dam2=float(i[:-1]) * conversion["B"]
      dam.append(dam2)
  return dam
print(hurr_damage(damages))

print("________________________________________________________________________________________________________________________________________")

#Function to print the hurricane dictionary based on the name as key and values as the corrsponding names,months,years,max_sustained_winds,areas_affected,dam,deaths...
print("FUNCTION TO PRINT HURRICANE_DATA AS KEY(NAME):VALUES(names,months,years,max_sustained_winds,areas_affected,dam,deaths). ")
hurricane_data={}
def hurr_record(names,months,years,max_sustained_winds,areas_affected,dam,deaths):
  for i in range(len(names)):
  #for j in names,months,years,max_sustained_winds,areas_affected,dam,deaths:
    abc={"Name":names[i],"Month":months[i],"Year":years[i],"Max_sustained_winds":max_sustained_winds[i],"Areas_affected":areas_affected[i],"Damage":dam[i],"Death_count":deaths[i]} 
    hurricane_data[names[i]]=abc
hurr_record(names,months,years,max_sustained_winds,areas_affected,dam,deaths)
print(len(hurricane_data))
#print(hurricane_data.keys())
#print(hurricane_data.values())
for key,value in hurricane_data.items():
  print("________________________________________________________________________________________________________________________________________")
  print(key,':',value)
#print(abc)

print("___________________________________________________________________________________________________________________________________________")

#Function to print the values based on the years which the hurricane has occured..
print("FUNCTION TO PRINT THE VALUES BASED ON THE YEARS WHICH HURRICANE HAS OCCURED. ")
year_dict=[]
def hurricane_by_year(year):
  for i in hurricane_data:
    if hurricane_data[i]["Year"] == year:
      year_dict.append(hurricane_data[i])
  return hurricane_by_year
#years = [1924, 1928, 1932, 1932, 1933, 1933, 1935, 1938, 1953, 1955, 1961, 1961, 1967, 1969, 1971, 1977, 1979, 1980, 1988, 1989, 1992, 1998, 2003, 2004, 2005, 2005, 2005, 2005, 2007, 2007, 2016, 2017, 2017, 2018]
hurricane_by_year(2017)
hurricane_by_year(1924)
for i in year_dict:
  print(i)

print("___________________________________________________________________________________________________________________________________________")

#Function to print number of times an areas has affected with the HURRICANE in Recent times..
print("FUNCTION TO PRINT HOW MANY TIMES AN AREA HAS BEEN AFFECTED BY THE HURRICANE IN RECENT TIMES. ")
affected_area_count={}
def area_count(areas_affected):
  for i in areas_affected:
    for j in i:
      if j not in affected_area_count:
        affected_area_count[j] = 1
      else:
        affected_area_count[j] += 1
area_count(areas_affected)
print(affected_area_count)
for key,value in affected_area_count.items():
  print("The number of Areas Affected by Hurricanes are--"+key,":",value)

print("___________________________________________________________________________________________________________________________________________")

#Function to print the highest number of times an area is affected by a HURRICANE.(going through areas_count dictionary)
print("FUNCTION TO PRINT THE HIGHEST NUMBER OF TIMES AN AREA IS AFFECTED BY THE HURRICANE.")
def maximum_affected_area(affected_area_count):
  max_area=''
  max_area_count=0
  for i in affected_area_count:
    if max_area_count < affected_area_count[i]:
      max_area = i
      max_area_count += affected_area_count[i]
  return max_area_count,max_area
print(maximum_affected_area(affected_area_count))

print("___________________________________________________________________________________________________________________________________________")

#Function to print which hurricane has caused most number of deaths based on the hurricane dictionary(hurricane_data).
print("FUNCTION TO PRINT WHICH HURRICANE HAS CAUSED MOST NUMBER OF DEATHS, USING HURRICANE_DATA.")
def max_deaths(hurricane_data):
  max_deaths_area=''
  max_death_count=0
  for i,j in hurricane_data.items():
    if max_death_count < hurricane_data[i]["Death_count"]:
      max_deaths_area = i
      max_death_count = hurricane_data[i]["Death_count"]
  return max_deaths_area,max_death_count
#print(max_deaths_area,max_death_count)
print(max_deaths(hurricane_data))

print("___________________________________________________________________________________________________________________________________________")

#Function to print which hurricane has caused most of the DAMAGE(Billion and Millions) to the particular area.
print("FUNCTION TO PRINT WHICH HURRICANE HAS CAUSED MOST DAMAGE TO THE AREA. ")
damage_recorded={}
#for k in range(len(hurricane_data)):
for i,j in hurricane_data.items():
  if hurricane_data[i]["Damage"] == "Damages not recorded":
    damage_recorded[i] = 0
  elif hurricane_data[i]["Damage"] != "Damages not recorded":
    damage_recorded[i]=hurricane_data[i]["Damage"]
#print(damage_recorded)
def max_damage(damage_recorded):
  max_damaged_area=''
  max_damage_caused=0
  for i,j in damage_recorded.items():
    if max_damage_caused < damage_recorded[i]:
      max_damaged_area = i
      max_damage_caused = damage_recorded[i]
  return max_damaged_area,max_damage_caused
print(max_damage(damage_recorded))

print("___________________________________________________________________________________________________________________________________________")

#Function to give ratings for the hurricanes based on the number of deaths occured due to the HURRICANES.
print("FUNCTION TO GIVE RATINGS FOR THE HURRICANES BASED ON THE NUMBER OF DEATHS OCCURED. ")
hurricanes_by_mortality = {1:[],2:[],3:[],4:[],5:[]}
def hurricane_rating(hurricane_data):
  for i,j in hurricane_data.items():
    mortality_scale = {1:0, 2:100, 3:500, 4:1000, 5:10000}
    if hurricane_data[i]["Death_count"] > mortality_scale[1] and hurricane_data[i]["Death_count"] < mortality_scale[2]:
      hurricanes_by_mortality[1].append(hurricane_data[i])
  
    elif hurricane_data[i]["Death_count"] > 100 and hurricane_data[i]["Death_count"] < 500:
      hurricanes_by_mortality[2].append(hurricane_data[i])
  
    elif hurricane_data[i]["Death_count"] > 500 and hurricane_data[i]["Death_count"] < 1000:
      hurricanes_by_mortality[3].append(hurricane_data[i])
  
    elif hurricane_data[i]["Death_count"] > 1000 and hurricane_data[i]["Death_count"] < 10000:
      hurricanes_by_mortality[4].append(hurricane_data[i])
  
    elif hurricane_data[i]["Death_count"] > 10000:
      hurricanes_by_mortality[5].append(hurricane_data[i])
  return hurricanes_by_mortality
hurricane_rating(hurricane_data)
for i,j in hurricanes_by_mortality.items():
  print("________________________________________________________________________________________________________________________________________")
  print(i,":",j)


print("_______________________________________________OR____________________________________________________________")

#Function to give ratings for the hurricanes based on the number of deaths occured due to the HURRICANES.
print("FUNCTION TO GIVE RATINGS BASED ON NUMBER OF DEATHS. ")
hurricanes_by_mortality = {1:[],2:[],3:[],4:[],5:[]}
for i,j in hurricane_data.items():
  mortality_scale = {1:0, 2:100, 3:500, 4:1000, 5:10000}
  if hurricane_data[i]["Death_count"] > mortality_scale[1] and hurricane_data[i]["Death_count"] < mortality_scale[2]:
    hurricanes_by_mortality[1].append(hurricane_data[i]["Death_count"])
  
  elif hurricane_data[i]["Death_count"] > 100 and hurricane_data[i]["Death_count"] < 500:
    hurricanes_by_mortality[2].append(hurricane_data[i]["Death_count"])
  
  elif hurricane_data[i]["Death_count"] > 500 and hurricane_data[i]["Death_count"] < 1000:
    hurricanes_by_mortality[3].append(hurricane_data[i]["Death_count"])
  
  elif hurricane_data[i]["Death_count"] > 1000 and hurricane_data[i]["Death_count"] < 10000:
    hurricanes_by_mortality[4].append(hurricane_data[i]["Death_count"])
  
  elif hurricane_data[i]["Death_count"] > 10000:
    hurricanes_by_mortality[5].append(hurricane_data[i]["Death_count"])
for i,j in hurricanes_by_mortality.items():
  print(i,":",j)

print("________________________________________________________________________________________________________________________________________")

#Function to rate the given HURRICANES based on thier respective damages they have given to the areas nearby.
hurricanes_by_damages = {1:[],2:[],3:[],4:[],5:[]}
def hurricane_rating(hurricane_data):
  for i,j in hurricane_data.items():
    damage_scale = {1: "Damages not recorded", 2: 100000000, 3: 1000000000, 4: 10000000000, 5: 50000000000}
    if hurricane_data[i]["Damage"] == damage_scale[1] or hurricane_data[i]["Damage"] < damage_scale[2]:
      hurricanes_by_damages[1].append(hurricane_data[i])
  
    elif hurricane_data[i]["Damage"] > damage_scale[2] and hurricane_data[i]["Damage"] < damage_scale[3]:
      hurricanes_by_damages[2].append(hurricane_data[i])
  
    elif hurricane_data[i]["Damage"] > damage_scale[3] and hurricane_data[i]["Damage"] < damage_scale[4]:
      hurricanes_by_damages[3].append(hurricane_data[i])
  
    elif hurricane_data[i]["Damage"] > damage_scale[4] and hurricane_data[i]["Damage"] < damage_scale[5]:
      hurricanes_by_damages[4].append(hurricane_data[i])
  
    elif hurricane_data[i]["Damage"] > damage_scale[5]:
      hurricanes_by_damages[5].append(hurricane_data[i])
  return hurricanes_by_damages
hurricane_rating(hurricane_data)
for i,j in hurricanes_by_damages.items():
  print("________________________________________________________________________________________________________________________________________")
  print("FUNCTION TO GIVE RATINGS FOR THE HURRICANES BASED ON THE DAMAGES IT HAS CAUSED. ")
  print(i,":",j)
print("________________________________________________________________________________________________________________________________________")







