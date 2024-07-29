# LLMoves

This is a project (inspired by [chess-llm](https://nicholas.carlini.com/writing/2023/chess-llm.html) ) to play chess against Large Language Models (LLMs).

This code is very bare-bones. It's just enough to make things run.
Maybe in the future I'll extend it to make it better.


## What is this?

This is a chess engine that plays chess by prompting LLM.
To do this it passes the entire game state as a PGN, and the model plays
whatever move the language model responds with. So in order to respond to
a standard King's pawn opening I prompt the model with

    [White "Garry Kasparov"]
    [Black "Magnus Carlsen"]
    [Result "1/2-1/2"]
    [WhiteElo "2900"]
    [BlackElo "2800"]
    
    1. e4

And then it responds `e5` which means my engine should return the move `e5`.


## Installing

This project has minimal dependencies: just python-chess and requests to
run the UCI engine.

    pip install -r requirements.txt


## Getting Started

### UCI engine

If you already have a UCI-compliant chess engine downloaded and want to play
against the model you can pass `./uci_engine.py`.

## Next steps

I highly doubt I'll do any of these things, but here are some things
I may want to do.

- Work on lichess-bot

- Search: what happens if instead of predicting the top-1 move you predict
different moves and take the "best"? How do you choose "best"?

- Resign if lost: how can you detect if the game is lost and then just
resign if it's obviously over?

- Other models: It would be great to hook this up to other models if any of them
become reasonably good at chess.
