
# 🗂️ C++ Version Control System — A Mini Git Clone

A lightweight **version control system** written in **C++**, inspired by Git, that lets you:
- Manage multiple versions of your project files
- Create commits
- Track and display commit history
- Revert to any previous commit
- Simulate staging and commit flow like real Git

> 🏁 **Final Semester Project** for **Data Structures & Algorithms Lab**  
> 🎓 Lahore Garrison University  
> 👩‍🏫 Instructor: Mam. Raeena Tauqir

---

## 📖 What is This?

This is a **minimal Git clone** built from scratch using **C++**, showcasing how real version control systems work. It emphasizes core programming concepts such as:

- Command line parsing with `argc`, `argv`
- Linked Lists for commit management
- File system manipulation
- Directory creation, file copying, and history tracking

> ⚠️ No external libraries or Git libraries are used — everything is built from scratch!

---

## 🧠 Core Features

| Feature | Description |
|--------|-------------|
| 📦 `add` | Adds files to the staging area |
| 📝 `commit` | Creates a snapshot of the current project (like Git commits) |
| 🔍 `log` | Displays the list of all commits in order |
| ⏪ `revert` | Reverts the project to any previous commit |
| 📁 Filesystem | Uses directories to store full versions of each commit |
| 🔗 Data Structures | Uses Linked Lists to manage commit metadata |

---

## 🛠️ How It Works

### 📌 Command-Based System

The system is entirely CLI-based. Here's how you use it:

```bash
# Add file to staging area
./vcs add main.cpp

# Commit with a message
./vcs commit "Initial commit"

# Show all commits
./vcs log

# Revert to specific commit
./vcs revert 1
```

### 🔄 Internal Flow

```text
[ main.cpp ] → [ gitClass.cpp ] → [ commitNodeList.cpp ]
       ↓
 Command Handling via argv/argc
       ↓
 File Operations & Staging
       ↓
 Linked List of Commits
       ↓
 File Version Snapshots in Directories
```

---

## 🧩 Code Structure Breakdown

### 📁 main.cpp
- Acts as the **command parser**.
- Reads user input via `argc/argv` and forwards control to `Git` class methods.
- Valid commands: `add`, `commit`, `log`, `revert`.

### 📁 gitClass.cpp
- The **brain of the system**.
- Handles:
  - Staging of files
  - Creating versioned folders
  - Copying staged files to a new commit
  - Logging and revert operations
- Manages:
  - `.vcs/` directory for metadata
  - Commit counters
  - Commit message and time

### 📁 commitNodeList.cpp
- Implements a **Linked List** to manage the history of commits.
- Each node:
  - Stores commit ID
  - Commit message
  - Timestamp
- Supports traversal to display logs or revert to any node.

---

## 🧪 Sample Session

```bash
> ./vcs add main.cpp
File main.cpp added to staging area.

> ./vcs commit "Added main functionality"
Commit 1 created.

> ./vcs add gitClass.cpp
> ./vcs commit "Core Git logic added"
Commit 2 created.

> ./vcs log
Commit 2: Core Git logic added
Commit 1: Added main functionality

> ./vcs revert 1
Reverted to commit 1: "Added main functionality"
```

---

## 🗃️ How Commits Are Stored

- Each commit creates a folder in `.vcs/commits/` named after its ID.
- Files added are **copied into these folders**, preserving full versions.
- Metadata like commit message & timestamp are saved in each directory.

```text
.vcs/
└── commits/
    ├── 1/
    │   ├── main.cpp
    │   └── meta.txt
    ├── 2/
    │   ├── main.cpp
    │   ├── gitClass.cpp
    │   └── meta.txt
```

---

## 🧠 Data Structures Used

| Structure | Role |
|----------|------|
| 🪢 Linked List | Manages commit history (in `commitNodeList.cpp`) |
| 🗂️ File system trees | Snapshots saved in `.vcs/commits/<id>` |
| 🧠 Pointers | Used to link commit nodes and traverse history |
| 📋 Command Arguments | Parsed using `argc` and `argv[]` in C++ |

---

## 🧰 Build & Run

### 🔧 Prerequisites
- A C++ compiler (g++, clang, etc.)

### ⚙️ Compile
```bash
g++ main.cpp gitClass.cpp commitNodeList.cpp -o vcs
```

### ▶️ Run
```bash
./vcs <command> [arguments]
```

---

## 📚 Takeaways

This project showcases how real-world version control tools like Git operate internally, using:

- **Low-level file operations**
- **Custom data structures**
- **Staging → Commit → Revert flow**
- **Linked lists for history**
- **Filesystem-based version management**

---

## 🙋‍♂️ FAQs

**Q: Is this an actual Git implementation?**  
A: No. It’s a lightweight clone built from scratch to simulate Git's behavior for learning purposes.

**Q: Can I extend it?**  
A: Absolutely! You can add diff tracking, branches, remote push/pull, or GUI.

**Q: Does it support multiple users or collaboration?**  
A: No, this is purely local and single-user. Think of it as Git’s "bare bones".

---

## 👨‍💻 Author

Made with 🔥 by **[Aditya Dave]**  
GitHub: [Aditya-Dave503](https://github.com/Aditya-Dave503)) 
Email: adityadave049@gmail.com 

Made with 🔥 by **[Aaryan Modi]**  
GitHub: [Aaryan-Modi](https://github.com/Aaryan-Modi)  
Email: aaryan.spdev@gmail.com

Made with 🔥 by **[Rudra Bhatt]**  
GitHub: [RudraBhat](https://github.com/RudraBhat)  
Email: youremail@example.com 

Made with 🔥 by **[Jay Limbasiya]**  
GitHub: [Jay0001-debug](https://github.com/Jay0001-debug)  
Email: jaylimbasiya0001@gmail.com

---

## 🏁 Final Words

This project is more than just a submission — it’s a deep dive into how tools we rely on every day are built from first principles. If you're learning C++, data structures, or want to build your own tools — this is a great starting point.

---
