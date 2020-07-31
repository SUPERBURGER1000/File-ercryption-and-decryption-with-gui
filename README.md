# File-ercryption-and-decryption-with-gui
this file ercryption has gui and aui and a music inthe end for fun


from cryptography.fernet import Fernet
from playsound import playsound
import speech_recognition as sr
import tkinter as tk
from tkinter import filedialog, Text
import os


root=tk.Tk()
apps = []


def write_key():

    key = Fernet.generate_key()
    with open("key.key", "wb") as key_file:
        key_file.write(key)

def load_key():

    return open("key.key", "rb").read()

def encrypt(filename, key):
     f = Fernet(key)
with open(filename, "rb") as file:
    file_data = file.read()
    encrypted_data = f.encrypt(file_data)
with open(filename, "wb") as file:
        file.write(encrypted_data)
    
def decrypt(filename, key):
    f = Fernet(key)
with open(filename, "rb") as file:
        encrypted_data = file.read()
decrypted_data = f.decrypt(encrypted_data)
with open(filename, "wb") as file:
        file.write(decrypted_data)
a=str(input("Do u want to write or speak?")
if a == "write" :
      def addApp():
    fileName = filedialog.askopenfilename(initialdir="/", title="Select File",
                                         filetypes=(("executables","*.exe"),("all files","*.*")))
    apps.append(fileName)
    print(fileName)
    canvas = tk.Canvas(root, height=700, width=700, bg="#263D42")
    canvas.pack()

    frame = tk.Frame(root, bg="white")
    frame.place(relwidth=0.8, relheight=0.8, relx=0.1, rely=0.1)

    openFile = tk.Button(root,text="Open File", padx=10, pady=5, fg="white", bg="#263D42")

    openFile.pack()


    RunApp = tk.Button(root,text="RunApp", padx=10, pady=5, fg="white", bg="#263D42")

    RunApp.pack()

    root.mainloop()

    file=fileName
    encrypt(file, key)
    playsound("Downloads\loud-version_7n1qEm2 (2).mp3")
     print ("do you want to decrypt the data? tell yes or no")
    l=()
    if l= yes:
                  decrypt(file,key)
    playsound("Downloads\loud-version_7n1qEm2 (2).mp3")      
            

else:
        
    with sr.Microphone() as source:
     print("Please tell us the file name :")
     audio = r.listen(source)
      try:
            text = r.recognize_google(audio)
            print("we heard this : {}".format(text))
        except:
            print("Sorry could not recognize what you said")
     v= str(input("are u confirmed with the file? please tell yes or no)
     if v= "yes" :             
      file = text
    encrypt(file, key)
    playsound("//Desktop/shot-on-iphone.mp3")             
    print ("do you want to decrypt the data? tell yes or no")
    l=()
    if l= 'yes':
                  decrypt(file,key)
    playsound("//Desktop/shot-on-iphone.mp3")  
