The project is about simulating MME and SGW of LTE network and GTPv2 communication among them.

If you want to try the code you will need a linux box (I would prefer two linux boxes, one to run mme and other to run sgw.)

Compile the code

----- gcc mme.c -o mme

------ gcc sgw.c -o sgw

and run the code. Please note that you will need to run sgw first.

--- ./sgw

--- ./mme

Use tcpdump to capture the packets on localhost.

--- tcpdump -xXvvv -w temp.cap -s 1500 -i l0

If you want to run the code on two linux boxes, you will need to modify the ip address in mme.c. Find the below section in code and change 127.0.0.1 to ip address on which sgw is running.

ggsn.sin\_family=AF\_INET;

ggsn.sin\_port=htons(2123);

ggsn.sin\_addr.s\_addr=inet\_addr("127.0.0.1");