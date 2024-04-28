from tkinter import *
from tkinter import messagebox
import openpyxl as xl

data = []
windows = Tk()
windows.geometry('900x650')
windows.title('GameNet Calculator')
windows.maxsize(900, 650)
windows.minsize(900, 650)
background = PhotoImage(file='D:/pythonProject/Game Net/tlos.png')
my_label = Label(windows, image=background)
my_label.place(x=0, y=0, relwidth=1, relheight=1)

# LABELS:
label1 = Label(text="Enter your time:", fg='white', bg='black')
label2 = Label(text="Device Number 1:", fg='white', bg='black')
label3 = Label(text="Enter your time:", fg='white', bg='black')
label4 = Label(text="Device Number 2", fg='white', bg='black')
label5 = Label(text="Enter your time:", fg='white', bg='black')
label6 = Label(text="Device Number 3", fg='white', bg='black')
label7 = Label(text="Enter your time:", fg='white', bg='black')
label8 = Label(text="Device Number 4", fg='white', bg='black')
label9 = Label(text="Enter your time:", fg='white', bg='black')
label10 = Label(text="Device Number 5", fg='white', bg='black')
label11 = Label(text="Enter your time:", fg='white', bg='black')
label12 = Label(text="Device Number 6", fg='white', bg='black')
label1.place(x=100, y=50)
label2.place(x=135, y=20)
label3.place(x=400, y=50)
label4.place(x=435, y=20)
label5.place(x=700, y=50)
label6.place(x=735, y=20)
label7.place(x=100, y=350)
label8.place(x=135, y=320)
label9.place(x=400, y=350)
label10.place(x=435, y=320)
label11.place(x=700, y=350)
label12.place(x=735, y=320)

# OUTPUT LABEL:
answer1 = Label(text='', fg='white', bg='black')
answer1.place(x=150, y=250)

answer2 = Label(text='', fg='white', bg='black')
answer2.place(x=450, y=250)

answer3 = Label(text='', fg='white', bg='black')
answer3.place(x=750, y=250)

answer4 = Label(text='', fg='white', bg='black')
answer4.place(x=150, y=550)

answer5 = Label(text='', fg='white', bg='black')
answer5.place(x=450, y=550)

answer6 = Label(text='', fg='white', bg='black')
answer6.place(x=750, y=550)


# BUTTON:
def calculator6():
    hour_input = int(inputs1.get())
    minute_input = int(inputs2.get())
    hour_output = int(inputs3.get())
    minute_output = int(inputs4.get())

    if minute_input > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    elif minute_output > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass
    if hour_input > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    elif hour_output > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass

    if hour_output < hour_input:
        hour_output = hour_output + 24

    answer = ((((hour_output * 60) + minute_output) - ((hour_input * 60) + minute_input)) * 100)
    remaining = answer % 1000
    answer = answer - remaining
    if remaining <= 250:
        remaining = 0
        answer = answer + remaining
    elif 250 < remaining <= 500:
        remaining = 500
        answer = answer + remaining
    elif 500 <= remaining < 750:
        remaining = 500
        answer = answer + remaining
    elif 750 >= remaining > 1000:
        remaining = 1000
        answer = answer + remaining
    answer6.config(text=str(answer))
    text = answer1.cget("text")
    data.append(int(text))
    if cal2:
        inputs1.delete(0, END),
        inputs2.delete(0, END),
        inputs3.delete(0, END),
        inputs4.delete(0, END)


cal2 = Button(text='Calculate', command=calculator6, fg='white', bg='black')
cal2.place(x=750, y=500)


def calculator5():
    vorodis = int(inputdp1.get())
    vorodid = int(inputdp2.get())
    khorojis = int(inputdp3.get())
    khorojid = int(inputdp4.get())

    if vorodid > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    elif khorojid > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass
    if vorodis > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    elif khorojis > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass

    if khorojis < vorodis:
        khorojis = khorojis + 24

    javab = ((((khorojis * 60) + khorojid) - ((vorodis * 60) + vorodid)) * 100)
    baqim = javab % 1000
    javab = javab - baqim
    if baqim <= 250:
        baqim = 0
        javab = javab + baqim
    elif 250 < baqim <= 500:
        baqim = 500
        javab = javab + baqim
    elif 500 <= baqim < 750:
        baqim = 500
        javab = javab + baqim
    elif 750 >= baqim > 1000:
        baqim = 1000
        javab = javab + baqim
    answer5.config(text=str(javab))
    text = answer1.cget("text")
    data.append(int(text))
    if cal2:
        inputdp1.delete(0, END),
        inputdp2.delete(0, END),
        inputdp3.delete(0, END),
        inputdp4.delete(0, END)


cal2 = Button(text='محاسبه', command=calculator5, fg='white', bg='black')
cal2.place(x=450, y=500)


def mohasebe4():
    vorodis = int(inputdc1.get())
    vorodid = int(inputdc2.get())
    khorojis = int(inputdc3.get())
    khorojid = int(inputdc4.get())

    if vorodid > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    elif khorojid > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass
    if vorodis > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    elif khorojis > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass

    if khorojis < vorodis:
        khorojis = khorojis + 24

    javab = ((((khorojis * 60) + khorojid) - ((vorodis * 60) + vorodid)) * 100)
    baqim = javab % 1000
    javab = javab - baqim
    if baqim <= 250:
        baqim = 0
        javab = javab + baqim
    elif 250 < baqim <= 500:
        baqim = 500
        javab = javab + baqim
    elif 500 <= baqim < 750:
        baqim = 500
        javab = javab + baqim
    elif 750 >= baqim > 1000:
        baqim = 1000
        javab = javab + baqim
    answer4.config(text=str(javab))
    text = answer1.cget("text")
    data.append(int(text))
    if cal2:
        inputdc1.delete(0, END),
        inputdc2.delete(0, END),
        inputdc3.delete(0, END),
        inputdc4.delete(0, END)


cal2 = Button(text='محاسبه', command=mohasebe4, fg='white', bg='black')
cal2.place(x=150, y=500)


def mohasebe3():
    vorodis = int(inputds1.get())
    vorodid = int(inputds2.get())
    khorojis = int(inputds3.get())
    khorojid = int(inputds4.get())

    if vorodid > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    elif khorojid > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass
    if vorodis > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    elif khorojis > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass

    if khorojis < vorodis:
        khorojis = khorojis + 24

    javab = ((((khorojis * 60) + khorojid) - ((vorodis * 60) + vorodid)) * 100)
    baqim = javab % 1000
    javab = javab - baqim
    if baqim <= 250:
        baqim = 0
        javab = javab + baqim
    elif 250 < baqim <= 500:
        baqim = 500
        javab = javab + baqim
    elif 500 <= baqim < 750:
        baqim = 500
        javab = javab + baqim
    elif 750 >= baqim > 1000:
        baqim = 1000
        javab = javab + baqim
    answer3.config(text=str(javab))
    text = answer1.cget("text")
    data.append(int(text))
    if cal2:
        inputds1.delete(0, END),
        inputds2.delete(0, END),
        inputds3.delete(0, END),
        inputds4.delete(0, END)


cal2 = Button(text='محاسبه', command=mohasebe3, fg='white', bg='black')
cal2.place(x=750, y=200)


def mohasebe2():
    vorodis = int(inputdd1.get())
    vorodid = int(inputdd2.get())
    khorojis = int(inputdd3.get())
    khorojid = int(inputdd4.get())

    if vorodid > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    elif khorojid > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass
    if vorodis > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    elif khorojis > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass

    if khorojis < vorodis:
        khorojis = khorojis + 24

    javab = ((((khorojis * 60) + khorojid) - ((vorodis * 60) + vorodid)) * 100)
    baqim = javab % 1000
    javab = javab - baqim
    if baqim <= 250:
        baqim = 0
        javab = javab + baqim
    elif 250 < baqim <= 500:
        baqim = 500
        javab = javab + baqim
    elif 500 <= baqim < 750:
        baqim = 500
        javab = javab + baqim
    elif 750 >= baqim > 1000:
        baqim = 1000
        javab = javab + baqim
    answer2.config(text=str(javab))
    text = answer1.cget("text")
    data.append(int(text))
    if cal2:
        inputdd1.delete(0, END),
        inputdd2.delete(0, END),
        inputdd3.delete(0, END),
        inputdd4.delete(0, END)


cal2 = Button(text='محاسبه', command=mohasebe2, fg='white', bg='black')
cal2.place(x=450, y=200)


def mohasebe1():
    vorodis = int(inputdy1.get())
    vorodid = int(inputdy2.get())
    khorojis = int(inputdy3.get())
    khorojid = int(inputdy4.get())

    if vorodid > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    elif khorojid > 59:
        messagebox.showerror("Minutes is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass
    if vorodis > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    elif khorojis > 23:
        messagebox.showerror("Hour is wrong!", "Please enter a number between 0 and 59!")
    else:
        pass

    if khorojis < vorodis:
        khorojis = khorojis + 24

    javab = ((((khorojis * 60) + khorojid) - ((vorodis * 60) + vorodid)) * 100)
    baqim = javab % 1000
    javab = javab - baqim
    if baqim <= 250:
        baqim = 0
        javab = javab + baqim
    elif 250 < baqim <= 500:
        baqim = 500
        javab = javab + baqim
    elif 500 <= baqim < 750:
        baqim = 500
        javab = javab + baqim
    elif 750 >= baqim > 1000:
        baqim = 1000
        javab = javab + baqim
    answer1.config(text=str(javab))
    text = answer1.cget("text")
    data.append(int(text))
    if cal2:
        inputdy1.delete(0, END),
        inputdy2.delete(0, END),
        inputdy3.delete(0, END),
        inputdy4.delete(0, END)


cal1 = Button(text='محاسبه', command=mohasebe1, fg='white', bg='black')
cal1.place(x=150, y=200)

# INPUT LABEL:
inputs1 = Entry(windows)
inputs1.place(x=725, y=400, width=40, height=25)
inputs2 = Entry(windows)
inputs2.place(x=775, y=400, width=40, height=25)
inputs3 = Entry(windows)
inputs3.place(x=725, y=450, width=40, height=25)
inputs4 = Entry(windows)
inputs4.place(x=775, y=450, width=40, height=25)

inputdp1 = Entry(windows)
inputdp1.place(x=425, y=400, width=40, height=25)
inputdp2 = Entry(windows)
inputdp2.place(x=475, y=400, width=40, height=25)
inputdp3 = Entry(windows)
inputdp3.place(x=425, y=450, width=40, height=25)
inputdp4 = Entry(windows)
inputdp4.place(x=475, y=450, width=40, height=25)

inputdc1 = Entry(windows)
inputdc1.place(x=125, y=400, width=40, height=25)
inputdc2 = Entry(windows)
inputdc2.place(x=175, y=400, width=40, height=25)
inputdc3 = Entry(windows)
inputdc3.place(x=125, y=450, width=40, height=25)
inputdc4 = Entry(windows)
inputdc4.place(x=175, y=450, width=40, height=25)

inputds1 = Entry(windows)
inputds1.place(x=725, y=100, width=40, height=25)
inputds2 = Entry(windows)
inputds2.place(x=775, y=100, width=40, height=25)
inputds3 = Entry(windows)
inputds3.place(x=725, y=150, width=40, height=25)
inputds4 = Entry(windows)
inputds4.place(x=775, y=150, width=40, height=25)

inputdd1 = Entry(windows)
inputdd1.place(x=425, y=100, width=40, height=25)
inputdd2 = Entry(windows)
inputdd2.place(x=475, y=100, width=40, height=25)
inputdd3 = Entry(windows)
inputdd3.place(x=425, y=150, width=40, height=25)
inputdd4 = Entry(windows)
inputdd4.place(x=475, y=150, width=40, height=25)

inputdy1 = Entry(windows)
inputdy1.place(x=125, y=100, width=40, height=25)
inputdy2 = Entry(windows)
inputdy2.place(x=175, y=100, width=40, height=25)
inputdy3 = Entry(windows)
inputdy3.place(x=125, y=150, width=40, height=25)
inputdy4 = Entry(windows)
inputdy4.place(x=175, y=150, width=40, height=25)

windows.mainloop()

def excel_processor(name):
    wb = xl.load_workbook(name)
    sheet = wb["Sheet1"]

    for i, value in enumerate(data, start=2):
        sheet.cell(row=2, column=i, value=value)
    wb.save(name)


excel_processor("Data.xlsx")

