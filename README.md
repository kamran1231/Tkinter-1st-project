# Tkinter-1st-project

import tkinter as tk
from tkinter import ttk


root = tk.Tk()
root.geometry('500x400+200+100')
root.title('kamran khan')

#create Label for name:
label_name = ttk.Label(root,text = 'Enter your Name: ')
label_name.grid(row = 1,column = 0,sticky = tk.W)

#create Label for age:
label_age = ttk.Label(root,text = 'Enter your Age: ')
label_age.grid(row = 2, column = 0,sticky = tk.W)

#create Label for Qualification:
label_qualification = ttk.Label(root,text = 'Enter your Qualification: ')
label_qualification.grid(row = 3, column = 0,sticky = tk.W)

#create Label for Email:
label_email = ttk.Label(root,text = 'Enter your Email: ')
label_email.grid(row = 4, column = 0,sticky = tk.W)

#create Label to Gender:
label_gender = ttk.Label(root,text = 'Select your Gender: ')
label_gender.grid(row = 5,column = 0,sticky = tk.W)

#create EnterBox for name:
name_var = tk.StringVar()
name_Entrybox = ttk.Entry(root,width = 20,textvariable = name_var)
name_Entrybox.grid(row = 1,column = 1)
name_Entrybox.focus()

#create EntryBox for Age:
age_var = tk.IntVar()
age_Entrybox = ttk.Entry(root,width = 20,textvariable = age_var)
age_Entrybox.grid(row = 2,column = 1)

#create EntryBox for Qualification:
qualification_var = tk.StringVar()
qualification_Entrybox = ttk.Entry(root,width = 20,textvariable = qualification_var)
qualification_Entrybox.grid(row = 3,column = 1)

#create EntryBox for Email:
email_var = tk.StringVar()
email_Entrybox = ttk.Entry(root,width = 20,textvariable = email_var)
email_Entrybox.grid(row = 4,column = 1)

#ComboBox for Gender:
combo_var = tk.StringVar()
combobtn1 = ttk.Combobox(root,width = 17,state = 'readonly',textvariable = combo_var)
combobtn1['values'] = ('Male','Female','Other')
combobtn1.current(0)
combobtn1.grid(row = 5,column = 1)

#RadioButton for userType:
userType_var = tk.StringVar()
radiobutton1 = ttk.Radiobutton(root,text = 'Student',value = 'Student',variable = userType_var)
radiobutton1.grid(row = 0,column = 0)
radiobutton2 = ttk.Radiobutton(root,text = 'Teacher',value = 'Teacher',variable = userType_var)
radiobutton2.grid(row = 0,column = 1)

#checkBox button

chkbtn_var = tk.IntVar()
checkBox1 = ttk.Checkbutton(root,text = 'Please Subscribe my channel',variable = chkbtn_var)
checkBox1.grid(row = 6, column = 0,columnspan = 2)




#Submit Button:
def action():
    usertype = userType_var.get()
    username = name_var.get()
    userage = age_var.get()
    useremail = email_var.get()
    userQualification = qualification_var.get()
    userGender = combo_var.get()
    print(f'Name: {username}\nAge: {userage}\nEmail: {useremail}\nQualification: {userQualification}'
          f'\nType: {usertype} \nGender Type: {userGender}')

    if chkbtn_var.get() == 0:
        subscribed = 'No Subscriptiom'
    else:
        subscribed = 'subscribed Done!'

    print(f'{subscribed}')



submit_btn = ttk.Button(root,text = 'Submit',command = action)
submit_btn.grid(row = 7,column = 0)






root.mainloop()
