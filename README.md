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

```python
import os
import shutil
import csv

try:
    # Create and write into a text file
    with open("sample.txt", "w") as file:
        file.write("Python File Handling Example")

    # Read text file
    with open("sample.txt", "r") as file:
        content = file.read()
        print(content)

    # Rename file
    os.rename("sample.txt", "updated_sample.txt")

    # Create folder
    os.makedirs("backup", exist_ok=True)

    # Move file
    shutil.move("updated_sample.txt", "backup/updated_sample.txt")

    print("File operations completed successfully!")

except FileNotFoundError:
    print("File not found.")

except Exception as e:
    print("An error occurred:", e)
