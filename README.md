# Chia Tic Tac Toe
- [chia-concepts/tic-tac-toe](https://github.com/kimsk/chia-concepts/blob/main/notebooks/misc/tic-tac-toe/README.md)
- [richardkiss/chiaswap](https://github.com/richardkiss/chiaswap)


## Creating Tic Tac Toe Coin

### Phase 1 -- Waiting Room
1. Alice enters and gives her PK to Bob and vice versa.
2. Alice enters Bob's PK and vice versa.
3. The waiting room puzzle `a` and its XCH address is generated for Alice and `b` and its XCH address is generated for Bob.
4. Alice sends 1 XCH and 1 mojo and Bob sends 1 XCH each to their provided XCH addresses.

> The waiting room puzzle for Alice allows the clawback after 24 hrs if Bob has not create his waiting room coin and vice versa.

### Phase 2 -- Tic Tac Toe Coin
1. Once two coins with Alice's and Bob's waiting room puzzles are created, anyone can spend (absorb) and the tic tac toe singleton coin with (2 XCH - 1 mojo) is created.


## Playing Tic Tac Toe Game
**TBA**
- [tic tac toe singleton notebook](https://github.com/kimsk/chia-concepts/blob/main/notebooks/misc/tic-tac-toe/singleton.ipynb)

