### 🧩 Digital Forensics Lab  

This repository documents my hands-on exercises and case analyses in **digital forensics**, focusing on evidence acquisition, imaging, artifact recovery, and reporting.  

It forms part of my coursework and personal projects in the **BSc Cyber Security** program at **ECU**, showcasing the use of professional forensic tools and methodologies for real-world investigation scenarios.  

## Tools & Environments  
- **OSForensics** – forensic imaging, file carving, and artifact recovery  
- **Autopsy** – case management, timeline analysis, and file system reconstruction  
- **Kali Linux / Ubuntu** – command-line hashing, forensic utilities, and evidence verification  
- **Encryption & Hashing Methods** – MD5, SHA1, and SHA256 for data integrity verification  
- **FTK Imager (Occasionally)** – used for image preview and validation  
- **VirtualBox / Windows VM** – controlled environments for image testing  

## Case Workflow Overview  

### 🔹 **1. Evidence Acquisition & Imaging**
- Acquired a **forensic disk image (.E01)** from a simulated Windows 10 system using **OSForensics**.  
- Ensured proper **chain of custody** documentation before analysis.  
- Verified image integrity using multiple hash algorithms:  
  ```bash
  md5sum disk_image.E01
  sha256sum disk_image.E01


Stored hash results in a separate verification log file.

## Artifacts and hash logs are stored in the evidence/ folder.

### 🔹 2. OSForensics Analysis

- Opened the acquired image in OSForensics and analyzed the following:

- User profiles and directories

- Recently accessed documents

- Web browser history and cached images

- Windows registry and prefetch data

- Used File Signature Verification to identify mismatched file extensions.

- Located hidden/deleted files using the Raw Disk Viewer.

- Extracted forensic timelines to map user activity over key timeframes.

## Learnings:

- How to correlate file modification times (MAC times) with system logs.

- The importance of cross-referencing recovered files with user timestamps.

### 🔹 3. Autopsy Investigation

- Imported the same .E01 image into Autopsy for deeper analysis.

## Modules used:

- Recent Activity Analyzer – found browser history, downloads, and cookies.

- Keyword Search – detected suspicious files and phrases.

- File Type Identification – located hidden images and PDFs.

- Timeline Viewer – reconstructed events for chronological reporting.

- Found key artifacts in:

- C:\Users\[Username]\AppData\Roaming\ (for cached logs and config files)

- C:\Windows\Prefetch\ (for application execution history)

-  Screenshots of Autopsy modules are included in the autopsy/screenshots/ folder.

### 🔹 4. File Hashing & Integrity Verification

- Used both Windows utilities and Linux CLI to compute and verify file hashes.

- Compared the hashes with original evidence logs to ensure no tampering.

- Applied basic encryption/decryption using OpenSSL for secure evidence transfer:

- openssl enc -aes-256-cbc -salt -in evidence.zip -out evidence.enc


## Learnings:

- How to perform forensic imaging and verification using professional tools.

- Understanding the chain of custody and why proper documentation matters.

- The ability to recover and interpret digital artifacts from OS and user directories.

- How metadata reveals user activity patterns and timeline reconstruction.

- Validating evidence integrity through multi-algorithm hashing.

- Applying encryption techniques to protect and transfer sensitive data.

- Clear documentation and reporting standards used in real-world forensic practice.
