📚 PaperHub – Automated Question Paper Bot

PaperHub is a demo automation system built using n8n that allows students to retrieve previous year question papers instantly using a Telegram bot.
Staff simply upload PDFs into Google Drive — the rest is fully automated.

🔄 System Workflow Overview
flowchart TD
    A [Staff Uploads PDF<br>Google Drive] --> B [n8n Trigger<br>File Created]
    B --> C [Extract Subject & Year<br>Function Node]
    C --> D [Append to Google Sheets<br>Paper Database]
    E [Student Requests<br>@nec_ques_bot] --> F [n8n Telegram Trigger]
    F --> G [Extract Subject & Year<br>Student Workflow]
    G --> H [Sheets Lookup<br>Match Papers]
    H --> I [Build Reply<br>Function Node]
    I --> J [Send PDF Link<br>Telegram Bot]

⚙️ How It Works
1. Staff Upload Workflow

➡️ Staff uploads a PDF into Google Drive
➡️ n8n Drive Trigger detects the newly created file
➡️ Filename is parsed (e.g., CN_2023.pdf)
➡️ Subject + Year extracted automatically
➡️ Clean Google Drive link generated
➡️ Data saved into Google Sheets

2. Student Bot Workflow

➡️ Student types:
• CN
• OOPS 2023
• DSP 2022
➡️ n8n extracts subject + year
➡️ Google Sheets searched automatically
➡️ Bot replies instantly with matching question papers

🤖 Try the Demo Bot

👉 https://t.me/nec_ques_bot

(Demo model created for learning and automation practice)

🧠 Tech Stack
Component	Purpose
n8n	Automation engine
Telegram Bot API	Student interaction
Google Drive API	Storage for uploaded papers
Google Sheets API	Searchable paper database
JavaScript (Function Nodes)	Parsing and logic

PaperHub/
│
├── PaperHub-STUDENT.json   # Student Telegram workflow
├── PaperHub-STAFF.json     # Staff upload workflow
└── README.md               # Project documentation

📝 
Staff Workflow
<img width="1920" height="1080" alt="Screenshot (1350)" src="https://github.com/user-attachments/assets/a1837bc9-84cf-42c7-809b-fabaf77971bf" />

Student Workflow
<img width="1920" height="1080" alt="Screenshot (1349)" src="https://github.com/user-attachments/assets/9974daf7-599d-42e3-a9d7-200a2697089a" />

Output
![Telegram (2)](https://github.com/user-attachments/assets/abf5649f-ecb6-4c8a-97aa-b434ba4dc8b2)

![Telegram (1)](https://github.com/user-attachments/assets/31191ae7-3e92-4cee-8646-5aec7578953f)



👨‍💻 Author
Hari Muthu Ganesh R
Creator of PaperHub (demo model)
CSE Automation & Development
