'''
Get necessary user input from the Console.

There is NO need to modify this file.

Created on Sep 22, 2011

@author: rcd, modified Jan 30, 2015 by shr
'''
import os
import Transforms 

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
    entries = os.listdir(datadir)
    for i,file in enumerate(entries):
        print "%d\t%s" % (i+1, file)
    choice = int(raw_input("enter choice> "))
    if 0 < choice <= len(entries):
        return open(os.path.join(datadir, entries[choice-1]), "r")
    return None


def choose_file_to_save ():
    """
    prompt for new file, user enters name, 
      return file (open for writing)
      return None if user makes bad choice
    """
    filename = raw_input("enter name of file to save output> ")
    try:
        return open(datadir+filename, "w")
    except:
        return None


def choose_transform ():
    """
    prompt for a transform, 
      return a transform (a function that accepts one string and returns a string)
      return None if user makes bad choice
    """
    for i,func in enumerate(xformFuncs):
        print "%d\t%s" % (i+1, func.func_doc.split("\n")[0])
    choice = int(raw_input("enter choice> "))
    if 0 < choice <= len(xformFuncs):
        return xformFuncs[choice-1]
    return None
