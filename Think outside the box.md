# Think Outside the Box
* **Event:** n00bzCTF2024
* **Problem Type:** Pwn
* **Points** 464
 

## Description
Description: You cannot beat my Tic-Tac-Toe bot! If you do, you get a flag! 


## Steps
Running the nc, we can clearly see its just a tic-tac-toe game, where your oppenent(bot) has already made his move('X') to (1,1) => as show below and we are asked to input our move ```i,i```

```
 _ | _ | _
---|---|---
 _ | X | _
---|---|---
 _ | _ | _
 ```

 So whatever you do, the match will either be a draw or end up in favour of the bot. After doing trial and error with random inputs I found out there is a check if your input numbers are less than 3 or not but there is no check for lower limit. So you can input negative numbers.<br>
 Thereby maybe by using only negative integers we can solve the challenge, but doing so will cause errors like segmentation fault.
 But if we look closely after giving input like ``` 0,-1 ```
 we see that the bot doesnt put anything during his turn for 2 rounds.
Now if we put the following input ``` 0,0 ``` ``` 1,0 ``` ``` 2,0 ```, we complete the first column thereby getting the flag
```
Welcome to Tic-Tac-Toe! In order to get the flag, just win! The bot goes first!
 _ | _ | _
---|---|---
 _ | X | _
---|---|---
 _ | _ | _
Move: 0,-1
 _ | _ | _
---|---|---
 _ | X | _
---|---|---
 _ | _ | _
Bot turn!
 _ | _ | _
---|---|---
 _ | X | _
---|---|---
 _ | _ | _
Move: 0,0
 O | _ | _
---|---|---
 _ | X | _
---|---|---
 _ | _ | _
Bot turn!
 O | _ | _
---|---|---
 _ | X | _
---|---|---
 _ | _ | _
Move: 1,0
 O | _ | _
---|---|---
 O | X | _
---|---|---
 _ | _ | _
Bot turn!
 O | _ | _
---|---|---
 O | X | X
---|---|---
 _ | _ | _
Move: 2,0
 O | _ | _
---|---|---
 O | X | X
---|---|---
 O | _ | _
 You won! Flag: n00bz{l173r4lly_0u7s1d3_7h3_b0x_L0L}
```
#### FLAG
n00bz{l173r4lly_0u7s1d3_7h3_b0x_L0L}