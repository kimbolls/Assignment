# Assignment
Group assignment ( Sport System )
print   ("Welcome to Uniten Sports Complex Court Rental System")
stations = """
List of Stations
1. Futsal
2. Sepak Takraw
3. Basketball
4. Badminton
"""

print stations
court_num = 0
while court_num <1 or court_num >4:
    try:
        court_num = int(raw_input("Please select the court you would like to book by inserting the relevant number : "))

    except ValueError:
        print ("You must enter a number")

    

    while court_num >4 or court_num <1:
        try:
            court_num = int(raw_input("Please enter only a NUMBER that is assigned to a court : "))

        except ValueError:
            print ("You must enter a number")     

if court_num == 1:
    court_selected = 'Futsal'

elif court_num ==2:
    court_selected = 'Sepak Takraw'

elif court_num == 3:
    court_selected = 'Basketball'

elif court_num == 4:
    court_selected = 'Badminton'
   

print "You inserted number : " , court_num ,",", court_selected


status = raw_input("Are you a Uniten Student? (Type Yes or No) : ")

if status == 'yes' or status == 'Yes' or status == 'YES':
    status = 'student'

elif status == 'no' or status == 'No' or status == 'NO':
    status = 'public'

else:
    status == raw_input("Please enter only 'Yes' or 'No' : ")


day = raw_input("When would you like to book the court , mention the day only : ")

print "You choose " , day , " as option."

hour = input("How many hours would you like to book/rent the court(Kindly type numbers only):  ")
            
if day == 'saturday' or day == 'sunday':
                week = 'weekend'

else:
    week = 'weekdays'

if court_num == 1 and status == 'student' and week == 'weekdays':
    payment_cost = hour * 50

elif court_num == 1 and status == 'public' and week == 'weekdays':
    payment_cost = hour * 60

elif court_num == 1 and status == 'student' and week == 'weekend':
    payment_cost = hour * 50

elif court_num == 1 and status == 'public' and week == 'weekend':
    payment_cost = hour * 80

#Payment for futsal ONLY

if court_num == 2 and status == 'student' and week == 'weekdays':
    payment_cost = hour * 20

elif court_num == 2 and status == 'public' and week == 'weekdays':
    payment_cost = hour * 60

elif court_num ==  2 and status == 'student' and week == 'weekend':
    payment_cost = hour * 25

elif court_num == 2 and status == 'public ' and week == 'weekend':
    payment_cost = hour * 65

#Payment for Sepak Takraw ONLY

if court_num == 3 and status == 'student' and week == 'weekdays':
    payment_cost = hour * 55

elif court_num == 3 and status == 'public' and week == 'weekdays':
    payment_cost = hour * 65

elif court_num ==  3 and status == 'student' and week == 'weekend':
    payment_cost = hour * 55

elif court_num == 3 and status == 'public ' and week == 'weekend':
    payment_cost = hour * 85


#Payment for Basketball ONLY

if court_num == 4 and status == 'student' and week == 'weekdays':
    payment_cost = hour * 30

elif court_num == 4 and status == 'public' and week == 'weekdays':
    payment_cost = hour * 60

elif court_num ==  4 and status == 'student' and week == 'weekend':
    payment_cost = hour * 35

elif court_num == 4 and status == 'public ' and week == 'weekend':
    payment_cost = hour * 65

#Payment for Badminton ONLY

print "             Rental Details          "
print "Court : " , court_num
print "Uniten Student or Public :" , status
print "Day : " , day
print "Hours : " , hour
print "Total amount you need to pay : " , payment_cost

#Summary

balance = payment_cost

while balance > 0:
    print "Amount of balance you need to pay remaining : " , balance
    payment_given = input("Please insert amount of payment : ")
    if payment_given < 0:
        print "Please enter a positive number .."
    else:
        balance = balance - payment_given      

if balance < 0:
    print " Your balance is : ", abs(balance)

    
print "Thank you for your payment! "

raw_input("")

