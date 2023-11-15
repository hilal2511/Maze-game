import random

directions= ["L", "R", "U", "D"]
swords= 3
potion= 3
point= 0
print("******************************")
print("You are in the middle of a maze.")
while True:
    print("******************************")
    print("\nWhere to go?")
    userDirection= input("\nLeft[L] Right[R] Up[Up] Down[D]: ")

    if userDirection in directions:
        event= random.choice(["Monster", "Potion", "Treasure", "Empty Road"])

        if event == "Monster":
            if swords== 0:
                print(f"A {event}!")
                print("You die. No swords left.")
                print(f"\nYou lost. Game ends. Your points: {point}")
                break
            else:
                swords -= 1
                point += 1
                print(f"A {event}!")
                print(f"You saved yourself with a sword.")
                print(f"\nPoints: {point}")
        if event== "Potion":
            if potion== 0:
                print(f"A {event}!")
                print("You die. No potion left!")
                print(f"\nYou lost. Game ends. Your points: {point}")
                break
            else:
                potion -= 1
                point += 1
                print(f"A {event}!")
                print(f"You saved yourself with a potion.")
                print(f"\nPoints: {point}")
        if event== "Treasure":
            point += 2
            print(f"A {event}! \nYou have earned 2 point.")
            print(f"Points: {point}")
        if event== "Empty Road":
            point += 1
            print(f"A {event}! \nYou have earned 1 point.")
            print(f"\nPoints: {point}")
    else:
        print("You should have entered valid direction!")
        print(f"You have collected {point} point so far.")
        print("Bye!")
        break 

