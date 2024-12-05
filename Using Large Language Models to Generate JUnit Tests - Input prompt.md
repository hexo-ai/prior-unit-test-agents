# Extracted Functions and Tests

## ../HumanEvalPython/original/id_50.py

### Original Code
```python
# id_50.py


def encode_shift(s: str):
    """
    returns encoded string by shifting every character by 5 in the alphabet.
    """
    return "".join([chr(((ord(ch) + 5 - ord("a")) % 26) + ord("a")) for ch in s])


def decode_shift(s: str):
    """
    takes as input string encoded with encode_shift function. Returns decoded string.
    """

    return "".join([chr(((ord(ch) - 5 - ord("a")) % 26) + ord("a")) for ch in s])

```

### Test Prompt
```python
# id_50_Test.java
from original.id_50 import decode_shift

import pytest

class id_50_Test:
    """
    Test class of id_50.py.
    It contains ten unit test cases for the :func:`original.id_50.decode_shift`.
    """

```

## ../HumanEvalPython/original/id_108.py

### Original Code
```python
# id_108.py

def count_nums(arr):
    """
    Write a function count_nums which takes an array of integers and returns
    the number of elements which has a sum of digits > 0.
    If a number is negative, then its first signed digit will be negative:
    e.g. -123 has signed digits -1, 2, and 3.
    >>> count_nums([]) == 0
    >>> count_nums([-1, 11, -11]) == 1
    >>> count_nums([1, 1, 2]) == 3
    """

    def digits_sum(n):
        neg = 1
        if n < 0: n, neg = -1 * n, -1 
        n = [int(i) for i in str(n)]
        n[0] = n[0] * neg
        return sum(n)
    return len(list(filter(lambda x: x > 0, [digits_sum(i) for i in arr])))


```

### Test Prompt
```python
# id_108_Test.java
from original.id_108 import count_nums

import pytest

class id_108_Test:
    """
    Test class of id_108.py.
    It contains ten unit test cases for the :func:`original.id_108.count_nums`.
    """

```

## ../HumanEvalPython/original/id_64.py

### Original Code
```python
# id_64.py
def vowels_count(s):
    """Write a function vowels_count which takes a string representing
    a word as input and returns the number of vowels in the string.
    Vowels in this case are 'a', 'e', 'i', 'o', 'u'. Here, 'y' is also a
    vowel, but only when it is at the end of the given word.

    Example:
    >>> vowels_count("abcde")
    2
    >>> vowels_count("ACEDY")
    3
    """

    vowels = "aeiouAEIOU"
    n_vowels = sum(c in vowels for c in s)
    if s[-1] == 'y' or s[-1] == 'Y':
        n_vowels += 1
    return n_vowels

```

### Test Prompt
```python
# id_64_Test.java
from original.id_64 import vowels_count

import pytest

class id_64_Test:
    """
    Test class of id_64.py.
    It contains ten unit test cases for the :func:`original.id_64.vowels_count`.
    """

```

## ../HumanEvalPython/original/id_159.py

### Original Code
```python
# id_159.py

def eat(number, need, remaining):
    """
    You're a hungry rabbit, and you already have eaten a certain number of carrots,
    but now you need to eat more carrots to complete the day's meals.
    you should return an array of [ total number of eaten carrots after your meals,
                                    the number of carrots left after your meals ]
    if there are not enough remaining carrots, you will eat all remaining carrots, but will still be hungry.
    
    Example:
    * eat(5, 6, 10) -> [11, 4]
    * eat(4, 8, 9) -> [12, 1]
    * eat(1, 10, 10) -> [11, 0]
    * eat(2, 11, 5) -> [7, 0]
    
    Variables:
    @number : integer
        the number of carrots that you have eaten.
    @need : integer
        the number of carrots that you need to eat.
    @remaining : integer
        the number of remaining carrots thet exist in stock
    
    Constrain:
    * 0 <= number <= 1000
    * 0 <= need <= 1000
    * 0 <= remaining <= 1000

    Have fun :)
    """

    if(need <= remaining):
        return [ number + need , remaining-need ]
    else:
        return [ number + remaining , 0]

```

### Test Prompt
```python
# id_159_Test.java
from original.id_159 import eat

import pytest

class id_159_Test:
    """
    Test class of id_159.py.
    It contains ten unit test cases for the :func:`original.id_159.eat`.
    """

```

## ../HumanEvalPython/original/id_35.py

### Original Code
```python
# id_35.py


def max_element(l: list):
    """Return maximum element in the list.
    >>> max_element([1, 2, 3])
    3
    >>> max_element([5, 3, -5, 2, -3, 3, 9, 0, 123, 1, -10])
    123
    """

    m = l[0]
    for e in l:
        if e > m:
            m = e
    return m


```

### Test Prompt
```python
# id_35_Test.java
from original.id_35 import max_element

import pytest

class id_35_Test:
    """
    Test class of id_35.py.
    It contains ten unit test cases for the :func:`original.id_35.max_element`.
    """

```

## ../HumanEvalPython/original/id_97.py

### Original Code
```python
# id_97.py

def multiply(a, b):
    """Complete the function that takes two integers and returns 
    the product of their unit digits.
    Assume the input is always valid.
    Examples:
    multiply(148, 412) should return 16.
    multiply(19, 28) should return 72.
    multiply(2020, 1851) should return 0.
    multiply(14,-15) should return 20.
    """

    return abs(a % 10) * abs(b % 10)

```

### Test Prompt
```python
# id_97_Test.java
from original.id_97 import multiply

import pytest

class id_97_Test:
    """
    Test class of id_97.py.
    It contains ten unit test cases for the :func:`original.id_97.multiply`.
    """

```

## ../HumanEvalPython/original/id_87.py

### Original Code
```python
# id_87.py

def get_row(lst, x):
    """
    You are given a 2 dimensional data, as a nested lists,
    which is similar to matrix, however, unlike matrices,
    each row may contain a different number of columns.
    Given lst, and integer x, find integers x in the list,
    and return list of tuples, [(x1, y1), (x2, y2) ...] such that
    each tuple is a coordinate - (row, columns), starting with 0.
    Sort coordinates initially by rows in ascending order.
    Also, sort coordinates of the row by columns in descending order.
    
    Examples:
    get_row([
      [1,2,3,4,5,6],
      [1,2,3,4,1,6],
      [1,2,3,4,5,1]
    ], 1) == [(0, 0), (1, 4), (1, 0), (2, 5), (2, 0)]
    get_row([], 1) == []
    get_row([[], [1], [1, 2, 3]], 3) == [(2, 2)]
    """

    coords = [(i, j) for i in range(len(lst)) for j in range(len(lst[i])) if lst[i][j] == x]
    return sorted(sorted(coords, key=lambda x: x[1], reverse=True), key=lambda x: x[0])

```

### Test Prompt
```python
# id_87_Test.java
from original.id_87 import get_row

import pytest

class id_87_Test:
    """
    Test class of id_87.py.
    It contains ten unit test cases for the :func:`original.id_87.get_row`.
    """

```

## ../HumanEvalPython/original/id_25.py

### Original Code
```python
# id_25.py
from typing import List


def factorize(n: int) -> List[int]:
    """ Return list of prime factors of given integer in the order from smallest to largest.
    Each of the factors should be listed number of times corresponding to how many times it appeares in factorization.
    Input number should be equal to the product of all factors
    >>> factorize(8)
    [2, 2, 2]
    >>> factorize(25)
    [5, 5]
    >>> factorize(70)
    [2, 5, 7]
    """

    import math
    fact = []
    i = 2
    while i <= int(math.sqrt(n) + 1):
        if n % i == 0:
            fact.append(i)
            n //= i
        else:
            i += 1

    if n > 1:
        fact.append(n)
    return fact

```

### Test Prompt
```python
# id_25_Test.java
from original.id_25 import factorize

import pytest

class id_25_Test:
    """
    Test class of id_25.py.
    It contains ten unit test cases for the :func:`original.id_25.factorize`.
    """

```

## ../HumanEvalPython/original/id_149.py

### Original Code
```python
# id_149.py

def sorted_list_sum(lst):
    """Write a function that accepts a list of strings as a parameter,
    deletes the strings that have odd lengths from it,
    and returns the resulted list with a sorted order,
    The list is always a list of strings and never an array of numbers,
    and it may contain duplicates.
    The order of the list should be ascending by length of each word, and you
    should return the list sorted by that rule.
    If two words have the same length, sort the list alphabetically.
    The function should return a list of strings in sorted order.
    You may assume that all words will have the same length.
    For example:
    assert list_sort(["aa", "a", "aaa"]) => ["aa"]
    assert list_sort(["ab", "a", "aaa", "cd"]) => ["ab", "cd"]
    """

    lst.sort()
    new_lst = []
    for i in lst:
        if len(i)%2 == 0:
            new_lst.append(i)
    return sorted(new_lst, key=len)

```

### Test Prompt
```python
# id_149_Test.java
from original.id_149 import sorted_list_sum

import pytest

class id_149_Test:
    """
    Test class of id_149.py.
    It contains ten unit test cases for the :func:`original.id_149.sorted_list_sum`.
    """

```

## ../HumanEvalPython/original/id_74.py

### Original Code
```python
# id_74.py

def total_match(lst1, lst2):
    '''
    Write a function that accepts two lists of strings and returns the list that has 
    total number of chars in the all strings of the list less than the other list.

    if the two lists have the same number of chars, return the first list.

    Examples
    total_match([], []) ➞ []
    total_match(['hi', 'admin'], ['hI', 'Hi']) ➞ ['hI', 'Hi']
    total_match(['hi', 'admin'], ['hi', 'hi', 'admin', 'project']) ➞ ['hi', 'admin']
    total_match(['hi', 'admin'], ['hI', 'hi', 'hi']) ➞ ['hI', 'hi', 'hi']
    total_match(['4'], ['1', '2', '3', '4', '5']) ➞ ['4']
    '''

    l1 = 0
    for st in lst1:
        l1 += len(st)
    
    l2 = 0
    for st in lst2:
        l2 += len(st)
    
    if l1 <= l2:
        return lst1
    else:
        return lst2


```

### Test Prompt
```python
# id_74_Test.java
from original.id_74 import total_match

import pytest

class id_74_Test:
    """
    Test class of id_74.py.
    It contains ten unit test cases for the :func:`original.id_74.total_match`.
    """

```

## ../HumanEvalPython/original/id_118.py

### Original Code
```python
# id_118.py

def get_closest_vowel(word):
    """You are given a word. Your task is to find the closest vowel that stands between 
    two consonants from the right side of the word (case sensitive).
    
    Vowels in the beginning and ending doesn't count. Return empty string if you didn't
    find any vowel met the above condition. 

    You may assume that the given string contains English letter only.

    Example:
    get_closest_vowel("yogurt") ==> "u"
    get_closest_vowel("FULL") ==> "U"
    get_closest_vowel("quick") ==> ""
    get_closest_vowel("ab") ==> ""
    """

    if len(word) < 3:
        return ""

    vowels = {"a", "e", "i", "o", "u", "A", "E", 'O', 'U', 'I'}
    for i in range(len(word)-2, 0, -1):
        if word[i] in vowels:
            if (word[i+1] not in vowels) and (word[i-1] not in vowels):
                return word[i]
    return ""

```

### Test Prompt
```python
# id_118_Test.java
from original.id_118 import get_closest_vowel

import pytest

class id_118_Test:
    """
    Test class of id_118.py.
    It contains ten unit test cases for the :func:`original.id_118.get_closest_vowel`.
    """

```

## ../HumanEvalPython/original/id_40.py

### Original Code
```python
# id_40.py


def triples_sum_to_zero(l: list):
    """
    triples_sum_to_zero takes a list of integers as an input.
    it returns True if there are three distinct elements in the list that
    sum to zero, and False otherwise.

    >>> triples_sum_to_zero([1, 3, 5, 0])
    False
    >>> triples_sum_to_zero([1, 3, -2, 1])
    True
    >>> triples_sum_to_zero([1, 2, 3, 7])
    False
    >>> triples_sum_to_zero([2, 4, -5, 3, 9, 7])
    True
    >>> triples_sum_to_zero([1])
    False
    """

    for i in range(len(l)):
        for j in range(i + 1, len(l)):
            for k in range(j + 1, len(l)):
                if l[i] + l[j] + l[k] == 0:
                    return True
    return False

```

### Test Prompt
```python
# id_40_Test.java
from original.id_40 import triples_sum_to_zero

import pytest

class id_40_Test:
    """
    Test class of id_40.py.
    It contains ten unit test cases for the :func:`original.id_40.triples_sum_to_zero`.
    """

```

## ../HumanEvalPython/original/id_11.py

### Original Code
```python
# id_11.py
from typing import List


def string_xor(a: str, b: str) -> str:
    """ Input are two strings a and b consisting only of 1s and 0s.
    Perform binary XOR on these inputs and return result also as a string.
    >>> string_xor('010', '110')
    '100'
    """

    def xor(i, j):
        if i == j:
            return '0'
        else:
            return '1'

    return ''.join(xor(x, y) for x, y in zip(a, b))

```

### Test Prompt
```python
# id_11_Test.java
from original.id_11 import string_xor

import pytest

class id_11_Test:
    """
    Test class of id_11.py.
    It contains ten unit test cases for the :func:`original.id_11.string_xor`.
    """

```

## ../HumanEvalPython/original/id_31.py

### Original Code
```python
# id_31.py


def is_prime(n):
    """Return true if a given number is prime, and false otherwise.
    >>> is_prime(6)
    False
    >>> is_prime(101)
    True
    >>> is_prime(11)
    True
    >>> is_prime(13441)
    True
    >>> is_prime(61)
    True
    >>> is_prime(4)
    False
    >>> is_prime(1)
    False
    """

    if n < 2:
        return False
    for k in range(2, n - 1):
        if n % k == 0:
            return False
    return True

```

### Test Prompt
```python
# id_31_Test.java
from original.id_31 import is_prime

import pytest

class id_31_Test:
    """
    Test class of id_31.py.
    It contains ten unit test cases for the :func:`original.id_31.is_prime`.
    """

```

## ../HumanEvalPython/original/id_9.py

### Original Code
```python
# id_9.py
from typing import List, Tuple


def rolling_max(numbers: List[int]) -> List[int]:
    """ From a given list of integers, generate a list of rolling maximum element found until given moment
    in the sequence.
    >>> rolling_max([1, 2, 3, 2, 3, 4, 2])
    [1, 2, 3, 3, 3, 4, 4]
    """

    running_max = None
    result = []

    for n in numbers:
        if running_max is None:
            running_max = n
        else:
            running_max = max(running_max, n)

        result.append(running_max)

    return result

```

### Test Prompt
```python
# id_9_Test.java
from original.id_9 import rolling_max

import pytest

class id_9_Test:
    """
    Test class of id_9.py.
    It contains ten unit test cases for the :func:`original.id_9.rolling_max`.
    """

```

## ../HumanEvalPython/original/id_60.py

### Original Code
```python
# id_60.py


def sum_to_n(n: int):
    """sum_to_n is a function that sums numbers from 1 to n.
    >>> sum_to_n(30)
    465
    >>> sum_to_n(100)
    5050
    >>> sum_to_n(5)
    15
    >>> sum_to_n(10)
    55
    >>> sum_to_n(1)
    1
    """

    return sum(range(n + 1))

```

### Test Prompt
```python
# id_60_Test.java
from original.id_60 import sum_to_n

import pytest

class id_60_Test:
    """
    Test class of id_60.py.
    It contains ten unit test cases for the :func:`original.id_60.sum_to_n`.
    """

```

## ../HumanEvalPython/original/id_93.py

### Original Code
```python
# id_93.py

def encode(message):
    """
    Write a function that takes a message, and encodes in such a 
    way that it swaps case of all letters, replaces all vowels in 
    the message with the letter that appears 2 places ahead of that 
    vowel in the english alphabet. 
    Assume only letters. 
    
    Examples:
    >>> encode('test')
    'TGST'
    >>> encode('This is a message')
    'tHKS KS C MGSSCGG'
    """

    vowels = "aeiouAEIOU"
    vowels_replace = dict([(i, chr(ord(i) + 2)) for i in vowels])
    message = message.swapcase()
    return ''.join([vowels_replace[i] if i in vowels else i for i in message])


```

### Test Prompt
```python
# id_93_Test.java
from original.id_93 import encode

import pytest

class id_93_Test:
    """
    Test class of id_93.py.
    It contains ten unit test cases for the :func:`original.id_93.encode`.
    """

```

## ../HumanEvalPython/original/id_54.py

### Original Code
```python
# id_54.py


def same_chars(s0: str, s1: str):
    """
    Check if two words have the same characters.
    >>> same_chars('eabcdzzzz', 'dddzzzzzzzddeddabc')
    True
    >>> same_chars('abcd', 'dddddddabc')
    True
    >>> same_chars('dddddddabc', 'abcd')
    True
    >>> same_chars('eabcd', 'dddddddabc')
    False
    >>> same_chars('abcd', 'dddddddabce')
    False
    >>> same_chars('eabcdzzzz', 'dddzzzzzzzddddabc')
    False
    """

    return set(s0) == set(s1)


```

### Test Prompt
```python
# id_54_Test.java
from original.id_54 import same_chars

import pytest

class id_54_Test:
    """
    Test class of id_54.py.
    It contains ten unit test cases for the :func:`original.id_54.same_chars`.
    """

```

## ../HumanEvalPython/original/id_138.py

### Original Code
```python
# id_138.py

def is_equal_to_sum_even(n):
    """Evaluate whether the given number n can be written as the sum of exactly 4 positive even numbers
    Example
    is_equal_to_sum_even(4) == False
    is_equal_to_sum_even(6) == False
    is_equal_to_sum_even(8) == True
    """

    return n%2 == 0 and n >= 8

```

### Test Prompt
```python
# id_138_Test.java
from original.id_138 import is_equal_to_sum_even

import pytest

class id_138_Test:
    """
    Test class of id_138.py.
    It contains ten unit test cases for the :func:`original.id_138.is_equal_to_sum_even`.
    """

```

## ../HumanEvalPython/original/id_15.py

### Original Code
```python
# id_15.py


def string_sequence(n: int) -> str:
    """ Return a string containing space-delimited numbers starting from 0 upto n inclusive.
    >>> string_sequence(0)
    '0'
    >>> string_sequence(5)
    '0 1 2 3 4 5'
    """

    return ' '.join([str(x) for x in range(n + 1)])

```

### Test Prompt
```python
# id_15_Test.java
from original.id_15 import string_sequence

import pytest

class id_15_Test:
    """
    Test class of id_15.py.
    It contains ten unit test cases for the :func:`original.id_15.string_sequence`.
    """

```

## ../HumanEvalPython/original/id_128.py

### Original Code
```python
# id_128.py

def prod_signs(arr):
    """
    You are given an array arr of integers and you need to return
    sum of magnitudes of integers multiplied by product of all signs
    of each number in the array, represented by 1, -1 or 0.
    Note: return None for empty arr.

    Example:
    >>> prod_signs([1, 2, 2, -4]) == -9
    >>> prod_signs([0, 1]) == 0
    >>> prod_signs([]) == None
    """

    if not arr: return None
    prod = 0 if 0 in arr else (-1) ** len(list(filter(lambda x: x < 0, arr)))
    return prod * sum([abs(i) for i in arr])

```

### Test Prompt
```python
# id_128_Test.java
from original.id_128 import prod_signs

import pytest

class id_128_Test:
    """
    Test class of id_128.py.
    It contains ten unit test cases for the :func:`original.id_128.prod_signs`.
    """

```

## ../HumanEvalPython/original/id_44.py

### Original Code
```python
# id_44.py


def change_base(x: int, base: int):
    """Change numerical base of input number x to base.
    return string representation after the conversion.
    base numbers are less than 10.
    >>> change_base(8, 3)
    '22'
    >>> change_base(8, 2)
    '1000'
    >>> change_base(7, 2)
    '111'
    """

    ret = ""
    while x > 0:
        ret = str(x % base) + ret
        x //= base
    return ret


```

### Test Prompt
```python
# id_44_Test.java
from original.id_44 import change_base

import pytest

class id_44_Test:
    """
    Test class of id_44.py.
    It contains ten unit test cases for the :func:`original.id_44.change_base`.
    """

```

## ../HumanEvalPython/original/id_83.py

### Original Code
```python
# id_83.py

def starts_one_ends(n):
    """
    Given a positive integer n, return the count of the numbers of n-digit
    positive integers that start or end with 1.
    """

    if n == 1: return 1
    return 18 * (10 ** (n - 2))

```

### Test Prompt
```python
# id_83_Test.java
from original.id_83 import starts_one_ends

import pytest

class id_83_Test:
    """
    Test class of id_83.py.
    It contains ten unit test cases for the :func:`original.id_83.starts_one_ends`.
    """

```

## ../HumanEvalPython/original/id_70.py

### Original Code
```python
# id_70.py

def strange_sort_list(lst):
    '''
    Given list of integers, return list in strange order.
    Strange sorting, is when you start with the minimum value,
    then maximum of the remaining integers, then minimum and so on.

    Examples:
    strange_sort_list([1, 2, 3, 4]) == [1, 4, 2, 3]
    strange_sort_list([5, 5, 5, 5]) == [5, 5, 5, 5]
    strange_sort_list([]) == []
    '''

    res, switch = [], True
    while lst:
        res.append(min(lst) if switch else max(lst))
        lst.remove(res[-1])
        switch = not switch
    return res

```

### Test Prompt
```python
# id_70_Test.java
from original.id_70 import strange_sort_list

import pytest

class id_70_Test:
    """
    Test class of id_70.py.
    It contains ten unit test cases for the :func:`original.id_70.strange_sort_list`.
    """

```

## ../HumanEvalPython/original/id_21.py

### Original Code
```python
# id_21.py
from typing import List


def rescale_to_unit(numbers: List[float]) -> List[float]:
    """ Given list of numbers (of at least two elements), apply a linear transform to that list,
    such that the smallest number will become 0 and the largest will become 1
    >>> rescale_to_unit([1.0, 2.0, 3.0, 4.0, 5.0])
    [0.0, 0.25, 0.5, 0.75, 1.0]
    """

    min_number = min(numbers)
    max_number = max(numbers)
    return [(x - min_number) / (max_number - min_number) for x in numbers]

```

### Test Prompt
```python
# id_21_Test.java
from original.id_21 import rescale_to_unit

import pytest

class id_21_Test:
    """
    Test class of id_21.py.
    It contains ten unit test cases for the :func:`original.id_21.rescale_to_unit`.
    """

```

## ../HumanEvalPython/original/id_8.py

### Original Code
```python
# id_8.py
from typing import List, Tuple


def sum_product(numbers: List[int]) -> Tuple[int, int]:
    """ For a given list of integers, return a tuple consisting of a sum and a product of all the integers in a list.
    Empty sum should be equal to 0 and empty product should be equal to 1.
    >>> sum_product([])
    (0, 1)
    >>> sum_product([1, 2, 3, 4])
    (10, 24)
    """

    sum_value = 0
    prod_value = 1

    for n in numbers:
        sum_value += n
        prod_value *= n
    return sum_value, prod_value

```

### Test Prompt
```python
# id_8_Test.java
from original.id_8 import sum_product

import pytest

class id_8_Test:
    """
    Test class of id_8.py.
    It contains ten unit test cases for the :func:`original.id_8.sum_product`.
    """

```

## ../HumanEvalPython/original/id_30.py

### Original Code
```python
# id_30.py


def get_positive(l: list):
    """Return only positive numbers in the list.
    >>> get_positive([-1, 2, -4, 5, 6])
    [2, 5, 6]
    >>> get_positive([5, 3, -5, 2, -3, 3, 9, 0, 123, 1, -10])
    [5, 3, 2, 3, 9, 123, 1]
    """

    return [e for e in l if e > 0]

```

### Test Prompt
```python
# id_30_Test.java
from original.id_30 import get_positive

import pytest

class id_30_Test:
    """
    Test class of id_30.py.
    It contains ten unit test cases for the :func:`original.id_30.get_positive`.
    """

```

## ../HumanEvalPython/original/id_61.py

### Original Code
```python
# id_61.py


def correct_bracketing(brackets: str):
    """ brackets is a string of "(" and ")".
    return True if every opening bracket has a corresponding closing bracket.

    >>> correct_bracketing("(")
    False
    >>> correct_bracketing("()")
    True
    >>> correct_bracketing("(()())")
    True
    >>> correct_bracketing(")(()")
    False
    """

    depth = 0
    for b in brackets:
        if b == "(":
            depth += 1
        else:
            depth -= 1
        if depth < 0:
            return False
    return depth == 0

```

### Test Prompt
```python
# id_61_Test.java
from original.id_61 import correct_bracketing

import pytest

class id_61_Test:
    """
    Test class of id_61.py.
    It contains ten unit test cases for the :func:`original.id_61.correct_bracketing`.
    """

```

## ../HumanEvalPython/original/id_92.py

### Original Code
```python
# id_92.py

def any_int(x, y, z):
    '''
    Create a function that takes 3 numbers.
    Returns true if one of the numbers is equal to the sum of the other two, and all numbers are integers.
    Returns false in any other cases.
    
    Examples
    any_int(5, 2, 7) ➞ True
    
    any_int(3, 2, 2) ➞ False

    any_int(3, -2, 1) ➞ True
    
    any_int(3.6, -2.2, 2) ➞ False
  

    
    '''

    
    if isinstance(x,int) and isinstance(y,int) and isinstance(z,int):
        if (x+y==z) or (x+z==y) or (y+z==x):
            return True
        return False
    return Falsess

```

### Test Prompt
```python
# id_92_Test.java
from original.id_92 import any_int

import pytest

class id_92_Test:
    """
    Test class of id_92.py.
    It contains ten unit test cases for the :func:`original.id_92.any_int`.
    """

```

## ../HumanEvalPython/original/id_55.py

### Original Code
```python
# id_55.py


def fib(n: int):
    """Return n-th Fibonacci number.
    >>> fib(10)
    55
    >>> fib(1)
    1
    >>> fib(8)
    21
    """

    if n == 0:
        return 0
    if n == 1:
        return 1
    return fib(n - 1) + fib(n - 2)


```

### Test Prompt
```python
# id_55_Test.java
from original.id_55 import fib

import pytest

class id_55_Test:
    """
    Test class of id_55.py.
    It contains ten unit test cases for the :func:`original.id_55.fib`.
    """

```

## ../HumanEvalPython/original/id_139.py

### Original Code
```python
# id_139.py

def special_factorial(n):
    """The Brazilian factorial is defined as:
    brazilian_factorial(n) = n! * (n-1)! * (n-2)! * ... * 1!
    where n > 0

    For example:
    >>> special_factorial(4)
    288

    The function will receive an integer as input and should return the special
    factorial of this integer.
    """

    fact_i = 1
    special_fact = 1
    for i in range(1, n+1):
        fact_i *= i
        special_fact *= fact_i
    return special_fact

```

### Test Prompt
```python
# id_139_Test.java
from original.id_139 import special_factorial

import pytest

class id_139_Test:
    """
    Test class of id_139.py.
    It contains ten unit test cases for the :func:`original.id_139.special_factorial`.
    """

```

## ../HumanEvalPython/original/id_14.py

### Original Code
```python
# id_14.py
from typing import List


def all_prefixes(string: str) -> List[str]:
    """ Return list of all prefixes from shortest to longest of the input string
    >>> all_prefixes('abc')
    ['a', 'ab', 'abc']
    """

    result = []

    for i in range(len(string)):
        result.append(string[:i+1])
    return result

```

### Test Prompt
```python
# id_14_Test.java
from original.id_14 import all_prefixes

import pytest

class id_14_Test:
    """
    Test class of id_14.py.
    It contains ten unit test cases for the :func:`original.id_14.all_prefixes`.
    """

```

## ../HumanEvalPython/original/id_129.py

### Original Code
```python
# id_129.py

def minPath(grid, k):
    """
    Given a grid with N rows and N columns (N >= 2) and a positive integer k, 
    each cell of the grid contains a value. Every integer in the range [1, N * N]
    inclusive appears exactly once on the cells of the grid.

    You have to find the minimum path of length k in the grid. You can start
    from any cell, and in each step you can move to any of the neighbor cells,
    in other words, you can go to cells which share an edge with you current
    cell.
    Please note that a path of length k means visiting exactly k cells (not
    necessarily distinct).
    You CANNOT go off the grid.
    A path A (of length k) is considered less than a path B (of length k) if
    after making the ordered lists of the values on the cells that A and B go
    through (let's call them lst_A and lst_B), lst_A is lexicographically less
    than lst_B, in other words, there exist an integer index i (1 <= i <= k)
    such that lst_A[i] < lst_B[i] and for any j (1 <= j < i) we have
    lst_A[j] = lst_B[j].
    It is guaranteed that the answer is unique.
    Return an ordered list of the values on the cells that the minimum path go through.

    Examples:

        Input: grid = [ [1,2,3], [4,5,6], [7,8,9]], k = 3
        Output: [1, 2, 1]

        Input: grid = [ [5,9,3], [4,1,6], [7,8,2]], k = 1
        Output: [1]
    """

    n = len(grid)
    val = n * n + 1
    for i in range(n):
        for j in range(n):
            if grid[i][j] == 1:
                temp = []
                if i != 0:
                    temp.append(grid[i - 1][j])

                if j != 0:
                    temp.append(grid[i][j - 1])

                if i != n - 1:
                    temp.append(grid[i + 1][j])

                if j != n - 1:
                    temp.append(grid[i][j + 1])

                val = min(temp)

    ans = []
    for i in range(k):
        if i % 2 == 0:
            ans.append(1)
        else:
            ans.append(val)
    return ans


```

### Test Prompt
```python
# id_129_Test.java
from original.id_129 import minPath

import pytest

class id_129_Test:
    """
    Test class of id_129.py.
    It contains ten unit test cases for the :func:`original.id_129.minPath`.
    """

```

## ../HumanEvalPython/original/id_45.py

### Original Code
```python
# id_45.py


def triangle_area(a, h):
    """Given length of a side and high return area for a triangle.
    >>> triangle_area(5, 3)
    7.5
    """

    return a * h / 2.0

```

### Test Prompt
```python
# id_45_Test.java
from original.id_45 import triangle_area

import pytest

class id_45_Test:
    """
    Test class of id_45.py.
    It contains ten unit test cases for the :func:`original.id_45.triangle_area`.
    """

```

## ../HumanEvalPython/original/id_82.py

### Original Code
```python
# id_82.py

def prime_length(string):
    """Write a function that takes a string and returns True if the string
    length is a prime number or False otherwise
    Examples
    prime_length('Hello') == True
    prime_length('abcdcba') == True
    prime_length('kittens') == True
    prime_length('orange') == False
    """

    l = len(string)
    if l == 0 or l == 1:
        return False
    for i in range(2, l):
        if l % i == 0:
            return False
    return True

```

### Test Prompt
```python
# id_82_Test.java
from original.id_82 import prime_length

import pytest

class id_82_Test:
    """
    Test class of id_82.py.
    It contains ten unit test cases for the :func:`original.id_82.prime_length`.
    """

```

## ../HumanEvalPython/original/id_71.py

### Original Code
```python
# id_71.py

def triangle_area(a, b, c):
    '''
    Given the lengths of the three sides of a triangle. Return the area of
    the triangle rounded to 2 decimal points if the three sides form a valid triangle. 
    Otherwise return -1
    Three sides make a valid triangle when the sum of any two sides is greater 
    than the third side.
    Example:
    triangle_area(3, 4, 5) == 6.00
    triangle_area(1, 2, 10) == -1
    '''

    if a + b <= c or a + c <= b or b + c <= a:
        return -1 
    s = (a + b + c)/2    
    area = (s * (s - a) * (s - b) * (s - c)) ** 0.5
    area = round(area, 2)
    return area

```

### Test Prompt
```python
# id_71_Test.java
from original.id_71 import triangle_area

import pytest

class id_71_Test:
    """
    Test class of id_71.py.
    It contains ten unit test cases for the :func:`original.id_71.triangle_area`.
    """

```

## ../HumanEvalPython/original/id_20.py

### Original Code
```python
# id_20.py
from typing import List, Tuple


def find_closest_elements(numbers: List[float]) -> Tuple[float, float]:
    """ From a supplied list of numbers (of length at least two) select and return two that are the closest to each
    other and return them in order (smaller number, larger number).
    >>> find_closest_elements([1.0, 2.0, 3.0, 4.0, 5.0, 2.2])
    (2.0, 2.2)
    >>> find_closest_elements([1.0, 2.0, 3.0, 4.0, 5.0, 2.0])
    (2.0, 2.0)
    """

    closest_pair = None
    distance = None

    for idx, elem in enumerate(numbers):
        for idx2, elem2 in enumerate(numbers):
            if idx != idx2:
                if distance is None:
                    distance = abs(elem - elem2)
                    closest_pair = tuple(sorted([elem, elem2]))
                else:
                    new_distance = abs(elem - elem2)
                    if new_distance < distance:
                        distance = new_distance
                        closest_pair = tuple(sorted([elem, elem2]))

    return closest_pair

```

### Test Prompt
```python
# id_20_Test.java
from original.id_20 import find_closest_elements

import pytest

class id_20_Test:
    """
    Test class of id_20.py.
    It contains ten unit test cases for the :func:`original.id_20.find_closest_elements`.
    """

```

## ../HumanEvalPython/original/id_51.py

### Original Code
```python
# id_51.py


def remove_vowels(text):
    """
    remove_vowels is a function that takes string and returns string without vowels.
    >>> remove_vowels('')
    ''
    >>> remove_vowels("abcdef\nghijklm")
    'bcdf\nghjklm'
    >>> remove_vowels('abcdef')
    'bcdf'
    >>> remove_vowels('aaaaa')
    ''
    >>> remove_vowels('aaBAA')
    'B'
    >>> remove_vowels('zbcd')
    'zbcd'
    """

    return "".join([s for s in text if s.lower() not in ["a", "e", "i", "o", "u"]])


```

### Test Prompt
```python
# id_51_Test.java
from original.id_51 import remove_vowels

import pytest

class id_51_Test:
    """
    Test class of id_51.py.
    It contains ten unit test cases for the :func:`original.id_51.remove_vowels`.
    """

```

## ../HumanEvalPython/original/id_109.py

### Original Code
```python
# id_109.py

def move_one_ball(arr):
    """We have an array 'arr' of N integers arr[1], arr[2], ..., arr[N].The
    numbers in the array will be randomly ordered. Your task is to determine if
    it is possible to get an array sorted in non-decreasing order by performing 
    the following operation on the given array:
        You are allowed to perform right shift operation any number of times.
    
    One right shift operation means shifting all elements of the array by one
    position in the right direction. The last element of the array will be moved to
    the starting position in the array i.e. 0th index. 

    If it is possible to obtain the sorted array by performing the above operation
    then return True else return False.
    If the given array is empty then return True.

    Note: The given list is guaranteed to have unique elements.

    For Example:
    
    move_one_ball([3, 4, 5, 1, 2])==>True
    Explanation: By performin 2 right shift operations, non-decreasing order can
                 be achieved for the given array.
    move_one_ball([3, 5, 4, 1, 2])==>False
    Explanation:It is not possible to get non-decreasing order for the given
                array by performing any number of right shift operations.
                
    """

    if len(arr)==0:
      return True
    sorted_array=sorted(arr)
    my_arr=[]
    
    min_value=min(arr)
    min_index=arr.index(min_value)
    my_arr=arr[min_index:]+arr[0:min_index]
    for i in range(len(arr)):
      if my_arr[i]!=sorted_array[i]:
        return False
    return True


```

### Test Prompt
```python
# id_109_Test.java
from original.id_109 import move_one_ball

import pytest

class id_109_Test:
    """
    Test class of id_109.py.
    It contains ten unit test cases for the :func:`original.id_109.move_one_ball`.
    """

```

## ../HumanEvalPython/original/id_65.py

### Original Code
```python
# id_65.py

def circular_shift(x, shift):
    """Circular shift the digits of the integer x, shift the digits right by shift
    and return the result as a string.
    If shift > number of digits, return digits reversed.
    >>> circular_shift(12, 1)
    "21"
    >>> circular_shift(12, 2)
    "12"
    """

    s = str(x)
    if shift > len(s):
        return s[::-1]
    else:
        return s[len(s) - shift:] + s[:len(s) - shift]

```

### Test Prompt
```python
# id_65_Test.java
from original.id_65 import circular_shift

import pytest

class id_65_Test:
    """
    Test class of id_65.py.
    It contains ten unit test cases for the :func:`original.id_65.circular_shift`.
    """

```

## ../HumanEvalPython/original/id_158.py

### Original Code
```python
# id_158.py

def find_max(words):
    """Write a function that accepts a list of strings.
    The list contains different words. Return the word with maximum number
    of unique characters. If multiple strings have maximum number of unique
    characters, return the one which comes first in lexicographical order.

    find_max(["name", "of", "string"]) == "string"
    find_max(["name", "enam", "game"]) == "enam"
    find_max(["aaaaaaa", "bb" ,"cc"]) == ""aaaaaaa"
    """

    return sorted(words, key = lambda x: (-len(set(x)), x))[0]

```

### Test Prompt
```python
# id_158_Test.java
from original.id_158 import find_max

import pytest

class id_158_Test:
    """
    Test class of id_158.py.
    It contains ten unit test cases for the :func:`original.id_158.find_max`.
    """

```

## ../HumanEvalPython/original/id_34.py

### Original Code
```python
# id_34.py


def unique(l: list):
    """Return sorted unique elements in a list
    >>> unique([5, 3, 5, 2, 3, 3, 9, 0, 123])
    [0, 2, 3, 5, 9, 123]
    """

    return sorted(list(set(l)))

```

### Test Prompt
```python
# id_34_Test.java
from original.id_34 import unique

import pytest

class id_34_Test:
    """
    Test class of id_34.py.
    It contains ten unit test cases for the :func:`original.id_34.unique`.
    """

```

## ../HumanEvalPython/original/id_96.py

### Original Code
```python
# id_96.py

def count_up_to(n):
    """Implement a function that takes an non-negative integer and returns an array of the first n
    integers that are prime numbers and less than n.
    for example:
    count_up_to(5) => [2,3]
    count_up_to(11) => [2,3,5,7]
    count_up_to(0) => []
    count_up_to(20) => [2,3,5,7,11,13,17,19]
    count_up_to(1) => []
    count_up_to(18) => [2,3,5,7,11,13,17]
    """

    primes = []
    for i in range(2, n):
        is_prime = True
        for j in range(2, i):
            if i % j == 0:
                is_prime = False
                break
        if is_prime:
            primes.append(i)
    return primes


```

### Test Prompt
```python
# id_96_Test.java
from original.id_96 import count_up_to

import pytest

class id_96_Test:
    """
    Test class of id_96.py.
    It contains ten unit test cases for the :func:`original.id_96.count_up_to`.
    """

```

## ../HumanEvalPython/original/id_86.py

### Original Code
```python
# id_86.py

def anti_shuffle(s):
    """
    Write a function that takes a string and returns an ordered version of it.
    Ordered version of string, is a string where all words (separated by space)
    are replaced by a new word where all the characters arranged in
    ascending order based on ascii value.
    Note: You should keep the order of words and blank spaces in the sentence.

    For example:
    anti_shuffle('Hi') returns 'Hi'
    anti_shuffle('hello') returns 'ehllo'
    anti_shuffle('Hello World!!!') returns 'Hello !!!Wdlor'
    """

    return ' '.join([''.join(sorted(list(i))) for i in s.split(' ')])

```

### Test Prompt
```python
# id_86_Test.java
from original.id_86 import anti_shuffle

import pytest

class id_86_Test:
    """
    Test class of id_86.py.
    It contains ten unit test cases for the :func:`original.id_86.anti_shuffle`.
    """

```

## ../HumanEvalPython/original/id_24.py

### Original Code
```python
# id_24.py


def largest_divisor(n: int) -> int:
    """ For a given number n, find the largest number that divides n evenly, smaller than n
    >>> largest_divisor(15)
    5
    """

    for i in reversed(range(n)):
        if n % i == 0:
            return i

```

### Test Prompt
```python
# id_24_Test.java
from original.id_24 import largest_divisor

import pytest

class id_24_Test:
    """
    Test class of id_24.py.
    It contains ten unit test cases for the :func:`original.id_24.largest_divisor`.
    """

```

## ../HumanEvalPython/original/id_148.py

### Original Code
```python
# id_148.py

def bf(planet1, planet2):
    '''
    There are eight planets in our solar system: the closerst to the Sun 
    is Mercury, the next one is Venus, then Earth, Mars, Jupiter, Saturn, 
    Uranus, Neptune.
    Write a function that takes two planet names as strings planet1 and planet2. 
    The function should return a tuple containing all planets whose orbits are 
    located between the orbit of planet1 and the orbit of planet2, sorted by 
    the proximity to the sun. 
    The function should return an empty tuple if planet1 or planet2
    are not correct planet names. 
    Examples
    bf("Jupiter", "Neptune") ==> ("Saturn", "Uranus")
    bf("Earth", "Mercury") ==> ("Venus")
    bf("Mercury", "Uranus") ==> ("Venus", "Earth", "Mars", "Jupiter", "Saturn")
    '''

    planet_names = ("Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune")
    if planet1 not in planet_names or planet2 not in planet_names or planet1 == planet2:
        return ()
    planet1_index = planet_names.index(planet1)
    planet2_index = planet_names.index(planet2)
    if planet1_index < planet2_index:
        return (planet_names[planet1_index + 1: planet2_index])
    else:
        return (planet_names[planet2_index + 1 : planet1_index])

```

### Test Prompt
```python
# id_148_Test.java
from original.id_148 import bf

import pytest

class id_148_Test:
    """
    Test class of id_148.py.
    It contains ten unit test cases for the :func:`original.id_148.bf`.
    """

```

## ../HumanEvalPython/original/id_75.py

### Original Code
```python
# id_75.py

def is_multiply_prime(a):
    """Write a function that returns true if the given number is the multiplication of 3 prime numbers
    and false otherwise.
    Knowing that (a) is less then 100. 
    Example:
    is_multiply_prime(30) == True
    30 = 2 * 3 * 5
    """

    def is_prime(n):
        for j in range(2,n):
            if n%j == 0:
                return False
        return True

    for i in range(2,101):
        if not is_prime(i): continue
        for j in range(2,101):
            if not is_prime(j): continue
            for k in range(2,101):
                if not is_prime(k): continue
                if i*j*k == a: return True
    return False

```

### Test Prompt
```python
# id_75_Test.java
from original.id_75 import is_multiply_prime

import pytest

class id_75_Test:
    """
    Test class of id_75.py.
    It contains ten unit test cases for the :func:`original.id_75.is_multiply_prime`.
    """

```

## ../HumanEvalPython/original/id_119.py

### Original Code
```python
# id_119.py

def match_parens(lst):
    '''
    You are given a list of two strings, both strings consist of open
    parentheses '(' or close parentheses ')' only.
    Your job is to check if it is possible to concatenate the two strings in
    some order, that the resulting string will be good.
    A string S is considered to be good if and only if all parentheses in S
    are balanced. For example: the string '(())()' is good, while the string
    '())' is not.
    Return 'Yes' if there's a way to make a good string, and return 'No' otherwise.

    Examples:
    match_parens(['()(', ')']) == 'Yes'
    match_parens([')', ')']) == 'No'
    '''

    def check(s):
        val = 0
        for i in s:
            if i == '(':
                val = val + 1
            else:
                val = val - 1
            if val < 0:
                return False
        return True if val == 0 else False

    S1 = lst[0] + lst[1]
    S2 = lst[1] + lst[0]
    return 'Yes' if check(S1) or check(S2) else 'No'

```

### Test Prompt
```python
# id_119_Test.java
from original.id_119 import match_parens

import pytest

class id_119_Test:
    """
    Test class of id_119.py.
    It contains ten unit test cases for the :func:`original.id_119.match_parens`.
    """

```

## ../HumanEvalPython/original/id_41.py

### Original Code
```python
# id_41.py


def car_race_collision(n: int):
    """
    Imagine a road that's a perfectly straight infinitely long line.
    n cars are driving left to right;  simultaneously, a different set of n cars
    are driving right to left.   The two sets of cars start out being very far from
    each other.  All cars move in the same speed.  Two cars are said to collide
    when a car that's moving left to right hits a car that's moving right to left.
    However, the cars are infinitely sturdy and strong; as a result, they continue moving
    in their trajectory as if they did not collide.

    This function outputs the number of such collisions.
    """

    return n**2

```

### Test Prompt
```python
# id_41_Test.java
from original.id_41 import car_race_collision

import pytest

class id_41_Test:
    """
    Test class of id_41.py.
    It contains ten unit test cases for the :func:`original.id_41.car_race_collision`.
    """

```

## ../HumanEvalPython/original/id_10.py

### Original Code
```python
# id_10.py


def is_palindrome(string: str) -> bool:
    """ Test if given string is a palindrome """
    return string == string[::-1]


def make_palindrome(string: str) -> str:
    """ Find the shortest palindrome that begins with a supplied string.
    Algorithm idea is simple:
    - Find the longest postfix of supplied string that is a palindrome.
    - Append to the end of the string reverse of a string prefix that comes before the palindromic suffix.
    >>> make_palindrome('')
    ''
    >>> make_palindrome('cat')
    'catac'
    >>> make_palindrome('cata')
    'catac'
    """

    if not string:
        return ''

    beginning_of_suffix = 0

    while not is_palindrome(string[beginning_of_suffix:]):
        beginning_of_suffix += 1

    return string + string[:beginning_of_suffix][::-1]

```

### Test Prompt
```python
# id_10_Test.java
from original.id_10 import make_palindrome

import pytest

class id_10_Test:
    """
    Test class of id_10.py.
    It contains ten unit test cases for the :func:`original.id_10.make_palindrome`.
    """

```

## ../HumanEvalPython/original/id_136.py

### Original Code
```python
# id_136.py

def largest_smallest_integers(lst):
    '''
    Create a function that returns a tuple (a, b), where 'a' is
    the largest of negative integers, and 'b' is the smallest
    of positive integers in a list.
    If there is no negative or positive integers, return them as None.

    Examples:
    largest_smallest_integers([2, 4, 1, 3, 5, 7]) == (None, 1)
    largest_smallest_integers([]) == (None, None)
    largest_smallest_integers([0]) == (None, None)
    '''

    smallest = list(filter(lambda x: x < 0, lst))
    largest = list(filter(lambda x: x > 0, lst))
    return (max(smallest) if smallest else None, min(largest) if largest else None)

```

### Test Prompt
```python
# id_136_Test.java
from original.id_136 import largest_smallest_integers

import pytest

class id_136_Test:
    """
    Test class of id_136.py.
    It contains ten unit test cases for the :func:`original.id_136.largest_smallest_integers`.
    """

```

## ../HumanEvalPython/original/id_102.py

### Original Code
```python
# id_102.py

def choose_num(x, y):
    """This function takes two positive numbers x and y and returns the
    biggest even integer number that is in the range [x, y] inclusive. If 
    there's no such number, then the function should return -1.

    For example:
    choose_num(12, 15) = 14
    choose_num(13, 12) = -1
    """

    if x > y:
        return -1
    if y % 2 == 0:
        return y
    if x == y:
        return -1
    return y - 1

```

### Test Prompt
```python
# id_102_Test.java
from original.id_102 import choose_num

import pytest

class id_102_Test:
    """
    Test class of id_102.py.
    It contains ten unit test cases for the :func:`original.id_102.choose_num`.
    """

```

## ../HumanEvalPython/original/id_153.py

### Original Code
```python
# id_153.py

def Strongest_Extension(class_name, extensions):
    """You will be given the name of a class (a string) and a list of extensions.
    The extensions are to be used to load additional classes to the class. The
    strength of the extension is as follows: Let CAP be the number of the uppercase
    letters in the extension's name, and let SM be the number of lowercase letters 
    in the extension's name, the strength is given by the fraction CAP - SM. 
    You should find the strongest extension and return a string in this 
    format: ClassName.StrongestExtensionName.
    If there are two or more extensions with the same strength, you should
    choose the one that comes first in the list.
    For example, if you are given "Slices" as the class and a list of the
    extensions: ['SErviNGSliCes', 'Cheese', 'StuFfed'] then you should
    return 'Slices.SErviNGSliCes' since 'SErviNGSliCes' is the strongest extension 
    (its strength is -1).
    Example:
    for Strongest_Extension('my_class', ['AA', 'Be', 'CC']) == 'my_class.AA'
    """

    strong = extensions[0]
    my_val = len([x for x in extensions[0] if x.isalpha() and x.isupper()]) - len([x for x in extensions[0] if x.isalpha() and x.islower()])
    for s in extensions:
        val = len([x for x in s if x.isalpha() and x.isupper()]) - len([x for x in s if x.isalpha() and x.islower()])
        if val > my_val:
            strong = s
            my_val = val

    ans = class_name + "." + strong
    return ans


```

### Test Prompt
```python
# id_153_Test.java
from original.id_153 import Strongest_Extension

import pytest

class id_153_Test:
    """
    Test class of id_153.py.
    It contains ten unit test cases for the :func:`original.id_153.Strongest_Extension`.
    """

```

## ../HumanEvalPython/original/id_7.py

### Original Code
```python
# id_7.py
from typing import List


def filter_by_substring(strings: List[str], substring: str) -> List[str]:
    """ Filter an input list of strings only for ones that contain given substring
    >>> filter_by_substring([], 'a')
    []
    >>> filter_by_substring(['abc', 'bacd', 'cde', 'array'], 'a')
    ['abc', 'bacd', 'array']
    """

    return [x for x in strings if substring in x]

```

### Test Prompt
```python
# id_7_Test.java
from original.id_7 import filter_by_substring

import pytest

class id_7_Test:
    """
    Test class of id_7.py.
    It contains ten unit test cases for the :func:`original.id_7.filter_by_substring`.
    """

```

## ../HumanEvalPython/original/id_143.py

### Original Code
```python
# id_143.py

def words_in_sentence(sentence):
    """
    You are given a string representing a sentence,
    the sentence contains some words separated by a space,
    and you have to return a string that contains the words from the original sentence,
    whose lengths are prime numbers,
    the order of the words in the new string should be the same as the original one.

    Example 1:
        Input: sentence = "This is a test"
        Output: "is"

    Example 2:
        Input: sentence = "lets go for swimming"
        Output: "go for"

    Constraints:
        * 1 <= len(sentence) <= 100
        * sentence contains only letters
    """

    new_lst = []
    for word in sentence.split():
        flg = 0
        if len(word) == 1:
            flg = 1
        for i in range(2, len(word)):
            if len(word)%i == 0:
                flg = 1
        if flg == 0 or len(word) == 2:
            new_lst.append(word)
    return " ".join(new_lst)

```

### Test Prompt
```python
# id_143_Test.java
from original.id_143 import words_in_sentence

import pytest

class id_143_Test:
    """
    Test class of id_143.py.
    It contains ten unit test cases for the :func:`original.id_143.words_in_sentence`.
    """

```

## ../HumanEvalPython/original/id_112.py

### Original Code
```python
# id_112.py

def reverse_delete(s,c):
    """Task
    We are given two strings s and c, you have to deleted all the characters in s that are equal to any character in c
    then check if the result string is palindrome.
    A string is called palindrome if it reads the same backward as forward.
    You should return a tuple containing the result string and True/False for the check.
    Example
    For s = "abcde", c = "ae", the result should be ('bcd',False)
    For s = "abcdef", c = "b"  the result should be ('acdef',False)
    For s = "abcdedcba", c = "ab", the result should be ('cdedc',True)
    """

    s = ''.join([char for char in s if char not in c])
    return (s,s[::-1] == s)

```

### Test Prompt
```python
# id_112_Test.java
from original.id_112 import reverse_delete

import pytest

class id_112_Test:
    """
    Test class of id_112.py.
    It contains ten unit test cases for the :func:`original.id_112.reverse_delete`.
    """

```

## ../HumanEvalPython/original/id_126.py

### Original Code
```python
# id_126.py

def is_sorted(lst):
    '''
    Given a list of numbers, return whether or not they are sorted
    in ascending order. If list has more than 1 duplicate of the same
    number, return False. Assume no negative numbers and only integers.

    Examples
    is_sorted([5]) ➞ True
    is_sorted([1, 2, 3, 4, 5]) ➞ True
    is_sorted([1, 3, 2, 4, 5]) ➞ False
    is_sorted([1, 2, 3, 4, 5, 6]) ➞ True
    is_sorted([1, 2, 3, 4, 5, 6, 7]) ➞ True
    is_sorted([1, 3, 2, 4, 5, 6, 7]) ➞ False
    is_sorted([1, 2, 2, 3, 3, 4]) ➞ True
    is_sorted([1, 2, 2, 2, 3, 4]) ➞ False
    '''

    count_digit = dict([(i, 0) for i in lst])
    for i in lst:
        count_digit[i]+=1 
    if any(count_digit[i] > 2 for i in lst):
        return False
    if all(lst[i-1] <= lst[i] for i in range(1, len(lst))):
        return True
    else:
        return False
    
    

```

### Test Prompt
```python
# id_126_Test.java
from original.id_126 import is_sorted

import pytest

class id_126_Test:
    """
    Test class of id_126.py.
    It contains ten unit test cases for the :func:`original.id_126.is_sorted`.
    """

```

## ../HumanEvalPython/original/id_99.py

### Original Code
```python
# id_99.py

def closest_integer(value):
    '''
    Create a function that takes a value (string) representing a number
    and returns the closest integer to it. If the number is equidistant
    from two integers, round it away from zero.

    Examples
    >>> closest_integer("10")
    10
    >>> closest_integer("15.3")
    15

    Note:
    Rounding away from zero means that if the given number is equidistant
    from two integers, the one you should return is the one that is the
    farthest from zero. For example closest_integer("14.5") should
    return 15 and closest_integer("-14.5") should return -15.
    '''

    from math import floor, ceil

    if value.count('.') == 1:
        # remove trailing zeros
        while (value[-1] == '0'):
            value = value[:-1]

    num = float(value)
    if value[-2:] == '.5':
        if num > 0:
            res = ceil(num)
        else:
            res = floor(num)
    elif len(value) > 0:
        res = int(round(num))
    else:
        res = 0

    return res


```

### Test Prompt
```python
# id_99_Test.java
from original.id_99 import closest_integer

import pytest

class id_99_Test:
    """
    Test class of id_99.py.
    It contains ten unit test cases for the :func:`original.id_99.closest_integer`.
    """

```

## ../HumanEvalPython/original/id_157.py

### Original Code
```python
# id_157.py

def right_angle_triangle(a, b, c):
    '''
    Given the lengths of the three sides of a triangle. Return True if the three
    sides form a right-angled triangle, False otherwise.
    A right-angled triangle is a triangle in which one angle is right angle or 
    90 degree.
    Example:
    right_angle_triangle(3, 4, 5) == True
    right_angle_triangle(1, 2, 3) == False
    '''

    return a*a == b*b + c*c or b*b == a*a + c*c or c*c == a*a + b*b

```

### Test Prompt
```python
# id_157_Test.java
from original.id_157 import right_angle_triangle

import pytest

class id_157_Test:
    """
    Test class of id_157.py.
    It contains ten unit test cases for the :func:`original.id_157.right_angle_triangle`.
    """

```

## ../HumanEvalPython/original/id_3.py

### Original Code
```python
# id_3.py
from typing import List


def below_zero(operations: List[int]) -> bool:
    """ You're given a list of deposit and withdrawal operations on a bank account that starts with
    zero balance. Your task is to detect if at any point the balance of account fallls below zero, and
    at that point function should return True. Otherwise it should return False.
    >>> below_zero([1, 2, 3])
    False
    >>> below_zero([1, 2, -4, 5])
    True
    """

    balance = 0

    for op in operations:
        balance += op
        if balance < 0:
            return True

    return False

```

### Test Prompt
```python
# id_3_Test.java
from original.id_3 import below_zero

import pytest

class id_3_Test:
    """
    Test class of id_3.py.
    It contains ten unit test cases for the :func:`original.id_3.below_zero`.
    """

```

## ../HumanEvalPython/original/id_106.py

### Original Code
```python
# id_106.py

def f(n):
    """ Implement the function f that takes n as a parameter,
    and returns a list of size n, such that the value of the element at index i is the factorial of i if i is even
    or the sum of numbers from 1 to i otherwise.
    i starts from 1.
    the factorial of i is the multiplication of the numbers from 1 to i (1 * 2 * ... * i).
    Example:
    f(5) == [1, 2, 6, 24, 15]
    """

    ret = []
    for i in range(1,n+1):
        if i%2 == 0:
            x = 1
            for j in range(1,i+1): x *= j
            ret += [x]
        else:
            x = 0
            for j in range(1,i+1): x += j
            ret += [x]
    return ret


```

### Test Prompt
```python
# id_106_Test.java
from original.id_106 import f

import pytest

class id_106_Test:
    """
    Test class of id_106.py.
    It contains ten unit test cases for the :func:`original.id_106.f`.
    """

```

## ../HumanEvalPython/original/id_132.py

### Original Code
```python
# id_132.py

def is_nested(string):
    '''
    Create a function that takes a string as input which contains only square brackets.
    The function should return True if and only if there is a valid subsequence of brackets 
    where at least one bracket in the subsequence is nested.

    is_nested('[[]]') ➞ True
    is_nested('[]]]]]]][[[[[]') ➞ False
    is_nested('[][]') ➞ False
    is_nested('[]') ➞ False
    is_nested('[[][]]') ➞ True
    is_nested('[[]][[') ➞ True
    '''

    opening_bracket_index = []
    closing_bracket_index = []
    for i in range(len(string)):
        if string[i] == '[':
            opening_bracket_index.append(i)
        else:
            closing_bracket_index.append(i)
    closing_bracket_index.reverse()
    cnt = 0
    i = 0
    l = len(closing_bracket_index)
    for idx in opening_bracket_index:
        if i < l and idx < closing_bracket_index[i]:
            cnt += 1
            i += 1
    return cnt >= 2

    

```

### Test Prompt
```python
# id_132_Test.java
from original.id_132 import is_nested

import pytest

class id_132_Test:
    """
    Test class of id_132.py.
    It contains ten unit test cases for the :func:`original.id_132.is_nested`.
    """

```

## ../HumanEvalPython/original/id_163.py

### Original Code
```python
# id_163.py

def generate_integers(a, b):
    """
    Given two positive integers a and b, return the even digits between a
    and b, in ascending order.

    For example:
    generate_integers(2, 8) => [2, 4, 6, 8]
    generate_integers(8, 2) => [2, 4, 6, 8]
    generate_integers(10, 14) => []
    """

    lower = max(2, min(a, b))
    upper = min(8, max(a, b))

    return [i for i in range(lower, upper+1) if i % 2 == 0]

```

### Test Prompt
```python
# id_163_Test.java
from original.id_163 import generate_integers

import pytest

class id_163_Test:
    """
    Test class of id_163.py.
    It contains ten unit test cases for the :func:`original.id_163.generate_integers`.
    """

```

## ../HumanEvalPython/original/id_122.py

### Original Code
```python
# id_122.py

def add_elements(arr, k):
    """
    Given a non-empty array of integers arr and an integer k, return
    the sum of the elements with at most two digits from the first k elements of arr.

    Example:

        Input: arr = [111,21,3,4000,5,6,7,8,9], k = 4
        Output: 24 # sum of 21 + 3

    Constraints:
        1. 1 <= len(arr) <= 100
        2. 1 <= k <= len(arr)
    """

    return sum(elem for elem in arr[:k] if len(str(elem)) <= 2)


```

### Test Prompt
```python
# id_122_Test.java
from original.id_122 import add_elements

import pytest

class id_122_Test:
    """
    Test class of id_122.py.
    It contains ten unit test cases for the :func:`original.id_122.add_elements`.
    """

```

## ../HumanEvalPython/original/id_116.py

### Original Code
```python
# id_116.py

def sort_array(arr):
    """
    In this Kata, you have to sort an array of non-negative integers according to
    number of ones in their binary representation in ascending order.
    For similar number of ones, sort based on decimal value.

    It must be implemented like this:
    >>> sort_array([1, 5, 2, 3, 4]) == [1, 2, 3, 4, 5]
    >>> sort_array([-2, -3, -4, -5, -6]) == [-6, -5, -4, -3, -2]
    >>> sort_array([1, 0, 2, 3, 4]) [0, 1, 2, 3, 4]
    """

    return sorted(sorted(arr), key=lambda x: bin(x)[2:].count('1'))

```

### Test Prompt
```python
# id_116_Test.java
from original.id_116 import sort_array

import pytest

class id_116_Test:
    """
    Test class of id_116.py.
    It contains ten unit test cases for the :func:`original.id_116.sort_array`.
    """

```

## ../HumanEvalPython/original/id_147.py

### Original Code
```python
# id_147.py

def get_max_triples(n):
    """
    You are given a positive integer n. You have to create an integer array a of length n.
        For each i (1 ≤ i ≤ n), the value of a[i] = i * i - i + 1.
        Return the number of triples (a[i], a[j], a[k]) of a where i < j < k, 
    and a[i] + a[j] + a[k] is a multiple of 3.

    Example :
        Input: n = 5
        Output: 1
        Explanation: 
        a = [1, 3, 7, 13, 21]
        The only valid triple is (1, 7, 13).
    """

    A = [i*i - i + 1 for i in range(1,n+1)]
    ans = []
    for i in range(n):
        for j in range(i+1,n):
            for k in range(j+1,n):
                if (A[i]+A[j]+A[k])%3 == 0:
                    ans += [(A[i],A[j],A[k])]
    return len(ans)


```

### Test Prompt
```python
# id_147_Test.java
from original.id_147 import get_max_triples

import pytest

class id_147_Test:
    """
    Test class of id_147.py.
    It contains ten unit test cases for the :func:`original.id_147.get_max_triples`.
    """

```

## ../HumanEvalPython/original/id_89.py

### Original Code
```python
# id_89.py

def encrypt(s):
    """Create a function encrypt that takes a string as an argument and
    returns a string encrypted with the alphabet being rotated. 
    The alphabet should be rotated in a manner such that the letters 
    shift down by two multiplied to two places.
    For example:
    encrypt('hi') returns 'lm'
    encrypt('asdfghjkl') returns 'ewhjklnop'
    encrypt('gf') returns 'kj'
    encrypt('et') returns 'ix'
    """

    d = 'abcdefghijklmnopqrstuvwxyz'
    out = ''
    for c in s:
        if c in d:
            out += d[(d.index(c)+2*2) % 26]
        else:
            out += c
    return out

```

### Test Prompt
```python
# id_89_Test.java
from original.id_89 import encrypt

import pytest

class id_89_Test:
    """
    Test class of id_89.py.
    It contains ten unit test cases for the :func:`original.id_89.encrypt`.
    """

```

## ../HumanEvalPython/original/id_98.py

### Original Code
```python
# id_98.py

def count_upper(s):
    """
    Given a string s, count the number of uppercase vowels in even indices.
    
    For example:
    count_upper('aBCdEf') returns 1
    count_upper('abcdefg') returns 0
    count_upper('dBBE') returns 0
    """

    count = 0
    for i in range(0,len(s),2):
        if s[i] in "AEIOU":
            count += 1
    return count

```

### Test Prompt
```python
# id_98_Test.java
from original.id_98 import count_upper

import pytest

class id_98_Test:
    """
    Test class of id_98.py.
    It contains ten unit test cases for the :func:`original.id_98.count_upper`.
    """

```

## ../HumanEvalPython/original/id_156.py

### Original Code
```python
# id_156.py

def int_to_mini_roman(number):
    """
    Given a positive integer, obtain its roman numeral equivalent as a string,
    and return it in lowercase.
    Restrictions: 1 <= num <= 1000

    Examples:
    >>> int_to_mini_roman(19) == 'xix'
    >>> int_to_mini_roman(152) == 'clii'
    >>> int_to_mini_roman(426) == 'cdxxvi'
    """

    num = [1, 4, 5, 9, 10, 40, 50, 90,  
           100, 400, 500, 900, 1000] 
    sym = ["I", "IV", "V", "IX", "X", "XL",  
           "L", "XC", "C", "CD", "D", "CM", "M"] 
    i = 12
    res = ''
    while number: 
        div = number // num[i] 
        number %= num[i] 
        while div: 
            res += sym[i] 
            div -= 1
        i -= 1
    return res.lower()

```

### Test Prompt
```python
# id_156_Test.java
from original.id_156 import int_to_mini_roman

import pytest

class id_156_Test:
    """
    Test class of id_156.py.
    It contains ten unit test cases for the :func:`original.id_156.int_to_mini_roman`.
    """

```

## ../HumanEvalPython/original/id_2.py

### Original Code
```python
# id_2.py


def truncate_number(number: float) -> float:
    """ Given a positive floating point number, it can be decomposed into
    and integer part (largest integer smaller than given number) and decimals
    (leftover part always smaller than 1).

    Return the decimal part of the number.
    >>> truncate_number(3.5)
    0.5
    """

    return number % 1.0

```

### Test Prompt
```python
# id_2_Test.java
from original.id_2 import truncate_number

import pytest

class id_2_Test:
    """
    Test class of id_2.py.
    It contains ten unit test cases for the :func:`original.id_2.truncate_number`.
    """

```

## ../HumanEvalPython/original/id_107.py

### Original Code
```python
# id_107.py

def even_odd_palindrome(n):
    """
    Given a positive integer n, return a tuple that has the number of even and odd
    integer palindromes that fall within the range(1, n), inclusive.

    Example 1:

        Input: 3
        Output: (1, 2)
        Explanation:
        Integer palindrome are 1, 2, 3. one of them is even, and two of them are odd.

    Example 2:

        Input: 12
        Output: (4, 6)
        Explanation:
        Integer palindrome are 1, 2, 3, 4, 5, 6, 7, 8, 9, 11. four of them are even, and 6 of them are odd.

    Note:
        1. 1 <= n <= 10^3
        2. returned tuple has the number of even and odd integer palindromes respectively.
    """

    def is_palindrome(n):
        return str(n) == str(n)[::-1]

    even_palindrome_count = 0
    odd_palindrome_count = 0

    for i in range(1, n+1):
        if i%2 == 1 and is_palindrome(i):
                odd_palindrome_count += 1
        elif i%2 == 0 and is_palindrome(i):
            even_palindrome_count += 1
    return (even_palindrome_count, odd_palindrome_count)


```

### Test Prompt
```python
# id_107_Test.java
from original.id_107 import even_odd_palindrome

import pytest

class id_107_Test:
    """
    Test class of id_107.py.
    It contains ten unit test cases for the :func:`original.id_107.even_odd_palindrome`.
    """

```

## ../HumanEvalPython/original/id_133.py

### Original Code
```python
# id_133.py


def sum_squares(lst):
    """You are given a list of numbers.
    You need to return the sum of squared numbers in the given list,
    round each element in the list to the upper int(Ceiling) first.
    Examples:
    For lst = [1,2,3] the output should be 14
    For lst = [1,4,9] the output should be 98
    For lst = [1,3,5,7] the output should be 84
    For lst = [1.4,4.2,0] the output should be 29
    For lst = [-2.4,1,1] the output should be 6
    

    """

    import math
    squared = 0
    for i in lst:
        squared += math.ceil(i)**2
    return squared

```

### Test Prompt
```python
# id_133_Test.java
from original.id_133 import sum_squares

import pytest

class id_133_Test:
    """
    Test class of id_133.py.
    It contains ten unit test cases for the :func:`original.id_133.sum_squares`.
    """

```

## ../HumanEvalPython/original/id_162.py

### Original Code
```python
# id_162.py

def string_to_md5(text):
    """
    Given a string 'text', return its md5 hash equivalent string.
    If 'text' is an empty string, return None.

    >>> string_to_md5('Hello world') == '3e25960a79dbc69b674cd4ec67a72c62'
    """

    import hashlib
    return hashlib.md5(text.encode('ascii')).hexdigest() if text else None

```

### Test Prompt
```python
# id_162_Test.java
from original.id_162 import string_to_md5

import pytest

class id_162_Test:
    """
    Test class of id_162.py.
    It contains ten unit test cases for the :func:`original.id_162.string_to_md5`.
    """

```

## ../HumanEvalPython/original/id_123.py

### Original Code
```python
# id_123.py

def get_odd_collatz(n):
    """
    Given a positive integer n, return a sorted list that has the odd numbers in collatz sequence.

    The Collatz conjecture is a conjecture in mathematics that concerns a sequence defined
    as follows: start with any positive integer n. Then each term is obtained from the 
    previous term as follows: if the previous term is even, the next term is one half of 
    the previous term. If the previous term is odd, the next term is 3 times the previous
    term plus 1. The conjecture is that no matter what value of n, the sequence will always reach 1.

    Note: 
        1. Collatz(1) is [1].
        2. returned list sorted in increasing order.

    For example:
    get_odd_collatz(5) returns [1, 5] # The collatz sequence for 5 is [5, 16, 8, 4, 2, 1], so the odd numbers are only 1, and 5.
    """

    if n%2==0:
        odd_collatz = [] 
    else:
        odd_collatz = [n]
    while n > 1:
        if n % 2 == 0:
            n = n/2
        else:
            n = n*3 + 1
            
        if n%2 == 1:
            odd_collatz.append(int(n))

    return sorted(odd_collatz)

```

### Test Prompt
```python
# id_123_Test.java
from original.id_123 import get_odd_collatz

import pytest

class id_123_Test:
    """
    Test class of id_123.py.
    It contains ten unit test cases for the :func:`original.id_123.get_odd_collatz`.
    """

```

## ../HumanEvalPython/original/id_117.py

### Original Code
```python
# id_117.py

def select_words(s, n):
    """Given a string s and a natural number n, you have been tasked to implement 
    a function that returns a list of all words from string s that contain exactly 
    n consonants, in order these words appear in the string s.
    If the string s is empty then the function should return an empty list.
    Note: you may assume the input string contains only letters and spaces.
    Examples:
    select_words("Mary had a little lamb", 4) ==> ["little"]
    select_words("Mary had a little lamb", 3) ==> ["Mary", "lamb"]
    select_words("simple white space", 2) ==> []
    select_words("Hello world", 4) ==> ["world"]
    select_words("Uncle sam", 3) ==> ["Uncle"]
    """

    result = []
    for word in s.split():
        n_consonants = 0
        for i in range(0, len(word)):
            if word[i].lower() not in ["a","e","i","o","u"]:
                n_consonants += 1 
        if n_consonants == n:
            result.append(word)
    return result


```

### Test Prompt
```python
# id_117_Test.java
from original.id_117 import select_words

import pytest

class id_117_Test:
    """
    Test class of id_117.py.
    It contains ten unit test cases for the :func:`original.id_117.select_words`.
    """

```

## ../HumanEvalPython/original/id_146.py

### Original Code
```python
# id_146.py

def specialFilter(nums):
    """Write a function that takes an array of numbers as input and returns 
    the number of elements in the array that are greater than 10 and both 
    first and last digits of a number are odd (1, 3, 5, 7, 9).
    For example:
    specialFilter([15, -73, 14, -15]) => 1 
    specialFilter([33, -2, -3, 45, 21, 109]) => 2
    """

    
    count = 0
    for num in nums:
        if num > 10:
            odd_digits = (1, 3, 5, 7, 9)
            number_as_string = str(num)
            if int(number_as_string[0]) in odd_digits and int(number_as_string[-1]) in odd_digits:
                count += 1
        
    return count 

```

### Test Prompt
```python
# id_146_Test.java
from original.id_146 import specialFilter

import pytest

class id_146_Test:
    """
    Test class of id_146.py.
    It contains ten unit test cases for the :func:`original.id_146.specialFilter`.
    """

```

## ../HumanEvalPython/original/id_88.py

### Original Code
```python
# id_88.py

def sort_array(array):
    """
    Given an array of non-negative integers, return a copy of the given array after sorting,
    you will sort the given array in ascending order if the sum( first index value, last index value) is odd,
    or sort it in descending order if the sum( first index value, last index value) is even.

    Note:
    * don't change the given array.

    Examples:
    * sort_array([]) => []
    * sort_array([5]) => [5]
    * sort_array([2, 4, 3, 0, 1, 5]) => [0, 1, 2, 3, 4, 5]
    * sort_array([2, 4, 3, 0, 1, 5, 6]) => [6, 5, 4, 3, 2, 1, 0]
    """

    return [] if len(array) == 0 else sorted(array, reverse= (array[0]+array[-1]) % 2 == 0) 

```

### Test Prompt
```python
# id_88_Test.java
from original.id_88 import sort_array

import pytest

class id_88_Test:
    """
    Test class of id_88.py.
    It contains ten unit test cases for the :func:`original.id_88.sort_array`.
    """

```

## ../HumanEvalPython/original/id_137.py

### Original Code
```python
# id_137.py

def compare_one(a, b):
    """
    Create a function that takes integers, floats, or strings representing
    real numbers, and returns the larger variable in its given variable type.
    Return None if the values are equal.
    Note: If a real number is represented as a string, the floating point might be . or ,

    compare_one(1, 2.5) ➞ 2.5
    compare_one(1, "2,3") ➞ "2,3"
    compare_one("5,1", "6") ➞ "6"
    compare_one("1", 1) ➞ None
    """

    temp_a, temp_b = a, b
    if isinstance(temp_a, str): temp_a = temp_a.replace(',','.')
    if isinstance(temp_b, str): temp_b = temp_b.replace(',','.')
    if float(temp_a) == float(temp_b): return None
    return a if float(temp_a) > float(temp_b) else b 

```

### Test Prompt
```python
# id_137_Test.java
from original.id_137 import compare_one

import pytest

class id_137_Test:
    """
    Test class of id_137.py.
    It contains ten unit test cases for the :func:`original.id_137.compare_one`.
    """

```

## ../HumanEvalPython/original/id_103.py

### Original Code
```python
# id_103.py

def rounded_avg(n, m):
    """You are given two positive integers n and m, and your task is to compute the
    average of the integers from n through m (including n and m). 
    Round the answer to the nearest integer and convert that to binary.
    If n is greater than m, return -1.
    Example:
    rounded_avg(1, 5) => "0b11"
    rounded_avg(7, 5) => -1
    rounded_avg(10, 20) => "0b1111"
    rounded_avg(20, 33) => "0b11010"
    """

    if m < n:
        return -1
    summation = 0
    for i in range(n, m+1):
        summation += i
    return bin(round(summation/(m - n + 1)))


```

### Test Prompt
```python
# id_103_Test.java
from original.id_103 import rounded_avg

import pytest

class id_103_Test:
    """
    Test class of id_103.py.
    It contains ten unit test cases for the :func:`original.id_103.rounded_avg`.
    """

```

## ../HumanEvalPython/original/id_152.py

### Original Code
```python
# id_152.py

def compare(game,guess):
    """I think we all remember that feeling when the result of some long-awaited
    event is finally known. The feelings and thoughts you have at that moment are
    definitely worth noting down and comparing.
    Your task is to determine if a person correctly guessed the results of a number of matches.
    You are given two arrays of scores and guesses of equal length, where each index shows a match. 
    Return an array of the same length denoting how far off each guess was. If they have guessed correctly,
    the value is 0, and if not, the value is the absolute difference between the guess and the score.
    
    
    example:

    compare([1,2,3,4,5,1],[1,2,3,4,2,-2]) -> [0,0,0,0,3,3]
    compare([0,5,0,0,0,4],[4,1,1,0,0,-2]) -> [4,4,1,0,0,6]
    """

    return [abs(x-y) for x,y in zip(game,guess)]

```

### Test Prompt
```python
# id_152_Test.java
from original.id_152 import compare

import pytest

class id_152_Test:
    """
    Test class of id_152.py.
    It contains ten unit test cases for the :func:`original.id_152.compare`.
    """

```

## ../HumanEvalPython/original/id_6.py

### Original Code
```python
# id_6.py
from typing import List


def parse_nested_parens(paren_string: str) -> List[int]:
    """ Input to this function is a string represented multiple groups for nested parentheses separated by spaces.
    For each of the group, output the deepest level of nesting of parentheses.
    E.g. (()()) has maximum two levels of nesting while ((())) has three.

    >>> parse_nested_parens('(()()) ((())) () ((())()())')
    [2, 3, 1, 3]
    """

    def parse_paren_group(s):
        depth = 0
        max_depth = 0
        for c in s:
            if c == '(':
                depth += 1
                max_depth = max(depth, max_depth)
            else:
                depth -= 1

        return max_depth

    return [parse_paren_group(x) for x in paren_string.split(' ') if x]

```

### Test Prompt
```python
# id_6_Test.java
from original.id_6 import parse_nested_parens

import pytest

class id_6_Test:
    """
    Test class of id_6.py.
    It contains ten unit test cases for the :func:`original.id_6.parse_nested_parens`.
    """

```

## ../HumanEvalPython/original/id_142.py

### Original Code
```python
# id_142.py



def sum_squares(lst):
    """"
    This function will take a list of integers. For all entries in the list, the function shall square the integer entry if its index is a 
    multiple of 3 and will cube the integer entry if its index is a multiple of 4 and not a multiple of 3. The function will not 
    change the entries in the list whose indexes are not a multiple of 3 or 4. The function shall then return the sum of all entries. 
    
    Examples:
    For lst = [1,2,3] the output should be 6
    For lst = []  the output should be 0
    For lst = [-1,-5,2,-1,-5]  the output should be -126
    """

    result =[]
    for i in range(len(lst)):
        if i %3 == 0:
            result.append(lst[i]**2)
        elif i % 4 == 0 and i%3 != 0:
            result.append(lst[i]**3)
        else:
            result.append(lst[i])
    return sum(result)

```

### Test Prompt
```python
# id_142_Test.java
from original.id_142 import sum_squares

import pytest

class id_142_Test:
    """
    Test class of id_142.py.
    It contains ten unit test cases for the :func:`original.id_142.sum_squares`.
    """

```

## ../HumanEvalPython/original/id_113.py

### Original Code
```python
# id_113.py

def odd_count(lst):
    """Given a list of strings, where each string consists of only digits, return a list.
    Each element i of the output should be "the number of odd elements in the
    string i of the input." where all the i's should be replaced by the number
    of odd digits in the i'th string of the input.

    >>> odd_count(['1234567'])
    ["the number of odd elements 4n the str4ng 4 of the 4nput."]
    >>> odd_count(['3',"11111111"])
    ["the number of odd elements 1n the str1ng 1 of the 1nput.",
     "the number of odd elements 8n the str8ng 8 of the 8nput."]
    """

    res = []
    for arr in lst:
        n = sum(int(d)%2==1 for d in arr)
        res.append("the number of odd elements " + str(n) + "n the str"+ str(n) +"ng "+ str(n) +" of the "+ str(n) +"nput.")
    return res

```

### Test Prompt
```python
# id_113_Test.java
from original.id_113 import odd_count

import pytest

class id_113_Test:
    """
    Test class of id_113.py.
    It contains ten unit test cases for the :func:`original.id_113.odd_count`.
    """

```

## ../HumanEvalPython/original/id_127.py

### Original Code
```python
# id_127.py

def intersection(interval1, interval2):
    """You are given two intervals,
    where each interval is a pair of integers. For example, interval = (start, end) = (1, 2).
    The given intervals are closed which means that the interval (start, end)
    includes both start and end.
    For each given interval, it is assumed that its start is less or equal its end.
    Your task is to determine whether the length of intersection of these two 
    intervals is a prime number.
    Example, the intersection of the intervals (1, 3), (2, 4) is (2, 3)
    which its length is 1, which not a prime number.
    If the length of the intersection is a prime number, return "YES",
    otherwise, return "NO".
    If the two intervals don't intersect, return "NO".


    [input/output] samples:
    intersection((1, 2), (2, 3)) ==> "NO"
    intersection((-1, 1), (0, 4)) ==> "NO"
    intersection((-3, -1), (-5, 5)) ==> "YES"
    """

    def is_prime(num):
        if num == 1 or num == 0:
            return False
        if num == 2:
            return True
        for i in range(2, num):
            if num%i == 0:
                return False
        return True

    l = max(interval1[0], interval2[0])
    r = min(interval1[1], interval2[1])
    length = r - l
    if length > 0 and is_prime(length):
        return "YES"
    return "NO"

```

### Test Prompt
```python
# id_127_Test.java
from original.id_127 import intersection

import pytest

class id_127_Test:
    """
    Test class of id_127.py.
    It contains ten unit test cases for the :func:`original.id_127.intersection`.
    """

```

## ../HumanEvalPython/original/id_104.py

### Original Code
```python
# id_104.py

def unique_digits(x):
    """Given a list of positive integers x. return a sorted list of all 
    elements that hasn't any even digit.

    Note: Returned list should be sorted in increasing order.
    
    For example:
    >>> unique_digits([15, 33, 1422, 1])
    [1, 15, 33]
    >>> unique_digits([152, 323, 1422, 10])
    []
    """

    odd_digit_elements = []
    for i in x:
        if all (int(c) % 2 == 1 for c in str(i)):
            odd_digit_elements.append(i)
    return sorted(odd_digit_elements)

```

### Test Prompt
```python
# id_104_Test.java
from original.id_104 import unique_digits

import pytest

class id_104_Test:
    """
    Test class of id_104.py.
    It contains ten unit test cases for the :func:`original.id_104.unique_digits`.
    """

```

## ../HumanEvalPython/original/id_68.py

### Original Code
```python
# id_68.py

def pluck(arr):
    """
    "Given an array representing a branch of a tree that has non-negative integer nodes
    your task is to pluck one of the nodes and return it.
    The plucked node should be the node with the smallest even value.
    If multiple nodes with the same smallest even value are found return the node that has smallest index.

    The plucked node should be returned in a list, [ smalest_value, its index ],
    If there are no even values or the given array is empty, return [].

    Example 1:
        Input: [4,2,3]
        Output: [2, 1]
        Explanation: 2 has the smallest even value, and 2 has the smallest index.

    Example 2:
        Input: [1,2,3]
        Output: [2, 1]
        Explanation: 2 has the smallest even value, and 2 has the smallest index. 

    Example 3:
        Input: []
        Output: []
    
    Example 4:
        Input: [5, 0, 3, 0, 4, 2]
        Output: [0, 1]
        Explanation: 0 is the smallest value, but  there are two zeros,
                     so we will choose the first zero, which has the smallest index.

    Constraints:
        * 1 <= nodes.length <= 10000
        * 0 <= node.value
    """

    if(len(arr) == 0): return []
    evens = list(filter(lambda x: x%2 == 0, arr))
    if(evens == []): return []
    return [min(evens), arr.index(min(evens))]

```

### Test Prompt
```python
# id_68_Test.java
from original.id_68 import pluck

import pytest

class id_68_Test:
    """
    Test class of id_68.py.
    It contains ten unit test cases for the :func:`original.id_68.pluck`.
    """

```

## ../HumanEvalPython/original/id_155.py

### Original Code
```python
# id_155.py

def even_odd_count(num):
    """Given an integer. return a tuple that has the number of even and odd digits respectively.

     Example:
        even_odd_count(-12) ==> (1, 1)
        even_odd_count(123) ==> (1, 2)
    """

    even_count = 0
    odd_count = 0
    for i in str(abs(num)):
        if int(i)%2==0:
            even_count +=1
        else:
            odd_count +=1
    return (even_count, odd_count)

```

### Test Prompt
```python
# id_155_Test.java
from original.id_155 import even_odd_count

import pytest

class id_155_Test:
    """
    Test class of id_155.py.
    It contains ten unit test cases for the :func:`original.id_155.even_odd_count`.
    """

```

## ../HumanEvalPython/original/id_1.py

### Original Code
```python
# id_1.py
from typing import List


def separate_paren_groups(paren_string: str) -> List[str]:
    """ Input to this function is a string containing multiple groups of nested parentheses. Your goal is to
    separate those group into separate strings and return the list of those.
    Separate groups are balanced (each open brace is properly closed) and not nested within each other
    Ignore any spaces in the input string.
    >>> separate_paren_groups('( ) (( )) (( )( ))')
    ['()', '(())', '(()())']
    """

    result = []
    current_string = []
    current_depth = 0

    for c in paren_string:
        if c == '(':
            current_depth += 1
            current_string.append(c)
        elif c == ')':
            current_depth -= 1
            current_string.append(c)

            if current_depth == 0:
                result.append(''.join(current_string))
                current_string.clear()

    return result

```

### Test Prompt
```python
# id_1_Test.java
from original.id_1 import separate_paren_groups

import pytest

class id_1_Test:
    """
    Test class of id_1.py.
    It contains ten unit test cases for the :func:`original.id_1.separate_paren_groups`.
    """

```

## ../HumanEvalPython/original/id_39.py

### Original Code
```python
# id_39.py


def prime_fib(n: int):
    """
    prime_fib returns n-th number that is a Fibonacci number and it's also prime.
    >>> prime_fib(1)
    2
    >>> prime_fib(2)
    3
    >>> prime_fib(3)
    5
    >>> prime_fib(4)
    13
    >>> prime_fib(5)
    89
    """

    import math

    def is_prime(p):
        if p < 2:
            return False
        for k in range(2, min(int(math.sqrt(p)) + 1, p - 1)):
            if p % k == 0:
                return False
        return True
    f = [0, 1]
    while True:
        f.append(f[-1] + f[-2])
        if is_prime(f[-1]):
            n -= 1
        if n == 0:
            return f[-1]


```

### Test Prompt
```python
# id_39_Test.java
from original.id_39 import prime_fib

import pytest

class id_39_Test:
    """
    Test class of id_39.py.
    It contains ten unit test cases for the :func:`original.id_39.prime_fib`.
    """

```

## ../HumanEvalPython/original/id_161.py

### Original Code
```python
# id_161.py

def solve(s):
    """You are given a string s.
    if s[i] is a letter, reverse its case from lower to upper or vise versa, 
    otherwise keep it as it is.
    If the string contains no letters, reverse the string.
    The function should return the resulted string.
    Examples
    solve("1234") = "4321"
    solve("ab") = "AB"
    solve("#a@C") = "#A@c"
    """

    flg = 0
    idx = 0
    new_str = list(s)
    for i in s:
        if i.isalpha():
            new_str[idx] = i.swapcase()
            flg = 1
        idx += 1
    s = ""
    for i in new_str:
        s += i
    if flg == 0:
        return s[len(s)::-1]
    return s

```

### Test Prompt
```python
# id_161_Test.java
from original.id_161 import solve

import pytest

class id_161_Test:
    """
    Test class of id_161.py.
    It contains ten unit test cases for the :func:`original.id_161.solve`.
    """

```

## ../HumanEvalPython/original/id_130.py

### Original Code
```python
# id_130.py

def tri(n):
    """Everyone knows Fibonacci sequence, it was studied deeply by mathematicians in 
    the last couple centuries. However, what people don't know is Tribonacci sequence.
    Tribonacci sequence is defined by the recurrence:
    tri(1) = 3
    tri(n) = 1 + n / 2, if n is even.
    tri(n) =  tri(n - 1) + tri(n - 2) + tri(n + 1), if n is odd.
    For example:
    tri(2) = 1 + (2 / 2) = 2
    tri(4) = 3
    tri(3) = tri(2) + tri(1) + tri(4)
           = 2 + 3 + 3 = 8 
    You are given a non-negative integer number n, you have to a return a list of the 
    first n + 1 numbers of the Tribonacci sequence.
    Examples:
    tri(3) = [1, 3, 2, 8]
    """

    if n == 0:
        return [1]
    my_tri = [1, 3]
    for i in range(2, n + 1):
        if i % 2 == 0:
            my_tri.append(i / 2 + 1)
        else:
            my_tri.append(my_tri[i - 1] + my_tri[i - 2] + (i + 3) / 2)
    return my_tri

```

### Test Prompt
```python
# id_130_Test.java
from original.id_130 import tri

import pytest

class id_130_Test:
    """
    Test class of id_130.py.
    It contains ten unit test cases for the :func:`original.id_130.tri`.
    """

```

## ../HumanEvalPython/original/id_120.py

### Original Code
```python
# id_120.py

def maximum(arr, k):
    """
    Given an array arr of integers and a positive integer k, return a sorted list 
    of length k with the maximum k numbers in arr.

    Example 1:

        Input: arr = [-3, -4, 5], k = 3
        Output: [-4, -3, 5]

    Example 2:

        Input: arr = [4, -4, 4], k = 2
        Output: [4, 4]

    Example 3:

        Input: arr = [-3, 2, 1, 2, -1, -2, 1], k = 1
        Output: [2]

    Note:
        1. The length of the array will be in the range of [1, 1000].
        2. The elements in the array will be in the range of [-1000, 1000].
        3. 0 <= k <= len(arr)
    """

    if k == 0:
        return []
    arr.sort()
    ans = arr[-k:]
    return ans

```

### Test Prompt
```python
# id_120_Test.java
from original.id_120 import maximum

import pytest

class id_120_Test:
    """
    Test class of id_120.py.
    It contains ten unit test cases for the :func:`original.id_120.maximum`.
    """

```

## ../HumanEvalPython/original/id_29.py

### Original Code
```python
# id_29.py
from typing import List


def filter_by_prefix(strings: List[str], prefix: str) -> List[str]:
    """ Filter an input list of strings only for ones that start with a given prefix.
    >>> filter_by_prefix([], 'a')
    []
    >>> filter_by_prefix(['abc', 'bcd', 'cde', 'array'], 'a')
    ['abc', 'array']
    """

    return [x for x in strings if x.startswith(prefix)]

```

### Test Prompt
```python
# id_29_Test.java
from original.id_29 import filter_by_prefix

import pytest

class id_29_Test:
    """
    Test class of id_29.py.
    It contains ten unit test cases for the :func:`original.id_29.filter_by_prefix`.
    """

```

## ../HumanEvalPython/original/id_145.py

### Original Code
```python
# id_145.py

def order_by_points(nums):
    """
    Write a function which sorts the given list of integers
    in ascending order according to the sum of their digits.
    Note: if there are several items with similar sum of their digits,
    order them based on their index in original list.

    For example:
    >>> order_by_points([1, 11, -1, -11, -12]) == [-1, -11, 1, -12, 11]
    >>> order_by_points([]) == []
    """

    def digits_sum(n):
        neg = 1
        if n < 0: n, neg = -1 * n, -1 
        n = [int(i) for i in str(n)]
        n[0] = n[0] * neg
        return sum(n)
    return sorted(nums, key=digits_sum)

```

### Test Prompt
```python
# id_145_Test.java
from original.id_145 import order_by_points

import pytest

class id_145_Test:
    """
    Test class of id_145.py.
    It contains ten unit test cases for the :func:`original.id_145.order_by_points`.
    """

```

## ../HumanEvalPython/original/id_78.py

### Original Code
```python
# id_78.py

def hex_key(num):
    """You have been tasked to write a function that receives 
    a hexadecimal number as a string and counts the number of hexadecimal 
    digits that are primes (prime number, or a prime, is a natural number 
    greater than 1 that is not a product of two smaller natural numbers).
    Hexadecimal digits are 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F.
    Prime numbers are 2, 3, 5, 7, 11, 13, 17,...
    So you have to determine a number of the following digits: 2, 3, 5, 7, 
    B (=decimal 11), D (=decimal 13).
    Note: you may assume the input is always correct or empty string, 
    and symbols A,B,C,D,E,F are always uppercase.
    Examples:
    For num = "AB" the output should be 1.
    For num = "1077E" the output should be 2.
    For num = "ABED1A33" the output should be 4.
    For num = "123456789ABCDEF0" the output should be 6.
    For num = "2020" the output should be 2.
    """

    primes = ('2', '3', '5', '7', 'B', 'D')
    total = 0
    for i in range(0, len(num)):
        if num[i] in primes:
            total += 1
    return total

```

### Test Prompt
```python
# id_78_Test.java
from original.id_78 import hex_key

import pytest

class id_78_Test:
    """
    Test class of id_78.py.
    It contains ten unit test cases for the :func:`original.id_78.hex_key`.
    """

```

## ../HumanEvalPython/original/id_114.py

### Original Code
```python
# id_114.py

def minSubArraySum(nums):
    """
    Given an array of integers nums, find the minimum sum of any non-empty sub-array
    of nums.
    Example
    minSubArraySum([2, 3, 4, 1, 2, 4]) == 1
    minSubArraySum([-1, -2, -3]) == -6
    """

    max_sum = 0
    s = 0
    for num in nums:
        s += -num
        if (s < 0):
            s = 0
        max_sum = max(s, max_sum)
    if max_sum == 0:
        max_sum = max(-i for i in nums)
    min_sum = -max_sum
    return min_sum

```

### Test Prompt
```python
# id_114_Test.java
from original.id_114 import minSubArraySum

import pytest

class id_114_Test:
    """
    Test class of id_114.py.
    It contains ten unit test cases for the :func:`original.id_114.minSubArraySum`.
    """

```

## ../HumanEvalPython/original/id_58.py

### Original Code
```python
# id_58.py


def common(l1: list, l2: list):
    """Return sorted unique common elements for two lists.
    >>> common([1, 4, 3, 34, 653, 2, 5], [5, 7, 1, 5, 9, 653, 121])
    [1, 5, 653]
    >>> common([5, 3, 2, 8], [3, 2])
    [2, 3]

    """

    ret = set()
    for e1 in l1:
        for e2 in l2:
            if e1 == e2:
                ret.add(e1)
    return sorted(list(ret))


```

### Test Prompt
```python
# id_58_Test.java
from original.id_58 import common

import pytest

class id_58_Test:
    """
    Test class of id_58.py.
    It contains ten unit test cases for the :func:`original.id_58.common`.
    """

```

## ../HumanEvalPython/original/id_134.py

### Original Code
```python
# id_134.py

def check_if_last_char_is_a_letter(txt):
    '''
    Create a function that returns True if the last character
    of a given string is an alphabetical character and is not
    a part of a word, and False otherwise.
    Note: "word" is a group of characters separated by space.

    Examples:
    check_if_last_char_is_a_letter("apple pie") ➞ False
    check_if_last_char_is_a_letter("apple pi e") ➞ True
    check_if_last_char_is_a_letter("apple pi e ") ➞ False
    check_if_last_char_is_a_letter("") ➞ False 
    '''

 
    check = txt.split(' ')[-1]
    return True if len(check) == 1 and (97 <= ord(check.lower()) <= 122) else False

```

### Test Prompt
```python
# id_134_Test.java
from original.id_134 import check_if_last_char_is_a_letter

import pytest

class id_134_Test:
    """
    Test class of id_134.py.
    It contains ten unit test cases for the :func:`original.id_134.check_if_last_char_is_a_letter`.
    """

```

## ../HumanEvalPython/original/id_151.py

### Original Code
```python
# id_151.py

def double_the_difference(lst):
    '''
    Given a list of numbers, return the sum of squares of the numbers
    in the list that are odd. Ignore numbers that are negative or not integers.
    
    double_the_difference([1, 3, 2, 0]) == 1 + 9 + 0 + 0 = 10
    double_the_difference([-1, -2, 0]) == 0
    double_the_difference([9, -2]) == 81
    double_the_difference([0]) == 0  
   
    If the input list is empty, return 0.
    '''

    return sum([i**2 for i in lst if i > 0 and i%2!=0 and "." not in str(i)])

```

### Test Prompt
```python
# id_151_Test.java
from original.id_151 import double_the_difference

import pytest

class id_151_Test:
    """
    Test class of id_151.py.
    It contains ten unit test cases for the :func:`original.id_151.double_the_difference`.
    """

```

## ../HumanEvalPython/original/id_5.py

### Original Code
```python
# id_5.py
from typing import List


def intersperse(numbers: List[int], delimeter: int) -> List[int]:
    """ Insert a number 'delimeter' between every two consecutive elements of input list `numbers'
    >>> intersperse([], 4)
    []
    >>> intersperse([1, 2, 3], 4)
    [1, 4, 2, 4, 3]
    """

    if not numbers:
        return []

    result = []

    for n in numbers[:-1]:
        result.append(n)
        result.append(delimeter)

    result.append(numbers[-1])

    return result

```

### Test Prompt
```python
# id_5_Test.java
from original.id_5 import intersperse

import pytest

class id_5_Test:
    """
    Test class of id_5.py.
    It contains ten unit test cases for the :func:`original.id_5.intersperse`.
    """

```

## ../HumanEvalPython/original/id_100.py

### Original Code
```python
# id_100.py

def make_a_pile(n):
    """
    Given a positive integer n, you have to make a pile of n levels of stones.
    The first level has n stones.
    The number of stones in the next level is:
        - the next odd number if n is odd.
        - the next even number if n is even.
    Return the number of stones in each level in a list, where element at index
    i represents the number of stones in the level (i+1).

    Examples:
    >>> make_a_pile(3)
    [3, 5, 7]
    """

    return [n + 2*i for i in range(n)]

```

### Test Prompt
```python
# id_100_Test.java
from original.id_100 import make_a_pile

import pytest

class id_100_Test:
    """
    Test class of id_100.py.
    It contains ten unit test cases for the :func:`original.id_100.make_a_pile`.
    """

```

## ../HumanEvalPython/original/id_110.py

### Original Code
```python
# id_110.py

def exchange(lst1, lst2):
    """In this problem, you will implement a function that takes two lists of numbers,
    and determines whether it is possible to perform an exchange of elements
    between them to make lst1 a list of only even numbers.
    There is no limit on the number of exchanged elements between lst1 and lst2.
    If it is possible to exchange elements between the lst1 and lst2 to make
    all the elements of lst1 to be even, return "YES".
    Otherwise, return "NO".
    For example:
    exchange([1, 2, 3, 4], [1, 2, 3, 4]) => "YES"
    exchange([1, 2, 3, 4], [1, 5, 3, 4]) => "NO"
    It is assumed that the input lists will be non-empty.
    """

    odd = 0
    even = 0
    for i in lst1:
        if i%2 == 1:
            odd += 1
    for i in lst2:
        if i%2 == 0:
            even += 1
    if even >= odd:
        return "YES"
    return "NO"
            

```

### Test Prompt
```python
# id_110_Test.java
from original.id_110 import exchange

import pytest

class id_110_Test:
    """
    Test class of id_110.py.
    It contains ten unit test cases for the :func:`original.id_110.exchange`.
    """

```

## ../HumanEvalPython/original/id_141.py

### Original Code
```python
# id_141.py

def file_name_check(file_name):
    """Create a function which takes a string representing a file's name, and returns
    'Yes' if the the file's name is valid, and returns 'No' otherwise.
    A file's name is considered to be valid if and only if all the following conditions 
    are met:
    - There should not be more than three digits ('0'-'9') in the file's name.
    - The file's name contains exactly one dot '.'
    - The substring before the dot should not be empty, and it starts with a letter from 
    the latin alphapet ('a'-'z' and 'A'-'Z').
    - The substring after the dot should be one of these: ['txt', 'exe', 'dll']
    Examples:
    file_name_check("example.txt") # => 'Yes'
    file_name_check("1example.dll") # => 'No' (the name should start with a latin alphapet letter)
    """

    suf = ['txt', 'exe', 'dll']
    lst = file_name.split(sep='.')
    if len(lst) != 2:
        return 'No'
    if not lst[1] in suf:
        return 'No'
    if len(lst[0]) == 0:
        return 'No'
    if not lst[0][0].isalpha():
        return 'No'
    t = len([x for x in lst[0] if x.isdigit()])
    if t > 3:
        return 'No'
    return 'Yes'

```

### Test Prompt
```python
# id_141_Test.java
from original.id_141 import file_name_check

import pytest

class id_141_Test:
    """
    Test class of id_141.py.
    It contains ten unit test cases for the :func:`original.id_141.file_name_check`.
    """

```

## ../HumanEvalPython/original/id_19.py

### Original Code
```python
# id_19.py
from typing import List


def sort_numbers(numbers: str) -> str:
    """ Input is a space-delimited string of numberals from 'zero' to 'nine'.
    Valid choices are 'zero', 'one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight' and 'nine'.
    Return the string with numbers sorted from smallest to largest
    >>> sort_numbers('three one five')
    'one three five'
    """

    value_map = {
        'zero': 0,
        'one': 1,
        'two': 2,
        'three': 3,
        'four': 4,
        'five': 5,
        'six': 6,
        'seven': 7,
        'eight': 8,
        'nine': 9
    }
    return ' '.join(sorted([x for x in numbers.split(' ') if x], key=lambda x: value_map[x]))

```

### Test Prompt
```python
# id_19_Test.java
from original.id_19 import sort_numbers

import pytest

class id_19_Test:
    """
    Test class of id_19.py.
    It contains ten unit test cases for the :func:`original.id_19.sort_numbers`.
    """

```

## ../HumanEvalPython/original/id_124.py

### Original Code
```python
# id_124.py

def valid_date(date):
    """You have to write a function which validates a given date string and
    returns True if the date is valid otherwise False.
    The date is valid if all of the following rules are satisfied:
    1. The date string is not empty.
    2. The number of days is not less than 1 or higher than 31 days for months 1,3,5,7,8,10,12. And the number of days is not less than 1 or higher than 30 days for months 4,6,9,11. And, the number of days is not less than 1 or higher than 29 for the month 2.
    3. The months should not be less than 1 or higher than 12.
    4. The date should be in the format: mm-dd-yyyy

    for example: 
    valid_date('03-11-2000') => True

    valid_date('15-01-2012') => False

    valid_date('04-0-2040') => False

    valid_date('06-04-2020') => True

    valid_date('06/04/2020') => False
    """

    try:
        date = date.strip()
        month, day, year = date.split('-')
        month, day, year = int(month), int(day), int(year)
        if month < 1 or month > 12:
            return False
        if month in [1,3,5,7,8,10,12] and day < 1 or day > 31:
            return False
        if month in [4,6,9,11] and day < 1 or day > 30:
            return False
        if month == 2 and day < 1 or day > 29:
            return False
    except:
        return False

    return True

```

### Test Prompt
```python
# id_124_Test.java
from original.id_124 import valid_date

import pytest

class id_124_Test:
    """
    Test class of id_124.py.
    It contains ten unit test cases for the :func:`original.id_124.valid_date`.
    """

```

## ../HumanEvalPython/original/id_48.py

### Original Code
```python
# id_48.py


def is_palindrome(text: str):
    """
    Checks if given string is a palindrome
    >>> is_palindrome('')
    True
    >>> is_palindrome('aba')
    True
    >>> is_palindrome('aaaaa')
    True
    >>> is_palindrome('zbcd')
    False
    """

    for i in range(len(text)):
        if text[i] != text[len(text) - 1 - i]:
            return False
    return True

```

### Test Prompt
```python
# id_48_Test.java
from original.id_48 import is_palindrome

import pytest

class id_48_Test:
    """
    Test class of id_48.py.
    It contains ten unit test cases for the :func:`original.id_48.is_palindrome`.
    """

```

## ../HumanEvalPython/original/id_59.py

### Original Code
```python
# id_59.py


def largest_prime_factor(n: int):
    """Return the largest prime factor of n. Assume n > 1 and is not a prime.
    >>> largest_prime_factor(13195)
    29
    >>> largest_prime_factor(2048)
    2
    """

    def is_prime(k):
        if k < 2:
            return False
        for i in range(2, k - 1):
            if k % i == 0:
                return False
        return True
    largest = 1
    for j in range(2, n + 1):
        if n % j == 0 and is_prime(j):
            largest = max(largest, j)
    return largest

```

### Test Prompt
```python
# id_59_Test.java
from original.id_59 import largest_prime_factor

import pytest

class id_59_Test:
    """
    Test class of id_59.py.
    It contains ten unit test cases for the :func:`original.id_59.largest_prime_factor`.
    """

```

## ../HumanEvalPython/original/id_135.py

### Original Code
```python
# id_135.py

def can_arrange(arr):
    """Create a function which returns the largest index of an element which
    is not greater than or equal to the element immediately preceding it. If
    no such element exists then return -1. The given array will not contain
    duplicate values.

    Examples:
    can_arrange([1,2,4,3,5]) = 3
    can_arrange([1,2,3]) = -1
    """

    ind=-1
    i=1
    while i<len(arr):
      if arr[i]<arr[i-1]:
        ind=i
      i+=1
    return ind

```

### Test Prompt
```python
# id_135_Test.java
from original.id_135 import can_arrange

import pytest

class id_135_Test:
    """
    Test class of id_135.py.
    It contains ten unit test cases for the :func:`original.id_135.can_arrange`.
    """

```

## ../HumanEvalPython/original/id_150.py

### Original Code
```python
# id_150.py

def x_or_y(n, x, y):
    """A simple program which should return the value of x if n is 
    a prime number and should return the value of y otherwise.

    Examples:
    for x_or_y(7, 34, 12) == 34
    for x_or_y(15, 8, 5) == 5
    
    """

    if n == 1:
        return y
    for i in range(2, n):
        if n % i == 0:
            return y
            break
    else:
        return x

```

### Test Prompt
```python
# id_150_Test.java
from original.id_150 import x_or_y

import pytest

class id_150_Test:
    """
    Test class of id_150.py.
    It contains ten unit test cases for the :func:`original.id_150.x_or_y`.
    """

```

## ../HumanEvalPython/original/id_4.py

### Original Code
```python
# id_4.py
from typing import List


def mean_absolute_deviation(numbers: List[float]) -> float:
    """ For a given list of input numbers, calculate Mean Absolute Deviation
    around the mean of this dataset.
    Mean Absolute Deviation is the average absolute difference between each
    element and a centerpoint (mean in this case):
    MAD = average | x - x_mean |
    >>> mean_absolute_deviation([1.0, 2.0, 3.0, 4.0])
    1.0
    """

    mean = sum(numbers) / len(numbers)
    return sum(abs(x - mean) for x in numbers) / len(numbers)

```

### Test Prompt
```python
# id_4_Test.java
from original.id_4 import mean_absolute_deviation

import pytest

class id_4_Test:
    """
    Test class of id_4.py.
    It contains ten unit test cases for the :func:`original.id_4.mean_absolute_deviation`.
    """

```

## ../HumanEvalPython/original/id_101.py

### Original Code
```python
# id_101.py

def words_string(s):
    """
    You will be given a string of words separated by commas or spaces. Your task is
    to split the string into words and return an array of the words.
    
    For example:
    words_string("Hi, my name is John") == ["Hi", "my", "name", "is", "John"]
    words_string("One, two, three, four, five, six") == ["One", "two", "three", "four", "five", "six"]
    """

    if not s:
        return []

    s_list = []

    for letter in s:
        if letter == ',':
            s_list.append(' ')
        else:
            s_list.append(letter)

    s_list = "".join(s_list)
    return s_list.split()


```

### Test Prompt
```python
# id_101_Test.java
from original.id_101 import words_string

import pytest

class id_101_Test:
    """
    Test class of id_101.py.
    It contains ten unit test cases for the :func:`original.id_101.words_string`.
    """

```

## ../HumanEvalPython/original/id_111.py

### Original Code
```python
# id_111.py

def histogram(test):
    """Given a string representing a space separated lowercase letters, return a dictionary
    of the letter with the most repetition and containing the corresponding count.
    If several letters have the same occurrence, return all of them.
    
    Example:
    histogram('a b c') == {'a': 1, 'b': 1, 'c': 1}
    histogram('a b b a') == {'a': 2, 'b': 2}
    histogram('a b c a b') == {'a': 2, 'b': 2}
    histogram('b b b b a') == {'b': 4}
    histogram('') == {}

    """

    dict1={}
    list1=test.split(" ")
    t=0

    for i in list1:
        if(list1.count(i)>t) and i!='':
            t=list1.count(i)
    if t>0:
        for i in list1:
            if(list1.count(i)==t):
                
                dict1[i]=t
    return dict1

```

### Test Prompt
```python
# id_111_Test.java
from original.id_111 import histogram

import pytest

class id_111_Test:
    """
    Test class of id_111.py.
    It contains ten unit test cases for the :func:`original.id_111.histogram`.
    """

```

## ../HumanEvalPython/original/id_140.py

### Original Code
```python
# id_140.py

def fix_spaces(text):
    """
    Given a string text, replace all spaces in it with underscores, 
    and if a string has more than 2 consecutive spaces, 
    then replace all consecutive spaces with - 
    
    fix_spaces("Example") == "Example"
    fix_spaces("Example 1") == "Example_1"
    fix_spaces(" Example 2") == "_Example_2"
    fix_spaces(" Example   3") == "_Example-3"
    """

    new_text = ""
    i = 0
    start, end = 0, 0
    while i < len(text):
        if text[i] == " ":
            end += 1
        else:
            if end - start > 2:
                new_text += "-"+text[i]
            elif end - start > 0:
                new_text += "_"*(end - start)+text[i]
            else:
                new_text += text[i]
            start, end = i+1, i+1
        i+=1
    if end - start > 2:
        new_text += "-"
    elif end - start > 0:
        new_text += "_"
    return new_text

```

### Test Prompt
```python
# id_140_Test.java
from original.id_140 import fix_spaces

import pytest

class id_140_Test:
    """
    Test class of id_140.py.
    It contains ten unit test cases for the :func:`original.id_140.fix_spaces`.
    """

```

## ../HumanEvalPython/original/id_18.py

### Original Code
```python
# id_18.py


def how_many_times(string: str, substring: str) -> int:
    """ Find how many times a given substring can be found in the original string. Count overlaping cases.
    >>> how_many_times('', 'a')
    0
    >>> how_many_times('aaa', 'a')
    3
    >>> how_many_times('aaaa', 'aa')
    3
    """

    times = 0

    for i in range(len(string) - len(substring) + 1):
        if string[i:i+len(substring)] == substring:
            times += 1

    return times

```

### Test Prompt
```python
# id_18_Test.java
from original.id_18 import how_many_times

import pytest

class id_18_Test:
    """
    Test class of id_18.py.
    It contains ten unit test cases for the :func:`original.id_18.how_many_times`.
    """

```

## ../HumanEvalPython/original/id_125.py

### Original Code
```python
# id_125.py

def split_words(txt):
    '''
    Given a string of words, return a list of words split on whitespace, if no whitespaces exists in the text you
    should split on commas ',' if no commas exists you should return the number of lower-case letters with odd order in the
    alphabet, ord('a') = 0, ord('b') = 1, ... ord('z') = 25
    Examples
    split_words("Hello world!") ➞ ["Hello", "world!"]
    split_words("Hello,world!") ➞ ["Hello", "world!"]
    split_words("abcdef") == 3 
    '''

    if " " in txt:
        return txt.split()
    elif "," in txt:
        return txt.replace(',',' ').split()
    else:
        return len([i for i in txt if i.islower() and ord(i)%2 == 0])

```

### Test Prompt
```python
# id_125_Test.java
from original.id_125 import split_words

import pytest

class id_125_Test:
    """
    Test class of id_125.py.
    It contains ten unit test cases for the :func:`original.id_125.split_words`.
    """

```

## ../HumanEvalPython/original/id_49.py

### Original Code
```python
# id_49.py


def modp(n: int, p: int):
    """Return 2^n modulo p (be aware of numerics).
    >>> modp(3, 5)
    3
    >>> modp(1101, 101)
    2
    >>> modp(0, 101)
    1
    >>> modp(3, 11)
    8
    >>> modp(100, 101)
    1
    """

    ret = 1
    for i in range(n):
        ret = (2 * ret) % p
    return ret

```

### Test Prompt
```python
# id_49_Test.java
from original.id_49 import modp

import pytest

class id_49_Test:
    """
    Test class of id_49.py.
    It contains ten unit test cases for the :func:`original.id_49.modp`.
    """

```

## ../HumanEvalPython/original/id_105.py

### Original Code
```python
# id_105.py

def by_length(arr):
    """
    Given an array of integers, sort the integers that are between 1 and 9 inclusive,
    reverse the resulting array, and then replace each digit by its corresponding name from
    "One", "Two", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine".

    For example:
      arr = [2, 1, 1, 4, 5, 8, 2, 3]   
            -> sort arr -> [1, 1, 2, 2, 3, 4, 5, 8] 
            -> reverse arr -> [8, 5, 4, 3, 2, 2, 1, 1]
      return ["Eight", "Five", "Four", "Three", "Two", "Two", "One", "One"]
    
      If the array is empty, return an empty array:
      arr = []
      return []
    
      If the array has any strange number ignore it:
      arr = [1, -1 , 55] 
            -> sort arr -> [-1, 1, 55]
            -> reverse arr -> [55, 1, -1]
      return = ['One']
    """

    dic = {
        1: "One",
        2: "Two",
        3: "Three",
        4: "Four",
        5: "Five",
        6: "Six",
        7: "Seven",
        8: "Eight",
        9: "Nine",
    }
    sorted_arr = sorted(arr, reverse=True)
    new_arr = []
    for var in sorted_arr:
        try:
            new_arr.append(dic[var])
        except:
            pass
    return new_arr


```

### Test Prompt
```python
# id_105_Test.java
from original.id_105 import by_length

import pytest

class id_105_Test:
    """
    Test class of id_105.py.
    It contains ten unit test cases for the :func:`original.id_105.by_length`.
    """

```

## ../HumanEvalPython/original/id_69.py

### Original Code
```python
# id_69.py

def search(lst):
    '''
    You are given a non-empty list of positive integers. Return the greatest integer that is greater than 
    zero, and has a frequency greater than or equal to the value of the integer itself. 
    The frequency of an integer is the number of times it appears in the list.
    If no such a value exist, return -1.
    Examples:
        search([4, 1, 2, 2, 3, 1]) == 2
        search([1, 2, 2, 3, 3, 3, 4, 4, 4]) == 3
        search([5, 5, 4, 4, 4]) == -1
    '''

    frq = [0] * (max(lst) + 1)
    for i in lst:
        frq[i] += 1;

    ans = -1
    for i in range(1, len(frq)):
        if frq[i] >= i:
            ans = i
    
    return ans

```

### Test Prompt
```python
# id_69_Test.java
from original.id_69 import search

import pytest

class id_69_Test:
    """
    Test class of id_69.py.
    It contains ten unit test cases for the :func:`original.id_69.search`.
    """

```

## ../HumanEvalPython/original/id_154.py

### Original Code
```python
# id_154.py

def cycpattern_check(a , b):
    """You are given 2 words. You need to return True if the second word or any of its rotations is a substring in the first word
    cycpattern_check("abcd","abd") => False
    cycpattern_check("hello","ell") => True
    cycpattern_check("whassup","psus") => False
    cycpattern_check("abab","baa") => True
    cycpattern_check("efef","eeff") => False
    cycpattern_check("himenss","simen") => True

    """

    l = len(b)
    pat = b + b
    for i in range(len(a) - l + 1):
        for j in range(l + 1):
            if a[i:i+l] == pat[j:j+l]:
                return True
    return False

```

### Test Prompt
```python
# id_154_Test.java
from original.id_154 import cycpattern_check

import pytest

class id_154_Test:
    """
    Test class of id_154.py.
    It contains ten unit test cases for the :func:`original.id_154.cycpattern_check`.
    """

```

## ../HumanEvalPython/original/id_38.py

### Original Code
```python
# id_38.py


def encode_cyclic(s: str):
    """
    returns encoded string by cycling groups of three characters.
    """
    # split string to groups. Each of length 3.
    groups = [s[(3 * i):min((3 * i + 3), len(s))] for i in range((len(s) + 2) // 3)]
    # cycle elements in each group. Unless group has fewer elements than 3.
    groups = [(group[1:] + group[0]) if len(group) == 3 else group for group in groups]
    return "".join(groups)


def decode_cyclic(s: str):
    """
    takes as input string encoded with encode_cyclic function. Returns decoded string.
    """

    return encode_cyclic(encode_cyclic(s))

```

### Test Prompt
```python
# id_38_Test.java
from original.id_38 import decode_cyclic

import pytest

class id_38_Test:
    """
    Test class of id_38.py.
    It contains ten unit test cases for the :func:`original.id_38.decode_cyclic`.
    """

```

## ../HumanEvalPython/original/id_0.py

### Original Code
```python
# id_0.py
from typing import List


def has_close_elements(numbers: List[float], threshold: float) -> bool:
    """ Check if in given list of numbers, are any two numbers closer to each other than
    given threshold.
    >>> has_close_elements([1.0, 2.0, 3.0], 0.5)
    False
    >>> has_close_elements([1.0, 2.8, 3.0, 4.0, 5.0, 2.0], 0.3)
    True
    """

    for idx, elem in enumerate(numbers):
        for idx2, elem2 in enumerate(numbers):
            if idx != idx2:
                distance = abs(elem - elem2)
                if distance < threshold:
                    return True

    return False


```

### Test Prompt
```python
# id_0_Test.java
from original.id_0 import has_close_elements

import pytest

class id_0_Test:
    """
    Test class of id_0.py.
    It contains ten unit test cases for the :func:`original.id_0.has_close_elements`.
    """

```

## ../HumanEvalPython/original/id_160.py

### Original Code
```python
# id_160.py

def do_algebra(operator, operand):
    """
    Given two lists operator, and operand. The first list has basic algebra operations, and 
    the second list is a list of integers. Use the two given lists to build the algebric 
    expression and return the evaluation of this expression.

    The basic algebra operations:
    Addition ( + ) 
    Subtraction ( - ) 
    Multiplication ( * ) 
    Floor division ( // ) 
    Exponentiation ( ** ) 

    Example:
    operator['+', '*', '-']
    array = [2, 3, 4, 5]
    result = 2 + 3 * 4 - 5
    => result = 9

    Note:
        The length of operator list is equal to the length of operand list minus one.
        Operand is a list of of non-negative integers.
        Operator list has at least one operator, and operand list has at least two operands.

    """

    expression = str(operand[0])
    for oprt, oprn in zip(operator, operand[1:]):
        expression+= oprt + str(oprn)
    return eval(expression)

```

### Test Prompt
```python
# id_160_Test.java
from original.id_160 import do_algebra

import pytest

class id_160_Test:
    """
    Test class of id_160.py.
    It contains ten unit test cases for the :func:`original.id_160.do_algebra`.
    """

```

## ../HumanEvalPython/original/id_131.py

### Original Code
```python
# id_131.py

def digits(n):
    """Given a positive integer n, return the product of the odd digits.
    Return 0 if all digits are even.
    For example:
    digits(1)  == 1
    digits(4)  == 0
    digits(235) == 15
    """

    product = 1
    odd_count = 0
    for digit in str(n):
        int_digit = int(digit)
        if int_digit%2 == 1:
            product= product*int_digit
            odd_count+=1
    if odd_count ==0:
        return 0
    else:
        return product

```

### Test Prompt
```python
# id_131_Test.java
from original.id_131 import digits

import pytest

class id_131_Test:
    """
    Test class of id_131.py.
    It contains ten unit test cases for the :func:`original.id_131.digits`.
    """

```

## ../HumanEvalPython/original/id_121.py

### Original Code
```python
# id_121.py

def solution(lst):
    """Given a non-empty list of integers, return the sum of all of the odd elements that are in even positions.
    

    Examples
    solution([5, 8, 7, 1]) ==> 12
    solution([3, 3, 3, 3, 3]) ==> 9
    solution([30, 13, 24, 321]) ==>0
    """

    return sum([x for idx, x in enumerate(lst) if idx%2==0 and x%2==1])

```

### Test Prompt
```python
# id_121_Test.java
from original.id_121 import solution

import pytest

class id_121_Test:
    """
    Test class of id_121.py.
    It contains ten unit test cases for the :func:`original.id_121.solution`.
    """

```

## ../HumanEvalPython/original/id_28.py

### Original Code
```python
# id_28.py
from typing import List


def concatenate(strings: List[str]) -> str:
    """ Concatenate list of strings into a single string
    >>> concatenate([])
    ''
    >>> concatenate(['a', 'b', 'c'])
    'abc'
    """

    return ''.join(strings)

```

### Test Prompt
```python
# id_28_Test.java
from original.id_28 import concatenate

import pytest

class id_28_Test:
    """
    Test class of id_28.py.
    It contains ten unit test cases for the :func:`original.id_28.concatenate`.
    """

```

## ../HumanEvalPython/original/id_144.py

### Original Code
```python
# id_144.py

def simplify(x, n):
    """Your task is to implement a function that will simplify the expression
    x * n. The function returns True if x * n evaluates to a whole number and False
    otherwise. Both x and n, are string representation of a fraction, and have the following format,
    <numerator>/<denominator> where both numerator and denominator are positive whole numbers.

    You can assume that x, and n are valid fractions, and do not have zero as denominator.

    simplify("1/5", "5/1") = True
    simplify("1/6", "2/1") = False
    simplify("7/10", "10/2") = False
    """

    a, b = x.split("/")
    c, d = n.split("/")
    numerator = int(a) * int(c)
    denom = int(b) * int(d)
    if (numerator/denom == int(numerator/denom)):
        return True
    return False

```

### Test Prompt
```python
# id_144_Test.java
from original.id_144 import simplify

import pytest

class id_144_Test:
    """
    Test class of id_144.py.
    It contains ten unit test cases for the :func:`original.id_144.simplify`.
    """

```

## ../HumanEvalPython/original/id_79.py

### Original Code
```python
# id_79.py

def decimal_to_binary(decimal):
    """You will be given a number in decimal form and your task is to convert it to
    binary format. The function should return a string, with each character representing a binary
    number. Each character in the string will be '0' or '1'.

    There will be an extra couple of characters 'db' at the beginning and at the end of the string.
    The extra characters are there to help with the format.

    Examples:
    decimal_to_binary(15)   # returns "db1111db"
    decimal_to_binary(32)   # returns "db100000db"
    """

    return "db" + bin(decimal)[2:] + "db"

```

### Test Prompt
```python
# id_79_Test.java
from original.id_79 import decimal_to_binary

import pytest

class id_79_Test:
    """
    Test class of id_79.py.
    It contains ten unit test cases for the :func:`original.id_79.decimal_to_binary`.
    """

```

## ../HumanEvalPython/original/id_115.py

### Original Code
```python
# id_115.py

def max_fill(grid, capacity):
    import math
    """
    You are given a rectangular grid of wells. Each row represents a single well,
    and each 1 in a row represents a single unit of water.
    Each well has a corresponding bucket that can be used to extract water from it, 
    and all buckets have the same capacity.
    Your task is to use the buckets to empty the wells.
    Output the number of times you need to lower the buckets.

    Example 1:
        Input: 
            grid : [[0,0,1,0], [0,1,0,0], [1,1,1,1]]
            bucket_capacity : 1
        Output: 6

    Example 2:
        Input: 
            grid : [[0,0,1,1], [0,0,0,0], [1,1,1,1], [0,1,1,1]]
            bucket_capacity : 2
        Output: 5
    
    Example 3:
        Input: 
            grid : [[0,0,0], [0,0,0]]
            bucket_capacity : 5
        Output: 0

    Constraints:
        * all wells have the same length
        * 1 <= grid.length <= 10^2
        * 1 <= grid[:,1].length <= 10^2
        * grid[i][j] -> 0 | 1
        * 1 <= capacity <= 10
    """

    return sum([math.ceil(sum(arr)/capacity) for arr in grid])


```

### Test Prompt
```python
# id_115_Test.java
from original.id_115 import max_fill

import pytest

class id_115_Test:
    """
    Test class of id_115.py.
    It contains ten unit test cases for the :func:`original.id_115.max_fill`.
    """

```

## ../HumanEvalPython/original/id_91.py

### Original Code
```python
# id_91.py

def is_bored(S):
    """
    You'll be given a string of words, and your task is to count the number
    of boredoms. A boredom is a sentence that starts with the word "I".
    Sentences are delimited by '.', '?' or '!'.
   
    For example:
    >>> is_bored("Hello world")
    0
    >>> is_bored("The sky is blue. The sun is shining. I love this weather")
    1
    """

    import re
    sentences = re.split(r'[.?!]\s*', S)
    return sum(sentence[0:2] == 'I ' for sentence in sentences)

```

### Test Prompt
```python
# id_91_Test.java
from original.id_91 import is_bored

import pytest

class id_91_Test:
    """
    Test class of id_91.py.
    It contains ten unit test cases for the :func:`original.id_91.is_bored`.
    """

```

## ../HumanEvalPython/original/id_62.py

### Original Code
```python
# id_62.py


def derivative(xs: list):
    """ xs represent coefficients of a polynomial.
    xs[0] + xs[1] * x + xs[2] * x^2 + ....
     Return derivative of this polynomial in the same form.
    >>> derivative([3, 1, 2, 4, 5])
    [1, 4, 12, 20]
    >>> derivative([1, 2, 3])
    [2, 6]
    """

    return [(i * x) for i, x in enumerate(xs)][1:]

```

### Test Prompt
```python
# id_62_Test.java
from original.id_62 import derivative

import pytest

class id_62_Test:
    """
    Test class of id_62.py.
    It contains ten unit test cases for the :func:`original.id_62.derivative`.
    """

```

## ../HumanEvalPython/original/id_33.py

### Original Code
```python
# id_33.py


def sort_third(l: list):
    """This function takes a list l and returns a list l' such that
    l' is identical to l in the indicies that are not divisible by three, while its values at the indicies that are divisible by three are equal
    to the values of the corresponding indicies of l, but sorted.
    >>> sort_third([1, 2, 3])
    [1, 2, 3]
    >>> sort_third([5, 6, 3, 4, 8, 9, 2])
    [2, 6, 3, 4, 8, 9, 5]
    """

    l = list(l)
    l[::3] = sorted(l[::3])
    return l

```

### Test Prompt
```python
# id_33_Test.java
from original.id_33 import sort_third

import pytest

class id_33_Test:
    """
    Test class of id_33.py.
    It contains ten unit test cases for the :func:`original.id_33.sort_third`.
    """

```

## ../HumanEvalPython/original/id_56.py

### Original Code
```python
# id_56.py


def correct_bracketing(brackets: str):
    """ brackets is a string of "<" and ">".
    return True if every opening bracket has a corresponding closing bracket.

    >>> correct_bracketing("<")
    False
    >>> correct_bracketing("<>")
    True
    >>> correct_bracketing("<<><>>")
    True
    >>> correct_bracketing("><<>")
    False
    """

    depth = 0
    for b in brackets:
        if b == "<":
            depth += 1
        else:
            depth -= 1
        if depth < 0:
            return False
    return depth == 0

```

### Test Prompt
```python
# id_56_Test.java
from original.id_56 import correct_bracketing

import pytest

class id_56_Test:
    """
    Test class of id_56.py.
    It contains ten unit test cases for the :func:`original.id_56.correct_bracketing`.
    """

```

## ../HumanEvalPython/original/id_46.py

### Original Code
```python
# id_46.py


def fib4(n: int):
    """The Fib4 number sequence is a sequence similar to the Fibbonacci sequnece that's defined as follows:
    fib4(0) -> 0
    fib4(1) -> 0
    fib4(2) -> 2
    fib4(3) -> 0
    fib4(n) -> fib4(n-1) + fib4(n-2) + fib4(n-3) + fib4(n-4).
    Please write a function to efficiently compute the n-th element of the fib4 number sequence.  Do not use recursion.
    >>> fib4(5)
    4
    >>> fib4(6)
    8
    >>> fib4(7)
    14
    """

    results = [0, 0, 2, 0]
    if n < 4:
        return results[n]

    for _ in range(4, n + 1):
        results.append(results[-1] + results[-2] + results[-3] + results[-4])
        results.pop(0)

    return results[-1]

```

### Test Prompt
```python
# id_46_Test.java
from original.id_46 import fib4

import pytest

class id_46_Test:
    """
    Test class of id_46.py.
    It contains ten unit test cases for the :func:`original.id_46.fib4`.
    """

```

## ../HumanEvalPython/original/id_17.py

### Original Code
```python
# id_17.py
from typing import List


def parse_music(music_string: str) -> List[int]:
    """ Input to this function is a string representing musical notes in a special ASCII format.
    Your task is to parse this string and return list of integers corresponding to how many beats does each
    not last.

    Here is a legend:
    'o' - whole note, lasts four beats
    'o|' - half note, lasts two beats
    '.|' - quater note, lasts one beat

    >>> parse_music('o o| .| o| o| .| .| .| .| o o')
    [4, 2, 1, 2, 2, 1, 1, 1, 1, 4, 4]
    """

    note_map = {'o': 4, 'o|': 2, '.|': 1}
    return [note_map[x] for x in music_string.split(' ') if x]

```

### Test Prompt
```python
# id_17_Test.java
from original.id_17 import parse_music

import pytest

class id_17_Test:
    """
    Test class of id_17.py.
    It contains ten unit test cases for the :func:`original.id_17.parse_music`.
    """

```

## ../HumanEvalPython/original/id_23.py

### Original Code
```python
# id_23.py


def strlen(string: str) -> int:
    """ Return length of given string
    >>> strlen('')
    0
    >>> strlen('abc')
    3
    """

    return len(string)

```

### Test Prompt
```python
# id_23_Test.java
from original.id_23 import strlen

import pytest

class id_23_Test:
    """
    Test class of id_23.py.
    It contains ten unit test cases for the :func:`original.id_23.strlen`.
    """

```

## ../HumanEvalPython/original/id_72.py

### Original Code
```python
# id_72.py

def will_it_fly(q,w):
    '''
    Write a function that returns True if the object q will fly, and False otherwise.
    The object q will fly if it's balanced (it is a palindromic list) and the sum of its elements is less than or equal the maximum possible weight w.

    Example:
    will_it_fly([1, 2], 5) ➞ False 
    # 1+2 is less than the maximum possible weight, but it's unbalanced.

    will_it_fly([3, 2, 3], 1) ➞ False
    # it's balanced, but 3+2+3 is more than the maximum possible weight.

    will_it_fly([3, 2, 3], 9) ➞ True
    # 3+2+3 is less than the maximum possible weight, and it's balanced.

    will_it_fly([3], 5) ➞ True
    # 3 is less than the maximum possible weight, and it's balanced.
    '''

    if sum(q) > w:
        return False

    i, j = 0, len(q)-1
    while i<j:
        if q[i] != q[j]:
            return False
        i+=1
        j-=1
    return True

```

### Test Prompt
```python
# id_72_Test.java
from original.id_72 import will_it_fly

import pytest

class id_72_Test:
    """
    Test class of id_72.py.
    It contains ten unit test cases for the :func:`original.id_72.will_it_fly`.
    """

```

## ../HumanEvalPython/original/id_81.py

### Original Code
```python
# id_81.py

def numerical_letter_grade(grades):
    """It is the last week of the semester and the teacher has to give the grades
    to students. The teacher has been making her own algorithm for grading.
    The only problem is, she has lost the code she used for grading.
    She has given you a list of GPAs for some students and you have to write 
    a function that can output a list of letter grades using the following table:
             GPA       |    Letter grade
              4.0                A+
            > 3.7                A 
            > 3.3                A- 
            > 3.0                B+
            > 2.7                B 
            > 2.3                B-
            > 2.0                C+
            > 1.7                C
            > 1.3                C-
            > 1.0                D+ 
            > 0.7                D 
            > 0.0                D-
              0.0                E
    

    Example:
    grade_equation([4.0, 3, 1.7, 2, 3.5]) ==> ['A+', 'B', 'C-', 'C', 'A-']
    """


   
    letter_grade = []
    for gpa in grades:
        if gpa == 4.0:
            letter_grade.append("A+")
        elif gpa > 3.7:
            letter_grade.append("A")
        elif gpa > 3.3:
            letter_grade.append("A-")
        elif gpa > 3.0:
            letter_grade.append("B+")
        elif gpa > 2.7:
            letter_grade.append("B")
        elif gpa > 2.3:
            letter_grade.append("B-")
        elif gpa > 2.0:
            letter_grade.append("C+")
        elif gpa > 1.7:
            letter_grade.append("C")
        elif gpa > 1.3:
            letter_grade.append("C-")
        elif gpa > 1.0:
            letter_grade.append("D+")
        elif gpa > 0.7:
            letter_grade.append("D")
        elif gpa > 0.0:
            letter_grade.append("D-")
        else:
            letter_grade.append("E")
    return letter_grade


```

### Test Prompt
```python
# id_81_Test.java
from original.id_81 import numerical_letter_grade

import pytest

class id_81_Test:
    """
    Test class of id_81.py.
    It contains ten unit test cases for the :func:`original.id_81.numerical_letter_grade`.
    """

```

## ../HumanEvalPython/original/id_52.py

### Original Code
```python
# id_52.py


def below_threshold(l: list, t: int):
    """Return True if all numbers in the list l are below threshold t.
    >>> below_threshold([1, 2, 4, 10], 100)
    True
    >>> below_threshold([1, 20, 4, 10], 5)
    False
    """

    for e in l:
        if e >= t:
            return False
    return True

```

### Test Prompt
```python
# id_52_Test.java
from original.id_52 import below_threshold

import pytest

class id_52_Test:
    """
    Test class of id_52.py.
    It contains ten unit test cases for the :func:`original.id_52.below_threshold`.
    """

```

## ../HumanEvalPython/original/id_95.py

### Original Code
```python
# id_95.py

def check_dict_case(dict):
    """
    Given a dictionary, return True if all keys are strings in lower 
    case or all keys are strings in upper case, else return False.
    The function should return False is the given dictionary is empty.
    Examples:
    check_dict_case({"a":"apple", "b":"banana"}) should return True.
    check_dict_case({"a":"apple", "A":"banana", "B":"banana"}) should return False.
    check_dict_case({"a":"apple", 8:"banana", "a":"apple"}) should return False.
    check_dict_case({"Name":"John", "Age":"36", "City":"Houston"}) should return False.
    check_dict_case({"STATE":"NC", "ZIP":"12345" }) should return True.
    """

    if len(dict.keys()) == 0:
        return False
    else:
        state = "start"
        for key in dict.keys():

            if isinstance(key, str) == False:
                state = "mixed"
                break
            if state == "start":
                if key.isupper():
                    state = "upper"
                elif key.islower():
                    state = "lower"
                else:
                    break
            elif (state == "upper" and not key.isupper()) or (state == "lower" and not key.islower()):
                    state = "mixed"
                    break
            else:
                break
        return state == "upper" or state == "lower" 

```

### Test Prompt
```python
# id_95_Test.java
from original.id_95 import check_dict_case

import pytest

class id_95_Test:
    """
    Test class of id_95.py.
    It contains ten unit test cases for the :func:`original.id_95.check_dict_case`.
    """

```

## ../HumanEvalPython/original/id_37.py

### Original Code
```python
# id_37.py


def sort_even(l: list):
    """This function takes a list l and returns a list l' such that
    l' is identical to l in the odd indicies, while its values at the even indicies are equal
    to the values of the even indicies of l, but sorted.
    >>> sort_even([1, 2, 3])
    [1, 2, 3]
    >>> sort_even([5, 6, 3, 4])
    [3, 6, 5, 4]
    """

    evens = l[::2]
    odds = l[1::2]
    evens.sort()
    ans = []
    for e, o in zip(evens, odds):
        ans.extend([e, o])
    if len(evens) > len(odds):
        ans.append(evens[-1])
    return ans


```

### Test Prompt
```python
# id_37_Test.java
from original.id_37 import sort_even

import pytest

class id_37_Test:
    """
    Test class of id_37.py.
    It contains ten unit test cases for the :func:`original.id_37.sort_even`.
    """

```

## ../HumanEvalPython/original/id_66.py

### Original Code
```python
# id_66.py

def digitSum(s):
    """Task
    Write a function that takes a string as input and returns the sum of the upper characters only'
    ASCII codes.

    Examples:
        digitSum("") => 0
        digitSum("abAB") => 131
        digitSum("abcCd") => 67
        digitSum("helloE") => 69
        digitSum("woArBld") => 131
        digitSum("aAaaaXa") => 153
    """

    if s == "": return 0
    return sum(ord(char) if char.isupper() else 0 for char in s)

```

### Test Prompt
```python
# id_66_Test.java
from original.id_66 import digitSum

import pytest

class id_66_Test:
    """
    Test class of id_66.py.
    It contains ten unit test cases for the :func:`original.id_66.digitSum`.
    """

```

## ../HumanEvalPython/original/id_76.py

### Original Code
```python
# id_76.py

def is_simple_power(x, n):
    """Your task is to write a function that returns true if a number x is a simple
    power of n and false in other cases.
    x is a simple power of n if n**int=x
    For example:
    is_simple_power(1, 4) => true
    is_simple_power(2, 2) => true
    is_simple_power(8, 2) => true
    is_simple_power(3, 2) => false
    is_simple_power(3, 1) => false
    is_simple_power(5, 3) => false
    """

    if (n == 1): 
        return (x == 1) 
    power = 1
    while (power < x): 
        power = power * n 
    return (power == x) 

```

### Test Prompt
```python
# id_76_Test.java
from original.id_76 import is_simple_power

import pytest

class id_76_Test:
    """
    Test class of id_76.py.
    It contains ten unit test cases for the :func:`original.id_76.is_simple_power`.
    """

```

## ../HumanEvalPython/original/id_27.py

### Original Code
```python
# id_27.py


def flip_case(string: str) -> str:
    """ For a given string, flip lowercase characters to uppercase and uppercase to lowercase.
    >>> flip_case('Hello')
    'hELLO'
    """

    return string.swapcase()

```

### Test Prompt
```python
# id_27_Test.java
from original.id_27 import flip_case

import pytest

class id_27_Test:
    """
    Test class of id_27.py.
    It contains ten unit test cases for the :func:`original.id_27.flip_case`.
    """

```

## ../HumanEvalPython/original/id_85.py

### Original Code
```python
# id_85.py

def add(lst):
    """Given a non-empty list of integers lst. add the even elements that are at odd indices..


    Examples:
        add([4, 2, 6, 7]) ==> 2 
    """

    return sum([lst[i] for i in range(1, len(lst), 2) if lst[i]%2 == 0])

```

### Test Prompt
```python
# id_85_Test.java
from original.id_85 import add

import pytest

class id_85_Test:
    """
    Test class of id_85.py.
    It contains ten unit test cases for the :func:`original.id_85.add`.
    """

```

## ../HumanEvalPython/original/id_13.py

### Original Code
```python
# id_13.py


def greatest_common_divisor(a: int, b: int) -> int:
    """ Return a greatest common divisor of two integers a and b
    >>> greatest_common_divisor(3, 5)
    1
    >>> greatest_common_divisor(25, 15)
    5
    """

    while b:
        a, b = b, a % b
    return a

```

### Test Prompt
```python
# id_13_Test.java
from original.id_13 import greatest_common_divisor

import pytest

class id_13_Test:
    """
    Test class of id_13.py.
    It contains ten unit test cases for the :func:`original.id_13.greatest_common_divisor`.
    """

```

## ../HumanEvalPython/original/id_42.py

### Original Code
```python
# id_42.py


def incr_list(l: list):
    """Return list with elements incremented by 1.
    >>> incr_list([1, 2, 3])
    [2, 3, 4]
    >>> incr_list([5, 3, 5, 2, 3, 3, 9, 0, 123])
    [6, 4, 6, 3, 4, 4, 10, 1, 124]
    """

    return [(e + 1) for e in l]

```

### Test Prompt
```python
# id_42_Test.java
from original.id_42 import incr_list

import pytest

class id_42_Test:
    """
    Test class of id_42.py.
    It contains ten unit test cases for the :func:`original.id_42.incr_list`.
    """

```

## ../HumanEvalPython/original/id_53.py

### Original Code
```python
# id_53.py


def add(x: int, y: int):
    """Add two numbers x and y
    >>> add(2, 3)
    5
    >>> add(5, 7)
    12
    """

    return x + y

```

### Test Prompt
```python
# id_53_Test.java
from original.id_53 import add

import pytest

class id_53_Test:
    """
    Test class of id_53.py.
    It contains ten unit test cases for the :func:`original.id_53.add`.
    """

```

## ../HumanEvalPython/original/id_94.py

### Original Code
```python
# id_94.py


def skjkasdkd(lst):
    """You are given a list of integers.
    You need to find the largest prime value and return the sum of its digits.

    Examples:
    For lst = [0,3,2,1,3,5,7,4,5,5,5,2,181,32,4,32,3,2,32,324,4,3] the output should be 10
    For lst = [1,0,1,8,2,4597,2,1,3,40,1,2,1,2,4,2,5,1] the output should be 25
    For lst = [1,3,1,32,5107,34,83278,109,163,23,2323,32,30,1,9,3] the output should be 13
    For lst = [0,724,32,71,99,32,6,0,5,91,83,0,5,6] the output should be 11
    For lst = [0,81,12,3,1,21] the output should be 3
    For lst = [0,8,1,2,1,7] the output should be 7
    """

    def isPrime(n):
        for i in range(2,int(n**0.5)+1):
            if n%i==0:
                return False

        return True
    maxx = 0
    i = 0
    while i < len(lst):
        if(lst[i] > maxx and isPrime(lst[i])):
            maxx = lst[i]
        i+=1
    result = sum(int(digit) for digit in str(maxx))
    return result


```

### Test Prompt
```python
# id_94_Test.java
from original.id_94 import skjkasdkd

import pytest

class id_94_Test:
    """
    Test class of id_94.py.
    It contains ten unit test cases for the :func:`original.id_94.skjkasdkd`.
    """

```

## ../HumanEvalPython/original/id_36.py

### Original Code
```python
# id_36.py


def fizz_buzz(n: int):
    """Return the number of times the digit 7 appears in integers less than n which are divisible by 11 or 13.
    >>> fizz_buzz(50)
    0
    >>> fizz_buzz(78)
    2
    >>> fizz_buzz(79)
    3
    """

    ns = []
    for i in range(n):
        if i % 11 == 0 or i % 13 == 0:
            ns.append(i)
    s = ''.join(list(map(str, ns)))
    ans = 0
    for c in s:
        ans += (c == '7')
    return ans


```

### Test Prompt
```python
# id_36_Test.java
from original.id_36 import fizz_buzz

import pytest

class id_36_Test:
    """
    Test class of id_36.py.
    It contains ten unit test cases for the :func:`original.id_36.fizz_buzz`.
    """

```

## ../HumanEvalPython/original/id_67.py

### Original Code
```python
# id_67.py

def fruit_distribution(s,n):
    """
    In this task, you will be given a string that represents a number of apples and oranges 
    that are distributed in a basket of fruit this basket contains 
    apples, oranges, and mango fruits. Given the string that represents the total number of 
    the oranges and apples and an integer that represent the total number of the fruits 
    in the basket return the number of the mango fruits in the basket.
    for examble:
    fruit_distribution("5 apples and 6 oranges", 19) ->19 - 5 - 6 = 8
    fruit_distribution("0 apples and 1 oranges",3) -> 3 - 0 - 1 = 2
    fruit_distribution("2 apples and 3 oranges", 100) -> 100 - 2 - 3 = 95
    fruit_distribution("100 apples and 1 oranges",120) -> 120 - 100 - 1 = 19
    """

    lis = list()
    for i in s.split(' '):
        if i.isdigit():
            lis.append(int(i))
    return n - sum(lis)

```

### Test Prompt
```python
# id_67_Test.java
from original.id_67 import fruit_distribution

import pytest

class id_67_Test:
    """
    Test class of id_67.py.
    It contains ten unit test cases for the :func:`original.id_67.fruit_distribution`.
    """

```

## ../HumanEvalPython/original/id_77.py

### Original Code
```python
# id_77.py

def iscube(a):
    '''
    Write a function that takes an integer a and returns True 
    if this ingeger is a cube of some integer number.
    Note: you may assume the input is always valid.
    Examples:
    iscube(1) ==> True
    iscube(2) ==> False
    iscube(-1) ==> True
    iscube(64) ==> True
    iscube(0) ==> True
    iscube(180) ==> False
    '''

    a = abs(a)
    return int(round(a ** (1. / 3))) ** 3 == a

```

### Test Prompt
```python
# id_77_Test.java
from original.id_77 import iscube

import pytest

class id_77_Test:
    """
    Test class of id_77.py.
    It contains ten unit test cases for the :func:`original.id_77.iscube`.
    """

```

## ../HumanEvalPython/original/id_26.py

### Original Code
```python
# id_26.py
from typing import List


def remove_duplicates(numbers: List[int]) -> List[int]:
    """ From a list of integers, remove all elements that occur more than once.
    Keep order of elements left the same as in the input.
    >>> remove_duplicates([1, 2, 3, 2, 4])
    [1, 3, 4]
    """

    import collections
    c = collections.Counter(numbers)
    return [n for n in numbers if c[n] <= 1]

```

### Test Prompt
```python
# id_26_Test.java
from original.id_26 import remove_duplicates

import pytest

class id_26_Test:
    """
    Test class of id_26.py.
    It contains ten unit test cases for the :func:`original.id_26.remove_duplicates`.
    """

```

## ../HumanEvalPython/original/id_84.py

### Original Code
```python
# id_84.py

def solve(N):
    """Given a positive integer N, return the total sum of its digits in binary.
    
    Example
        For N = 1000, the sum of digits will be 1 the output should be "1".
        For N = 150, the sum of digits will be 6 the output should be "110".
        For N = 147, the sum of digits will be 12 the output should be "1100".
    
    Variables:
        @N integer
             Constraints: 0 ≤ N ≤ 10000.
    Output:
         a string of binary number
    """

    return bin(sum(int(i) for i in str(N)))[2:]

```

### Test Prompt
```python
# id_84_Test.java
from original.id_84 import solve

import pytest

class id_84_Test:
    """
    Test class of id_84.py.
    It contains ten unit test cases for the :func:`original.id_84.solve`.
    """

```

## ../HumanEvalPython/original/id_12.py

### Original Code
```python
# id_12.py
from typing import List, Optional


def longest(strings: List[str]) -> Optional[str]:
    """ Out of list of strings, return the longest one. Return the first one in case of multiple
    strings of the same length. Return None in case the input list is empty.
    >>> longest([])

    >>> longest(['a', 'b', 'c'])
    'a'
    >>> longest(['a', 'bb', 'ccc'])
    'ccc'
    """

    if not strings:
        return None

    maxlen = max(len(x) for x in strings)
    for s in strings:
        if len(s) == maxlen:
            return s

```

### Test Prompt
```python
# id_12_Test.java
from original.id_12 import longest

import pytest

class id_12_Test:
    """
    Test class of id_12.py.
    It contains ten unit test cases for the :func:`original.id_12.longest`.
    """

```

## ../HumanEvalPython/original/id_43.py

### Original Code
```python
# id_43.py


def pairs_sum_to_zero(l):
    """
    pairs_sum_to_zero takes a list of integers as an input.
    it returns True if there are two distinct elements in the list that
    sum to zero, and False otherwise.
    >>> pairs_sum_to_zero([1, 3, 5, 0])
    False
    >>> pairs_sum_to_zero([1, 3, -2, 1])
    False
    >>> pairs_sum_to_zero([1, 2, 3, 7])
    False
    >>> pairs_sum_to_zero([2, 4, -5, 3, 5, 7])
    True
    >>> pairs_sum_to_zero([1])
    False
    """

    for i, l1 in enumerate(l):
        for j in range(i + 1, len(l)):
            if l1 + l[j] == 0:
                return True
    return False

```

### Test Prompt
```python
# id_43_Test.java
from original.id_43 import pairs_sum_to_zero

import pytest

class id_43_Test:
    """
    Test class of id_43.py.
    It contains ten unit test cases for the :func:`original.id_43.pairs_sum_to_zero`.
    """

```

## ../HumanEvalPython/original/id_90.py

### Original Code
```python
# id_90.py

def next_smallest(lst):
    """
    You are given a list of integers.
    Write a function next_smallest() that returns the 2nd smallest element of the list.
    Return None if there is no such element.
    
    next_smallest([1, 2, 3, 4, 5]) == 2
    next_smallest([5, 1, 4, 3, 2]) == 2
    next_smallest([]) == None
    next_smallest([1, 1]) == None
    """

    lst = sorted(set(lst))
    return None if len(lst) < 2 else lst[1]

```

### Test Prompt
```python
# id_90_Test.java
from original.id_90 import next_smallest

import pytest

class id_90_Test:
    """
    Test class of id_90.py.
    It contains ten unit test cases for the :func:`original.id_90.next_smallest`.
    """

```

## ../HumanEvalPython/original/id_63.py

### Original Code
```python
# id_63.py


def fibfib(n: int):
    """The FibFib number sequence is a sequence similar to the Fibbonacci sequnece that's defined as follows:
    fibfib(0) == 0
    fibfib(1) == 0
    fibfib(2) == 1
    fibfib(n) == fibfib(n-1) + fibfib(n-2) + fibfib(n-3).
    Please write a function to efficiently compute the n-th element of the fibfib number sequence.
    >>> fibfib(1)
    0
    >>> fibfib(5)
    4
    >>> fibfib(8)
    24
    """

    if n == 0:
        return 0
    if n == 1:
        return 0
    if n == 2:
        return 1
    return fibfib(n - 1) + fibfib(n - 2) + fibfib(n - 3)

```

### Test Prompt
```python
# id_63_Test.java
from original.id_63 import fibfib

import pytest

class id_63_Test:
    """
    Test class of id_63.py.
    It contains ten unit test cases for the :func:`original.id_63.fibfib`.
    """

```

## ../HumanEvalPython/original/id_32.py

### Original Code
```python
# id_32.py
import math


def poly(xs: list, x: float):
    """
    Evaluates polynomial with coefficients xs at point x.
    return xs[0] + xs[1] * x + xs[1] * x^2 + .... xs[n] * x^n
    """
    return sum([coeff * math.pow(x, i) for i, coeff in enumerate(xs)])


def find_zero(xs: list):
    """ xs are coefficients of a polynomial.
    find_zero find x such that poly(x) = 0.
    find_zero returns only only zero point, even if there are many.
    Moreover, find_zero only takes list xs having even number of coefficients
    and largest non zero coefficient as it guarantees
    a solution.
    >>> round(find_zero([1, 2]), 2) # f(x) = 1 + 2x
    -0.5
    >>> round(find_zero([-6, 11, -6, 1]), 2) # (x - 1) * (x - 2) * (x - 3) = -6 + 11x - 6x^2 + x^3
    1.0
    """

    begin, end = -1., 1.
    while poly(xs, begin) * poly(xs, end) > 0:
        begin *= 2.0
        end *= 2.0
    while end - begin > 1e-10:
        center = (begin + end) / 2.0
        if poly(xs, center) * poly(xs, begin) > 0:
            begin = center
        else:
            end = center
    return begin

```

### Test Prompt
```python
# id_32_Test.java
from original.id_32 import find_zero

import pytest

class id_32_Test:
    """
    Test class of id_32.py.
    It contains ten unit test cases for the :func:`original.id_32.find_zero`.
    """

```

## ../HumanEvalPython/original/id_57.py

### Original Code
```python
# id_57.py


def monotonic(l: list):
    """Return True is list elements are monotonically increasing or decreasing.
    >>> monotonic([1, 2, 4, 20])
    True
    >>> monotonic([1, 20, 4, 10])
    False
    >>> monotonic([4, 1, 0, -10])
    True
    """

    if l == sorted(l) or l == sorted(l, reverse=True):
        return True
    return False


```

### Test Prompt
```python
# id_57_Test.java
from original.id_57 import monotonic

import pytest

class id_57_Test:
    """
    Test class of id_57.py.
    It contains ten unit test cases for the :func:`original.id_57.monotonic`.
    """

```

## ../HumanEvalPython/original/id_47.py

### Original Code
```python
# id_47.py


def median(l: list):
    """Return median of elements in the list l.
    >>> median([3, 1, 2, 4, 5])
    3
    >>> median([-10, 4, 6, 1000, 10, 20])
    15.0
    """

    l = sorted(l)
    if len(l) % 2 == 1:
        return l[len(l) // 2]
    else:
        return (l[len(l) // 2 - 1] + l[len(l) // 2]) / 2.0

```

### Test Prompt
```python
# id_47_Test.java
from original.id_47 import median

import pytest

class id_47_Test:
    """
    Test class of id_47.py.
    It contains ten unit test cases for the :func:`original.id_47.median`.
    """

```

## ../HumanEvalPython/original/id_16.py

### Original Code
```python
# id_16.py


def count_distinct_characters(string: str) -> int:
    """ Given a string, find out how many distinct characters (regardless of case) does it consist of
    >>> count_distinct_characters('xyzXYZ')
    3
    >>> count_distinct_characters('Jerry')
    4
    """

    return len(set(string.lower()))

```

### Test Prompt
```python
# id_16_Test.java
from original.id_16 import count_distinct_characters

import pytest

class id_16_Test:
    """
    Test class of id_16.py.
    It contains ten unit test cases for the :func:`original.id_16.count_distinct_characters`.
    """

```

## ../HumanEvalPython/original/id_22.py

### Original Code
```python
# id_22.py
from typing import List, Any


def filter_integers(values: List[Any]) -> List[int]:
    """ Filter given list of any python values only for integers
    >>> filter_integers(['a', 3.14, 5])
    [5]
    >>> filter_integers([1, 2, 3, 'abc', {}, []])
    [1, 2, 3]
    """

    return [x for x in values if isinstance(x, int)]

```

### Test Prompt
```python
# id_22_Test.java
from original.id_22 import filter_integers

import pytest

class id_22_Test:
    """
    Test class of id_22.py.
    It contains ten unit test cases for the :func:`original.id_22.filter_integers`.
    """

```

## ../HumanEvalPython/original/id_73.py

### Original Code
```python
# id_73.py

def smallest_change(arr):
    """
    Given an array arr of integers, find the minimum number of elements that
    need to be changed to make the array palindromic. A palindromic array is an array that
    is read the same backwards and forwards. In one change, you can change one element to any other element.

    For example:
    smallest_change([1,2,3,5,4,7,9,6]) == 4
    smallest_change([1, 2, 3, 4, 3, 2, 2]) == 1
    smallest_change([1, 2, 3, 2, 1]) == 0
    """

    ans = 0
    for i in range(len(arr) // 2):
        if arr[i] != arr[len(arr) - i - 1]:
            ans += 1
    return ans

```

### Test Prompt
```python
# id_73_Test.java
from original.id_73 import smallest_change

import pytest

class id_73_Test:
    """
    Test class of id_73.py.
    It contains ten unit test cases for the :func:`original.id_73.smallest_change`.
    """

```

## ../HumanEvalPython/original/id_80.py

### Original Code
```python
# id_80.py

def is_happy(s):
    """You are given a string s.
    Your task is to check if the string is happy or not.
    A string is happy if its length is at least 3 and every 3 consecutive letters are distinct
    For example:
    is_happy(a) => False
    is_happy(aa) => False
    is_happy(abcd) => True
    is_happy(aabb) => False
    is_happy(adb) => True
    is_happy(xyy) => False
    """

    if len(s) < 3:
      return False

    for i in range(len(s) - 2):
      
      if s[i] == s[i+1] or s[i+1] == s[i+2] or s[i] == s[i+2]:
        return False
    return True

```

### Test Prompt
```python
# id_80_Test.java
from original.id_80 import is_happy

import pytest

class id_80_Test:
    """
    Test class of id_80.py.
    It contains ten unit test cases for the :func:`original.id_80.is_happy`.
    """

```

