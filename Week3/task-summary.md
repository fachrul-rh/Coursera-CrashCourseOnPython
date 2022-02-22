<!-- @format -->

# Practice Quiz: While loops

Fill in the blanks to make the print_prime_factors function print all the prime factors of a number. A prime factor is a number that is prime and divides another without a remainder.

```
def print_prime_factors(number):
  # Start with two, which is the first prime
  factor = 2
  # Keep going until the factor is larger than the number
  while factor <= number:
    # Check if factor is a divisor of number
    if number % factor == 0:
      # If it is, print it and divide the original number
      print(factor)
      number = number / factor
    else:
      # If it's not, increment the factor by one
      factor += 1
  return "Done"

print_prime_factors(100)
# Should print 2,2,5,5
# DO NOT DELETE THIS COMMENT
```

The following code can lead to an infinite loop. Fix the code so that it can finish successfully for all numbers.

Note: Try running your function with the number 0 as the input, and see what you get!

```
def is_power_of_two(n):
  # Check if the number can be divided by two without a remainder
  while n != 0 and n % 2 == 0:
    n = n / 2
  # If after dividing by two the number is 1, it's a power of two
  if n == 1:
    return True
  return False


print(is_power_of_two(0)) # Should be False
print(is_power_of_two(1)) # Should be True
print(is_power_of_two(8)) # Should be True
print(is_power_of_two(9)) # Should be False
```

Fill in the empty function so that it returns the sum of all the divisors of a number, without including it. A divisor is a number that divides into another without a remainder.

```
def sum_divisors(n):
  sum = 0
  i = 1
  while i < n:
    if n % i == 0:
      sum += i
    i += 1
    # Return the sum of all divisors of n, not including n
  return sum

print(sum_divisors(0))
# 0
print(sum_divisors(3)) # Should sum of 1
# 1
print(sum_divisors(36)) # Should sum of 1+2+3+4+6+9+12+18
# 55
print(sum_divisors(102)) # Should be sum of 2+3+6+17+34+51
# 114
```

The multiplication_table function prints the results of a number passed to it multiplied by 1 through 5. An additional requirement is that the result is not to exceed 25, which is done with the break statement. Fill in the blanks to complete the function to satisfy these conditions.

```
def multiplication_table(number):
	# Initialize the starting point of the multiplication table
	multiplier = 1
	# Only want to loop through 5
	while multiplier <= 5:
		result = number * multiplier
		# What is the additional condition to exit out of the loop?
		if result > 25:
			break
		print(str(number) + "x" + str(multiplier) + "=" + str(result))
		# Increment the variable for the loop
		multiplier += 1

multiplication_table(3)
# Should print: 3x1=3 3x2=6 3x3=9 3x4=12 3x5=15

multiplication_table(5)
# Should print: 5x1=5 5x2=10 5x3=15 5x4=20 5x5=25

multiplication_table(8)
# Should print: 8x1=8 8x2=16 8x3=24
```

# Practice Quiz: For Loops

Fill in the blanks to make the factorial function return the factorial of n. Then, print the first 10 factorials (from 0 to 9) with the corresponding number. Remember that the factorial of a number is defined as the product of an integer and all integers before it. For example, the factorial of five (5!) is equal to 1*2*3*4*5=120. Also recall that the factorial of zero (0!) is equal to 1.

```
def factorial(n):
    result = 1
    for x in range(1, n):
        result = result * x
    return result

for n in range(0,10):
    print(n, factorial(n+1))
```

Write a script that prints the first 10 cube numbers (x\*\*3), starting with x=1 and ending with x=10.

```
for x in range(1,11):
  print(x**3)
```

Write a script that prints the multiples of 7 between 0 and 100. Print one multiple per line and avoid printing any numbers that aren't multiples of 7. Remember that 0 is also a multiple of 7.

```
for i in range(0,101,7):
    print(i)
```

The retry function tries to execute an operation that might fail, it retries the operation for a number of attempts. Currently the code will keep executing the function even if it succeeds. Fill in the blank so the code stops trying after the operation succeeded.

```
def retry(operation, attempts):
  for n in range(attempts):
    if operation():
      print("Attempt " + str(n) + " succeeded")
      break
    else:
      print("Attempt " + str(n) + " failed")

retry(create_user, 3)
retry(stop_service, 5)
```

# Practice Quiz: Recursion

Fill in the blanks to make the is_power_of function return whether the number is a power of the given base. Note: base is assumed to be a positive number. Tip: for functions that return a boolean value, you can return the result of a comparison.

```
def is_power_of(number, base):
  number = number / base
  # Base case: when number is smaller than base.
  if number < base:
    # If number is equal to 1, it's a power (base**0).
    return False
  else:
    return True

  # Recursive case: keep dividing number by base.
  return is_power_of(number, base)

print(is_power_of(8,2)) # Should be True
print(is_power_of(64,4)) # Should be True
print(is_power_of(70,10)) # Should be False
```

The count_users function recursively counts the amount of users that belong to a group in the company system, by going through each of the members of a group and if one of them is a group, recursively calling the function and counting the members. But it has a bug! Can you spot the problem and fix it?

```
def count_users(group):
  count = 0
  for member in get_members(group):
    count += 1
    if is_group(member):
      count += count_users(member) - 1
  return count

print(count_users("sales")) # Should be 3
print(count_users("engineering")) # Should be 8
print(count_users("everyone")) # Should be 18
```

# Graded Assessment

Fill in the blanks of this code to print out the numbers 1 through 7.

```
number = 1
while number <= 7:
	print(number, end=" ")
	number += 1
```

The show_letters function should print out each letter of a word on a separate line. Fill in the blanks to make that happen.

```
def show_letters(word):
	for i in word:
		print(i)

show_letters("Hello")
# Should print one line per letter
```

Implement the sum_positive_numbers function, as a recursive function that returns the sum of all positive numbers between the number n received and 1. For example, when n is 3 it should return 1+2+3=6, and when n is 5 it should return 1+2+3+4+5=15

```
def sum_positive_numbers(n):
  if n == 0:
    return 0
  else:
    return n + sum_positive_numbers(n-1)

print(sum_positive_numbers(3)) # Should be 6
print(sum_positive_numbers(5)) # Should be 15
```

Pertanyaan #3
Complete the function digits(n) that returns how many digits the number has. For example: 25 has 2 digits and 144 has 3 digits. Tip: you can figure out the digits of a number by dividing it by 10 once per digit until there are no digits left

```
def digits(n):
	count = 0
	if n == 0:
	  return 1
	while n > 0:
		count += 1
		n = n // 10
	return count

print(digits(25))   # Should print 2
print(digits(144))  # Should print 3
print(digits(1000)) # Should print 4
print(digits(0))    # Should print 1
```

This function prints out a multiplication table (where each number is the result of multiplying the first number of its row by the number at the top of its column). Fill in the blanks so that calling multiplication_table(1, 3) will print out:

1 2 3

2 4 6

3 6 9

```
def multiplication_table(start, stop):
	for x in range(start, stop + 1):
		for y in range(start, stop + 1):
			print(str(x*y), end=" ")
		print()

multiplication_table(1, 3)
# Should print the multiplication table shown above
```

The counter function counts down from start to stop when start is bigger than stop, and counts up from start to stop otherwise. Fill in the blanks to make this work correctly.

```
def counter(start, stop):
    x = start
    if x > stop:
        return_string = 'Counting down: '
        while x >= stop:
            return_string += str(x)
            if x > stop:
                return_string += ','
            x -= 1
    else:
        return_string = 'Counting up: '
        while x <= stop:
            return_string += str(x)
            if x < stop:
                return_string += ','
            x += 1
    return return_string

print(counter(1, 10)) # Should be "Counting up: 1,2,3,4,5,6,7,8,9,10"
print(counter(2, 1)) # Should be "Counting down: 2,1"
print(counter(5, 5)) # Should be "Counting up: 5"
```

The even_numbers function returns a space-separated string of all positive numbers that are divisible by 2, up to and including the maximum that's passed into the function. For example, even_numbers(6) returns “2 4 6”. Fill in the blank to make this work

```
def even_numbers(maximum):
    return_string = ""
    for x in range(2, maximum+1, 2):
        return_string += str(x) + " "
    return return_string.strip()

print(even_numbers(6))  # Should be 2 4 6
print(even_numbers(10)) # Should be 2 4 6 8 10
print(even_numbers(1))  # No numbers displayed
print(even_numbers(3))  # Should be 2
print(even_numbers(0))  # No numbers displayed
```

The following code raises an error when executed. What's the reason for the error?

```
def decade_counter():
	while year < 50:
		year += 10
	return year
```
