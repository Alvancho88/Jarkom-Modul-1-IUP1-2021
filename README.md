# Jarkom-Modul-1-IUP1-2021
Repository Laporan Resmi Praktikum Modul 1 Jarkom Wireshark

**Group's Member:**

**(05111942000010) Agustinus Aldi Irawan**

**(05111942000017) Juan Carlos T. P.**

**(05111942000028) Salma Izzatul Islam**

Work Explanation:

**Aldi**

2,3,8,9,10,15

**Juan**

1,4,5,6,7

**Salma**

11,12,13,14

# Question 1
**What web server is used on "ichimarumaru.tech"!**

```
http.host == "ichimarumaru.tech"
```

**Explanation**

At the first input ```http.host == "ichimarumaru.tech"``` as the filter.

![Screenshot (6970)](https://user-images.githubusercontent.com/61174498/134769802-c5fad366-6e97-4836-8abe-e6bc0a786799.png)

After that select one of them and follow TCP Stream. Then it will appear as below:

![Screenshot (6971)](https://user-images.githubusercontent.com/61174498/134769807-e99974a5-1e68-48c6-a5a9-f0dc24130b53.png)

**Solution**

Web Server: nginx/1.18.0 (Ubuntu)

# Question 2
**Find the packets from the web that use the basic authentication method!**

```
http.auth basic
```

**Screenshot**

![Screenshot (6972)](https://user-images.githubusercontent.com/61174498/134769815-9cc469fd-203f-4ad0-ae4a-80e0aa0f6aa2.png)

**Explanation**

Solution: Screenshot

# Question 3
**Follow the instructions at basic.ichimaru maru.tech! Username and password can be obtained from the .pcapng file!**

```
http.host == basic.ichimarumaru.tech
```

**Screenshot**

![Screenshot (6973)](https://user-images.githubusercontent.com/61174498/134769830-f75a3bc0-380f-428c-9bce-2cb232e92fa1.png)


![Screenshot (6974)](https://user-images.githubusercontent.com/61174498/134769832-e8ceaf28-6446-4ad8-9a6f-69659d427b9e.png)

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
mysql.command==3
```

**Explanation**

Input ```mysql.command==3``` as the filter.

![Screenshot (6948)](https://user-images.githubusercontent.com/61174498/134769847-5b49daa3-09c7-4c7f-89ca-4ccfbaf54c36.png)

Solution: Screenshot


# Question 5
**Login to portal.ichimarumaru.tech then follow the instructions! The username and password can be obtained from the insert query in the users table from the .pcap file!**

```
mysql.query matches insert
```

**Explanation**

At the first input ```mysql.query matches insert``` as the filter.

![Screenshot (6975)](https://user-images.githubusercontent.com/61174498/134769851-e1636af4-248e-45a4-82b2-cc26a8e6aeee.png)

Select one packet and follow TCP Stream. It will show the username and password.

Username: akakanomi, pass: pemisah4lautan

![Screenshot (6976)](https://user-images.githubusercontent.com/61174498/134769855-16fbd1e3-6e42-4456-9146-8c84c94cd8ce.png)

Login to portal.ichimarumaru.tech and input the username and password. After login, it will appear one question like below:

![Screenshot (6977)](https://user-images.githubusercontent.com/61174498/134769859-c2dc36dc-35a0-4ad9-804f-cce009efa202.png)

**Solution**

Sebutkan urutan konfigurasi pengkabelan T568B!

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

![Screenshot (6978)](https://user-images.githubusercontent.com/61174498/134769867-202eb5ca-1d09-43ec-85af-7cc796916080.png)

**Explanation**

Solution: ftp.request is used when handling FTP Server

USER		Authentication username.

PASS		Authentication password

# Question 7
**There are 500 zip files saved to FTP Server with names 0.zip, 1.zip, 2.zip, ..., 499.zip. Save and Open the pdf file. (Hint = the name of the pdf is "Real.pdf")**

```
frame contains “Real.pdf” 
```

**Explanation**

At the first input ```frame contains “Real.pdf”``` as the filter.

![Screenshot (6979)](https://user-images.githubusercontent.com/61174498/134769873-5c78650c-84e2-407e-ba12-4862defbe2e0.png)

Select one of the packet, then follow TCP Stream.

![Screenshot (6980)](https://user-images.githubusercontent.com/61174498/134769879-117b453e-d374-47f6-9e8e-ee8cce6cd43f.png)

Change show data to "Raw" and save as pdf. Open the pdf and you got the solution.

![Screenshot (6981)](https://user-images.githubusercontent.com/61174498/134769884-a869d0a3-3a62-4960-8b99-1971df098142.png)

Solution: In the form of pdf.


# Question 8
**Look for the packets that show the retrieval of files from the FTP!**

```
ftp.request.command == STOR
```

**Screenshot**

![Screenshot (6996)](https://user-images.githubusercontent.com/61174498/134770580-93d41dbb-83ab-4032-a6f0-13335ab090dd.png)

**Explanation**

Solution: STOR (Retrieval of files)

RETR		Retrieve a copy of the file

STOR		Accept the data and to store the data as a file at the server site

# Question 9
**From the packets going to FTP, there are indications of storing some files. One of them is a file containing confidential data with the name "secret.zip". Save and open the file!**

```
ftp-data.command contains "secret.zip"
```

**Screenshot**

![Screenshot (6982)](https://user-images.githubusercontent.com/61174498/134769906-9123c33a-57eb-4225-af4c-893a2ac4f07d.png)

![Screenshot (6983)](https://user-images.githubusercontent.com/61174498/134769910-34349d8d-8410-4f57-8768-49ee711ab1e5.png)

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

![Screenshot (6984)](https://user-images.githubusercontent.com/61174498/134769920-baec42d3-976d-4511-a36e-68b65fc1e4e4.png)

![Screenshot (6985)](https://user-images.githubusercontent.com/61174498/134769921-39706a2b-f56b-404d-bf88-a953d2cc8b46.png)

![Screenshot (6986)](https://user-images.githubusercontent.com/61174498/134769925-9d0b8699-4c26-4a40-b82c-25026ed1d24d.png)

![Screenshot (6987)](https://user-images.githubusercontent.com/61174498/134769929-6eebedfd-d1c6-40ee-a897-b11aa767c047.png)

![Screenshot (6988)](https://user-images.githubusercontent.com/61174498/134769930-a0e39b7d-7dd9-408d-9659-feec1670be80.png)

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

![Screenshot (6989)](https://user-images.githubusercontent.com/61174498/134769939-1c44471f-92e6-4028-ae6b-5edcdf88cc1a.png)

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

![Screenshot (6990)](https://user-images.githubusercontent.com/61174498/134769951-b9f73a5c-7e15-4e44-8c5d-65e5ca8a69a3.png)

**Explanation**
Solution:

Port 21 mainly used TCP

# Question 13
**Filter so that wireshark only shows packets going to port 443!**

```
tcp.dstport == 443
```

**Screenshot**

![Screenshot (6991)](https://user-images.githubusercontent.com/61174498/134769955-092dd1b4-f733-40f3-8ffe-39c9c8a9d5b6.png)

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

![Screenshot (6992)](https://user-images.githubusercontent.com/61174498/134769963-bc62d345-8345-45fe-b2a5-350224ec21d2.png)

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

![Screenshot (6993)](https://user-images.githubusercontent.com/61174498/134769967-3c0c99e4-3403-40a8-957b-42d233c70d3a.png)

**Explanation**
Solution:

ip address can be found using 

```
config /all
```

SRC filter will filter packets from designated address

**Problems**
-Not used to Wireshark
-Not used to Networking
-Not used to puzzle based question
