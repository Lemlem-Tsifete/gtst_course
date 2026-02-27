# Linux File System & Text Editors

##  1. The Linux File Hierarchy Standard (FHS)

Unlike Windows, which uses drive letters (C:, D:), Linux organizes everything under the **Root Directory (`/`)**.

| **Directory** | **Purpose**                                                        |
| ------------- | ------------------------------------------------------------------ |
| `/root`       | The home directory for the **Root User** (Administrator).          |
| `/boot`       | Contains files needed to start the system (Kernel, Grub).          |
| `/etc`        | **Configuration files** for the system and installed apps.         |
| `/dev`        | Hardware files (e.g., hard drives, USBs, keyboards).               |
| `/lib`        | Essential shared libraries for the binaries in `/bin` and `/sbin`. |
| `/media`      | Mount point for **removable media** (USB sticks, CD-ROMs).         |
| `/mnt`        | **Temporary** mount point for filesystems (used by admins).        |
| `/opt`        | **Optional** add-on software packages (third-party apps).          |
| `/sbin`       | Essential system binaries (Reserved for **root/sudo** users).      |
| `/usr`        | User utilities and applications (The largest directory).           |
| `/home`       | Personal directories for regular users.                            |
| `/var`        | **Variable data** (Logs, mail spools, and databases).              |

---

## 📝 2. Vim (The Advanced Editor)

Vim is a "modal" editor. You must be in the right mode to perform specific tasks.

### Visual Mode (Highlighting & Manipulation)

|**Key**|**Mode**|**Use Case**|
|---|---|---|
|`v`|**Character-wise**|Highlight specific letters or words.|
|`Shift + V`|**Line-wise**|Highlight entire lines at once.|
|`Ctrl + V`|**Block-wise**|Select columns/rectangular blocks of text.|

### Common Vim Actions

- **y** — Copy (Yank) selected text.
    
- **p** — Paste text after the cursor.
    
- **d** — Delete (Cut) selected text.
    
- **:u** — Undo last action.
    
- **Ctrl + r** — Redo.
    
- **:%! grep "word"** — Filter the current file to only show lines containing "word".
    

---

## 📝 3. Nano (The Simple Editor)

Nano is a modeless editor, making it easier for beginners.

|**Shortcut**|**Action**|
|---|---|
|`Ctrl + S`|**Save** the file (Write Out).|
|`Ctrl + X`|**Exit** Nano.|
|`Alt + U`|**Undo** last action.|
|`Alt + E`|**Redo** last action.|
|`Ctrl + W`|**Where Is** (Search for a word).|
|`Ctrl + K`|**Cut** (Kill) entire line.|
|`Ctrl + U`|**Uncut** (Paste) the line.|

---

## ⌨️ 4. Terminal Shortcuts (Universal)

These shortcuts work in the Kali GNOME terminal and most other Linux emulators:

- `Ctrl + Shift + C` : **Copy** highlighted text from the terminal.
    
- `Ctrl + Shift + V` : **Paste** text into the terminal.
    
- `Ctrl + L` : **Clear** the screen (same as typing `clear`).
    
- `Ctrl + C` : **Stop/Cancel** a running command (e.g., stop an Nmap scan).
    
- `Ctrl + Z` : **Suspend** a command (sends it to the background).

# Linux user management

- person who use the computer is called "user"
- every users have group what is the group important is can create other users has can add 
- 2 kinds users. Root id = 0 , Normal user id start with 1 - 999

Create user 
- useradd - a command simple add the new user on Linux shell Sh
- Adduser -a command  for add a user in Detailed sell bash
to see the created files are stored inside and see   *cat /etc/passwd*
user password are stored inside  see *cat /etc/shadow*
*id* to see the detail of it 

## Some advanced user commands 
to change their user password 
when using *adduser* inter a new password when using *useradd*
`sudo passwd userName`

To change user id
*user id* is an id that Linux default give to the user 
and also it have a group the same name to the user name created 
now to change the id
first see the id it has using command `cat /etc/passwd` 
to change the id 
`sudo usermod -u 1003 userName `
to change the group also using 
`suo usermod -g 1001 userName`
to delete the user 
`sudo userdel -r userName`
how to login in the add user account 
`su - userName`
 the  change the user shell
`sudo usermod userName -s/bin/bash`
create a new group 
`sudo groupadd groupname`
Add users to the group
`sudo usermod -aG groupname userName`
to verify 
`groups groupname`
To delete form that group using
`sudo gpassw -d username groupname`
when we create using *useradd* command to see on the home directory using this command 
`sudo mkhomedir_helper <your username>`

