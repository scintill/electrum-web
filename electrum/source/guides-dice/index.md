title: Dice
prev: cool-storage
next: ecommerce
---

#### Step 1) roll one six sided dice to determine block

*ie. which giant rectangular block to scroll to*

**Examples**:

- if Dice_A == 6, go to block 6
- if Dice_A == 1, go to block 1

```bash
$ rolldice -s 1d6
Roll #1: (5 ) = 5
# go to block 5
```

#### Step 2) roll two six sided dice to determine column

**Examples**:

- if Dice_A == even, then go to columns labeled EVEN
- if Dice_B == 6, then go to column "EVEN-6"
- if Dice_A == odd, then go to columns labeled ODD
- if Dice_B == 1, then go to column "ODD-1"

```bash
$ rolldice -s 2x1d6
Roll #1: (4 ) = 4
Roll #2: (3 ) = 3
# go to column EVEN-3
```

#### Step 3) roll two six sided dice to determine row

**Examples**:

- if Dice_A == 1 && Dice_B == 1, pick row "1-1"
- if Dice_A == 1 && Dice_B == 3, pick row "1-3"
- if Dice_A == 2 && Dice_B == 4, pick row "2-4"
- if Dice_A == 5 && Dice_B == 5, roll again
- if Dice_A == 5 && Dice_B == 6, roll again
- if Dice_A == 6 && Dice_B == 4, roll again
- if Dice_A == 6 && Dice_B == 5, roll again
- if Dice_A == 6 && Dice_B == 6, roll again

```bash
$ rolldice -s 2x1d6
Roll #1: (2 ) = 2
Roll #2: (5 ) = 5
# roll again
$ rolldice -s 2x1d6
Roll #1: (1 ) = 1
Roll #2: (3 ) = 3
# go to row 1-3
```

#### Step 4) Write down the word at the intersection

**road**

#### Step 5) Repeat Steps 1-4 twelve times
