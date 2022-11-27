from tkinter import * 

def calcBmi():
    height = float(heightEntry.get())
    height *= height
    weight = float(weightEntry.get())
    bmi = round(weight/height,2)

   
    outputLabel = Label(resultFrame,text=bmi,font='Times 24',)
    outputLabel.place(x=250,y=400)
    outputLabel.pack()

    if bmi <= 18.5:
        rangeLabel = Label(window,text='Under Weight',font='Times 24')
        rangeLabel.place(x=150,y=500)
    elif bmi > 18.5 and bmi < 24.9:
        rangeLabel = Label(window,text='Healthy Weight',font='Times 24')
        rangeLabel.place(x=150,y=500)
    elif bmi > 25 and bmi < 29.9:
        rangeLabel = Label(window,text='Over Weight',font='Times 24')
        rangeLabel.place(x=150,y=500)
    elif bmi >= 30:
        rangeLabel = Label(window,text='Obese',font='Times 24')
        rangeLabel.place(x=150,y=500)

window = Tk()
window.title('Body Mass Index')
window.geometry('600x600')


title = Label(window,text='Calculate your Body Mass Index',font='Times 24 underline')
title.place(x=70,y=100)

weightLabel = Label(window,text='Weight:',font=('Calibri',18))
weightLabel.place(x=180,y=200)

heightLabel = Label(window,text='Height:',font=('Calibri',18))
heightLabel.place(x=180,y=250)

weightEntry = Entry(window,text='',bd=1,width=5)
weightEntry.place(x=260,y=210)

heightEntry = Entry(window,text='',bd=1,width=5)
heightEntry.place(x=260,y=260)

weightUnit = Label(window,text='Kg',font=('Calibri',18))
weightUnit.place(x=290,y=200)
heightUnit = Label(window,text='m',font=('Calibri',18))
heightUnit.place(x=290,y=250)

resultFrame = LabelFrame(window,text='BMI:',font=('Calibri',24))
resultFrame.pack(padx=50,pady=50) #packs the data on the window
resultFrame.place(x=200,y=400)

calculateBtn = Button(text='Calculate',bd=2,command=calcBmi)
calculateBtn.place(x=240,y=300)



window.mainloop()