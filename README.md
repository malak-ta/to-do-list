# to-do-list
A simple command-line To-Do List app built with Python
tasks[]
while True :
  print ("Your List ")
  for i in range (len(tasks)):
    print(i + 1, "-", tasks[i])
  print ("1-add  \n 2-delete \n 3-exit ")  
  choice = input("Your choice")
  if choice == "1":
    task= input(" add new task")
    tasks.append(task)
  elif choice == "2":
   num= int(input("the task you want to delete "))
   tasks.pop(num-1)
  elif choice == "3": 
   print ("Yr tasks" , tasks)
   break 
  else:
   print("invalid ") 

  try:
    with open("tasks.txt", "r") as file:
        tasks = file.read().splitlines()
except FileNotFoundError:
    tasks = []

while True:
    print("Your List")
    for i in range(len(tasks)):
        print(i + 1, "-", tasks[i])
    
    print("1-add \n2-delete \n3-exit")
    choice = input("Your choice: ")
    
    if choice == "1":
        task = input("add new task: ")
        tasks.append(task)
    elif choice == "2":
        num = int(input("the task you want to delete: "))
        tasks.pop(num - 1)
    elif choice == "3":
        with open("tasks.txt", "w") as file:
            for task in tasks:
                file.write(task + "\n")
        print("Yr tasks saved:", tasks)
        break
    else:
        print("invalid")
