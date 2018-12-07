Hello GIT and Github

What are we going to do with this new repository?

All new code learned:

As a refresher, function syntax looks like this:
def some_function(some_input1, some_input2):
  … do something with the inputs …
  return output
For example, a function that takes a number and checks to see if it is greater than ten would look like this

def greaterThanTen(number):
  if number > 10:
    return True
  else:
    return False
And this would produce output like:

>>> greaterThanTen(20)
True
>>> greaterThanTen(-10)
False
>>> greaterThanTen(10)
False

# Write your in_range function here:
def in_range(num, lower, upper):
  if (num >= lower) and (num <= upper):
    return True
  else: 
    return False
# Uncomment these function calls to test your in_range function:
#print(in_range(10, 10, 10))
# should print True
#print(in_range(5, 10, 20))
# should print False

# Write your movie_review function here:
def movie_review(rating):
  if (rating <= 5):
    return "Avoid at all costs!"
  elif (rating >5) and (rating < 9):
    return "This one was fun."
  else: 
    return "Outstanding!"
# Uncomment these function calls to test your movie_review function:
print(movie_review(9))
# should print "Outstanding!"
print(movie_review(4))
# should print "Avoid at all costs!"
print(movie_review(6))
# should print "This one was fun."

# Write your twice_as_large function here:
def twice_as_large(num1, num2):
  if num1 > 2 * num2:
    return True
  else:
    return False
# Uncomment these function calls to test your twice_as_large function:
print(twice_as_large(10, 5))
# should print False
print(twice_as_large(11, 5))
# should print True

# Write your large_power function here:
def large_power(base, exponent):
  if ((base ** exponent) > 5000):
    return True
  else:
    return False
  
# Uncomment these function calls to test your large_power function:
print(large_power(2, 13))
# should print True
print(large_power(2, 12))
# should print False

# Write your divisible_by_ten function here:
def divisible_by_ten(num):
  if ((num % 10) == 0):
    return True
  else:
    return False
  


# Uncomment these function calls to test your divisible_by_ten function:
print(divisible_by_ten(20))
# should print True
print(divisible_by_ten(25))
# should print False

# Write your max_num function here:
def max_num(num1, num2, num3):
  if (num1 > num2) and (num1 > num3):
    return num1
  elif (num2 > num1) and (num2 > num3):
    return num2
  elif (num3 > num1) and (num3 > num2):
    return num3
  elif (num1 == num2) or (num1 == num3) or (num2 == num3):
    return "It's a tie!"
  
# Uncomment these function calls to test your max_num function:
print(max_num(-10, 0, 10))
# should print 10
print(max_num(-10, 5, -30))
# should print 5
print(max_num(-5, -10, -10))
# should print -5
print(max_num(2, 3, 3))
# should print "It's a tie!"

BETTER CODE------------------------
# Write your max_num function here:
def max_num(num1, num2, num3):
  if num1 > num2 and num1 > num3:
    return num1
  elif num2 > num1 and num2 > num3:
    return num2
  elif num3 > num1 and num3 > num2:
    return num3
  else:
    return "It's a tie!"
# Uncomment these function calls to test your max_num function:
print(max_num(-10, 0, 10))
# should print 10
print(max_num(-10, 5, -30))
# should print 5
print(max_num(-5, -10, -10))
# should print -5
print(max_num(2, 3, 3))
# should print "It's a tie"

# Write your over_budget function here:
def over_budget(budget, food_bill, electricity_bill, internet_bill, rent):
  if (budget < food_bill + electricity_bill + internet_bill + rent):
    return True
  else:
    return False
  
# Uncomment these function calls to test your over_budget function:
print(over_budget(100, 20, 30, 10, 40))
# should print False
print(over_budget(80, 20, 30, 10, 30))
# should print True

MY CODE -----------------------------
def ground_shipping_cost(weight):
  if weight <= 2:
    return weight * 1.5 + 20
  elif weight <= 6:
    return weight * 3 + 20
  elif weight <= 10:
    return weight * 4 + 20
  else: 
    return weight * 4.75 + 20
  
premium_ground_shipping = 125

def drone_shipping_cost(weight):
  if weight <= 2:
    return weight * 4.5
  elif weight <= 6:
    return weight * 9
  elif weight <= 10:
    return weight * 12
  else: 
    return weight * 14.25
  
def cheapest_shipping_cost(weight):
  if (ground_shipping_cost(weight) < premium_ground_shipping) and (ground_shipping_cost(weight) < drone_shipping_cost(weight)):
    return print("the cheapest shipping method is ground and it costs " +str((ground_shipping_cost(weight))))
  elif (premium_ground_shipping < ground_shipping_cost(weight)) and (premium_ground_shipping < drone_shipping_cost(weight)):
    return print("the cheapest shipping method is premium and it costs " +str((premium_ground_shipping)))
  else:
    return print("The cheapest shipping method is drone and it costs " +str(drone_shipping_cost(weight)))
  
  
cheapest_shipping_cost(2)
    
BETTER CODE ------------------------
def ground_shipping(weight):
  if weight <= 2:
    price_per_pound = 1.5
  elif weight <= 6:
    price_per_pound = 3
  elif weight <= 10:
    price_per_pound = 4
  else:
    price_per_pound = 4.75
    
  return 20 + (price_per_pound * weight)

print(ground_shipping(8.4))

shipping_cost_premium = 125

def drone_shipping(weight):
  if weight <= 2:
    price_per_pound = 4.5
  elif weight <= 6:
    price_per_pound = 9
  elif weight <= 10:
    price_per_pound = 12
  else:
    price_per_pound = 14.25
    
  return (price_per_pound * weight)

print(drone_shipping(1.5))

def cheapest_shipping_method(weight):
  
  ground = ground_shipping(weight)
  premium = shipping_cost_premium
  drone = drone_shipping(weight)
  
  if (ground < premium) and ground < drone:
    method = "standard ground"
    cost = ground
  elif premium < ground and premium < drone:
    method = "premium ground"
    cost = premium
  else: 
    method = "drone"
    cost = drone
    
  
  print("The cheapest option available is $%.2f with %s shipping."
       % (cost, method)
       )

cheapest_shipping_method(4.8)
cheapest_shipping_method(41.5)
cheapest_shipping_method(2)

