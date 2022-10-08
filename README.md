# Chia Tic Tac Toe
- [chia-concepts/tic-tac-toe](https://github.com/kimsk/chia-concepts/blob/main/notebooks/misc/tic-tac-toe/README.md)
- [richardkiss/chiaswap](https://github.com/richardkiss/chiaswap)


## Creating Tic Tac Toe Coin

### Phase 1 -- Waiting Room
1. Alice (P1) enters and gives her PK to Bob (P2) and vice versa.
2. Alice enters Bob's PK and vice versa.
3. The waiting room puzzle `a` and its XCH address is generated for Alice and `b` and its XCH address is generated for Bob.
4. Alice sends 1 XCH and 1 mojo and Bob sends 1 XCH each to their provided XCH addresses.

#### -- [Clawback](./notebook/clawback.ipynb)
> The waiting room puzzle for Alice allows the clawback after 100 blocks has passed if Bob has not create his waiting room coin and vice versa.

### Phase 2 -- Singleton Tic Tac Toe (Game) Coin
1. Once two coins with Alice's and Bob's waiting room puzzles are created, Alice can create a spend bundle, provide signatures for Alice's and Bob's spend and create the tic tac toe singleton coin with (2 XCH + 1 mojo).

2. Alice's coin creates an ephermeral launcher coin that creates the game coin. Bob's coin is burned.


#### Security
- Alice's sign the `launcher_id` for both Alice's and Bob's spend.
- Alice's coin asserts coin announcement from the launcher coin.
- Bob's coin asserts coin announcement from the launcher coin.
- Both Alice's and Bob's coins are curried in both players' PK which is also provided to the launcher coin as Key/Value.
- Key/Value List for the launcher coin:
```clojure
(
    ("game" . "tic-tac-toe")
    ("p1_pk" . <alice_pk>)
    ("p2_pk" . <bob_pk>)
)
```

- When Alice's coin is spent, the launcher coin is created, spent, creating the game coin and generate the coin announcement. Alice's coin calculates coin announcement and assert it.
- When Bob's coin is spent, Bob's coin calculates coin annoucement and assert it.

## Playing Tic Tac Toe Game
**TBA**
- [tic tac toe singleton notebook](https://github.com/kimsk/chia-concepts/blob/main/notebooks/misc/tic-tac-toe/singleton.ipynb)

