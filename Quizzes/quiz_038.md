# code
```.py
import random
from matplotlib import pyplot as plt

class Coordinates:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    def __repr__(self):
        return f"Coordinate: ({self.x}, {self.y})"

class City:
    def __init__(self, name:str, location:Coordinates):
        self.name = name
        self.location = location
    def __repr__(self):
        return f"[City Object]  City {self.name} is located at {self.location}"
    def get_distance(self,cityB):
        if isinstance(cityB,City):
            x1,y1=self.location.x,self.location.y
            x2,y2 = cityB.location.x, cityB.location.y
        else:
            raise TypeError("Input should be an object of the class city")
        distance = (abs(x1 - x2) ** 2 + abs(y1 - y2) ** 2) ** 0.5
        return distance

class Country:
    def __init__(self, name):
        self.name = name
        self.cities =[]
    def add_city(self, new_city:City):
        self.cities.append(new_city)
    def __repr__(self):
        return f"[Country Object]   {self.name} has {len(self.cities)} cities"

# create 10 random cities and add them to a country
cities_in_japan= ["Tokyo", "Osaka", "Kyoto", "Nagoya", "Sapporo",
                  "Fukuoka", "Kobe", "Kawasaki", "Kitakyushu", "Saitama"]

x=[]
y=[]

japan = Country(name="Japan")
for city in cities_in_japan:
    x_random = random.randint(0,100)
    y_random = random.randint(0,100)
    city = City(name=city, location=Coordinates(x_random, y_random))
    print(city)
    japan.add_city(city)
print(japan)


# plot a scatter plot of the cities in Japan
plt.xlabel("Distance(km)")
plt.ylabel("Distance(km)")
for i in japan.cities:
    x=i.location.x
    y=i.location.y
    plt.text(x,y,i.name)
    plt.scatter(x,y,s=100)
plt.show()
```

# graph plotted

<img width="455" alt="Screen Shot 2023-01-26 at 8 07 43 AM" src="https://user-images.githubusercontent.com/100017195/214712325-49ae0c6c-5a1c-4fba-a101-3917e7708c1c.png">
