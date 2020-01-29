Comunicación unicast: de una a una
==================================

![Chapter 5 image](chapter5.png)

Introducción
------------

La comunicación unicast, enviar mensajes a un único receptor, es la forma habitual de comunicación en Intenet. Por ejemplo, para ver una página web enviamos mensajes unicast a un servidor, que a su vez nos envía la página que hay que mostrar en el navegador.

En este capítulo vamos a enviar mensajes unicast a la placa micro:bit de otro compañero. Y en el proceso vamos a aprender ideas y conceptos fundamentales de las redes de ordenadores, incluyendo:

- el concepto de *unicast*

- el concepto de *protocolo*

- el concepto de *dirección* y *dirección IP*

- el concepto de *paquete de datos* y de *cabecera*

### Qué vas a necesitar:

    2 micro:bits
    1 pizarra
    rotuladores/notas adhesivas
    1 colega

Background
----------

This chapter covers unicast communication. So, what is unicast?

!!! hint "Definition 1: _Unicast_"
	Transmission of a message to a single receiver.

When transmitting messages to each other, computers use *protocols*.

!!! hint "Definition 2: _Protocol_"
	A set of rules for how messages are sent across networks.

Simply, protocols define how computers should send messages and what
they should do when they receive a message. On the Internet, every
computer or device follows the Internet Protocol (IP).

According to Internet Protocol, each device is given a unique *address*,
called an *IP address*. Remember you have already used special addresses
for broadcast and multicast. In this chapter, we consider unicast
addresses. *IP address* is used for unicast on the Internet.

!!! hint "Definition 3: _IP address_"
	A unique string that identifies computers that use the
	Internet Protocol  to communicate over a network. This string is made up
	of 4 decimal numbers, that range between 0 and 255. Each decimal is
	separated by dots. For example, 213.248.234.11 is an IP address.

Your micro:bit also has an address (but it is a bit different). You
already partly changed your micro:bit’s address, by changing the group
ID.

When two computers communicate, the sender sends a data packet  to the
receiver.

!!! hint "Definition 4: _Data packet_" 
	A data packet is a piece of data sent over a network.
	This piece of data has an actual message part (for example, an image or
	a text) and one or more header parts. A header contains helpful
	information for protocols like the sender and receiver IP addresses.

![A data packet contains a message and a header. A header contains information to help a protocol such as sender and receiver addresses, and message types. Different protocols may add different headers to a message.](Datapacket.png)

!!! note ""
	**Figure 1:** A data packet contains a message and a header. A header contains information to help a protocol such as sender and receiver addresses, and message types. Different protocols may add different headers to a message.

The figure above shows how the data and one header forms a data
packet. In this figure, as well as the sender and receiver addresses,
the example header also includes a message type. Message type tells the
receiver whether it is receiving, for example, a text or an image.
Remember, in the previous chapters, your programmed your receivers to
receive a specific type of message. If your packets contained a header
with the message type, then it would be easier to write the receiver
program.

In this chapter, to unicast to other micro:bits, you will create a data
packet by adding a header with source and destination addresses.

Programming: Sending and receiving unicast messages
---------------------------------------------------

In this section, you will program your micro:bits to send and receive
unicast messages completing four tasks. To start with, you need two
micro:bits.

For unicast to work, your radio should receive all messages sent, but
your program should read only the ones that are addressed to you. This
is like seeing all the post coming into your house, but only opening the
envelopes with your name on.

### Task 1: Configure your radio

**Description:** To receive any packet, sent by anybody, you need to use
broadcast as the underlying communication.

**Instruction:** Set your radio group ID like you did in
[Broadcast Communication: One to All](../broadcast/broadcast.md).

### Task 2: Design your header

**Description:** The sender micro:bit needs to add a header to each
message before sending. The message header will include:

- sender address

- receiver address

For the message header, you will create a special string.

**Instruction:** First construct the sender and receiver addresses. With
your teammate, pick two-letter strings as micro:bit addresses. You need
one address for your micro:bit, and one address for your teammate’s
micro:bit. For example, you can use your initials: These are “CS” and
“AK” for the authors of this book. **Important! Your addresses should be
unique across all the addresses of micro:bits that are in the same room
with you.**

Next, join the strings for sender and receiver addresses to create a
header. You will use the blocks under the *Text* menu in the MakeCode Blocks editor
shown in the figure below. Create your header using the blocks in this menu.

![Text menu in PXT](TextMenuinPXT.png)

!!! note ""
	Text menu in the MakeCode Blocks editor

### Task 3: Create your packet and send

**Description:** Now it is time to create your packet. As shown in the
figure with the example packet, a header and a message form a packet. Your final
packet will have the following information:

- sender address

- receiver address

- your message

**Instruction:** Pick a string as your message. For example: “Hello”.
Use the Text blocks to join your message string with your header.

Now, your sender micro:bit is ready to send unicast packets.

### Task 4: Receive a packet

**Description:** When the receiver micro:bit receives a packet, it
decides whether to receive or ignore the packet. Notice that the
receiver micro:bit receives a single string, but it knows that this
string is made up of:

- Sender address: first 2 letters

- Receiver address: next 2 letters

- Sender’s message: the rest of the string

The receiver needs to use this information to decide which packets are
for itself.

**Instruction:** Divide the received string into the *sender address*,
*receiver address*, and *sender’s message* variables.  Use
the Text blocks, for example *substring* and *compare*.

Check if the *receiver address* is equal to your micro:bit’s address. If
it is, then your micro:bit is the rightful receiver. Display the sender
address and the message on your display. If your micro:bit is not the
receiver, be a good citizen, and ignore the message.

### Challenge: Filter senders

**Description:** Sometimes, you may not want to receive messages just
from anybody. For this, you will write a program so that you only
receive messages from two people you know. We will call this your
*allow-list* (often referred to as a *whitelist*).

**Instruction:** Extend the receiver program to also check the *sender
address* field in the header. Check whether this address is in your allow-list. If yes, display the sender address and the message. If not,
ignore the message. Test your program with addresses in and out of your
whitelist.

Extended activity
-----------------

!!! attention "Exercise 1"
	You may have written two separate programs: one for the receiver and one for the sender. Change your program so that both micro:bits can send and receive.

!!! attention "Exercise 2"
	Did you try listening out for messages sent from other micro:bits in your class? How could your program achieve this? Is this the right thing to do? How might you protect your messages from others snooping?

!!! attention "Exercise 3"
	In this chapter, we have covered one way to do a unicast: Putting sender and receiver addresses in a data packet header. But there is another way. Remember [Group communication: one to many](../groupcommunication/groupcommunication.md). If you set your group to be
	only for your pair of micro:bits, then this is like you are unicasting. To unicast like this, choose a unique group ID, like you did for group communication. Announce it on the board so that no one else uses it. Write programs for your pair of micro:bits that send and receive using this radio group ID. What are the limitations of doing unicast like this? **Hint: Think about how many possible group IDs there are. Would this be enough for everyone in the world who has a micro:bit?**

Problems
--------

1. In what ways is unicast like broadcast and group communication? In what ways is it different?

2. Which ones are not IP addresses?

    1. -1.0.0.1

    2. 278.0.10.0

    3. 104.20.14.61

    4. 127.0.0.1

    5. 161.23.84;18

    6. 161.73.246.13

    7. 104.20.14.61.15

3. In this chapter, you used two-letter strings for your addresses. How many different people can you unicast using this address size?

4. When selecting an address size for your message header, can you pick any size you like? In your program, what happens if you increase your address size to 10 letters? Do you see any benefits? Or are there any limitations?

5. How does the size of a data packet header affect the actual packet size? If your data packet size were 100 Bytes, and your header size were 10 Bytes, how big could your messages be? What happens if the header size increases to 50 Bytes?

Resources
---------

- Video: IP addresses and DNS (code.org) -
    <https://youtu.be/5o8CwafCxnU>

- Video: IP addresses (CommonCraft) -
    <https://www.commoncraft.com/video/ip-addresses>

- BBC bitesize networks -
    <http://www.bbc.co.uk/education/topics/zjxtyrd>
