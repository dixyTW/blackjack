# BlackJack

Notes and Thoughts: 
1. How do I determine when to pass in other classes as parameters, and which
functions should go to which class
2. How do I make my code more readable
3. How do I plan ahead so I don't rewrite too much code
4. Everything is public so anywhere in the code classes would have access to other class's variables, not sure how I should decide if something should be private or public.

Main: simply executes the game BlackJack

BlackJack: Controls the flow of the game. Has Player, Dealer and Deck set as global variables
so functions within the class has access to them (not sure whether it should be a global variable or should I be passing these variables as parameters to the functions within the class e.g. check_split(Player player) or check_split())

Deck: Deck itself is a Stack of Cards. I chose to use a stack because the Deck behaves similar to a stack (LIFO). Card value initialization is done by the Deck. I used collections.shuffle to shuffle the deck. 

Cards: Cards have symbol (unused, just for aesthetic purposes), values and name. The value of Ace is defaulted to 11, and is adjusted to 1 if needed according to the value of a given hand.

Hand: Hand is a Stack of Cards. Once each round is finished, the cards are popped from the hand and pushed back into the deck. Each hand has a value assotiated to it, db_down to indicate whether the player decided to double down on that Hand, finish to indicate whether the Hand is busted or the player chose to Stand, bet to show the money betted on that Hand, and blackjack indicating whether the is a BlackJack or not.

Player: Player has money that keeps track of the Player's current money, a list of hands because player's can split, list length of 4 because the maximum number of hands a player can have is 4 (2 pairs of the same kind both spliting). 

Dealer: Dealer doesn't have much attributes since he/she doesn't do much and just plays by the rules, ideally Dealer should extend player, but player has list of hands and dealer only needs one, not sure what to do about that, so I created an individual class for dealer.
