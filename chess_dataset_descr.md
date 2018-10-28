This is the dataset of chess games, downloaded from [https://www.kaggle.com/datasnaek/chess](https://www.kaggle.com/datasnaek/chess). The dataset represents a list of chess games. The output of the dataset is winner, which is either represented as white, black, or draw. Additionality, another possible output is the end game type (I don't intend to use this as an output, though), which can be draw, out of time, mate, or resign. The list of features I initially had access to were:
* rated: whether or not the game is rated, as a boolean
* created_at: time of the game creation (I will not use this feature)
* last_move_at: time of the last move (I will not use this feature)
* turns: number of turns in the game
* victory_status: out of time, resign, draw, or mate (I will not use this as an ouput, but I may use it for analysis)
* increment_code: timing of the game (i.e. 10+2 means each player has 10 minutes in total, and after each move, a 2 second addition to the player's timer is made)
* white_id: name of white player (I will not use this feature)
* white_rating: rating of white player
* black_id: name of black player (I will not use this feature)
* black_rating: rating of black player
* moves: a list of moves (I WILL use this feature the most, and extrapulate it into more features)
* opening_eco: name of the opening as a standardized notation
* opening_name: name of the opening (I will not use this feature)
* opening_ply: number of turns in the opening

output:
* winner: winner of the game, can either be White, Black, Draw

I have already manipulated the dataset using one-hot encoding on the winner and victory_status. In order to analyze the dataset, I will one-hot encode the increment_code. Also, I will break the "moves" up into a variety of features (which I haven't yet entirely decided) probably numbering around 20 features. Some will be:
* number of pieces lost in opening
* number of pieces lost in mid-game
* number of pieces lost in end-game
* has_castled
* number of times in check
* features for "number of times [insert chess piece here] moved" 
* number of en passants (I'll have to test if this is useful)
* number of promotions
* queenside or kingside castling?
* length of the mid-game
* opening type (this could be hugely import, and I would like to visualize this against the outcome of the game especially)
	* number of pieces moved in the opening
	* which pieces are moved in the opening
	* how many squares is white targeting at the end of the opening?
	* how many squares is black targeting at the end of the opening?
* mid-game and end-game analysis in a similar fashion to that of the opening game above

While I may not use all of these features, I would like to encode them and use PCA to reduce the dimensionality if possible, or use clustering. I'd also like to visualize all these factors against the game outcome to see which ones influence the dataset more.

I picked this dataset because I really love playing chess. I also think the length (20.2k) of the dataset is good for analysis, and I can draw some conclusions. Perhaps I can use the conclusions that I draw from this project in my own chess games (like knowing which openings support white vs support black, etc...)