# code
```.py
import sqlite3

haiku = '''Code flows like a stream
Algorithms guide its way
In silence, it solves'''

# connect to the file, if the file doesn't exist, the database file will automatically create
connection = sqlite3.connect("quiz_046.db")
# get the cursor to the database
cursor = connection.cursor()
# create database with table words (quety)
query = f"""CREATE TABLE haiku(
    id INTEGER PRIMARY KEY,
    word NOT NULL,
    length integer 
)"""

cursor.execute(query)

for word in haiku.split():
    # insert every word and length in the database
    insert_query = f""" INSERT into haiku(word, length) values("{word}", {len(word)})
    """
    cursor.execute(insert_query)
    connection.commit() # to save
# query the average of all the lengths
average_query=""" SELECT avg(length) from haiku"""

out=cursor.execute(average_query).fetchone()
connection.commit()

# close database

print("average word length is", out)

```
# evidence
<img width="1552" alt="image" src="https://user-images.githubusercontent.com/100017195/219217040-0280550a-3fac-4cab-9cb4-0142c37e31b7.png">
