# Asha_ML_TASK1
+*In[2]:*+
[source, ipython3]
----
##Question-1:Writing a Python code to find factorial of given number without using in built function.
import time

#Taking input number into a variable
input_num = int(input("Please give input number to find its factorial: "))
print("Input number given is: ", input_num)
x = input_num
fact = 1

#Logic to find factorial of number with using inbuilt function 'fact()'
for counter in range(input_num,0,-1):
    fact = fact * counter

time.sleep(1)
#Output is stored in fact variable
print("\nThe factorial of ", input_num, "is: ", fact)
----


+*Out[2]:*+
----
Please give input number to find its factorial: 4
Input number given is:  4

The factorial of  4 is:  24
----


+*In[10]:*+
[source, ipython3]
----
##Q2.Return the relation to Luke Skywalker if given any name as input
##Improveised the given problem

#Main function
person_name = input("What is my name? ")

#Function to get their relation with Luke
def relation_to_Luke(name):
    if (name == 'Darth Vader'):
        return("I am your father", name)
    elif (name == 'Leia'):
        return("I am your sister", name)
    elif (name == 'Han'):
        return("I am your brother in law", name)
    elif (name == 'R2D2'):
        return("I am your droid", name)
    else:
        name = "non of your relation"
        return("I am a stranger", name)
if __name__ == "__main__":
    relation, person_name = relation_to_Luke(person_name)
    print("Luke! I am "+person_name+". "+relation)
----


+*Out[10]:*+
----
What is my name? Darth Vader
Luke! I am Darth Vader. I am your father
----


+*In[14]:*+
[source, ipython3]
----
##Q3.Without using inbuilt function, find the number of digits of a number

in_num = int(input("Enter any non zero positive number to find its number of digits: "))

def digits_calc(num):
    digit = 0
    while (num != 0):
        digit += 1
        num //= 10 ##integer division
    return digit

if __name__ == "__main__":
    Number_of_digits = digits_calc(in_num)
    print("The number of digits of a given number ", in_num, " is: ", Number_of_digits)

----


+*Out[14]:*+
----
Enter any non zero positive number to find its number of digits: 789321456987
The number of digits of a given number  789321456987  is:  12
----


+*In[15]:*+
[source, ipython3]
----
##Q4.Multiplication of Factorial of any given number without using inbuilt functions

in_num = int(input("Enter any number to find its multiplication of factorial: "))

def prod_fact(num):
    prod = 1
    while (num > 1):
        fact = 1
        for counter in range(num,0,-1):
            fact = fact*counter
        prod = prod*fact
        num -= 1
    return prod

if __name__ == "__main__":
    result = prod_fact(in_num)
    print("The multiplication of factorials of " + str(in_num) + " is: " + str(result))
----


+*Out[15]:*+
----
Enter any number to find its multiplication of factorial: 7
The multiplication of factorials of 7 is: 125411328000
----


+*In[19]:*+
[source, ipython3]
----
##Q5.Program to find sum of squares of given inputs without using built-in functions a2 + b2 + c2 ...

num_in = int(input("Enter the number of inputs for which you are going to calculate: "))
in_list = []

for cnt in range(num_in, 0, -1):
    in_num = int(input("Enter the value" + str(num_in-cnt+1) + ": "))
    in_list.append(in_num)

print("The collection of given inputs: ",in_list)

def sum_squares(list_):
    sum_ = 0
    for list_item in list_:
        square = list_item * list_item
        sum_ = sum_ + square
    return sum_

if __name__ == "__main__":
    result = sum_squares(in_list)

    #print("The sum of sqares of given input list of items is: ", result)
    for i in in_list:
        print('sqr(' + str(i) + ')+', end = '')
    print("...= ", result)
----


+*Out[19]:*+
----
Enter the number of inputs for which you are going to calculate: 6
Enter the value1: 1
Enter the value2: 2
Enter the value3: 3
Enter the value4: 4
Enter the value5: 5
Enter the value6: 6
The collection of given inputs:  [1, 2, 3, 4, 5, 6]
sqr(1)+sqr(2)+sqr(3)+sqr(4)+sqr(5)+sqr(6)+...=  91
----


+*In[21]:*+
[source, ipython3]
----
##Q6.Function to find operation between operators

operand_1 = int(input("Please enter the value of operand1: "))
operand_2 = int(input("Please enter the value of operand2: "))
operator = input("Please enter the type of operation to do between operand_1 and operand_2: ")

def operation(op1,op2,op):
    if op == '+':
        return(op1 + op2)
    elif op == '-':
        return(op1 - op2)
    elif op == '*':
        return(op1 * op2)
    elif op == '/':
        return(op1 / op2)


if __name__ == "__main__":
    result = operation(operand_1,operand_2,operator)
    print("Operation ", "'", operator, "'", "between ", operand_1, "and", operand_2, " is: ", result)
----


+*Out[21]:*+
----
Please enter the value of operand1: 6
Please enter the value of operand2: 3
Please enter the type of operation to do between operand_1 and operand_2: *
Operation  ' * ' between  6 and 3  is:  18
----


+*In[28]:*+
[source, ipython3]
----
##Q7.Print strings as per given inputs

in_num = int(input("Enter a numeric positive integer: "))
print("The given number is: ", in_num, '\n')

def print_string(num):
    count = 1
    
    while count<=num:
        if count%2 == 1:
            print("I CAN\t", end='')
        else:
            print("I WILL\t",end='')
        count += 1

    
print_string(in_num)

----


+*Out[28]:*+
----
Enter a numeric positive integer: 4
The given number is:  4 

I CAN	I WILL	I CAN	I WILL	----


+*In[30]:*+
[source, ipython3]
----
##Q8.Determine the number of pair of each glove with matching color

list_ = [num for num in input("Enter the item based on color of gloves seperated by comma: ").split(',')]

str_list = [str(item) for item in list_]
print("Given items based on colors are: ", str_list)


def count_pairs(list_):
    pair = 0
    unpair = 0
    up_list = []
    for item in list_:
        if item not in up_list:
            up_list.append(item)
    print("Unique items among the given list are: ",up_list)

    for item in up_list:
        cnt = 0
        for i in list_:
            if item == i:
                cnt += 1
        print("\nThe number of", item, "in the given list is: ", cnt)
        print("The number of pair of", item, "in the given list is: ", cnt//2)
        pair = pair + cnt//2
        print("The number of unpaired ", item, "in the given list is: ", cnt%2)
        unpair = unpair + cnt%2
    return pair, unpair

if __name__ == "__main__":
    pair, unpair = count_pairs(list_)
    print("\nThe total number of pairs is: ", pair)
    print("The total number of odd gloves left is: ", unpair)
----


+*Out[30]:*+
----
Enter the item based on color of gloves seperated by comma: red,yellow,pik,red,pik
Given items based on colors are:  ['red', 'yellow', 'pik', 'red', 'pik']
Unique items among the given list are:  ['red', 'yellow', 'pik']

The number of red in the given list is:  2
The number of pair of red in the given list is:  1
The number of unpaired  red in the given list is:  0

The number of yellow in the given list is:  1
The number of pair of yellow in the given list is:  0
The number of unpaired  yellow in the given list is:  1

The number of pik in the given list is:  2
The number of pair of pik in the given list is:  1
The number of unpaired  pik in the given list is:  0

The total number of pairs is:  2
The total number of odd gloves left is:  1
----


+*In[32]:*+
[source, ipython3]
----
##Q9.Find if the array formed by combining two lists is in sequence
import time

list1 = []
list1 = [int(item) for item in (input("Enter only list of items in first list seperating items by comma: ")).split(',')]
list2 = []
list2 = [int(item) for item in (input("Enter only list of items in second list seperating items by comma: ")).split(',')]

print("\nThe first given list is: ", list1)
print("The second given list is: ", list2)

time.sleep(2)

def consecutive_combo(l1,l2):
    list_ = l1 + l2
    list_.sort()
    print('\nCombined list of given lists: ', list_)
    
    for counter in range(0,len(list_)-1,1):
        diff = list_[counter+1]-list_[counter]
    
        if diff != 1:
            return "\nFalse! The combined list is not in order"
        else:
            continue
        
    return "\nTrue! The combined list is in order"

if __name__ == "__main__":
    time.sleep(2)
    result = consecutive_combo(list1, list2)
    time.sleep(2)
    print(result)
----


+*Out[32]:*+
----
Enter only list of items in first list seperating items by comma: 1,5,9
Enter only list of items in second list seperating items by comma: 6,8,3

The first given list is:  [1, 5, 9]
The second given list is:  [6, 8, 3]

Combined list of given lists:  [1, 3, 5, 6, 8, 9]

False! The combined list is not in order
----


+*In[33]:*+
[source, ipython3]
----
##Q10.Find the profit for given dictionary
data = {
    "cost price": 32.67,
    "sell price": 45.00,
    "inventory":  1200}

print("The profit per unit is: ", data["sell price"] - data["cost price"]) #profit_per_unit
approx_value = round((data["sell price"] - data["cost price"])* data["inventory"])
print("The accurate total profit for whole inventory ignoring all other assumptions is:", (data["sell price"] - data["cost price"])* data["inventory"])
print("\nThe approximate total profit for whole inventory ignoring all other assumptions is:", approx_value)

----


+*Out[33]:*+
----
The profit per unit is:  12.329999999999998
The accurate total profit for whole inventory ignoring all other assumptions is: 14795.999999999998

The approximate total profit for whole inventory ignoring all other assumptions is: 14796
----


+*In[ ]:*+
[source, ipython3]
----

----
