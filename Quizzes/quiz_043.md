# Console

```.db
CREATE TABLE if not exists Movies(
    id INTEGER PRIMARY KEY,
    name text,
    producer text,
    director text,
    category text,
    budget text,
    year integer
);


INSERT INTO Movies (name, producer,director,category,budget,year) values("Parasite","Barunson", "Bong Joon-ho","Thriller", "15.5 million USD", "2019");
INSERT INTO Movies (name, producer,director,category,budget,year) values("Pulp Fiction","Laurence Bender", "Quentin Tarantino", "Crime/Drama", "8.5 million USD", "1994")
```

# Proof
<img width="858" alt="image" src="https://user-images.githubusercontent.com/100017195/217433438-1a930fdc-5521-40a4-94c4-0484d59b1003.png">
