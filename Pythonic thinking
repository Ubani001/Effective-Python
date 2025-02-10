import sys

print(sys.version_info)

print(sys.version)


#Pythonic Thinking, Difference between bytes and str.....

a = b'h\65llo'
print(list(a))
print(a)

a = 'a\u0300 propos'
print(list(a))
print(a)

#Encoding and Decoding of Bytes and Str.. (Unicode Sandwich)
#first instance takes str to bytes
def to_str(bytes_or_str):
    if isinstance(bytes_or_str, bytes):
        value = bytes_or_str.decode('utf-8')
    else:
        value = bytes_or_str
        return value #instance of str
print(repr(to_str(b'foo')))
print(repr(to_str('bar')))

#Second instamce returns a byte

def to_bytes(bytes_or_str):
    if isinstance(bytes_or_str, str):
        value = bytes_or_str.encode('utf-8')
    else:
        value = bytes_or_str
        return value #instance of bytes
print(repr(to_bytes(b'foo')))
print(repr(to_bytes('bar')))

print(b'one' + b'two')

assert b'red' > b'blue'

print(4)
print('4')

d = 6
e = 8
f = e < d
print(f)

# i did not get this, i was told to use 
# print(locale.getpreferredencoding(())') i still didn't get it
#with open('data.bin', 'r', encoding='cp1252') as f:
 #   data = f.read()
 
 #formatting strings "%d"
 
a = 0b10111011
b = 0xc5f
print('Binary is %d, hex is %d' % (a,b))

#C style format string
key = 'my_var'
value = 1.234
formatted = '%-10s = %.2f' % (key, value)
print(formatted)

#kiitchen pantry, tuples []

pantry = [
    ('avocados', 1.25),
    ('bananas', 2.5),
    ('cherries', 15),
]
for i, (item, count) in enumerate(pantry):
    print('#%d: %-10s = %.2f' % (i, item, count))

pantry = [
    ('avocados', 1.25),
    ('bananas', 2.5),
    ('cherries', 15),    ]

for i, (item, count) in enumerate(pantry):
    print('#%d: %-10s = %d' % (
        i + 1,
        item.title(),
        round(count)
    ))    
    
    #third example of formatting expression
    
    template = '%s loves food. See %s cook.'
    name = 'Max'
    formatted = template % (name, name)
    print(formatted)
    
    name = 'john'
    formatted = template % (name.title(), name.title())
    print(formatted)
    
#Dictionaries in formatting expressions

soup = 'lentii'
formatted = 'Today\'s soup is %(soup)s.' % {'soup': soup}
print(formatted)
    
menu = {
    'soup': 'lentil',
    'oyster': 'kumamoto',
    'special': 'schnitzel',
        
}
template = ('Today\'s soup is %(soup)s,'
            'buy one get %(oyster)s oysters,'
            'and our special entree is %(special)s.'
            )
formatted = template % menu
print(formatted)

template = '%s loves food'
name = 'bash'
formatted = template % (name)
print(formatted)

#new formattin with python 3 'a' for thousand seperator
a = 1234.5678
formatted = format(a, ',.2f')
print(formatted)

b = 'my string'
formatted = format(b, '^20s')
print('*', formatted, '*')

#wite helper functions instead of complex expressions. Helps to single line of 
# expression with a lot of logic 
from urllib.parse import parse_qs
my_values = parse_qs('red=5&blue=0&green=',
                     keep_blank_values=True)
print(repr(my_values))
                     
print('red: ', my_values.get('red'))
print('blue:    ', my_values.get('blue'))
print('opacity: ', my_values.get('opacity'))

red = my_values.get('red', [''])[0] or 0
green = my_values.get('green', [''])[0] or 0
opacity = my_values.get('opacity', [''])[0] or 0

print(f'Red:    {red!r}')
print(f'Green:  {green!r}')
print(f'opacity:    {opacity!r}')

#Prefer Multiple Assignment Unpacking Over Indexing

snack_calories = {
    
    
    'chips': 140,
    'popcorn': 80,
    'nuts': 190,
}
items = tuple(snack_calories.items())
print(items)

#The values in tuples can be accessed through numerical indexes:

item = ('peanut butter', 'jelly')
first = item[0]
second = item[1]
print(first, 'and', second)

item = ('yam', 'beans')
first, second = item
print(item)

#DAY 2
#Unpacking, not avisable to use in your codes

favorite_snacks = {
    'salty':    ('pretzels', 100),
    'sweet':    ('cookies', 180),
    'veggie':   ('carrots', 20),
}
((type1, (name1, cals1)),
 (type2, (name2, cals2)),
 (type3, (name3, cals3))
 ) = favorite_snacks.items()

print(f'Favorite {type1} is {name1} with {cals1} calories')
print(f'Favorite {type2} is {name2} with {cals2} calories')
print(f'Favorite {type3} is {name3} with {cals3} calories')

#Unpacking can be used to swap values

def bubble_sort(a):
    for _ in range(len(a)):
        for i in range(1, len(a)):
            if a[i] < a[i-1]:
                temp = a[i]
                a[i] = a[i-1]
                a[i-1] = temp        
names = ['pretezls', 'carrots', 'arugula', 'bacon']
bubble_sort(names)
print(names)

def bubble_sort(a):
    for _ in range(len(a)):
        if a[i] < a[i-1]:
            a[i-1], a[i] = a[i], a[i-1]
names = ['pere', 'jane', 'ben', 'kane']
bubble_sort(names)
print(names)

##iteration of unacking without unpacking
snacks = [('bacon', 350), ('donut', 240), ('muffin', 190)]
for i in range(len(snacks)):
    item = snacks[i]
    name = item[0]
    calories = item[1]
    print(f'#{i+1}: {name} has {calories} calories')

#unpacking using the enumerate built-in function

snack = [('popcorn', 500), ('buns', 400), ('pie', 600)]
for rank, (name, calories) in enumerate(snack, 1):
    print(f'#{rank}: {name} has {calories} calories')
    
#python has a special syntax called unpacking for assigning multiple values in as ingle statement
#it also reducd visual noise

#PREFER ENUMERATE OVER RANGE
#the range built-in function is useful for loop that iterate iver a set of integers

from random import randint

random_bits = 0
for i in range(32):
    if randint(0,1):
        random_bits |= 1 << i
        
print(bin(random_bits))

#iterating over strings

flavor_list = ['vanilla', 'chocolate', 'pecan', 'strawberry']
for flavor in flavor_list:
    print(f'{flavor} is dellicious')

#printing the rank of my favorite ice cream flavor

for i in range(len(flavor_list)):
    flavor = flavor_list[i]
    print(f'{i + 1}: {flavor}')
    
it = enumerate(flavor_list)
print(next(it))
print(next(it))

#for multiple unpacking

for i, flavor in enumerate(flavor_list):
    print(f'{i+1}: {flavor}')

for i, flavor in enumerate(flavor_list, 1):
    print(f'{i}: {flavor}')
    
#summary? enumerate provide concise syntax
#USE ZIP TO PROCESS ITERATORS N PARALLEL

names =  ['cecilia', 'Lise', 'Marie']
counts = [len(n) for n in names]
print(counts)

#iterate ove the list

longest_name = None
max_count = 0

for i in range(len(names)):
    count = counts[i]
    if count > max_count:
        longest_name = names[i]
        max_count = count
print(longest_name)

for i in range(len(names)):
    count = counts[i]
    if count < max_count:
        shortest_name = names[i]
        max_count = count
print(shortest_name)

for i, name in enumerate(names):
    count = counts[i]
    if count > max_count:
        longest_name = name
        max_count = count
print(name)

#codes are too noisy, python provides the zip built in function

for name, count in zip(names, counts):
    if count > max_count:
        longest_name = name
        max_count = count
print(name)

names.append('rosemary')
for name, count in zip(names, counts):
    print(name)
    
#But in many other cases, the truncating behavior of zip is surprising
#and bad. If you don’t expect the lengths of the lists passed to zip to
#be equal, consider using the zip_longest function from the itertools
#built-in module instead

import itertools

for name, count in itertools.zip_longest(names, counts):
    print(f'{name}: {count}')
    
#AVOID ELSE BLOCKS AFTR FOR AND WHILE LOOPS

for i in range(3):
    print('Loop', i)
    break
else:
    print('Else block!')
    
#using the break statement 
for i in range(3):
    print('Loop', i)
    if i == 3:
        break
else:
    print('Else block')
    
#else block also runs in an empty sequence

for x in []:
    print('Never runs')
else:
    print('for Else Block')
    
#to check weather two nu,bers are coprime

a  = 4
b  = 9
for i in range(2, min(a,b) + 1):
    print('Testing', i)
    if a % i == 0 and b % i == 0:
        print('Not coprime')
        break
else:
    print('Coprime')
    
#Alternatively 
def coprime(a,b):
    for i in range(2, min(a,b) + 1):
        if a % i == 0 and b % i == 0:
            return False
    return True

#The second way is to have a result variable that indicates whether I’ve
#found what I’m looking for in the loop. I break out of the loop as soon
#as I find something:

def coprime_alternate(a, b):
    is_coprime = True
    for i in range(2, min(a,b) + 1):
        if a % i == 0 and b % i == 0:
            is_coprime = False
            break
    return is_coprime

# prevent repetition with assignment exprssion
#content of the fruit jar defined
fresh_fruit = {
    'apple': 10,
    'banana': 8,
    'lemon': 5,
}
def make_lemonade(count):
    ...
    
def out_of_stocks():
    ...
    
count = fresh_fruit.get('lemon', 0)
if count:
    make_lemonade(count)
else:
    out_of_stocks() 
    
def make_cider(count):
    ...
count = fresh_fruit.get('apple', 0)
if count >= 4:
    make_cider(count)
else:
    out_of_stocks()

def slice_bananas(count):
    ...
class OutOfBananas(Exception):
    pass

def make_smoothies(count):
    ...
    
pieces = 0
count = fresh_fruit.get('bananas', 0)
if count >= 2:
    pieces = slice_bananas(count)
else:
    pieces = 0
try:
    smoothies = make_smoothies(pieces)
except OutOfBananas:
    out_of_stocks()

#   DAY 3, 
# CHAPTER 2 (LIST AND DICTIONARIES)
# know how to slice sequences

a = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h']
print('Middle two: ', a[3:5])
print('All but ends:', a[1:7])
print(a[:5])
print(a[5:])
print(a[5:len(a)])
print(len(a[5:]))
print(a[:])
print(a[:-3])
print(a[-4:-1])

# [:20] first 20 items [-20:] last 20 items
first_twenty_items = a[:20]
last_twenty_items = a[-20:]

print(a)
# modifying the result of slicing won't affect the original result
b = a[3:]
print('Before:  ', b)
b[1] = 99
print('After:   ', b)
print('No change: ', a)

print('Before', a)
print(a[2:7])
a[2:7] = [99, 22, 14]
print('After', a)

print('Before', a)
a[2:3] = [47, 11]
print('After', a)

# Avoid striding and slicing ina single expression
#python has special syntax  for the stride of a slice in the form 
# [start:end:stride]. stride makes it easy to group by even and odd indexes in a list

x = ['red', 'orange', 'yellow', 'green', 'blue', 'purple']
odds = x[::2]
evens = x[1::2]
print(odds)
print(evens)

x = b'mongoose'
y = x[::-1]
print(y)

x = 'ᇓৌ'
y = x[::-1]
print(y)

#prefer catch-all unpacking over slicing

car_ages = [0, 9, 4, 8, 7, 20, 19, 1, 6, 15]
car_ages_descending = sorted(car_ages, reverse=True)
oldest = car_ages_descending[0]
second_oldest = car_ages_descending[1]
others = car_ages_descending[2:]
print(oldest, second_oldest, others)

#achieving same result without indexing of slicing

car_ages = [0, 9, 4, 8, 7, 20, 19, 1, 6, 15]
car_ages_descending = sorted(car_ages, reverse=True)
oldest, second_oldest, *others = car_ages_descending
print(oldest, second_oldest, others)

#for the youngest car

car_ages_ascending = sorted(car_ages)
*youngest, second_youngest, others = car_ages_ascending
print(youngest, second_youngest, others)

#using multiple starred expresssion in an unpacking assignment

car_inventory = {
    'Downtown': ('Silver Shadow', 'Pinto', 'DMC'),
    'Airport': ('Skyline', 'Viper', 'Gremlin', 'Nova'),
}
((loc1, (best1, *rest1)), 
 (loc2, (best2, *rest2))) = car_inventory.items()
print(f'Best at {loc1} is {best1}, {len(rest1)} others')
print(f'Best at {loc2} is {best2}, {len(rest2)} others')

short_list = [1,2,3,4]
first, second, *rest = short_list
print(first,second, rest)

def generate_csv():
    yield ('date', 'make', 'model', 'year', 'price')
    ...
all_csv_rows = list(generate_csv())
header = all_csv_rows[0]
rows = all_csv_rows[1:]
print('csv header:', header)
print('row count:', len(rows))

#unpacking with a starred expression

def generate_csv():
    yield ('date', 'make', 'model', 'year', 'price')
    ...
it = generate_csv()
header, *rows = it
print('csv header:', header)
print('row count:', len(rows))

#SORT BY COMPLEX CRITERIA USING THE KEY PARAMETER

numbers = [93, 86, 11, 68, 70]
numbers1 = ['cat', 'ant', 'rat', 'fish']
numbers.sort()
print(numbers, numbers1)

class Tool:
    def __init__(self, name, weight):
        self.name = name
        self.weight = weight
        
    def __repr__(self):
        return f'Tool({self.name!r}, {self.weight})'
        
tools = [
        Tool('level', 3.5),
        Tool('hammer', 1.25),
        Tool('screwdriver', 0.5),
        Tool('chisel', 0.25),
    ]
    
#Here, I use the lambda keyword to define a function for the 
# key parameter that enables me to sort the list of Tool 
# objects alphabetically by
#their name:

print('Unsorted:', repr(tools))
tools.sort(key=lambda x: x.name)
print('\nSorted: ', tools)

tools.sort(key=lambda x: x.weight)
print('By weight:', tools)

#Using the lambda function to access attributes 

places = ['home', 'work', 'New York', 'Paris', 'abbey']
places.sort()
print('Case sensitive: ', places)
places.sort(key=lambda x: x.lower())
print('Case insensitive: ', places)

 #using multiple criteria for sorting, using weight  and name
 
power_tools = [
     Tool('drill', 4),
     Tool('circular saw', 5),
     Tool('jackhammer', 40),
     Tool('sander', 4)
 ]
saw = (5, 'circular saw')
jackhammer = (40, 'jackhammer')
drill = (4, 'drill')
sander = (4, 'sander')

power_tools.sort(key=lambda x: (x.weight, x.name), 
                 reverse=True)
print(power_tools)

power_tools.sort(key=lambda x: x.name)
print(power_tools)

power_tools.sort(key=lambda x: x.weight, reverse=True)
print(power_tools)

#Dict insertion ordering 

baby_names = {
    'cat': 'kitten',
    'dog': 'puppy',
}
print(baby_names)

#using thw kwrags catch all parameter
#python 3.5

def my_func(**kwargs):
    for key, value in kwargs.items():
        print('%s = %s' % (key, value))
my_func(goose='gosling', kangaroo='joey')

def my_func(**kwargs):
    for key, value in kwargs.items():
        print(f'{key} = {value}')
my_func(goose='goslng', kangaroo='joey')

#in previous versions classes also use the dict type for their 
#instance dictionaries
class Myclass:
    def __init__(self):
        self.aligator = 'hatchling'
        self.elephant = 'calf'
a = Myclass()
for key, value in a.__dict__.items():
    print('%s = %s' % (key, value))

# writing a program to show the results of a
#contest for the cutest baby animal. 

#start with a dictionary containing the total 
# vote count for each animal
votes = {
    'otter': 1281,
    'polar bear': 587,
    'fox': 863
}

#define function to save the voting data 
# and rank of each animal into the preovided empty dict...
def populate_ranks(votes, ranks):
    names = list(votes.keys())
    names.sort(key=votes.get, reverse=True)
    for i, name in enumerate(names, 1):
        ranks[name] = i
 #function that tells which animal won the context       
def get_winner(ranks):
    return next(iter(ranks))
#confirming that these function work as designed 
# and deliver the result expected
ranks = {}
populate_ranks(votes, ranks)
print(ranks)
winner = get_winner(ranks)
print(winner)

#the UI element that shows the result should be in 
# alphabetical order instead of rank order to
# achieve this we use the inbuilt module collections.abc to 
# define a new dictionary-like class that iterates contents 
# in alphaetical order

from collections.abc import MutableMapping

class SortedDict(MutableMapping):
    def __init__(self):
        self.data = {}
    def __getitem__(self, key):
        return self.data[key]
    def __setitem__(self, key, value):
        self.data[key] = value
    def __delitem__(self, key):
        del self.data[key]
    def __iter__(self):
        keys = list(self.data.keys())
        keys.sort()
        for key in keys:
            yield keys
            
    def __len__(self):
        return len(self.data)
    
sorted_ranks = SortedDict()
populate_ranks(votes, sorted_ranks)
print(sorted_ranks.data)
winner = get_winner(sorted_ranks)
print(winner)   

#get over to handle missing dictionary keys

counters = {
    'pumpernickel': 2,
    'sourdough': 1,
}
key = 'wheat'

if key in counters:
    count = counters[key]
else:
    count = 0
    
counters[key] = count + 1
count = counters.get(key, 0)
counters[key] = count + 1

if key not in counters:
    counters[key] = 0
counters[key] += 1

if key in counters:
    counters[key] += 1
else:
    counters[key] = 1
    
try:
    counters[key] += 1
except: 
    KeyError
    counters[key] = 1


# CHAPTER 3 FUNCTIONS
def get_stats(numbers):
    minimum = min(numbers)
    maximum = max(numbers)
    return minimum, maximum

lengths = [63, 73, 72, 60, 67, 71, 61, 72, 70]

minimum, maximum = get_stats(lengths)

print(f'min: {minimum}, max: {maximum}')

def get_avg_ratio(numbers):
    average = sum(numbers) / len(numbers)
    scaled = [x / average for x in numbers]
    scaled.sort(reverse=True)
    return scaled

longest, *middle, shortest = get_avg_ratio(lengths)
print(f'Longest: {longest:>4.0%}')
print(f'Shortest: {shortest:>4.0}')

#determine  the average length, median length, and total population
#can be achieved by expanding the get stats function


def get_stats(numbers):
    minimum = min(numbers)
    maximum = max(numbers)
    count = len(numbers)
    average = sum(numbers) / count
    
    sorted_numbers = sorted(numbers)
    middle = count // 2
    if count % 2 == 0:
        lower = sorted_numbers[middle - 1]
        upper = sorted_numbers[middle]
        median = (lower + upper) / 2
    else:
        median = sorted_numbers[middle]
        
    return minimum, maximum, average, median, count
minimum, maximum, average, median, count = get_stats(lengths)
print(f'Min: {minimum}, Max: {maximum}')
print(f'Average: {average}, Median: {median}, Count {count}')

#prefer raising exceptions to returning none

def careful_divide(a,b):
    try:
        return a / b
    except ZeroDivisionError:
        return None
x, y = 0, 5
result = careful_divide(x, y)
if not result:
    print('Invalid inputs') 
    
    
    
 #   def careful_divide(a: float, b: float) -> float:
 #"""Divides a by b.
 #Raises:
 #ValueError: When the inputs cannot be divided.
 #"""
 #try:
 #return a / b
 #except ZeroDivisionError as e:
 #raise ValueError('Invalid inputs')
    
def careful_divide(a, b):
    try:
        return a / b
    except ZeroDivisionError as e:
        raise ValueError("Invalid inputs")  
x, y = 5, 2
try:
    result = careful_divide(x, y)
except ValueError:
    print('Invalid inputs')
else:
    print('Result is %.1f' % result) 
    
#how closure interacts with variable scope
#This pattern is useful when you’re rendering a
#user interface and want important messages or exceptional events to
#be displayed before everything else.

numbers = [8, 3, 1, 2, 5, 4, 7, 6]
group = {2, 3, 5, 7}
def sort_priority(values, group):
    def helper(x):
        if x in group:
            return (0, x)
        return (1, x)
    values.sort(key=helper)
numbers = [8, 3, 1, 2, 5, 4, 7, 6]
group = {2, 3, 5, 7}
sort_priority(numbers, group)
print(numbers)

#Reducing visual noise with variable positional arguments
 #For example, say that I want to log some debugging information. With a fixed number
 # of arguments, I would need a function that takes a message and a
 # list of values:
def log(message, values):
    if not values:
        print(message)
    else:
        values_str = ','.join(str(x) for x in values)
        print(f'{message}: {values_str}')
log('My numbers are', [1, 2])
log('Hi there', []) 

#ir is a noisy code, since we are passing an empty code 
# it is better this way

# * is used for unpacking tuples (catch-All unpacking over slicing)
def log(message, *values):
    if not values:
        print(message)
    else:
        values_str = ','.join(str(x) for x in values)
        print(f'{message}: {values_str}')
log('My numbers are', 1, 2)
log('Hi there')
 
#if i have  a sequence and want to pass positional argument,
# use the starrred function
favourites = [7, 33, 99]
log('Favourite colors', *favourites)

def my_generators():
    for i in range(10):
        yield i
        
def my_func(*args):
    print(args)
    
it = my_generators()
my_func(*it)

#problem with arg, you cannot add positional arguments to a function

def log(sequence, message, *values):
    if not values:
        print(f'{sequence} - {message}')
    else:
        values_str = ','.join(str(x) for x in values)
        print(f'{sequence} - {message}: {values_str}')
log(1, 'Favourites', 7, 33)
log(1, 'Hi there!')
log('Favourite numbers', 7, 33)

#provide optional behavior with keyword arguments
def remainder(number, divisor):
    return number % divisor

my_kwargs = {
    'number': 20,
    'divisor': 6,
}
remainder(**my_kwargs)
print(my_kwargs)

def print_parameters(**kwargs):
    for key, value in kwargs.items():
        print(f'{key} = {value}')
print_parameters(alpha=1.5, beta=9, gamma=4)

def flow_rate(weight_diff, time_diff):
    return weight_diff / time_diff
weight_diff = 0.5
time_dif = 3
flow = flow_rate(weight_diff, time_dif)
print(f'{flow:.3} kg per second')

#use none docstring to specify dynamic default arguments

from time import sleep
from datetime import datetime

def log(message, when=datetime.now()):
    print(f'{when}: {message}')
log('Hi there!')
sleep(0.1)
log('Hello again')

def log(message, when=None):
   """Log a message with a timestamp.
   
   Args:
        message: Message to print.
        When: datetime of when the message occured.
        Defaults to the present time.   
   """
   if when is None:
       when = datetime.now()
       print(f'{when}: {message}')
log('Hi there!')
sleep(0.1)
log('Hello again')      

#using JSON

import json 

def decode(data, default={}):
    try:
        return json.loads(data)
    except ValueError:
        return default
    
foo = decode('bad data')
foo['stuff'] = 5
bar = decode('also bad')
bar['meep'] = 1
print('Foo:', foo)
print('Bar:', bar)

def decode(data, default=None):
    """Load JSON data from a string.
    
    Args:
        data: JSON data to decode.
        default: Value to return if decoding fails.
    """
    try:
        return json.loads(data)
    except ValueError:
        if default is None:
            default = {}
        return default
foo = decode('bad data')
foo['stuff'] = 5
bar = decode('also bad')
bar['meep'] = 1
print('Foo:', foo)
print('Bar:', bar)


from typing import Optional

def log_typed(message, str, 
              when: Optional[datetime]=None) -> None:
    """Log a message with a timestamp.
    
    Args:
        message: Message to print.
        when: datetime of when the message occured.
            Defaults to the present time.
                """
    if when is None:
        when = datetime.now()
    print(f'{when}: {message}')
    
#ENFORCE CLARITY WITH KEYWORD ONLY AND POSITIONAL ONLY ARG.

def safe_division(number, divisor,
                  ignore_overflow,
                  ignore_zero_division):
    try:
        return number / divisor
    except OverflowError:
        if ignore_overflow:
            return 0
        else:
            raise
    except ZeroDivisionError:
        if ignore_zero_division:
            return float('infinity')
result = safe_division(1.0, 10**500, True, False)
print(result)

# Reducing noise and improving code readability

def safe_division_b(number, divisor,
                  ignore_overflow=False,
                  ignore_zero_division=False):
    
    try:
        return number / divisor
    except OverflowError:
        if ignore_overflow:
            return 0
        else:
            raise
    except ZeroDivisionError:
        if ignore_zero_division:
            return float('infinity')
    ...
result = safe_division_b(1.0, 10**500, ignore_overflow=True)
print(result)

result = safe_division_b(1.0, 0, ignore_zero_division=True)
print(result)

def safe_div(numerator, denominator, /, 
             ndigits=10, *,
             ignore_overflow=False,
             ignore_zero_division=True):
    try:
        fraction = numerator / denominator
        return round(fraction, ndigits)
    except OverflowError:
        if ignore_overflow:
            return 0
        else:
            raise
    except ZeroDivisionError:
        if ignore_zero_division:
            return float('inf')
        else:
            raise
result = safe_div(22, 7)
print(result)

result = safe_div(22, 7, 5)
print(result)

result = safe_div(22, 7, ndigits=2)
print(result)

#define function decorators with functools.wraps

def trace(func):
    def wrapper(*args, **kwargs):
        result = func(*args, **kwargs)
        print(f'{func.__name__}({args!r}, {kwargs!r})'
            f'-> {result!r}')
        return result
    return wrapper
# this decorstor can be applied to a function by using the @ symbol
@trace 
def fibonacci(n):
    """Retun the n-th Fibonacci number"""
    if n in (0, 1):
        return n
    return (fibonacci(n - 2) + fibonacci(n - 1))
fibonacci = trace(fibonacci)
fibonacci(4)
print(fibonacci)
