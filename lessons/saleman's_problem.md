composition
# the salesman's problem: 
The salesman's problem, also known as the traveling salesman problem, is a classic optimization problem where the goal is to find the shortest route that visits a set of cities and returnsto the starting city. Possible solutions include using algorithms such as branch and bound, genetic algorithms,and simulated annealing. Approximate methods such as the nearest neighbor algorithm and the greedy algorithm can also be used. Heuristic methods such as the 2-opt, 3-opt, and k-opt algorithms are also used to find good solutions quickly.

# code
```.py
import random
import math

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
            x1=self.location.x
            y1=self.location.x
            x2 = cityB.location.x
            y2 = cityB.location.x
            distance= (abs(x1-x2)**2+abs(y1-y2)**2)**0.5
            return distance
        else:
            raise TypeError

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
japan = Country(name="Japan")
for city in cities_in_japan:
    x_random = random.randint(0,100)
    y_random = random.randint(0,100)
    city = City(name=city, location=Coordinates(x_random, y_random))
    print(city)
    japan.add_city(city)

print(japan)
```
