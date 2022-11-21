# [Igo](https://en.wikipedia.org/wiki/Go_(game))
An implementation of the ancient Asian game of Go, to facilitate the learning of mathematical analysis models.  
For a non-programmatic introduction to the game, see [the Wikipedia article on the topic.](https://en.wikipedia.org/wiki/Rules_of_Go)


## Structure
The module is divided into three parts: Go-Ban, Go-Ishi, and Go-Seki;
which represent the Board, the Pieces, and the Analysis respectively.


### Go-Ban
The Go-Ban is the game board within the game of Go. It is defined as a yellow square sporting a 19x19 grid of black lines upon whose intersections
players take turns placing stones, with Black moving first. The board is traditionally 

The GoBan class deals with initializing the framework of the game.  It defines a dictionary that lists all of the tracked
attributes associated with either player; this includes the number of pieces placed and pieces lost, number of groups both
nominally alive and independantly alive, and other constants defined by the game itself.  


### Go-Ishi
Go-Ishi referrs to the stones placed upon the board; the Kuro Go-Ishi und die Shiro Go-Ishi, or the Black Go-Stones and the White Go-Stones respectively.

The GoIshi class contains functionality for simulating the game.  A stone of the color of the player who's turn it currently is placed upon the board and play is passed to the other player.  If any stones are to be captured, they are reverted to empty and the amount of stones lost is given to the capturing player.  A stone is considered to be _captured_ if all of their adjacent open spaces, or _liberties_, are occupied by the opposing player.

Traditionally, the Kuro Go-Ishi are made of a special "_Nachiguro_" slate mined from the deep mountains of Kumano, within the Mei prefecture of Nippon.
The Shiro Go-Ishi in turn are crafted from the shells of a certain clam known to wash upon the shores of the City of Hyuga's Okuraga-hama Beach, of Miyazaki prefecture.  

Today, due to countless centuries of Shiro Go-Ishi production in the city of Hyuga, the clamshells are depleting and all modern clamshell Go-Ishi from Hyuga are produced using clamshells imported from Mexico.  While these shells are considered to be be of the same quality as the traditional Hyuga clamshells, they do not carry the same _sentimental_ value as the Hyuga clamshell stones and as such Shiro Go-Ishi made with actual clams collected from Hyuga are referred to as _Legendary_ Hyuga Clam Go-Stones.


### Go-Seki
_Seki_ is Japanese for _analysis_, ergo Go-Seki is the analysis of the game of Go.  The GoSeki class deals with determining the state of the board and enumerating attributes of formations upon it.  Within the game an individual stone is called a _unit_, and a collection of units sharing liberties is called a _group_. A group is considered to be _alive_ if it has at least one open space within its borders.  If a group contains two or more eyes, it is _unkillable_, that its, it can never be removed from play.  A unit or group can be in danger, or _in seki_ if they could be captured based on their current configuration.

To end the game, both players agree to pass consecutively by passing one of their stones to the other as captured.  When play ends, any units or groups in seki are removed from play as captures.  
