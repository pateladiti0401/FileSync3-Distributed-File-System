# 🗂️ FileSync3: Distributed File System

**FileSync3** is a distributed file system that enables seamless file management between a client and three dedicated servers: `Smain`, `Spdf`, and `Stext`. While users interact solely with `Smain`, it intelligently routes `.c`, `.pdf`, and `.txt` files to their respective servers behind the scenes.

---

## 🚀 Features

- 📤 **Upload Files**  
  Upload `.c`, `.pdf`, or `.txt` files to `Smain`.

- 📥 **Download Files**  
  Retrieve files directly from `Smain`.

- ❌ **Remove Files**  
  Delete files from the server and retrieve them locally.

- 🗜️ **Create Tar Archives**  
  Generate `.tar` files by extension and download them.

- 📍 **Display File Paths**  
  Show the full path of files on the server.

---

## 🧠 Server Distribution Logic

- `.c` files → Stored on **Smain**
- `.pdf` files → Transferred to **Spdf**
- `.txt` files → Transferred to **Stext**

All operations are client-facing only on `Smain`; users are unaware of the distribution mechanics.

---

## 🛠️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/pateladiti0401/FileSync3-Distributed-File-System.git
cd FileSync3-Distributed-File-System
# FileSync3: Distributed File System
```

### 2. **Compile the Servers and Client:**
    ```bash
    gcc -o smain Smain.c
    gcc -o spdf Spdf.c
    gcc -o stext Stext.c
    gcc -o client client.c
    ```

###  3. **Start the Servers:**
    - Start Smain server:
      ```bash
      ./smain
      ```
    - Start Spdf server:
      ```bash
      ./spdf
      ```
    - Start Stext server:
      ```bash
      ./stext
      ```

###  4. **Run the Client:**
    ```bash
    ./client
    ```

## Usage
- **Upload a File:**
    ```bash
    ufile sample.txt /destination/path/
    ufile sample.c /destination/path/
    ufile sample.pdf /destination/path/
    ```
- **Download a File:**
    ```bash
    dfile sample.txt
    ```
- **Remove a File:**
    ```bash
    rmfile sample.txt
    ```
- **Create and Download a Tar File:**
    ```bash
    dtar .c
    dtar .pdf
    dtar .txt
    ```
- **Display Path**
    ```bash
    display pathname
    ```

## Sample Files
For testing, you can use the following sample files:
- `sample.txt`
- `sample.c`
- `sample.pdf`

These files can be uploaded, downloaded, and managed using the client commands.

## Project Structure
- `smain.c` - Handles client connections and manages the distribution of files.
- `spdf.c` - Manages the storage of PDF files.
- `stext.c` - Manages the storage of text files.
- `client.c` - Client program to interact with the Smain server.
