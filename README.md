# Function to display the To-Do List
def display_todo_list(todo_list):
    print("To-Do List:")
    for i, task in enumerate(todo_list, start=1):
        print(f"{i}. {task}")

# Function to add a task to the To-Do List
def add_task(todo_list, task):
    todo_list.append(task)
    print(f"Task '{task}' added to the To-Do List.")

# Function to remove a task from the To-Do List
def remove_task(todo_list, task_number):
    if 1 <= task_number <= len(todo_list):
        removed_task = todo_list.pop(task_number - 1)
        print(f"Task '{removed_task}' removed from the To-Do List.")
    else:
        print("Invalid task number.")

# Main function to run the To-Do List application
def main():
    todo_list = []

    while True:
        print("\n1. Display To-Do List")
        print("2. Add Task")
        print("3. Remove Task")
        print("4. Quit")

        choice = input("Enter your choice (1-4): ")

        if choice == '1':
            display_todo_list(todo_list)
        elif choice == '2':
            task = input("Enter the task to add: ")
            add_task(todo_list, task)
        elif choice == '3':
            task_number = int(input("Enter the task number to remove: "))
            remove_task(todo_list, task_number)
        elif choice == '4':
            print("Quitting the To-Do List application. Goodbye!")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 4.")

if __name__ == "__main__":
    main()
