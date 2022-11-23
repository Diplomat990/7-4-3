
#import modules

import random

def quiz():
    print('Welcome to sunderland mathematical quiz')
    
    take_test = input('Do you want to test your mathematical powers : ').title()#This code ask the user if they are interested in taking the quiz.

    if take_test != 'Yes': #if the player answer is not equal to yes , then the programme quits using quits(), if yes prog would continue to run.
        quit() #end prog if the player does not want to play.#This checkx if the user typed in yes and continue the programme or No to end the prog
    player_name = input('State your name genius : ').title()
    print ('hello ' + player_name)


    from random import randrange as r #this line of code ensures that the questions asked are generated randomly within a range


    while True: #This while statement checks that the user enter a correct value , which has to be an interger
        try:
            no_questions = int(input('How many questions do you want to answer : '))# The player can indicate how many questions they want to answer.
            break #if the player enters a non interger value the programme breaks and prints the below line  'Please input numbers only'
        except:
            print('Please input numbers only')
    while True:  #This while statement checks that the user enter a correct value , which has to be an interger
        try:     
            max_num = int(input('Highest number intended to play : ')) #This indicates the number highest number the player wants the mathematical question to be  
            break #if the player enters a non interger value the programme breaks and prints the below line  'Please input numbers only'
        except:
            print('Please input numbers only')   
       
    score = 0 #The score count is set to 0 so it can be incremented and stored to keep a record of how many anwers the player got correctly.

    answer_list = [] # This show player the question to be answered


#loop through number of questions
    for q in range (no_questions):
        num1 = r(1, max_num+1)
        num2 = r(1, max_num+1)
        ans = num1 * num2 #multiplies the 2 variables num1 and numb2 to ask user a question 
        u_ans = int(input((f'{num1} X {num2}')))
        if u_ans == ans: #checks that the player got the answer correctly.
            score += 1 #increment the player score each time they get an answer correctly
    print(f'Thank you for playing!  \n{player_name} got {score} out of {no_questions} ({round(score/no_questions*100)})%') #this uses the 'f' format prints out the player name , score, percentage , n/also shows the numbers they got correctly

#code below ask if a new player would be interested in taking the quiz
#create a while loop to continue to ask new users to play
playagain = 'yes' 
while playagain == 'yes': 
    quiz() #runs the quiz from the beginning if a new player types in yes to play.
    print('New player interested in testing their mathematical genius? (yes or no)')
    playagain = input()