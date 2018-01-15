# Poker

Hussain Dar


I have implemented a poker program in C++ where 5 players can play and decide who is the champion of poker. The players will face off in one round and
each player draws 5 cards from the deck to the hand and whoever gets the highest value hand wins. If two or more people have the 
same value in the hand then the progam will randomly pick one of the player as the winner thus adding more luck to the fun. 

This program looks for the following types of hands in Poker from highest to lowest through the use of the following functions:
```
1.Straight flush 
Five cards in a sequence, all in the same suit

bool isStraightFlush(vector<Card> playerHand);

2.Four of a kind 
All four cards of the same rank

bool isFourOfAKind(vector<Card> playerHand);


3.Full House
Three of a kind with a pair

bool isFullHouse(vector<Card> playerHand);

4.Flush
Any five cards of the same suit, but not in a sequence.

bool isFlush(vector<Card> playerHand);

5.Straight
Five cards in a sequence, but not of the same suit.

bool isStraight(vector<Card> playerHand);

6.Three of a kind
Three cards of the same rank.

bool isThreeOfAKind(vector<Card> playerHand);


7.Two pair
Two different pairs

bool isTwoPairs(vector<Card> playerHand);

8.Pair
Two cards of the same rank

bool isOnePair(vector<Card> playerHand);

9.High Card
When you haven't made any of the hands above, the highest card plays
```
This program consists of two classes. One is a Deck class and two is a Player class. The Deck class holds a struct of type Card that
holds information about a card's rank and suit. A Deck is premade and then shuffled. The Player class holds information about the user's
name and their score

For testing purposes I have made several setter functions inside the Deck class that allows the user to get certain cards in their hand
so that I can show all the different test cases of a player winning with a certain hand
```
void setPlayer1Hand(vector<Card> samplePlayerHand);
void setPlayer2Hand(vector<Card> samplePlayerHand);
void setPlayer3Hand(vector<Card> samplePlayerHand);
void setPlayer4Hand(vector<Card> samplePlayerHand);
void setPlayer5Hand(vector<Card> samplePlayerHand);
``` 
So if you wanted to test out these functions then all you would need to do is in the main.cpp file just comment out:
``` 
theDeck.draw();
```  
and in something like this in place of the draw function:
```  
theDeck.setPlayer1Hand(theDeck.getMockDataOfThreeOfAKind());
theDeck.setPlayer2Hand(theDeck.getMockDataOfStraightFlush());
theDeck.setPlayer3Hand(theDeck.getMockDataOfFourOfAKind());
theDeck.setPlayer4Hand(theDeck.getMockDataOfFullHouse());
theDeck.setPlayer5Hand(theDeck.getMockDataOfFlush());
```  
You would also need to change 
```  
Player player1("player1",theDeck.checkPlayerScore(theDeck.getPlayer1Hand())),
    player2("player2",theDeck.checkPlayerScore(theDeck.getPlayer2Hand())),
    player3("player3",theDeck.checkPlayerScore(theDeck.getPlayer3Hand())),
    player4("player4",theDeck.checkPlayerScore(theDeck.getPlayer4Hand())),
    player5("player5",theDeck.checkPlayerScore(theDeck.getPlayer5Hand()));
```  
to something like this
```  
Player player1("player1",theDeck.checkPlayerScore(theDeck.getMockDataOfThreeOfAKind())),
    player2("player2",theDeck.checkPlayerScore(theDeck.getMockDataOfStraightFlush())),
    player3("player3",theDeck.checkPlayerScore(theDeck.getMockDataOfFourOfAKind())),
    player4("player4",theDeck.checkPlayerScore(theDeck.getMockDataOfFullHouse())),
    player5("player5",theDeck.checkPlayerScore(theDeck.getMockDataOfFlush()));
```
I had to make the following assumptions while working on this poker game since I do not know poker that well
and there are many variations of the rules:

``` 
1.Ace has the highest rank
2.A poker round with 5 people last one turn
3.If a tie occurs then someone is chosen as random
``` 
I also have sample output images that will be available for the public to look at. They will stored in a directory called output.

The trickiest thing about this poker game was not realizing sooner that sorting my hand would make my life easier. When checking for each type of
hand I tried making sure to avoid unecessary calculations in order to improve efficiency. To run this program you just need to make sure you have
all the .cpp and h files together and compile, link, and executing the program. I ran mine through Xcode because Xcode gives me a great
way to debug.




