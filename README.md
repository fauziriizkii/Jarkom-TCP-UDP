# Jarkom-TCP-UDP

#### Soal No 1
 
> What is the IP address and TCP port number used by the client computer (source) that is transferring the alice.txt file to gaia.cs.umass.edu? To answer this question, it’s probably easiest to select an HTTP message and explore the details of the TCP packet used to carry this HTTP message, using the “details of the selected packet header window” (refer to Figure 2 in the “Getting Started with Wireshark” Lab if you’re uncertain about the Wireshark windows).

````
Ip Address : 192.168.101.123
Port       : 56966
````

![image](https://github.com/fauziriizkii/Jarkom-TCP-UDP/assets/114478450/e5427a34-4862-4a56-a04f-4af8bb05f2c0)


### Soal No 2
> What is the IP address of gaia.cs.umass.edu? On what port number is it sending and receiving TCP segments for this connection?

````
IP Address : 128.119.245.12
Port       : 80
````

![image](https://github.com/fauziriizkii/Jarkom-TCP-UDP/assets/114478450/f4537d79-3e45-49f9-9f8d-6d9bf0fb1e41)

### Soal No 3
> What is the sequence number of the TCP SYN segment that is used to initiate the TCP connection between the client computer and gaia.cs.umass.edu? (Note: this is the “raw” sequence number carried in the TCP segment itself; it is NOT the packet # in the “No.” column in the Wireshark window. Remember there is no such thing as a “packet number” in TCP or UDP; as you know, there are sequence numbers in TCP and that’s what we’re after here. Also note that this is not the relative sequence number with respect to the starting sequence number of this TCP session.). What is it in this TCP segment that identifies the segment as a SYN segment? Will the TCP receiver in this session be able to use Selective Acknowledgments (allowing TCP to function a bit more like a “selective repeat” receiver, see section 3.4.5 in the text)?

````
Sequence number (raw) = 4236649287 
Flags = 0x002 (SYN)
````

![image](https://github.com/fauziriizkii/Jarkom-TCP-UDP/assets/114478450/8b8f6a98-e143-49fc-b153-812a389030e9)

### Soal No 4
> What is the sequence number of the SYNACK segment sent by gaia.cs.umass.edu to the client computer in reply to the SYN? What is it in the segment that identifies the segment as a SYNACK segment? What is the value of the Acknowledgement field in the SYNACK segment? How did gaia.cs.umass.edu determine that value?

````
Sequence number (raw) = 1068969752 
Acknowledgment number (raw) = 4236649188 
Flags = 0x012 (SYN, ACK)
````

![image](https://github.com/fauziriizkii/Jarkom-TCP-UDP/assets/114478450/081371b2-e4bc-43b7-a093-94941ec278da)

### Soal No 5
> What is the sequence number of the TCP segment containing the header of the HTTP POST command? Note that in order to find the POST message header, you’ll need to dig into the packet content field at the bottom of the Wireshark window, looking for a segment with the ASCII text “POST” within its DATA field. How many bytes of data are contained in the payload (data) field of this TCP segment? Did all of the data in the transferred file alice.txt fit into this single segment?

````
Sequence number (raw) = 4236801228
Payload size = 1358 Bytes
````
![image](https://github.com/fauziriizkii/Jarkom-TCP-UDP/assets/114478450/3f8f5357-0c56-49b0-a4af-176688d0bdbe)

### Soal No 6
> Consider the TCP segment containing the HTTP “POST” as the first segment in the data transfer part of the TCP connection.

````
Arrival Time: 09 : 43 : 26.840557000 WIB
Receiving Time = 09 : 43 : 26.885500000
````

![image](https://github.com/fauziriizkii/Jarkom-TCP-UDP/assets/114478450/91882994-3b75-45d9-98a1-8d755837df45)

![image](https://github.com/fauziriizkii/Jarkom-TCP-UDP/assets/114478450/671117f8-4f6b-477e-a92d-43199e4049c0)

### Soal No 7
> What is the length (header plus payload) of each of the first four data-carrying TCP segments?

````
Header = 32 + payload = 1358 bytes,
Total = 1390 bytes
````

### Soal No 1
> Select the first UDP segment in your trace. What is the packet number4 of this segment in the trace file? What type of application-layer payload or protocol message is being carried in this UDP segment? Look at the details of this packet in Wireshark. How many fields there are in the UDP header? (You shouldn’t look in the textbook! Answer these questions directly from what you observe in the packet trace.) What are the names of these fields?

````
No. Packet = 289
````
![image](https://github.com/fauziriizkii/Jarkom-TCP-UDP/assets/114478450/33b9c0d4-e34a-46e1-a7fc-8db625f0984e)

Header = Source port, Destination port, Length, and Checksum

![image](https://github.com/fauziriizkii/Jarkom-TCP-UDP/assets/114478450/a35d6b57-21d3-430c-bf6c-6c7513f3459f)

### Soal No 2
> By consulting the displayed information in Wireshark’s packet content field for this packet (or by consulting the textbook), what is the length (in bytes) of each of the UDP header fields?

````
total length dari UDP header adalah 2 + 2 + 2 + 2 = 8 bytes
````

## Soal No 3
> The value in the Length field is the length of what? (You can consult the text for this answer). Verify your claim with your captured UDP packet. 

````
34 is the value of total size of the packet, as it is the total sum of UDP header (8 bytes) + UDP payload (26 bytes)
````

![image](https://github.com/fauziriizkii/Jarkom-TCP-UDP/assets/114478450/74466375-ee00-465a-8756-5cad9f074b8b)

### Soal No 4
> What is the maximum number of bytes that can be included in a UDP payload? (Hint: the answer to this question can be determined by your answer to 2. above)

Maksimum jumlah byte yang dapat dimuat dalam payload UDP adalah 65.527 byte. UDP memiliki bidang 16-bit untuk panjang payload, yang mampu mewakili angka dari 0 hingga 65.535 (2^16 - 1). Namun, header UDP memiliki panjang 8 byte. Dengan demikian, ukuran payload terbesar adalah 65.535 - 8 = 65.527 byte. Ini mewakili jumlah data maksimum yang dapat diangkut oleh payload sebuah paket UDP tunggal.

### Soal No 5
> What is the largest possible source port number? (Hint: see the hint in 4.)

Angka tertinggi yang dapat digunakan sebagai nomor port sumber dalam protokol lapisan transportasi UDP atau TCP adalah 65.535. Hal ini dikarenakan representasi menggunakan 16 bit, yang mencakup rentang angka dari 0 hingga 65.535 (2^16 - 1). Nomor port berperan dalam identifikasi berbagai titik akhir komunikasi di dalam sebuah perangkat, dan merupakan elemen kunci dalam sistem addressing pada jaringan komunikasi.

### Soal No 6
> What is the protocol number for UDP? Give your answer in decimal notation. To answer this question, you’ll need to look into the Protocol field of the IP datagram containing this UDP segment (see Figure 4.13 in the text, and the discussion of IP header fields).

Hasil : 17

![image](https://github.com/fauziriizkii/Jarkom-TCP-UDP/assets/114478450/64443012-c77c-48b7-aa7b-abf5c213b827)

### Soal No 7
> Examine the pair of UDP packets in which your host sends the first UDP packet and the second UDP packet is a reply to this first UDP packet. (Hint: for a second packet to be sent in response to a first packet, the sender of the first packet should be the destination of the second packet).
> What is the packet number5 of the first of these two UDP segments in the trace file?

Packet number 290 comes first, followed by packet number 291. The source port number in packet 290 (request) matches the destination port number in packet 291 (reply).







