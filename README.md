<h1>ExpNo 9: Solve Wumpus World Problem using Python demonstrating Inferences from Propositional Logic</h1> 
<h3>Name: R Anirudh                    </h3>
<h3>Register Number: 212223230016               </h3>
<h3>Date: 23/11/2026               </h3>
<H3>Aim:</H3>
<p>
    To solve  Wumpus World Problem using Python demonstrating Inferences from Propositional Logic
</p>
<h1>Problem Description</h1>
<hr>
<h2>Wumpus World</h2>
<hr>
The Wumpus world is a simple world example to illustrate the worth of a knowledge-based agent and to represent knowledge representation.

The figure below shows a Wumpus world containing one pit and one Wumpus. There is an agent in room [1,1]. The goal of the agent is to exit the Wumpus world alive. The agent can exit the Wumpus world by reaching room [4,4]. The wumpus world contains exactly one Wumpus and one pit. There will be a breeze in the rooms adjacent to the pit, and there will be a stench in the rooms adjacent to Wumpus.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/cd6b68dc-c79f-4dcb-8126-04da90d65912)

<center>Wumpus World Representation</center>
<p>
This is a python program that uses propositional logic sentences to check which rooms are safe. 

It is assumed that there will always be a safe path that the agent can take to exit the Wumpus world. The logical agent can take four actions: Up, Down, Left and Right. These actions help the agent move from one room to an adjacent room. The agent can perceive two things: Breeze and Stench.
</p>

<hr>
<h1>Program:</h1>
<hr>

```py

wumpus = [["Save","Breeze","PIT","Breeze"],
          ["Smell","Save","Breeze","Save"],
          ["WUMPUS","GOLD","PIT","Breeze"],
          ["Smell","Save","Breeze","PIT"]]

row = 0
column = 0
arrow = True
player = True
score = 0

while player:
    choice = input("press u to move up\npress d to move down\npress l to move left\npress r to move right\n")

    if choice == "u":
        row -= 1
    elif choice == "d":
        row += 1
    elif choice == "l":
        column -= 1
    elif choice == "r":
        column += 1
    else:
        print("move denied")

    if row < 0 or row > 3 or column < 0 or column > 3:
        print("move denied")
        row = max(0, min(row, 3))
        column = max(0, min(column, 3))

    print("current location: ", wumpus[row][column], "\n")

    if wumpus[row][column] == "Smell" and arrow:
        a = input("do you want to throw an arrow\npress y to throw\npress n to save your arrow\n")

        if a == "y":
            direction = input("press u to throw up\npress d to throw down\npress l to throw left\npress r to throw right\n")

            nr, nc = row, column

            if direction == "u":
                nr -= 1
            elif direction == "d":
                nr += 1
            elif direction == "l":
                nc -= 1
            elif direction == "r":
                nc += 1

            if 0 <= nr < 4 and 0 <= nc < 4 and wumpus[nr][nc] == "WUMPUS":
                print("wumpus killed!")
                score += 1000
                wumpus[nr][nc] = "Save"
                wumpus[1][0] = "Save"
                wumpus[3][0] = "Save"
            else:
                print("arrow wasted...")
                score -= 10

            print("score: ", score)
            arrow = False

    if wumpus[row][column] == "WUMPUS":
        score -= 1000
        print("\nWumpus here!!\nYou Die\nAnd your score is: ", score)
        break

    elif wumpus[row][column] == "GOLD":
        score += 1000
        print("GOLD FOUND!You won....\nYour score is: ", score)
        break

    elif wumpus[row][column] == "PIT":
        score -= 1000
        print("Ahhhhh!!!!\nYou fell in pit.\nAnd your score is: ", score)
        break
```

<hr>
<h1>Output:</h1>
<hr>
<img width="490" height="743" alt="image" src="https://github.com/user-attachments/assets/e471f97b-f905-4dee-a8f9-656fa5969ae7" />


<H3>Result:</H3>
<p>
    Hence, solving  Wumpus World Problem using Python demonstrating Inferences from Propositional Logic has been executed successfully
</p>

