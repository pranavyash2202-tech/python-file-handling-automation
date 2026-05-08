# 📁 Python File Handling & Automation

🚀 **Internship Project | Alfido Tech**

This project was developed as part of the **Python Developer Internship at Alfido Tech**.  
The objective of this task is to demonstrate Python file handling, automation logic, and exception handling through real-world file operations.

---

## 📌 Project Overview

File handling is one of the most important concepts in Python programming and automation.  
This project automates common file operations such as:

- Reading files  
- Writing files  
- Renaming files  
- Moving files  
- Deleting files  
- Handling errors using exception handling  

The project demonstrates how Python can simplify repetitive file management tasks efficiently.

---

## 🎯 Key Objectives

- Understand file handling in Python  
- Read and write TXT/CSV files  
- Automate file operations  
- Implement exception handling using `try-except`  
- Write clean and maintainable Python code  

---

## 🛠️ Technologies Used

- **Python**
- **OS Module**
- **Shutil Module**
- **CSV Module**

---

## ⚙️ Features Implemented

✅ Read text files  
✅ Write data into files  
✅ Read CSV files  
✅ Rename files automatically  
✅ Move files between folders  
✅ Delete unwanted files  
✅ Handle errors using `try-except`  

---

## 💻 Code Implementation

import os
import shutil
import csv

# -------------------------------
# FILE HANDLING: READ & WRITE TXT
# -------------------------------

def write_text_file(filename):
    try:
        with open(filename, 'w') as file:
            file.write("Hello, this is a sample text file.\n")
            file.write("This file is created using Python.\n")
        print(f"[INFO] Text file '{filename}' created successfully.")

    except Exception as e:
        print(f"[ERROR] Failed to write text file: {e}")


def read_text_file(filename):
    try:
        with open(filename, 'r') as file:
            content = file.read()
        print(f"[INFO] Reading '{filename}':\n{content}")

    except FileNotFoundError:
        print("[ERROR] File not found.")
    except Exception as e:
        print(f"[ERROR] Something went wrong: {e}")


# -------------------------------
# FILE HANDLING: READ & WRITE CSV
# -------------------------------

def write_csv_file(filename):
    try:
        data = [
            ["Name", "Age", "City"],
            ["Pranav", 20, "Bhagalpur"],
            ["Rahul", 22, "Delhi"]
        ]

        with open(filename, 'w', newline='') as file:
            writer = csv.writer(file)
            writer.writerows(data)

        print(f"[INFO] CSV file '{filename}' created successfully.")

    except Exception as e:
        print(f"[ERROR] Failed to write CSV file: {e}")


def read_csv_file(filename):
    try:
        with open(filename, 'r') as file:
            reader = csv.reader(file)
            print(f"[INFO] Reading CSV file '{filename}':")
            for row in reader:
                print(row)

    except FileNotFoundError:
        print("[ERROR] CSV file not found.")
    except Exception as e:
        print(f"[ERROR] Something went wrong: {e}")


# -------------------------------
# AUTOMATION: RENAME FILE
# -------------------------------

def rename_file(old_name, new_name):
    try:
        os.rename(old_name, new_name)
        print(f"[INFO] File renamed from '{old_name}' to '{new_name}'.")

    except FileNotFoundError:
        print("[ERROR] File to rename not found.")
    except Exception as e:
        print(f"[ERROR] Rename failed: {e}")


# -------------------------------
# AUTOMATION: MOVE FILE
# -------------------------------

def move_file(source, destination):
    try:
        shutil.move(source, destination)
        print(f"[INFO] File moved to '{destination}'.")

    except FileNotFoundError:
        print("[ERROR] File to move not found.")
    except Exception as e:
        print(f"[ERROR] Move failed: {e}")


# -------------------------------
# AUTOMATION: DELETE FILE
# -------------------------------

def delete_file(filename):
    try:
        os.remove(filename)
        print(f"[INFO] File '{filename}' deleted successfully.")

    except FileNotFoundError:
        print("[ERROR] File to delete not found.")
    except Exception as e:
        print(f"[ERROR] Delete failed: {e}")


# -------------------------------
# MAIN FUNCTION TO RUN ALL TASKS
# -------------------------------

def main():
    txt_file = "sample.txt"
    csv_file = "data.csv"
    renamed_file = "renamed_sample.txt"
    moved_folder = "backup"

    # Create a folder for moving file
    if not os.path.exists(moved_folder):
        os.mkdir(moved_folder)

    # TXT operations
    write_text_file(txt_file)
    read_text_file(txt_file)

    # CSV operations
    write_csv_file(csv_file)
    read_csv_file(csv_file)

    # Rename file
    rename_file(txt_file, renamed_file)

    # Move file
    move_file(renamed_file, os.path.join(moved_folder, renamed_file))

    # Delete CSV file
    delete_file(csv_file)


# Run the program
if __name__ == "__main__":
    main()
