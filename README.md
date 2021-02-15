# python_assignment
import re

def Grocery_list():
    
    user_name = input('Enter your name:').capitalize()
    
    # phone number verification
while True:
    try:
        user_phone = int(input('Please enter a valid phone-number: +234-'))
    except ValueError:
        print('invalid number')
        continue

    if len(str(user_phone)) == 10:
        break
    else:
        continue

# email address verification

user_email = ' '
while True:
    # a regular expression for validating an Email
    regex = '^[a-z0-9]+[\._]?[a-z0-9]+[@]\w+[.]\w{2,3}$'
    
    user_email = input('Enter a valid email address: ')

    try:
        if re.search(regex, user_email):
            break
    except ValueError:
        print("Invalid Email")


Grocery_list()

grocery_list = {}

grocery_history = []

stop = False

while not stop:

  name = input("item name:\n")

  quantity = input("Quantity purchased:\n")

  cost = input("Price per Item:\n")

  grocery_item = {'item_name':name, 'quantity':int(quantity),'cost':float(cost)}

  grocery_history.append(grocery_item)

  response = input("Would you like to enter another item?\n Type 'c' for continue or 'q' to quit:\n")

  if response == 'q':
    stop = True

grand_total = 0

for item in grocery_history:
  item_total = item['quantity'] * item['cost']

  grand_total += item_total

  print("%d %s @ N%.2f total N%.2f" %(item['quantity'], item['item_name'], item['cost'], item_total))

  item_total = 0

print("Grand total: N%.2f" % grand_total)
