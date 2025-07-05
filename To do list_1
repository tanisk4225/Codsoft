import tkinter as tk
from tkinter import messagebox, simpledialog

class ToDo:
    def __init__(self, task_id, title):
        self.task_id = task_id
        self.title = title
        self.status = "Status Pending"

    def __str__(self):
        return f"ID: {self.task_id} | Title: {self.title} | Status: {self.status}"

class TaskManager:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)

    def get_all_tasks(self):
        return self.tasks

    def find_task(self, task_id):
        return next((task for task in self.tasks if task.task_id == task_id), None)

    def remove_task(self, task_id):
        task = self.find_task(task_id)
        if task:
            self.tasks.remove(task)
            return True
        return False

    def mark_task_completed(self, task_id):
        task = self.find_task(task_id)
        if task:
            task.status = "Completed"
            return True
        return False

def refresh_listbox():
    listbox.delete(0, tk.END)
    for task in manager.get_all_tasks():
        listbox.insert(tk.END, str(task))

def add_task():
    task_id = simpledialog.askstring("Task ID", "Enter Task ID:")
    title = simpledialog.askstring("Task Title", "Enter Task Title:")
    if task_id and title:
        manager.add_task(ToDo(task_id, title))
        refresh_listbox()

def remove_task():
    task_id = simpledialog.askstring("Remove Task", "Enter Task ID to remove:")
    if task_id and manager.remove_task(task_id):
        messagebox.showinfo("Success", "Task removed.")
    else:
        messagebox.showerror("Error", "Task not found.")
    refresh_listbox()

def mark_completed():
    task_id = simpledialog.askstring("Mark Completed", "Enter Task ID to mark as completed:")
    if task_id and manager.mark_task_completed(task_id):
        messagebox.showinfo("Success", "Task marked as completed.")
    else:
        messagebox.showerror("Error", "Task not found.")
    refresh_listbox()

manager = TaskManager()
root = tk.Tk()
root.title("To-Do List GUI")

listbox = tk.Listbox(root, width=60)
listbox.pack(pady=20)
button_frame = tk.Frame(root)
button_frame.pack()
tk.Button(button_frame, text="Add Task", command=add_task).grid(row=0, column=0, padx=2)
tk.Button(button_frame, text="Remove Task", command=remove_task).grid(row=0, column=1, padx=2)
tk.Button(button_frame, text="Complete Task", command=mark_completed).grid(row=0, column=2, padx=2)
tk.Button(button_frame, text="End", command=root.quit).grid(row=0, column=3, padx=2)

refresh_listbox()
root.mainloop()