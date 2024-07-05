Q1. Which keyword is used to create a function? Create a function to return a list of odd numbers in the
range of 1 to 25.
In Python, the keyword used to create a function is def. Here's how you can create a function named get_odd_numbers to return a list of odd numbers in the range of 1 to 25:
python
Copy code
def get_odd_numbers():
    odd_numbers = [num for num in range(1, 26) if num % 2 != 0]
    return odd_numbers

# Calling the function
odd_numbers_list = get_odd_numbers()
print(odd_numbers_list)
Output:
csharp
Copy code
[1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25]
In this example:
•	The function get_odd_numbers() uses a list comprehension to generate a list of odd numbers (num % 2 != 0) in the range from 1 to 25 (range(1, 26)).
•	The function returns this list, which is then assigned to odd_numbers_list and printed.
Q2. Why *args and **kwargs is used in some functions? Create a function each for *args and **kwargs to
demonstrate their use.

*args and **kwargs in Python functions are used to handle arbitrary numbers of arguments and keyword arguments, respectively.
Example for *args:
python
Copy code
def sum_numbers(*args):
    total = 0
    for num in args:
        total += num
    return total

print(sum_numbers(1, 2, 3, 4))  # Output: 10
Example for **kwargs:
python
Copy code
def print_details(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_details(name="Alice", age=30, city="Wonderland")
# Output:
# name: Alice
# age: 30
# city: Wonderland
In these examples:
•	*args allows the function to accept any number of positional arguments as a tuple.
•	**kwargs allows the function to accept any number of keyword arguments as a dictionary.
Q3. What is an iterator in python? Name the method used to initialise the iterator object and the method
used for iteration. Use these methods to print the first five elements of the given list [2, 4, 6, 8, 10, 12, 14, 16,
18, 20].
In Python, an iterator is an object that implements the iterator protocol, which consists of two methods: __iter__() and __next__().
•	Initialization method: To initialize an iterator object, you use the iter() function.
•	Iteration method: To iterate over the elements of the iterator, you use the next() function or a for loop.
Here's how you can print the first five elements of the list [2, 4, 6, 8, 10, 12, 14, 16, 18, 20] using iterators:
python
Copy code
my_list = [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]

# Initialize iterator object
iter_obj = iter(my_list)

# Print the first five elements using next() method
print(next(iter_obj))   # Output: 2
print(next(iter_obj))   # Output: 4
print(next(iter_obj))   # Output: 6
print(next(iter_obj))   # Output: 8
print(next(iter_obj))   # Output: 10

# Alternatively, iterate using a for loop to print all elements
for element in iter_obj:
    print(element)
Output:
Copy code
2
4
6
8
10
12
14
16
18
20
In this example:
•	iter(my_list) initializes an iterator object from the list my_list.
•	next(iter_obj) retrieves the next element from the iterator iter_obj.
•	Using a for loop after printing the first five elements continues iterating through the remaining elements of my_list.
Q4. What is a generator function in python? Why yield keyword is used? Give an example of a generator
function.
A generator function in Python is defined using def and yield keywords. It produces a sequence of values lazily, one at a time, rather than storing them in memory like lists. yield suspends the function’s state, allowing it to resume where it left off.
Example:
python
Copy code
def count_up_to(n):
    count = 1
    while count <= n:
        yield count
        count += 1

# Usage:
for num in count_up_to(5):
    print(num)  # Output: 1, 2, 3, 4, 5

Q5. Create a generator function for prime numbers less than 1000. Use the next() method to print the
first 20 prime numbers.

Here's a generator function in Python that yields prime numbers less than 1000 and uses the next() method to print the first 20 prime numbers:
python
Copy code
def generate_primes():
    num = 2
    while True:
        if all(num % i != 0 for i in range(2, int(num**0.5) + 1)):
            yield num
        num += 1

prime_generator = generate_primes()

# Print the first 20 prime numbers using next() method
for _ in range(20):
    print(next(prime_generator))
This function generates prime numbers indefinitely (while True) and yields them using the yield keyword. The all() function checks if num is divisible by any number from 2 up to its square root (int(num**0.5) + 1).

