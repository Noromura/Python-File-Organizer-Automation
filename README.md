Python-File-Organizer-Automation

A simple Python automation script that automatically organizes files inside a folder (such as Downloads) into subfolders based on file type, and renames them following a clean pattern with date and index.
The project also generates detailed logs for every action performed.

📁 Features

Automatically organizes files into specific folders:

Images

PDFs

Documents

Spreadsheets

Videos

Programs

Compressed files

Renames all organized files using:

Category

Date

Index

Generates operation logs

Beginner-friendly Python project

⚙️ Technologies Used

Python 3

Native modules:

os

shutil

datetime

🚀 How to Run the Project in VS Code

Follow these steps to run the automation locally.

1️⃣ Install Python

If you don’t have Python installed yet:
👉 https://www.python.org/downloads/

During installation, make sure to enable:
✔ Add Python to PATH

2️⃣ Open the Project in VS Code

Open VS Code

Go to File > Open Folder

Select your project folder:
Python-File-Organizer-Automation

3️⃣ Open the Script File

In the VS Code Explorer, open your Python file:

organizer.py


(or whatever name you used for the automation script)

4️⃣ Install the Python Extension

In VS Code, install the extension:

➡️ Python (by Microsoft)

This enables running Python scripts directly in the editor.

5️⃣ Set the Folder Path You Want to Organize

Inside the script, modify:

PASTA_ALVO = r"C:\Users\SeuUsuario\Downloads"


Change "SeuUsuario" to your actual user, like:

PASTA_ALVO = r"C:\Users\Joao\Downloads"


Or replace it with any folder you want.

6️⃣ Run the Script

You can run the automation in two ways:

✔ Method 1 — Using the Run Button

Open the .py file and click:

▶ Run Python File

This button appears at the top right of the editor.

✔ Method 2 — Running Through the Terminal

Open the VS Code terminal:
Terminal > New Terminal

Run:

python organizer.py

📋 Expected Output

VS Code should display:

🔧 Organizing files...
Moved: photo.png → Images
Moved: document.pdf → PDFs

✏️ Renaming files...
Renamed: photo.png → Images_2025-01-01_1.png

✅ Automation completed!


A log file will be generated at:

logs/automacao_log.txt

📝 Notes

Always verify the target folder path before running

The script only moves files, it does NOT delete anything

You can add more file extensions inside the dictionary

Works on Windows, Linux, and macOS (paths must be adjusted)

🤝 Contributing

Feel free to submit pull requests!
You can improve the automation with more categories, better logging, or even create a GUI version.
