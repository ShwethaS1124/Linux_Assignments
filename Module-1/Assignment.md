# Linux Assignments

## 1. Create a file and add executable permission to all users(user,group and others)

```bash
touch file1
chmod a+x file1
ls -l file1 
```

## OUTPUT:

<img width="629" height="92" alt="image" src="https://github.com/user-attachments/assets/208acb33-f3a4-43ea-bfc0-f3965d65fb41" />

## 2. Create a file and remove write permission for group user alone.

```bash
touch file2
chmod g-w file2
ls -l file2
```

## OUTPUT:

<img width="625" height="77" alt="image" src="https://github.com/user-attachments/assets/216c9e66-e7d6-4635-805e-76c9b3a9731e" />

## 3. Create a file and add a softlink to the file in different directory.(Eg: Create a file in dir1dir2/file and create a softlink for file inside dir1)

```bash
mkdir -p dir1/dir2
touch -p dir1/dir2/file
ln -s dir2/file dir1/file_link
ls -l dir1
```
## OUTPUT:

<img width="653" height="103" alt="image" src="https://github.com/user-attachments/assets/6bb030e5-4ea1-456f-b833-f5028cbd847a" />

## 4. Use ps command with options to display all active process running on the system

```bash
ps -ef
```

## OUTPUT:

<img width="664" height="545" alt="image" src="https://github.com/user-attachments/assets/ede8e02c-5e6b-4058-9835-86688e53a22b" />

## 5. Create 3 files in a dir1 and re-direct the output of list command with sorted by timestamp of the files to a file

```bash
mkdir -p dir1
touch dir1file1 dir1/file2 dir1/file3
ls -lt dir1
ls -lt dir1 > dir1/file_list.txt
cat dir1/file_list.txt
```

## OUTPUT:

<img width="652" height="180" alt="image" src="https://github.com/user-attachments/assets/58c72062-9c66-453a-beee-14d0ef89aa9d" />
