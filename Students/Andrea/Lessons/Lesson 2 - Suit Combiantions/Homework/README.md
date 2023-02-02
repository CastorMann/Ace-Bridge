# HOMEWORK

A suit combination is a set of cards divided between two hands, and the solution to a suit combination is a sequence of plays which is optimal in order to win a specified amount of tricks. This week's homework consists of 5 suit combinations and one deal on the topic. I will showcase the solution to one of the suit combinations in order to show how you can go about solving a suit combination. I hope you're familiar with combinatorics in math, because we will be using some of that to solve our suit combinations. In each suit combination, we can assume that we have an unlimited amount of entries to each hand, so we can start to play a card from any hand at any point.

* AKJT  - 5432
* AKJT98 - 32
* AKT9   - 5432
* AK987  - Q654
* AKJT9  - Q876

In the suit combinations above, assume that the left cards are in the north hand and that the right cards are in the south hand.

The solution to the first suit combination is to first play the Ace from north and the 2 from south. After that we enter south and lead the 3 towards the Jack, attempting to finesse the Queen. If the Jack wins, we re-enter south and lead the 4 towards the Ten, repeating the finesse of the Queen. We can reach this conclusion by comparing all possible lines of play and counting the number of layouts that each line is successful in. This is where the math comes in. 

Lets begin by listing all possible lines of play:

1. A + double finesse (the one described above)
2. Double finesse (without first winning the ace)
3. A + K (no finesse, hope that the Queen will drop)

We continue by listing all possible layouts:

Qxxxx - .       (1 combination)
Qxxx  - x       (4 combinations)
Qxx   - xx      (6 combinations)
Qx    - xxx     (4 combinations)
Q     - xxxx    (1 combinations)
.     - Qxxxx   (1 combination)
x     - Qxxx    (4 combinations)
xx    - Qxx     (6 combinations)
xxx   - Qx      (4 combinations)
xxxx  - Q       (1 combination)

the number of combinations for each type of layout comes from the number of ways that we can arrange the small cards (marked by x) between the two hands. For example, Qxx - xx is a total of 6 combinations because 4 unknown cards divided 2-2 between 2 hands can be done in 4 choose 2 = 4!/(2!*2!) = 24/4 = 6 ways. We could also show this by listing all possibilities if the unknown cards are for instance 5432:

Q32 - 54
Q42 - 53
Q52 - 43
Q43 - 52
Q53 - 42
Q54 - 32

Now, lets continue by counting the number of winning layouts for each line, starting with the first line of play (A + double finesse).

Qxxxx - . will work, because the Q is on side so the finesse will work. (1 combination)
the same goes for Qxxx - x, Qxx - xx, Qx - xxx and Q - xxx (4 + 6 + 4 + 1 = 15 combinations)

. - Qxxxx will fail because the finesse is will not work, since the wrong hand has the Queen. The same goes for x - Qxxx, xx - Qxx and xxx - Qx. 

However, the layout xxxx - Q will still work, even though the Queen is on the wrong hand, since it will drop under the Ace in the first trick (this is why we start by playing the ace instead of just doing the double finesse immediately). This is 1 layout.

In total, we will win in 1 + 15 + 1 = 17 layouts.

By the logic explained above, the second line of play will win in the same layouts as the first, except it will lose in the xxxx - Q case, so its a total of 16 layouts.

The 3rd case will only win in the Qx - xxx, Qx - xxx, Q - xxxx and xxxx - Q layouts. This is 4 + 4 + 1 + 1 = 10 layouts in total.

In conclusion, the first line, A + double finesse, the one described in the solution text is the best line, succeeding in 17 layouts out of a total of 32, giving us a total likelihood of success of 17/32 which is approximately 53%.

I know this is a lot and it might be difficult to comprehend all of this at once, but try to read through it a couple of times if you need to and the we will go through it all on Monday. Now, try to find a solution to the 4 other suit combinations.

Finally, I'll give you a full deal that I want you to plan the play for. The contract is 7NT, so you need all 13 tricks. Try to find a way to guarantee the contract regardless of the layout of the opponents cards.

North hand:

♠️ A5432
♥️ AKQ
♦️ J2
♣️ A32


South hand:

♠️ KQ98
♥️ J32
♦️ AKQ
♣️ KQJ

The lead is the 2 of hearts. Remember to count your sure tricks and where you can find your potential tricks that you need in order to take 13 tricks.