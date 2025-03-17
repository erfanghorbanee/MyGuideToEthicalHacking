# Web browser forensics

## Tools

### Hindsight

Internet history forensics for Google Chrome/Chromium

Hindsight is a free tool for analyzing web artifacts. It started with the browsing history of the Google Chrome web browser and has expanded to support other Chromium-based applications (with more to come!). Hindsight can parse a number of different types of web artifacts, including URLs, download history, cache records, bookmarks, autofill records, saved passwords, preferences, browser extensions, HTTP cookies, and Local Storage records (HTML5 cookies). Once the data is extracted from each file, it is correlated with data from other history files and placed in a timeline.

<https://github.com/obsidianforensics/hindsight>

### Browser History Examiner

Browser History Examiner (BHE) is a forensic software tool for capturing,
analysing and reporting internet history from the main desktop web browsers.

BHE can assist in various digital investigations such as civil & criminal digital forensics cases,
security incidents, human resources investigations and general employee activity reporting.

<https://www.foxtonforensics.com/browser-history-examiner/>

## Recovering deleted history

### **1. Recovering from Browser Cache & Log Files**

- Even if history is deleted, browsers store **cache files, cookies, and log files** that can reveal past activity.
- Some browsers maintain **internal logs** of visited websites, even after history deletion.

### **2. Examining SQLite Databases**

- Most modern browsers (Chrome, Firefox, Edge) store history in **SQLite databases** (e.g., `History.db` for Chrome).
- If history is deleted, forensic tools can analyze the database and potentially recover deleted entries using **database journal files** or **write-ahead logs (WAL)**.

### **3. File System Recovery**

- Deleted history is often just **marked as deleted** but remains on the disk until overwritten.
- Forensic tools use **file carving** and **low-level disk analysis** to extract remnants of deleted browser history.

### **4. Analyzing DNS Cache**

- Even if browser history is wiped, the **DNS cache** retains records of visited domains.
- Tools like `ipconfig /displaydns` (Windows) or `dscacheutil -cachedump` (macOS) can reveal recently visited websites.

### **5. Extracting Data from RAM & Swap Files**

- Some browsing data remains in **RAM** (if the system hasn't been restarted).
- Page files or swap memory can contain fragments of history.

### **6. Checking System Restore Points & Backups**

- Windows and macOS create **restore points, backups, or Time Machine snapshots**, which may include browser history from an earlier state.

### **7. Network Traffic Analysis**

- If a system is connected to a network with logging enabled, tools like **Wireshark** or **proxy logs** can reconstruct browsing history.

### **8. Cloud Synchronization**

- If the user has browser sync enabled (Google Account, iCloud, etc.), history may still be accessible from another synced device.
