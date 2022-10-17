# My Most Recent Education 

I am currently a junior at the *Universivty of Missouri* studying Information Technology! I've Been at Mizzou for a full year now and I've enjoyed most of it! I feel like I
am finally finding my college friends and really making my mark on the university. I really enjoy Information Technology because I have been doing it for over 4 years now
since joining the militray. I hope to get a job in cyber security and continue working in the IT field. 

## Before College 

Before I went to Mizzou, I spent a full year at the *Cyber Center of Excellence* in Fort Gorden, Georgia. Where I learned a lot about information technology and the way 
computers worked. 

![Snapchat-770054518](https://user-images.githubusercontent.com/115883101/196245032-a8f4a3d9-3a52-47de-b91b-fbd8d4e64437.jpg)

### After Graduation from Fort Gorden

I spent a semester at the *University of Central Missouri* learning the basics of [python](https://www.python.org/). Where I
created this:

```
#import random 
import random

#create def for print options 
def printOptions():
    
    #print the menu
    print("What would you like to do? \n")
    print("1. Play Again")
    print("2. View Statistics")
    print("3. Quit\n")
    
    #ask user to enter choice 
    choice = int(input("Enter choice: "))
    return choice

#create def for load game
def loadGame():
    
    #ask user to enter name 
    userName = input("Enter your name: ")

    try:
        #open the file in read mode
        fin = open(userName + ".rps","r")

        #create results
        results = {"name": "", "wins": 0, "loss": 0, "tie": 0}
        i = 0
        for line in fin:
            if i is 0:
                
                #strip line and get name
                results['name'] = line.strip()
            elif i is 1:
                
                #get the wins
                results['wins'] = int(line)
            elif i is 2:
                
                #get the loss
                results['loss'] = int(line)
            elif i is 3:
                
                #get the tie
                results['tie'] = int(line)
            i = i + 1

        return results

    except:
        print("Hello" +userName+ "your game file does not found")
        result = loadGame()
        return results
  
#create def for quit game
def quitGame(results):
    
    #create a file with user name
    fout = open(results["name"]+".rps","w")
    
    #write data into the file
    fout.write(results['name']+"\n"+str(results['wins'])+"\n"
               +str(results['loss'])+"\n"+str(results['tie']))
    
    #close the file
    fout.close()
    print(results['name']+", your game has been saved.")

#create def for print stat
def printStats(total,results):
    
    #print the name
    print(results['name']+", here are your game play statistics...")

    #print number of wins, looses, and ties
    print("Wins: "+str(results['wins']))
    print("Losses: "+str(results['loss']))
    print("Ties: "+str(results['tie']))

    #if the loss is 0, then the ratio is 0
    if results['loss'] is 0:
        print ("\nWin/Loss Ratio: 0")
        
    #otherwise, find and print the ratio
    else:
        print("\nWin/Loss Ratio: "+str(round(results['wins']/results['loss'],2)))
        
    #call print option 
    temp = printOptions()
    if temp is 1:
        
        #call play game 
        playGame(total + 1, results)
    elif temp is 2:
        
        #call print stat
        printStats(total,results)
    elif temp is 3:
        
        #call quit game
        quitGame(results)
    else:
        print("Enter a valid entry")
        
        #call print stat again 
        printStatistics(total,results)
      
#create def fucntion
def getValue(x):
    if x is 1:
        return "Rock"
    elif x is 2:
        return "Paper"
    elif x is 3:
        return "Scissors"

#create def function and compare values with user and comp
def winnerWinner(user,comp):
     if user is 1 and comp is 2:
         return "comp"
     elif user is 1 and comp is 3:
         return "user"
     elif user is 2 and comp is 1:
         return "user"
     elif user is 2 and comp is 3:
         return "comp"
     elif user is 3 and comp is 1:
         return "comp"
     elif user is 3 and comp is 2:
         return "user"
     else:
         return "tie"

#create def for play game 
def playGame(total,results):
    
    #print round number
    print("Round "+str(total))
    
    #print menu with spacing
    print("\n1. Rock")
    print("2. Paper")
    print("3. Scissors\n")
    
    #read the input
    choice = int(input("What will it be? "))
    
    #if choice is between 1 and 3
    if choice <= 3 and choice >= 1:
        
        #create a random val between 1 and 3
        computerValue = random.randint(1,3)
        print(computerValue)
        
        #call winner winner 
        winner = winnerWinner(choice,computerValue)
        
        #creat if statment for user winning 
        if winner is "user":
            print("You chose "+getValue(choice)+". The computer chose "
                  +getValue(computerValue)+". You win!")
            
            #update the wins of the user
            results['wins'] = results['wins'] + 1
            
        #create elif if computer wins 
        elif winner is "comp":
            print("You chose " + getValue(choice) + ". The computer chose "
                  + getValue(computerValue) + ". You lose!")
            
            #update the loss of the users
            results['loss'] = results['loss'] + 1
            
        #create elif if tie
        elif winner is "tie":
            print("You chose " + getValue(choice) + ". The computer chose "
                  + getValue(computerValue) + ". Game Tied")
            
            #update the tie of the user
            results['tie'] = results['tie'] + 1
            
    #else statement if invaild number is entered 
    else:
        print("Please enter a number that is in the range 1 to 3")
        
        #play the game again
        playGame(total,results)
        
    #call print options
    temp = printOptions()
    if temp is 1:
        
        playGame(total+1,results)
    elif temp is 2:
        
        printStats(total,results)
    elif temp is 3:
        
        quitGame(results)
    else:
        print("Enter a valid choice!")

#creat def for start new game
def NewGame():
    
    #read the name
    name = input("What is your name? ")
    
    #print the message
    print("Hello "+name+". Let's Play!")
    
    #assign the values to result
    result = {"name":name,"wins":0,"loss":0,"tie":0}
    
    #call play game 
    playGame(1,result)

#create welcome prompt 
print("Welcome to Rock, Paper, Scissors!")
print()
print("1. Start New Game")
print("2. Load Game")
print("3. Quit")
print("")

#ask user input 
option = int(input("Enter choice: "))

#create if-elif statment 
if option is 1:
    NewGame()
    
#create elif statment for option 2 
elif option is 2:
    
    #call load game fuction 
    results = loadGame()
    
    #print the result
    print("Welcome back, "+results["name"]+" let's play again!")
    
    #find the sum of wins, loss, and ties
    total = results['wins'] +results+['loss'] + results['tie']
    
    #call the function print option 
    temp = printOptions()
    if temp is 1:
    
        playGame(total + 1, results)
    elif temp is 2:
        
        #call print stat
        printStatistics(total, results)
    elif temp is 3:
        
         #call the function quit game
        quitGame(results)
    else:
        print("Enter a valid choice!")
       
```

After that, I later transfered to Mizzou and continuted studying Information Technology. So far at Mizzou I've 
learned:

- **Cyber Security**
- **Java**
- **Networking**

If you'd like to continue learning about me, reread the page, or go back to the [home page](README.md), please click one!

- [Learn About Me!](AboutMe.md)
- [Learn About My Work!](MyWork.md)
- [Learn About My Travels!](Travels.md)
- [Learn About My Education!](Education.md)
- [Learn About My Interests!](MyInterests.md)

 
