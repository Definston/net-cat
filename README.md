
# Net-Cat

The project consists on recreating the NetCat in a Server-Client Architecture that can run in a server mode on a specified port listening for incoming connections, and it can be used in client mode, trying to connect to a specified port and transmitting information to the server.

The project must work in a similar way that the original NetCat works, in other words, it is necessary to create a group chat. The project must have the following features :
## Features:
- TCP connection between server and multiple clients (relation of 1 to many).
- A name requirement to the client.
- Control connections quantity.
- Clients must be able to send messages to the chat.
- Do not broadcast EMPTY messages from a client.
- Messages sent, must be identified by the time that was sent and the user name of who sent the message, example : [2020-01-20 15:48:41][client.name]:[client.message]
- If a Client joins the chat, all the previous messages sent to the chat must be uploaded to the new Client.
- If a Client connects to the server, the rest of the Clients must be informed by the server that the Client joined the group.
- If a Client exits the chat, the rest of the Clients must be informed by the server that the Client left.
- All Clients must receive the messages sent by other Clients.
- If a Client leaves the chat, the rest of the Clients must not disconnect.

## Usage
To run the server you need to enter the command:
```bash
$ go run .
Listening on the port :8989
```
Or choose your own port
```bash
$ go run . -port=2525
Listening on the port :2525
$ nc localhost "port"
$
```
Then in the new terminal connect to the server

```bash
$ nc localhost 2525
Welcome to TCP-Chat!
         _nnnn_
        dGGGGMMb
       @p~qp~~qMb
       M|@||@) M|
       @,----.JM|
      JS^\__/  qKL
     dZP        qKRb
    dZP          qKKb
   fZP            SMMb
   HZM            MMMM
   FqM            MMMM
 __| ".        |\dS"qML
 |    `.       | `' \Zq
_)      \.___.,|     .'
\____   )MMMMMP|   .'
     `-'       `--'
[ENTER YOUR NAME]: Yenlik
[2020-01-20 16:03:43][Yenlik]:hello
[2020-01-20 16:03:46][Yenlik]:How are you?
[2020-01-20 16:04:10][Yenlik]:
Lee has joined our chat...
[2020-01-20 16:04:15][Yenlik]:
[2020-01-20 16:04:32][Lee]:Hi everyone!
[2020-01-20 16:04:32][Yenlik]:
[2020-01-20 16:04:35][Lee]:How are you?
[2020-01-20 16:04:35][Yenlik]:great, and you?
[2020-01-20 16:04:41][Yenlik]:
[2020-01-20 16:04:44][Lee]:good!
[2020-01-20 16:04:44][Yenlik]:
[2020-01-20 16:04:50][Lee]:alright, see ya!
[2020-01-20 16:04:50][Yenlik]:bye-bye!
[2020-01-20 16:04:57][Yenlik]:
Lee has left our chat...
[2020-01-20 16:04:59][Yenlik]:
```