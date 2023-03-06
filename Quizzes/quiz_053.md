# code

```.py
text = "This is a sample text. It contains some words that will be counted"

# dictionary to store the words and their counts
word_counts = {
}

# split the text into words

words= text.split(" ")

# loop through the words and count them
for i in words:
    if i in word_counts.keys():
        word_counts[i]+=1
    else:
        word_counts[i]=1

for i in word_counts:
    print(f"{i.center(10)} : {word_counts[i]}")

```

# evidence
<img width="194" alt="image" src="https://user-images.githubusercontent.com/100017195/223020102-4de7fe9a-fc68-41c9-96fd-a2aaa305a7d2.png">
