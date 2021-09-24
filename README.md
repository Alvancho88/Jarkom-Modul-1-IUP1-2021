# Jarkom-Modul-1-IUP1-2021
Repository Laporan Resmi Praktikum Modul 1 Jarkom Wireshark

**Group's Member:**

**(05111942000010) Agustinus Aldi Irawan**

**(05111942000017) Juan Carlos T. P.**

**(05111942000028) Salma Izzatul Islam**

# Question 1
**What web server is used on "ichimarumaru.tech"!**

```
http.host == "ichimarumaru.tech"
```

# Question 2
**Find the packets from the web that use the basic authentication method!**

```
http.auth basic
```

# Question 3
**Follow the instructions at basic.ichimaru maru.tech! Username and password can be obtained from the .pcapng file!**

```
http.host == basic.ichimarumaru.tech
```

# Question 4
**Find the mysql packets that contain the select query command!**

```
 mysql.query matches select
```

# Question 5
**Login to portal.ichimarumaru.tech then follow the instructions! The username and password can be obtained from the insert query in the users table from the .pcap file!**

```
mysql.query matches insert
```

# Question 6
**Find username and password when logging into FTP Server!**

```
ftp.request.command == USER || ftp.request.command == PASS
```

# Question 7
**There are 500 zip files saved to FTP Server with names 0.zip, 1.zip, 2.zip, ..., 499.zip. Save and Open the pdf file. (Hint = the name of the pdf is "Real.pdf")**

```
frame contains “Real.pdf” 
```

# Question 8
**Look for the packets that show the retrieval of files from the FTP!**

```
ftp.request.command == RETR
```

# Question 9
**From the packets going to FTP, there are indications of storing some files. One of them is a file containing confidential data with the name "secret.zip". Save and open the file!**

```
ftp-data.command contains "secret.zip"
```

# Question 10
**Also there is "history.txt" which probably contains the history of the bash server! Use the contents of "history.txt" to find the password to open the secret file in "secret.zip"!**

```
ftp-data.command contains "history.txt"
```

# Question 11
**Filter so that wireshark only picks up packets coming from port 80!**

```
tcp.srcport == 80
```

# Question 12
**Filter so that wireshark only picks up packets containing port 21!**

```
tcp.port == 21
```

# Question 13
**Filter so that wireshark only shows packets going to port 443!**

```
tcp.dstport == 443
```

# Question 14
**Filter so that wireshark only picks up packets going to kemenag.go.id!**

```
dst host kemenag.go.id
```

# Question 15
**Filter so that wireshark only picks up packets coming from your local ip address!**

```
ip.src==<local ip address>
```
