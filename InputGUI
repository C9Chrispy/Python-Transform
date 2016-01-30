'''
Get necessary user input from series of GUI dialogs.

There is NO need to modify this file.

Created on Sep 22, 2011

@author: rcd, modified Jan 30, 2015 by shr
'''
import os
import Transforms,base64
import tkFileDialog, tkSimpleDialog
import Tkinter


# single instance of GUI
root = Tkinter.Tk()    
# folder where data files are stored
datadir = os.getcwd()+"/../data/"
# available transform functions
xformFuncs = [getattr(Transforms, x) for x in dir(Transforms) if x.startswith("transform_")]



def choose_file_to_open ():
    """
    prompt for existing file, 
      return the file (open for reading)
      return None if user makes bad choice
    """
    return tkFileDialog.askopenfile(title="choose file",
                                    initialdir=datadir)


def choose_file_to_save ():
    """
    prompt for new file, user enters name, 
      return file (open for writing)
      return None if user makes bad choice
    """
    return tkFileDialog.asksaveasfile(title="save file",
                                      initialdir=datadir)


class MyDialog(tkSimpleDialog.Dialog):
    selection = Tkinter.IntVar()
    def body(self, master):
        for i,func in enumerate(xformFuncs):
            b = Tkinter.Radiobutton(master, text=func.func_doc.split("\n")[0], variable=self.selection, value=(i+1))
            b.pack(anchor=Tkinter.W)

def choose_transform ():
    """
    prompt for a transform, 
      return a transform (a function that accepts one string and returns a string)
      return None if user makes bad choice
    """
    choice = MyDialog(root, title="choose transform").selection.get()
    if 0 < choice <= len(xformFuncs):
        return xformFuncs[choice-1]
    return None
