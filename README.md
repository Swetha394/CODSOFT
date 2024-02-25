# CODSOFT
class Task:
    def __init__(self, description, completed=False):
        self.description = description
        self.completed = completed

class ToDoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)

    def remove_task(self, task_index):
        del self.tasks[task_index]

    def mark_task_as_completed(self, task_index):
        self.tasks[task_index].completed = True

    def display_tasks(self):
        for index, task in enumerate(self.tasks):
            status = "Completed" if task.completed else "Not Completed"
            print(f"{index + 1}. {task.description} - {status}")

def main():
    todo_list = ToDoList()

    while True:
        print("\n===== To-Do List Menu =====")
        print("1. Add Task")
        print("2. Remove Task")
        print("3. Mark Task as Completed")
        print("4. Display Tasks")
        print("5. Quit")

        choice = input("Enter your choice: ")

        if choice == "1":
            description = input("Enter task description: ")
            todo_list.add_task(Task(description))
        elif choice == "2":
            index = int(input("Enter task index to remove: ")) - 1
            todo_list.remove_task(index)
        elif choice == "3":
            index = int(input("Enter task index to mark as completed: ")) - 1
            todo_list.mark_task_as_completed(index)
        elif choice == "4":
            todo_list.display_tasks()
        elif choice == "5":
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
