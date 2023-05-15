# age-calculator
ABOUT:
The Age Calculator In Python is a simple project
developed using Python. The project is for the user
convenient, to help them find out about their exact age in
year, month and days. The project file contains a python
script ( Age_Calculator_GUI.py). This is a simple GUI-
base project which is very easy to understand and use.
Also, this project makes a convenient way for the user to
discover the exact age.
This simple project is in Python. Talking about the
features of this system, this python application is
designed to calculate the age of the uses. So, you can
simply enter the birth date, and given date in day, month,
and year in the text fields and click ‘Resultant Age’
button. It is capable of handling all types of exceptions.

Also, the design of this system is pretty simple so
that the user won’t get any difficulties while working on
it.

SOURCE CODE:
# import all functions from the tkinter
from tkinter import *
#import Message Box module
from tkinter import messagebox
#import the Themed tk module
from tkinter import ttk
#import the time date module
from datetime import date
# Function for clearing the
# contents of all text entry boxes
def clearAll() :
# deleting the content from the entry box
dayField.delete(0, END)
monthField.delete(0, END)
yearField.delete(0, END)
givenDayField.delete(0, END)
givenMonthField.delete(0, END)
givenYearField.delete(0, END)
rsltDayField.delete(0, END)
rsltMonthField.delete(0, END)
rsltYearField.delete(0, END)

# function for checking error
def checkError() :

# if any of the entry field is empty
# then show an error message and clear
# all the entries
if (dayField.get() == &quot;&quot; or monthField.get() == &quot;&quot;
or yearField.get() == &quot;&quot; or givenDayField.get() == &quot;&quot;
or givenMonthField.get() == &quot;&quot; or givenYearField.get() == &quot;&quot;) :
# show the error message
messagebox.showerror(&quot;Input Error&quot;)
# clearAll function calling
clearAll()
return -1
#Function to Calculate the age
def calculateAge():
#check for error
value = checkError()

#if there is a error then value will be - 1
if value==-1:
return
else:
# take a value from the respective entry boxes
# get method returns current text as string
birth_day = int(dayField.get())
birth_month = int(monthField.get())
birth_year = int(yearField.get())
given_day = int(givenDayField.get())
given_month = int(givenMonthField.get())
given_year = int(givenYearField.get())

# if birth date is greater then given birth_month
# then donot count this month and add 30 to the date so
# as to subtract the date and get the remaining days
month =[31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
if (birth_day &gt; given_day):
given_month = given_month - 1
given_day = given_day + month[birth_month-1]

# if birth month exceeds given month, then
# donot count this year and add 12 to the
# month so that we can subtract and find out
# the difference
if (birth_month &gt; given_month):
given_year = given_year - 1
given_month = given_month + 12
# calculate day, month, year
calculated_day = given_day - birth_day;
calculated_month = given_month - birth_month;
calculated_year = given_year - birth_year;
# calculated day, month, year write back
# to the respective entry boxes
# insert method inserting the
# value in the text entry box.
rsltDayField.insert(10, str(calculated_day))
rsltMonthField.insert(10, str(calculated_month))
rsltYearField.insert(10, str(calculated_year))

#The Driver Code

if __name__ == &#39;__main__&#39;:
#Creating the GUI window
root = Tk()
#Setting the background color
root.config(background=&#39;light green&#39;)
#Setting the name of the GUI applications
root.title(&#39;Age Calculator&#39;)
#Setting the geometry of the GUI application
root.geometry(&#39;525x260&#39;)
#Create the Date of birth : Label
dob = Label(root, bg = &#39;blue&#39;)
#Create the Given Date : Label
givenDate = Label(root, text=&#39;Given Date&#39;, bg = &#39;blue&#39;)
#Create the Given Date : Label
birthDate = Label(root, text=&#39;Birth Date&#39;, bg = &#39;blue&#39;)
# Create a Day : label
day = Label(root, text = &#39;Day&#39;, bg = &#39;light green&#39;)
# Create a Month : label
month = Label(root, text = &#39;Month&#39;, bg = &#39;light green&#39;)
# Create a Year : label
year = Label(root, text = &#39;Year&#39;, bg = &#39;light green&#39;)
# Create a Given Day : label
givenDay = Label(root, text = &quot;Given Day&quot;, bg = &quot;light green&quot;)
# Create a Given Month : label
givenMonth = Label(root, text = &quot;Given Month&quot;, bg = &quot;light green&quot;)

# Create a Given Year : label
givenYear = Label(root, text = &quot;Given Year&quot;, bg = &quot;light green&quot;)
# Create a Years : label
rsltYear = Label(root, text = &quot;Years&quot;, bg = &quot;light green&quot;)
# Create a Month : label
rsltMonth = Label(root, text = &quot;Month&quot;, bg = &quot;light green&quot;)
# Create a Days : label
rsltDay = Label(root, text = &quot;Days&quot;, bg = &quot;light green&quot;)
# Create a text entry box for filling or typing the information.
dayField = Entry(root)
monthField = Entry(root)
yearField = Entry(root)
givenDayField = Entry(root)
givenMonthField = Entry(root)
givenYearField = Entry(root)
rsltYearField = Entry(root)
rsltMonthField = Entry(root)
rsltDayField = Entry(root)
# rsltYearField = Entry(root)
# rsltMonthField = Entry(root)
# rsltDayField = Entry(root)
# Create a Resultant Age Button and attached to calculateAge function
resultantAge = Button(root, text = &quot;Resultant Age&quot;, fg = &quot;Black&quot;, bg = &quot;Red&quot;,
command = calculateAge)
# Create a Clear All Button and attached to clearAll function
clearAllEntry = Button(root, text = &quot;Clear All Output&quot;, fg = &#39;Black&#39;, bg = &#39;Red&#39;,
command = clearAll)

# grid method is used for placing
# the widgets at respective positions
# in table like structure .
dob.grid(row = 0, column = 1)
day.grid(row = 1, column = 0)
dayField.grid(row = 1, column = 1)
month.grid(row = 2, column = 0)
monthField.grid(row = 2, column = 1)
year.grid(row = 3, column = 0)
yearField.grid(row = 3, column = 1)
givenDate.grid(row = 0, column = 4)
birthDate.grid(row = 0, column = 1)
givenDay.grid(row = 1, column = 3)
givenDayField.grid(row = 1, column = 4)
givenMonth.grid(row = 2, column = 3)
givenMonthField.grid(row = 2, column = 4)
givenYear.grid(row = 3, column = 3)
givenYearField.grid(row = 3, column = 4)
resultantAge.grid(row = 4, column = 2)
rsltYear.grid(row = 5, column = 2)
rsltYearField.grid(row = 6, column = 2)
rsltMonth.grid(row = 7, column = 2)
rsltMonthField.grid(row = 8, column = 2)
rsltDay.grid(row = 9, column = 2)
rsltDayField.grid(row = 10, column = 2)

clearAllEntry.grid(row = 12, column = 2)

# Start the GUI
root.mainloop()

OUTPUT:

OUTPUT WITH USER INPUT:
