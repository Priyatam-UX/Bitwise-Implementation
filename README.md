# Bitwise-Implementation
Logic gates implmented with help of python (GUI) 
Let’s look at each of the logic gates in Python in detail with some easy examples.

All of us are quite familiar while implementing logic gates in the processing of electrical signals and are widely used in the electrical and electronics industry. They are used in the diodes and transistors so that we can design by proper alignment of these electronic devices. In this article we will learn about the implementation of some basic gates ‘and‘, ‘or‘ ,’not‘ , ‘nand‘ ,’nor‘ in Python 3.x or earlier.

These gates can be implemented by using user-defined functions designed in accordance with that of the truth table associated with the respective gate.

from tkinter import *
top=Tk()
res = 0
tfprs = ""
def and1(a,b):
    global res
    res = int(a and b)
def or1(a,b):
    global res
    res  = int(a | b)
def not1(a):
    global res
    res = int(not a)
def xor1(a,b):
    global res
    res = int((a and not b) or (not a and b))
def result(event=None):
    global top,res,E3
    text = StringVar()
    E3=Entry(top,textvariable=text,bd=5)
    E3.grid(row=4,column=1)
    text.set(str(res))
def exit1(top):
    top.destroy()
def exit2(top):
    top.destroy()
def selected():
    global tfprs
    tfprs = var.get()
def expl(a,b):
    global top,tfprs,res
    binary1 = StringVar()
    binary2 = StringVar()
    top1=Toplevel(top)
    value1 = IntVar()
    l1=Label(top1,text="Number 1").grid(row=0,column=0)
    e1=Entry(top1,textvariable = value1,bd=5)
    value1.set(a)
    e1.grid(row=0,column=1)
    e3=Entry(top1,textvariable = binary1,bd=5)
    l3=Label(top1,text="Binary Number 1").grid(row=0,column=2)
    binary1.set(format(a,'b'))
    e3.grid(row=0,column=3)
    value2 = IntVar()
    l2=Label(top1,text="Number 2").grid(row=1,column=0)
    e2=Entry(top1,textvariable = value2,bd=5)
    value2.set(b)
    e2.grid(row=1,column=1)
    l4=Label(top1,text="Binary Number 2").grid(row=1,column=2)
    e4=Entry(top1,textvariable = binary2,bd=5)
    binary2.set(format(b,'b'))
    e4.grid(row=1,column=3)
    l5=Label(top1,text="t.f.p.r.s").grid(row=2,column=2) #says text from previous radiobutton selection
    operator = StringVar()
    e5=Entry(top1,textvariable = operator,bd=5)
    operator.set(tfprs)
    operator.set(tfprs)
    e5.grid(row=2,column=3)
    dres = IntVar()
    l6=Label(top1,text="Decimal Result").grid(row=3,column=1)
    e6=Entry(top1,textvariable = dres ,bd=5)
    dres.set(res)
    e6.grid(row=3,column=2)
    b1=Button(top1,bd=5,text="Exit",command=lambda top=top1:exit2(top1)).grid(row=4,column=0)
    top.mainloop()
def dotwo(a,b):
    selected()
    expl(a,b)

num1 = IntVar()
L1=Label(top,text="Number 1").grid(row=0,column=0)
E1=Entry(top,textvariable = num1,bd=5)
num1.set(1)
E1.grid(row=0,column=1)
num2 = IntVar()
L2=Label(top,text="Number 2").grid(row=0,column=2)
E2=Entry(top,textvariable =num2,bd=5)
num2.set(1)
E2.grid(row=0,column=3)
var=StringVar()

R1=Radiobutton(top,text="AND",variable=var,value="AND",command=lambda: and1(int(E1.get()),int(E2.get())))
R1.grid(row=1,column=0)
R2=Radiobutton(top,text="OR",variable=var,value="OR",command=lambda: or1(int(E1.get()),int(E2.get())))
R2.grid(row=1,column=1)
R3=Radiobutton(top,text="NOT",variable=var,value="NOT",command=lambda: not1(int(E1.get())))
R3.grid(row=2,column=0)
R4=Radiobutton(top,text="XOR",variable=var,value="XOR",command=lambda: xor1(int(E1.get()),int(E2.get())))
R4.grid(row=2,column=1)
label=Label(top)
label.grid()

B1=Button(top,text="Result is:",command=result,bd=5)
B1.grid(row=3,column=0)
B2=Button(top,text="Explanation",command=lambda:dotwo(int(E1.get()),int(E2.get())),bd=5)
B2.grid(row=3,column=1)
B3=Button(top,bd=5,text="Exit",command=lambda top=top:exit1(top)).grid(row=3,column=2)
L3=Label(top,text="Result is:").grid(row=4,column=0)
E3=Entry(top,bd=5)
E3.grid(row=4,column=1)
top.mainloop()
