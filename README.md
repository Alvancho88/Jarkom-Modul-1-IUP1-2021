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

**Screenshot**



**Explanation**

Solution: nginx/1.18.0 (Ubuntu)


# Question 2
**Find the packets from the web that use the basic authentication method!**

```
http.auth basic
```

**Screenshot**



**Explanation**

Solution: Screenshot


# Question 3
**Follow the instructions at basic.ichimaru maru.tech! Username and password can be obtained from the .pcapng file!**

```
http.host == basic.ichimarumaru.tech
```

**Screenshot**



**Explanation**

Solution: 

username: kuncimenujulautan

password: tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN

Next Question: Sebutkan urutan konfigurasi pengkabelan T568A!

1. White Green		

2. Green		

3. White Orange		

4. Blue			

5. White Blue

6. Orange

7. White Brown

8. Brown

# Question 4
**Find the mysql packets that contain the select query command!**

```
 mysql.query matches select
```

**Screenshot**



**Explanation**

Solution: Screenshot


# Question 5
**Login to portal.ichimarumaru.tech then follow the instructions! The username and password can be obtained from the insert query in the users table from the .pcap file!**

```
mysql.query matches insert
```

**Screenshot**



**Explanation**

Solution: Screenshot

Next Question: Sebutkan urutan konfigurasi pengkabelan T568B!

1. White Orange	

2. Orange

3. White Green		

4. Blue			

5. White Blue

6. Green

7. White Brown

8. Brown

# Question 6
**Find username and password when logging into FTP Server!**

```
ftp.request.command == USER || ftp.request.command == PASS
```

**Screenshot**



**Explanation**

Solution: ftp.request is used when handling FTP Server


# Question 7
**There are 500 zip files saved to FTP Server with names 0.zip, 1.zip, 2.zip, ..., 499.zip. Save and Open the pdf file. (Hint = the name of the pdf is "Real.pdf")**

```
frame contains “Real.pdf” 
```

**Screenshot**



**Explanation**

Solution: Ubah show data as “Raw”, lalu save as pdf


# Question 8
**Look for the packets that show the retrieval of files from the FTP!**

```
ftp.request.command == RETR
```

**Screenshot**



**Explanation**

Solution: RETR (Retrieval of files)


# Question 9
**From the packets going to FTP, there are indications of storing some files. One of them is a file containing confidential data with the name "secret.zip". Save and open the file!**

```
ftp-data.command contains "secret.zip"
```

**Screenshot**



**Explanation**

Solution: 

look for secret.zip

Follow TCP Stream

Save as zip file

Open, and you need password for access...

# Question 10
**Also there is "history.txt" which probably contains the history of the bash server! Use the contents of "history.txt" to find the password to open the secret file in "secret.zip"!**

```
ftp-data.command contains "history.txt"
```

**Screenshot**



**Explanation**

Solution:

Look for history.txt

Follow TCP Stream

There is a hint of bukanapapa.txt

Look for bukanapapap.txt

Follow TCP Stream

Got the Password

Open the zip file

Got Pranked by Luffy

# Question 11
**Filter so that wireshark only picks up packets coming from port 80!**

```
tcp.srcport == 80
```

**Screenshot**



**Explanation**

Solution:

Port 80 mainly used TCP

SRC filter will filter packets from designated address (80 in this case)

# Question 12
**Filter so that wireshark only picks up packets containing port 21!**

```
tcp.port == 21
```

**Screenshot**



**Explanation**
Solution:

Port 21 mainly used TCP

# Question 13
**Filter so that wireshark only shows packets going to port 443!**

```
tcp.dstport == 443
```

**Screenshot**



**Explanation**
Solution:

Port 443 mainly used TCP

DST filter will filter packets to designated address (443 in this case)

# Question 14
**Filter so that wireshark only picks up packets going to kemenag.go.id!**

```
dst host kemenag.go.id
```

**Screenshot**



**Explanation**
Solution:

DST filter will filter packets to designated address

Host target is kemenag.go.id

# Question 15
**Filter so that wireshark only picks up packets coming from your local ip address!**

```
ip.src==<local ip address>
```

**Screenshot**




**Explanation**
Solution:

ip address can be found using 

```
config /all
```

SRC filter will filter packets from designated address
