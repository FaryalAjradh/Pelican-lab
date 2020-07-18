Title: Chess Program
Date: 2020-05-12 17:15
Category: Personal
Tags: pelican, publishing, chess, python
Slug: my-blog-post
Author: Fariyal A.
Summary: <i>'Check'</i> this out for a short summary of the program.

### Intro :
A few days ago me and my batchmates worked on making a chess program that lets the user know if their piece might move from one position to another, if a piece is able to capture another piece by parsing a PGN file. We covered edge cases like en passant, castling etc etc. 
</br>
This program was divided into subprograms that were well structered using the principle of modularity of code.

### Generating moves :
The function setup() was used to make an empty board view and an empty piece view that will help us monitor future moves given in the pgn file. In this step, pgn_to_moves() was used to parse the pgn file. In make_moves() we update the board view and piece move one by one until the last move and in the end, when we come to the last move, we check if its a black or white move. If black move exists, we update the two views one last time and display the board; otherwise we directly display the board. 
</br>
The key function in this part of the program is make_one_move() that first checks if its a pawn move (since it has to be handled specially). If it is indeed a pawn move, we call make_pawn_move() and if castling is being carried out, we invoke castle() function, otherwise it means its simply a regular piece so we call move_piece() function.

### Moving Pieces :
In this part of the program, first we check if its a regular pawn move ie the pawn moves only forward, if its a capture ie the pawn moves diagonally and captures the pawn of opponent, if its pawn promotion ie the pawn has come to the end of the board and lastly if its an en passant move. According to the specific move, we carry out different other funtions to update board and piece views.
</br>
We have specified the rules of movements for all other pieces. Using the functions not_blocked() and get_from_square() we update the movements of all other pieces in our board and piece views.   