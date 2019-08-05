1 April 2019

          Hyper Text Othhelo Game Control Protocol (HTOGCP/1.0)

Abstract
   This document subscribes how to Othhelo works on network.

1. How to work
  Othhelo needs server for games on network.
  The server controls rooms and client.
  
  Host of room(host) requests server to make room with board size.
  Host can set password to room.
  The server returns room number(oops,it needs 64bit interger).
  
  Guest of room(guest) requests server to login with room number.
  The server returns board size.
  
  If guest logined successfly, the server notifies clients got ready.
  Host is always black turn.
  Commands to put is send opposite by server.But server doesn't parse these commands.
  If connection closed, the server notifies that to opposite.
  
2.Commands
  <hoge> is variable.
  Client side:
    ROOM <width> <height>
      Make room with specified size.
    ROOM <width> <height> PASSWORD <password>
      Make room with specified size and set password to room.
    LOGIN <room number>
      Login to room.
    LOGIN <room number> PASSWORD <password>
      Login to room with password.
    PUT <x> <y>
      Put a piece to specified position.
    FREEPUT <x> <y>
      Put a piece to specified position with ignoring reversi roles.
    CLOSED
      This command is sended when connection close.
  
  Server side:
    SUCCESS
      This command is sended when commands to server processed successfly.
       Added some variables if needs.
    READY
       This command is sended when guest connected successfly.
    CLOSED
      This command is sended when a client connection closed.

3.Afterword
  This is joke document but this protocol works on "Othhelo" and "OthheloServer" in my repository.
  Please enjoy! :)

