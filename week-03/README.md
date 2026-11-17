
# Week 03 – Password Cracking & Recovery

## NetworkWalks Cybersecurity Internship | Batch B084

## 1. Overview

Week 03 focused on understanding password security, password hash extraction, dictionary attacks, and password recovery techniques.

During this week, I completed two mandatory practical projects using different password recovery approaches:

1. **PM1 – Password Cracking with John the Ripper**
2. **PM2 – Password Cracking with NetworkWalks Tools**

The practicals provided hands-on experience with both locally installed cybersecurity tools and browser-based password recovery tools.

## 2. Objectives

- Understand password protection and password hashing.
- Learn how password hashes are extracted from protected PDF files.
- Perform dictionary attacks using John the Ripper.
- Explore Johnny, the graphical frontend for John the Ripper.
- Use NetworkWalks Hash Calculator.
- Perform password recovery using NetworkWalks Password Cracker.
- Verify recovered passwords by opening protected PDF documents.
- Capture flags and document practical results.

## 3. Lab Environment

| Component | Details |
|---|---|
| Operating System | Kali Linux |
| Virtualization | Oracle VirtualBox |
| Terminal | Kali Linux Terminal |
| Browser | Mozilla Firefox |
| Password Recovery Tool | John the Ripper |
| GUI Frontend | Johnny |
| Hash Extraction Tool | pdf2john |
| Online Hash Calculator | NetworkWalks |
| Online Password Cracker | NetworkWalks |
| Attack Technique | Dictionary Attack |

## 4. Projects Completed

### PM1 – Password Cracking with John the Ripper

**Objective:**

Recover the password of the assigned protected PDF using John the Ripper and Johnny.

**Tools Used:**

- John the Ripper (Jumbo)
- pdf2john
- Johnny
- JTR_default_password.txt

**Tasks Performed:**

1. Installed and verified John the Ripper in Kali Linux.
2. Verified the availability of pdf2john.
3. Prepared the assigned encrypted PDF and wordlist.
4. Extracted the PDF password hash using pdf2john.
5. Saved the extracted hash into `hash1.txt`.
6. Performed a dictionary attack using John the Ripper.
7. Displayed and verified the recovered password.
8. Opened the protected PDF successfully.
9. Installed and launched Johnny.
10. Repeated the password recovery demonstration using the GUI.

**Result:**

Successfully recovered the assigned PDF password using both CLI and GUI methods.

[View PM1 – John the Ripper](./W3-PM1-%20Password%20Cracking%20with%20JTR/)

---

### PM2 – Password Cracking with NetworkWalks Tools

**Objective:**

Recover the password of the assigned protected PDF using NetworkWalks online tools.

**Tools Used:**

- NetworkWalks Hash Calculator
- NetworkWalks Password Cracker
- Mozilla Firefox

**Tasks Performed:**

1. Prepared the PM2-specific encrypted PDF.
2. Opened the NetworkWalks Hash Calculator.
3. Uploaded the assigned PDF.
4. Extracted the PDF password hash.
5. Copied the generated hash.
6. Opened NetworkWalks Password Cracker.
7. Submitted the extracted hash.
8. Performed the password recovery exercise.
9. Verified the recovered password.
10. Opened the protected PDF and captured the assigned flags.

**Result:**

Successfully completed the assigned password recovery exercises and captured the required flags.

[View PM2 – NetworkWalks Tools](./W3-PM2-%20Password%20Cracking%20with%20NW%20Tools/)

## 5. Key Learnings

Through these practical exercises, I learned:

- The difference between encryption and hashing.
- How password-protected PDFs use password-verification mechanisms.
- How to extract PDF password hashes.
- How dictionary attacks work.
- How John the Ripper processes candidate passwords.
- How to use wordlists during password recovery.
- How Johnny provides a graphical interface for John the Ripper.
- How browser-based password recovery tools work.
- How to verify recovered passwords and document security testing results.

## 6. CLI vs GUI vs Online Tools

| Feature | John CLI | Johnny GUI | NetworkWalks Tools |
|---|---|---|---|
| Execution | Terminal | Graphical interface | Web browser |
| Hash extraction | pdf2john | Uses loaded hash file | Hash Calculator |
| Password recovery | John | John backend | Password Cracker |
| Configuration | Commands | GUI options | Web interface |
| Environment | Kali Linux | Kali Linux | Browser |

## 7. Overall Results

| Project | Description | Status |
|---|---|---|
| PM1 | John the Ripper CLI | Completed |
| PM1 | Johnny GUI | Completed |
| PM2 | NetworkWalks Hash Calculator | Completed |
| PM2 | NetworkWalks Password Cracker | Completed |
| PM2 | Password verification and flag capture | Completed |

**Mandatory Projects Completed: 2/2**

## 8. Conclusion

Week 03 provided practical experience with password recovery techniques and the importance of password security.

I successfully completed both mandatory projects:

- PM1 using John the Ripper and Johnny.
- PM2 using NetworkWalks Hash Calculator and Password Cracker.

These exercises helped me understand the workflow of extracting password hashes, performing dictionary attacks, recovering passwords, and verifying results.

This practical knowledge strengthened my understanding of password security and Linux-based cybersecurity tools.

---

**Internship:** NetworkWalks Cybersecurity Internship  
**Batch:** B084  
**Week:** 03  
**Focus Area:** Password Cracking & Recovery  
**Mandatory Projects:** 2  
**Completion Status:** Completed
