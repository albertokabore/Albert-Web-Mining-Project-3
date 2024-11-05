# Matplotlib and pyplot

Complete the tasks in the Python Notebook in this repository.
To be submitted for credit, all changes must be committed and pushed to this repository (do not create your own repository unless instructed to on the course website).

## Rubric

Each question is worth two points: 

* Data plotted as described by the question (1 pt)
* Plot contains required elements (title, axis labels, axis titles, legend if required)

Question 1. Given the text below, create a bar plot (or a horizontal bar plot) that shows the frequency distribution of characters in the string. 
A dictionary has been created for you containing the characters and the frequencies of the characters.
Make sure your bar plot has the bars labelled correctly (with the character it represents the frequency of).

```python
from collections import Counter
from random import randint
import matplotlib.pyplot as plt
```

```python
from collections import Counter
TEXT = "At three o’clock precisely I was at Baker Street, but Holmes had not yet returned. The landlady informed me that he had left the house shortly after eight o’clock in the morning. I sat down beside the fire, however, with the intention of awaiting him, however long he might be. I was already deeply interested in his inquiry, for, though it was surrounded by none of the grim and strange features which were associated with the two crimes which I have already recorded, still, the nature of the case and the exalted station of his client gave it a character of its own. Indeed, apart from the nature of the investigation which my friend had on hand, there was something in his masterly grasp of a situation, and his keen, incisive reasoning, which made it a pleasure to me to study his system of work, and to follow the quick, subtle methods by which he disentangled the most inextricable mysteries. So accustomed was I to his invariable success that the very possibility of his failing had ceased to enter into my head.".lower()
letter_freq = dict(Counter(TEXT))

# make a bar plot with an appropriate title, correct xtick labels, and labeled axes
```

```python
#Create the bar plot
plt.figure(figsize=(14, 8))
plt.barh(list(letter_freq.keys()), list(letter_freq.values()))
plt.xlabel('Frequency')
plt.ylabel('Character')
plt.title('Frequency Distribution of Characters in Text')
plt.show()
```

Question 2. Generate a sequence of at least 5 random numbers (integers are fine), and visualize the data using both `scatter` and `plot` on different axes.  You may use the index of the value as its x value in the plot.

```python
# Re-importing necessary libraries after environment reset
import matplotlib.pyplot as plt
import numpy as np

# Generate a sequence of 5 random integers
random_numbers = np.random.randint(1, 100, 5)
x_values = range(len(random_numbers))

# Create the visualizations
fig, (ax1, ax2) = plt.subplots(2, 1, figsize=(8, 10))

# Scatter plot
ax1.scatter(x_values, random_numbers)
ax1.set_title("Scatter Plot of Random Numbers")
ax1.set_xlabel("Index")
ax1.set_ylabel("Value")

# Line plot
ax2.plot(x_values, random_numbers, marker='o')
ax2.set_title("Line Plot of Random Numbers")
ax2.set_xlabel("Index")
ax2.set_ylabel("Value")

plt.tight_layout()
plt.show()
```

Question 3. Do the same question as above, but change the syle and color of both the scatter and the plot.

```python
# Generate a new sequence of 5 random integers for variety
random_numbers = np.random.randint(1, 100, 5)
x_values = range(len(random_numbers))

# Create the visualizations with customized style and color
fig, (ax1, ax2) = plt.subplots(2, 1, figsize=(8, 10))

# Scatter plot with custom color and style
ax1.scatter(x_values, random_numbers, color='purple', marker='x', s=100)
ax1.set_title("Styled Scatter Plot of Random Numbers")
ax1.set_xlabel("Index")
ax1.set_ylabel("Value")

# Line plot with custom color and style
ax2.plot(x_values, random_numbers, color='orange', linestyle='--', marker='D', markersize=8)
ax2.set_title("Styled Line Plot of Random Numbers")
ax2.set_xlabel("Index")
ax2.set_ylabel("Value")

plt.tight_layout()
plt.show()
```

Question 4. Given the data sets below, plot or scatter both on the same set of axes.  You are plotting the time it takes to execute a sorting algorithm on a list of a given size; your x axis should be the size, and the y axis is time.  Assume that `insertion_sort_times[i]` is how long it took to sort a list of length `sizes[i]`.  Add a legend to your plot showing which is insertion sort and which is merge sort.  Use the variable names to determine which data is which. 

```python
sizes = [10, 20, 50, 100, 1000, 5000]
insertion_sort_times = [0.0010252999999999998, 0.0027026999999999954, 0.010147200000000002, 0.0381137, 3.6303399, 91.2180796]
merge_sort_times = [0.00161889999999687, 0.003635600000009731, 0.0090655000000055, 0.020108000000007564, 0.2687474000000094, 1.6147050999999948]
```
```python
# Plot both sorting times on the same axes
plt.figure(figsize=(10, 6))

# Plot insertion sort times
plt.plot(sizes, insertion_sort_times, label='Insertion Sort', marker='o', linestyle='-', color='blue')

# Plot merge sort times
plt.plot(sizes, merge_sort_times, label='Merge Sort', marker='s', linestyle='--', color='red')

# Set axis labels and title
plt.xlabel("List Size")
plt.ylabel("Time (seconds)")
plt.title("Execution Time of Sorting Algorithms by List Size")

# Add legend to distinguish between insertion and merge sort
plt.legend()

plt.show()
```


# Export to HTML and Finalize Repo






