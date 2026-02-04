# Linux Assignment 2

## 1.Use the appropriate command to list all files larger than 1 MB in the current directory and save the output to a file.

```
find . -maxdepth 1 -type f -size +1M
```
## OUTPUT:

<img width="648" height="39" alt="image" src="https://github.com/user-attachments/assets/d32b5071-893c-4202-aae8-839c2fb06304" />

## 2.Replace all occurences of "localhost" with "127.0.0.1" in a configuration file named config.txt, and save the updated file as updated_config.txt.

```
sed 's/localhost/127.0.0.1/g' config.txt > updated_config.txt
```
## OUTPUT:

<img width="523" height="81" alt="image" src="https://github.com/user-attachments/assets/309a324d-3510-4454-8c12-bfe6f7d32857" />

## 3. Use the appropriate command to search for lines containing the word "ERROR" in a log file but exclude lines containing "DEBUG". Save the results to a file named filtered_log.txt

```
ubuntu_eur337@EURLTP-337:~$ grep "ERROR" log.txt | grep -v "DEBUG" > filtered_log.txt
cat filtered_log.txt
```

## OUTPUT:

<img width="646" height="125" alt="image" src="https://github.com/user-attachments/assets/ab8d1a46-7a88-4eaa-a4e8-f58e5f960d85" />

## 4.Write a code to identify the process with the highest memory usage and terminate it .

```
TOP_PROC=$(ps aux --sort=-%mem | awk 'NR>1 {if($1!="root" && $11!="systemd" && $11!="unattended-upgr"){print $2, $11; exit}}')
PID=$(echo $TOP_PROC | awk '{print $1}')
PROC_NAME=$(echo $TOP_PROC | awk '{print $2}')

if [ -z "$PID" ]; then
    echo "No safe process found to terminate."
    exit 1
fi
if kill -9 $PID 2>/dev/null; then
    echo "Process $PROC_NAME (PID: $PID) has been terminated."
else
    echo "Failed to terminate process $PROC_NAME (PID: $PID). Permission denied."
fi

```

OUTPUT:

<img width="652" height="176" alt="image" src="https://github.com/user-attachments/assets/eaf1bc83-f941-4b99-8bae-1f1634f48f3a" />

## 5. Use the networking tool command and print all the gateway available in a sorted manner.

```
ip route show | awk '/default/ {print $3}' | sort
```

## OUTPUT:

<img width="655" height="61" alt="image" src="https://github.com/user-attachments/assets/7a8b6bb4-8754-4c84-88b5-b5dda155bc65" />



