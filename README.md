# Sniffer
<p align="center"><img src="https://media.giphy.com/media/9XZyr2dtPQDEY4dviP/giphy.gif" /></p>
<p align="center">Program for monitoring network packets</p>

sniffer is listening by default with filter:
* Interface: `lo`
* Protocol: `UDP`
* Port: `1234`

And search for messages of two types:

### Type 1

| Type | Enrollment | Name Lenght | Name | 
| :------------: | :------------ | :------------ |  :------------ |
| 1 Byte | 8 Bytes | 2 Bytes | According to `Name Lenght`	| 

### Type 2

| Type | Enrollment | 
| :------------: | :------------ |
| 1 Byte | 8 Bytes | 


### Download libpcap

```sh
sudo apt-get install libpcap-dev
```

### Compiling

```sh
# Compiling sniffer
gcc sniffer.c -lpcap -o sniffer

# Compiling sender
gcc sender.c -o sender
```

### Running

For the sniffer add the interface in which you will be listening as a parameter

And for the sender add: the interface, the destination mac, the destination ip, the port, the enrollment, and the student's name (message type and name size will be inferred)

```sh
# In Terminal 1 
sudo ./sniffer lo

# In Terminal 2
sudo ./sender lo 00:00:00:00:00:00 127.0.0.1 4321 98764532 user_name # Pattern with menssage type 1
sudo ./sender lo 00:00:00:00:00:00 127.0.0.1 4321 98764532 # Or Pattern with menssage type 2
```
<!-- # Tipo 1
gcc test.c -o test && ./test lo 50:3e:aa:5c:7a:dc 127.0.0.1 4321 98764532 barbalho12
# Tipo 2
gcc test.c -o test && ./test lo 50:3e:aa:5c:7a:dc 127.0.0.1 4321 98764532 -->


<!-- 	
gcc sniffer.c -lpcap -o sniffer && sudo ./sniffer lo
gcc send2.c -o send2 && sudo ./send2
gcc send1.c -o send1 && sudo ./send1 
-->

<!-- https://www.binarytides.com/packet-sniffer-code-c-linux/ -->
