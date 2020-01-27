"""
Date: 200127
Authors: Or, Jonathan, Damian
Description: Main responsible for the loop
"""
ID = 0
TARGET_TIME = 1
EXECUTED = 2
ACTION = 3
CONDITION = 4
DATE_FORMAT = "%Y%m%d%H%M%S"


import csv
import datetime
import time
import os

def looper():
    with open("looper.txt","r") as looperFile1:
        while(looperFile1.readline() is "loop"):
            readSources()
            readRecords()
            time.sleep(60)


def readSources():

def addRecord():

def execute():

def readRecords():
    now1 = datetime.datetime.now().strftime(DATE_FORMAT)
    now1 = now1[2:len(now1)]
    print(now1)
    with open("taskMail1.csv",'r') as file1:
        csv1 = csv.reader(file1, delimiter=',')
        csv_w1 = csv.writer(file1, delimiter=',')
        line_count = 0
        for row in csv1:
            if line_count == 0:
                print(f'Column names are {", ".join(row)}')
                line_count += 1
            else:
                message1 = "id: " + row[ID] + " | target time: " + row[TARGET_TIME]
                #print(message1)
                line_count += 1
                diff1 = int(row[TARGET_TIME]) - int(now1)
                print("row: "+str(line_count)+" |diff1: " + str(diff1) + " | condition: " + row[CONDITION])
                if diff1 < 100 and row[CONDITION] is "1":
                    print("Action: " + row[ACTION])
                    action1 = row[ACTION]
                    os.system(action1)
                    #csv_w1[line_count][EXECUTED] = "1"
        print("Finished.")

readRecords()