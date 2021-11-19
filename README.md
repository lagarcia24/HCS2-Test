import os
import time
import random
def clearConsole():
    command = 'clear'
    if os.name in ('nt', 'dos'):
        command = 'cls'
    os.system(command)
print("---MyBelen---\n")
print("---Teacher Edition---\n\n---Computer Science Class---\n")
def randomGrade():
    ranGrade = random.randint(50, 105)
    return ranGrade
def randomGPA():
    ranGPA = random.uniform(0, 4)
    return round(ranGPA, 2)
megaList = []
def profileInfo():
    myList = []
    name = str(input("Name: "))
    gender = str(input("Gender(M/F): "))
    year = str(input("Year(9-12): "))
    if year == "9":
        myList.extend([["Biology", randomGrade()], ["Computer Science", randomGrade()], ["Geometry", randomGrade()], ["World History", randomGrade()], ["English", randomGrade()], ["Theology", randomGrade()], ["Spanish", randomGrade()]])
    if year == "10":
        myList.extend([["Chemistry", randomGrade()], ["Computer Science", randomGrade()], ["Algebra", randomGrade()], ["US History", randomGrade()], ["American Literature", randomGrade()], ["Theology", randomGrade()], ["Spanish", randomGrade()]])
    if year == "11":
        myList.extend([["Physics", randomGrade()], ["Computer Science", randomGrade()], ["Pre-Calculus", randomGrade()], ["U.S. Government", randomGrade()], ["British Literature", randomGrade()], ["Theology", randomGrade()], ["Art-History", randomGrade()]])
    if year == "12":
        myList.extend([["Philosophy", randomGrade()], ["Computer Science", randomGrade()], ["Mathematics", randomGrade()], ["Latin American History", randomGrade()], ["World Literature" , randomGrade()], ["Theology", randomGrade()], ["Economics", randomGrade()]])
    height_ft = int(input("Height(feet): "))
    height_in = float(input("    (inches): "))
    heightTotal = height_ft + (height_in / 12)
    roundedHeight = str(round(heightTotal, 2))
    print("Height: " + str(roundedHeight) + " feet")
    weight = str(input("Weight(lb): "))
    for i in range(len(myList)):
        print(myList[i][0] + "- " + str(myList[i][1]))
    myGrade = []
    myTotalgpa = []
    for i in range(len(myList)):
        myGrade.append(myList[i][1])
    for j in range(len(myList)):
        if myGrade[j] >= 93.00:
            myTotalgpa.append(4.00)
        elif myGrade[j] >= 90.00 and myGrade[j] < 93.00:
            myTotalgpa.append(3.70)
        elif myGrade[j] >= 87.00 and myGrade[j] < 90.00:
            myTotalgpa.append(3.30)
        elif myGrade[j] >= 83.00 and myGrade[j] < 87.00:
            myTotalgpa.append(3.00)
        elif myGrade[j] >= 80.00 and myGrade[j] < 83.00:
            myTotalgpa.append(2.70)
        elif myGrade[j] >= 77.00 and myGrade[j] < 80.00:
            myTotalgpa.append(2.30)
        elif myGrade[j] >= 73.00 and myGrade[j] < 77.00:
            myTotalgpa.append(2.00)
        elif myGrade[j] >= 70.00 and myGrade[j] < 73.00:
            myTotalgpa.append(1.70)
        elif myGrade[j] >= 67.00 and myGrade[j] < 70.00:
            myTotalgpa.append(1.30)
        elif myGrade[j] >= 65.00 and myGrade[j] < 67.00:
            myTotalgpa.append(1.00)
        elif myGrade[j] < 65.00:
            myTotalgpa.append(0.00)
    addedGPAs = myTotalgpa[0] + myTotalgpa[1] + myTotalgpa[2] + myTotalgpa[3] + myTotalgpa[4] + myTotalgpa[5] + myTotalgpa[6]
    averageGPA = addedGPAs / len(myTotalgpa)
    roundedAveGPA = round(averageGPA, 2)
    if year == "9":
        totalGPA = str(roundedAveGPA)
    if year == "10":
        totalGPA = str(round((roundedAveGPA + randomGPA()) / 2, 2))
    if year == "11":
        totalGPA = str(round((roundedAveGPA + randomGPA() + randomGPA()) / 3, 2))
    if year == "12":
        totalGPA = str(round((roundedAveGPA + randomGPA() + randomGPA() + randomGPA()) / 4, 2))
    print("Average GPA of all years is " + str(totalGPA))
    mainList = [name, gender, year, roundedHeight, weight, myList, totalGPA]
    return mainList

def menuChoice():
    while True:
        print("-" * 25)
        print("What would you like to do")
        print("-" * 25)
        print("[A]dd Student.")
        print("[R]emove Student.")
        print("[E]dit Student.")
        print("[S]earch Students.")
        print("[F]ilter Students.")
        print("[Q]uit")
        choice = input("Choice: ")
        while choice not in ("A", "R", "E", "S", "F", "Q"):
            choice = input("Choice: ")
        print("-" * 25)
        def searchBar():
            if searchCat == "Name":
                indexSearch = 0
            elif searchCat == "Gender":
                indexSearch = 1
            elif searchCat == "Year":
                indexSearch = 2 
            elif searchCat == "Height":
                indexSearch = 3
            elif searchCat == "Weight":
                indexSearch = 4
            elif searchCat == "Class":
                indexSearch = 5
            elif searchCat == "Grade":
                indexSearch = 5
            elif searchCat == "average GPA":
                indexSearch = 6
            searchedOption = str(input("Enter student " + str(searchCat) + ": "))
            print("-" * 25)
            for i in range(len(megaList)):
                if megaList[i][indexSearch] == str(searchedOption) or str(megaList[i][indexSearch][0]) == str(searchedOption) or str(megaList[i][indexSearch][1]) == str(searchedOption):
                    if indexSearch == 0:
                        for j in range(len(megaList[i])):
                            if j == 0:
                                print("-" * 6)
                                print("Name: " + megaList[i][0])
                                print("-" * 6)
                            elif j == 1:
                                print("Gender: " + megaList[i][j])
                            elif j == 2:
                                print("Year: " + str(megaList[i][j]) + "th")
                            elif j == 3:
                                print("Height: " + str(megaList[i][j]) + " feet")
                            elif j == 4:
                                print("Weight: " + str(megaList[i][j]) + " lbs")
                            elif j == 5:
                                for k in range(7):
                                    print(str(megaList[i][j][k][0]) + "- " + str(megaList[i][j][k][1]))
                            elif j == 6:
                                print("Average GPA: " + str(megaList[i][j])) 
                    elif indexSearch == 1 or indexSearch == 2 or indexSearch == 3 or indexSearch == 4 or indexSearch == 6:       
                        for d in range(len(megaList)):
                            if str(megaList[d][indexSearch]) == str(searchedOption):
                                print(megaList[d][0])
                    elif indexSearch == 5:
                        if searchCat == "Grade":
                            print(str(megaList[i][indexSearch][0][0]))
                            for d in range(len(megaList)):
                                if str(megaList[i][indexSearch][d][0]) == str(searchedOption):
                                    print(str(megaList[i][0]))
                        if searchCat == "Class":
                            print(str(megaList[i][indexSearch][0][1]))
                            for d in range(len(megaList)):
                                if str(megaList[i][indexSearch][d][1]) == str(searchedOption):
                                    print(str(megaList[i][0]))
                    break
        if choice == "Q":
            clearConsole()
            print("Turning off")
            time.sleep(1)
            clearConsole()
            print("Turning off.")
            time.sleep(1)
            clearConsole()
            print("Turning off..")
            time.sleep(1)
            clearConsole()
            print("Turning off...")
            time.sleep(1)
            clearConsole()
            time.sleep(3)
            reboot = input("Would you like to reboot?(PRESS ANY KEY): ")
            clearConsole()
            print("Loading")
            time.sleep(1)
            clearConsole()
            print("Loading.")
            time.sleep(1)
            clearConsole()
            print("Loading..")
            time.sleep(1)
            clearConsole()
            print("Loading...")
            time.sleep(2)
            clearConsole()
        elif choice == "A":
            megaList.append(profileInfo())
            print("-" * 6)
            for i in range(len(megaList)):
                print(str(megaList[i][0]))
            print("-" * 6)
            yn = input("continue?(PRESS ANY KEY): ")
            clearConsole()
        elif choice == "S":
            searchCat = "Name"
            searchBar()
            yn = input("continue?(PRESS ANY KEY): ")
            clearConsole()
        elif choice == "F":
            searchCat = input("What category would you like to filter: ")
            print("-" * 25)
            searchBar()
            yn = input("continue?(PRESS ANY KEY): ")
            clearConsole()
        elif choice == "R":
            studentRemove = input("Enter student to remove: ")
            for i in range(len(megaList)):
                if megaList[i][0] == studentRemove:
                    megaList.remove(megaList[i])
                    print("-" * 6)
                    print(studentRemove + " has been removed.")
                    print("-" * 6)
                    break
            yn = input("continue?(PRESS ANY KEY): ")
            clearConsole()
        elif choice == "E":
            editedStudent = str(input("Enter name of student in profile being edited: "))
            for i in range(len(megaList)):
                if str(megaList[i][0]) == editedStudent:
                    editedInfo = str(input("Enter what info will be edited: "))
                    if editedInfo == "Name":
                        indexSearch = 0
                        megaList[i][indexSearch] = str(input("Enter edit: "))
                    elif editedInfo == "Gender":
                        indexSearch = 1
                        megaList[i][indexSearch] = str(input("Enter edit: "))
                    elif editedInfo == "Year":
                        indexSearch = 2
                        megaList[i][indexSearch] = str(input("Enter edit: ")) 
                    elif editedInfo == "Height":
                        indexSearch = 3
                        megaList[i][indexSearch] = str(input("Enter edit: "))
                    elif editedInfo == "Weight":
                        indexSearch = 4
                        megaList[i][indexSearch] = str(input("Enter edit: "))
                    elif editedInfo == "Grade":
                        indexSearch = 5
                        print("As a computer science teacher,\n you can only alter the grade of your class.")
                        megaList[i][indexSearch][1][1] = int(input("Enter grade: "))
                    elif editedInfo == "Class":
                        indexSearch = 5
                        print("As a computer science teacher,\n you can only change the class of the student.")
                        megaList[i][indexSearch][1][0] = str(input("Enter class: "))
                    elif editedInfo == "average GPA":
                        indexSearch = 6
                        megaList[i][indexSearch] = str(input("Enter edit: "))
            yn = input("continue?(PRESS ANY KEY): ")
            clearConsole()
menuChoice()
