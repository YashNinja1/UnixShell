# 🖥️ Custom Unix Command Shell (C)

A lightweight Unix-like command shell implemented in C, designed to replicate core functionalities of a traditional Linux shell using low-level POSIX system calls. 

This project demonstrates practical, low-level understanding of process management, signal handling, command execution, and file descriptor manipulation in a UNIX environment.

---

## ✨ Features

- **Interactive Shell:** Dynamic prompt displaying the current working directory.
- **Process Execution:** Executes standard Linux binaries using `fork()`, `execvp()`, and `wait()`.
- **Built-in Commands:**
  - `cd <directory>` — Changes the current working directory.
  - `exit` — Terminates the shell session gracefully.
- **Advanced Command Operators:**
  - `&&` — **Parallel Execution:** Runs multiple commands concurrently.
  - `##` — **Sequential Execution:** Executes commands one after another.
- **I/O Redirection:** Output redirection (`>`) supported via file descriptor manipulation.
- **Signal Handling:** Graceful management of keyboard signals:
  - `Ctrl + C` (`SIGINT`)
  - `Ctrl + Z` (`SIGTSTP`)
- **Error Handling:** Robust validation for invalid commands or empty user inputs.

---

## 🧠 Key Concepts & Systems Programming

- **Process Lifecycle Management:** Parent-child process creation, lifecycle synchronization, and exit status tracking.
- **File Descriptor Manipulation:** Utilizing `open()` and `dup2()` to achieve standard output redirection.
- **Signal Interruption:** Custom handlers to prevent parent shell termination on interrupt signals.
- **String Parsing & Tokenization:** Parsing command-line inputs into arguments and tracking operators (`&&`, `##`, `>`).
- **POSIX System Calls:** Direct communication with the kernel using low-level C primitives.

---

## 🛠️ Built With

![C](https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![POSIX](https://img.shields.io/badge/POSIX-System%20Calls-00599C?style=for-the-badge)

- **Language:** C (C99 / C11)
- **Environment:** Linux / UNIX
- **APIs:** POSIX System Calls (`unistd.h`, `sys/wait.h`, `signal.h`, `fcntl.h`)

---

## 🚀 Getting Started

### Prerequisites

A C compiler (such as `gcc` or `clang`) and a Unix-like operating system (Linux, macOS, or WSL).

### Build & Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yashkharche/custom-unix-shell.git
   cd custom-unix-shell
   ```

2. **Compile the program:**
   ```bash
   gcc -Wall -Wextra myshell.c -o myshell
   ```

3. **Launch the shell:**
   ```bash
   ./myshell
   ```

---

## 💡 Example Usage

### 1. Basic Command
```bash
myshell> ls -l
```

### 2. Parallel Execution (`&&`)
Executes all listed commands simultaneously in parallel:
```bash
myshell> ls && pwd && date
```

### 3. Sequential Execution (`##`)
Executes commands one after the other in sequence:
```bash
myshell> ls ## echo "Hello World" ## pwd
```

### 4. Output Redirection (`>`)
Redirects stdout of a command into a designated target file:
```bash
myshell> ls -la > output.txt
```

---

## 📈 Learning Outcomes

- Acquired hands-on experience managing UNIX process execution and concurrency.
- Understood the low-level mechanics of how production shells interact with the OS kernel.
- Mastered signal safety and file descriptor table manipulation in system-level C programming.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).