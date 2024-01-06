first of all you can import the libraries for GUI and Internet speed

from tkinter import *                   #pip install tk
import speedtest                       #pip install speedtest-cli


# function for check download and Upload the mbps
def speedcheck():
    sp=speedtest.Speedtest()
    sp.get_servers()
    down=str(round(sp.download()/(10**6),3))+"Mbps"
    up=str(round(sp.upload()/(10**6),3))+"Mbps"
    lab_down.config(text=down)
    lab_up.config(text=up)
    # print(down)
    # print(up)

# then create GUI with specified your screen size and your need
sp=Tk()
sp.title("Internet Speed Test")
sp.geometry("500x500")
sp.config(bg="black")

# creating the Labels

lab=Label(sp,text="Internet Speed",font=("Time New Roman",25,"bold"),bg="black",fg="red")
lab.place(x=67,y=40,height=30,width=380)

lab=Label(sp,text="Download Speed",font=("Time New Roman",15,"bold"),bg="black",fg="blue")
lab.place(x=30,y=100,height=30,width=180)

lab_down=Label(sp,text="00",font=("Time New Roman",25,"bold"),bg="black",fg="green")
lab_down.place(x=35,y=150,height=30,width=180)

lab=Label(sp,text="Upload Speed",font=("Time New Roman",15,"bold"),bg="black",fg="blue")
lab.place(x=220,y=100,height=30,width=380)

lab_up=Label(sp,text="00",font=("Time New Roman",25,"bold"),bg="black",fg="green")
lab_up.place(x=225,y=150,height=30,width=380)

# Create the Button


button1=Button(sp,text="Check Speed",command=speedcheck,font=("Time New Roman",25,"bold"),bg="black",fg="yellow",relief=RAISED)
button1.place(x=125,y=250,height=30,width=280)






sp.mainloop()




# if __name__==__main__:
#     root=Tk()
