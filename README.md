from colorama import Fore
def replay():
    
    return input(Fore.GREEN + 'Do you want to play again? Enter Yes or No: ').lower().startswith('y')

def batting(name1,name2):

            balls = 60
            ballsBat = 0
            playerRuns = 0
            print(Fore.CYAN + f"-----------------------------------\n{name1} is batting\n")
            while ballsBat < balls:
                Runs = int(getpass.getpass(Fore.YELLOW + f"{name1} Enter a number to bat: "))
                Bowl =int(getpass.getpass(Fore.YELLOW + f"{name2} Enter a number to bowl: ")) 
                
                if Runs==Bowl:
                    print(Fore.RED + f"{name1} number is {Runs}, {name2}number is {Bowl}")
                    print(Fore.RED + f"{name1} are Out. {name1} total score is {playerRuns}\n")
                    break
                elif Runs>6:
                    print(Fore.RED + "ERROR 408 :( , PLEASE TRY INPUTTING A NUMBER BELOW 7")
                    continue
                elif Bowl>6:
                    print(Fore.RED + "ERROR 408 :( , PLEASE TRY INPUTTING A NUMBER BELOW 7")
                    continue
                else:
                    playerRuns += Runs
                    print(Fore.GREEN + f"{name1} number: {Runs}, {name2} number: {Bowl}")
                    print(Fore.GREEN + f"{name1} runs now are {playerRuns}\n")
                
                ballsBat += 1
            print(f"-----------------------------------\n{name2}\n")
            balls2 = 60
            ballsBat2 = 0
            Runs2 = 0
            while ballsBat2 < balls2:
                Bat2 =int(getpass.getpass(Fore.YELLOW + f"{name2} Enter a number to bat: ")) 
                bowl2 = int(getpass.getpass(Fore.YELLOW + f"{name1} Enter a number to bowl: "))
                
                if Bat2 == bowl2:
                    print(Fore.RED + f"{name2} number is {Bat2}, {name1} number is {bowl2}")
                    print(Fore.RED + f"{name2} is Out. {name2}'s total runs are {Runs2}")
                    break
                elif Runs>6:
                    print(Fore.RED + "ERROR 408 :( , PLEASE TRY INPUTTING A NUMBER BELOW 7")
                    continue
                elif Bowl>6:
                    print(Fore.RED + "ERROR 408 :( , PLEASE TRY INPUTTING A NUMBER BELOW 7")
                    continue
                else:
                    Runs2 += Bat2
                    print(Fore.GREEN + f"{name2}'s number is {Bat2}, {name1} number is {bowl2}")
                    print(Fore.GREEN + f"{name2}'s score is {Runs2}\n")
                    
                    if Runs2 > playerRuns:
                        break
                ballsBat2 += 1
                
            print("-----------------------------------\nRESULTS: ")
                
            if Runs2 < playerRuns:
                print(Fore.GREEN + f"\n{name1} have wow the game. \n\n{name1} total runs are {playerRuns} in {ballsBat} balls and the {name2} scored {Runs2} in {ballsBat2} bowls")
            elif Runs2 == playerRuns:
                print(Fore.YELLOW + f"The game is a tie, {name1} score {playerRuns} and the {name2} also scored {Runs2}")
            else:
                print(Fore.GREEN + f"\n{name2} won the game.\n\n{name2}'s total runs are {Runs2} in {ballsBat2} bowls, and {name1} score {playerRuns}")

import getpass 
p1=input(Fore.CYAN + 'Enter player 1 name')
p2=input(Fore.CYAN + 'Enter player 2 name')
print(Fore.MAGENTA + f'Welcome to hand cricket {p1} and {p2}')
while True:
    SumValue = "junk"
    oddoreven= input(Fore.GREEN + f"Welcome to the toss, {p1} please choose either odd(o) or even(e):\n").lower()
    if oddoreven!='o' and oddoreven!='e':
        print(Fore.RED + 'INVALID input choose either odd(o) or even(e) ONLY')
        continue
    toss1= int(getpass.getpass(f"{p1} choose a number between 1 and 6"))
    toss2= int(getpass.getpass(f"{p2} choose a number between 1 and 6"))
    if (toss1>6 or toss1<1):
        print(Fore.RED + "Invalid Input, ERROR 402 :(")
        continue
    elif (toss2>6 or toss2<1):
        print(Fore.RED + "Invalid Input, ERROR 402 :(")
        continue
    else:
        print(Fore.CYAN + f"{p1} chose {toss1} and the {p2} chose {toss2}")
        sumToss = toss1 + toss2
        if (sumToss%2) == 0:
                SumValue = "e"
                print(Fore.RED + "It's even")
        else:
                SumValue = "o"   
                print(Fore.RED + "It's odd")
    if SumValue == oddoreven:
        batbowl = input(f"{p1} have won the toss, would you like to bat(b) or bowl(bo)")
        if batbowl=='b':
            batting(p1,p2)
        elif batbowl=='bo': 
            batting(p2,p1)
    
    else:
        batbowl = input(f"{p2} have won the toss, would you like to bat(b) or bowl(bo)")
        if batbowl=='b':
            batting(p2,p1)
        elif batbowl=='bo':
            batting(p1,p2)
    if not replay():
        print(Fore.GREEN + 'Thank you for Playing!')
        break

