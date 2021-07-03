# filepath
findReadWrite
# FileReadWrite.py

#Functions for checking  if a file exits, read from the file write from the file


from io import DEFAULT_BUFFER_SIZE
import os


def fileExists(filePath):
    exists = os.path.exists(filePath)
    return exists


def writeFile(filePath, textToWrite):
    fileHandle = open(filePath, "w")  # w stands for write
    fileHandle.write(textToWrite)
    fileHandle.close()


def readFile(filePath):
    if not fileExists(filePath):
        print("The file," + filePath + "does not exist - cannot read it.")
        return ''

    fileHandle = open(filePath, "r")  # r means read
    data = fileHandle.read()
    fileHandle.close()
    return data

#previous code from filereadwrite pasted here

DATA_FILE_PATH = 'TestData.txt' #path to the file as a constant

stringToWriteOutToFile = "something new" #could be anything,




writeFile(DATA_FILE_PATH, stringToWriteOutToFile)

stringReadInFromFile = readFile(DATA_FILE_PATH)
print('Read in', stringReadInFromFile)

