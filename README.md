# FIFA Ranking
> [!WARNING]
> We are not the official FIFA ranking website and are not affiliated with them in any way. We are simply a website that calculates and predicts the points of national teams in the FIFA world rankings for upcoming updates before they are released on the official FIFA website

## How do we calculate:
We use the Elo System adopted by FIFA since 2018, and it is as follows:

P = PBefore + I x (W - WE)

- **P = Points after calculation**
- **PBefore: Points before calculation**
- **I = Match type:**
```
Friendly matches played outside of International Match Calendar windows : I = 5
```

```
Friendly matches played during International Match Calendar windows: I = 10
```

```
Group phase matches of Nations League competitions: I = 15
```

```
Play-off and final matches of Nations League competitions: I = 25
```

```
Confederation final competition matches up until the QF stage: I = 35
```

```
Confederation final competition matches from the QF stage onwards; all FIFA Confede-
rations Cup matches: I = 40
```

```
FIFA World Cup final competition matches up until QF stage: I = 50
```

```
FIFA World Cup final competition matches from QF stage onwards: I = 60
```

- **W**: Match result:
```
Win = 1
```

```
Draw = 0.5
```

```
WIN In Penalties: 0.75
```

```
Lose In Penalties: 0.5
```

```
Lose: 0
```

- **WE: Expected result:**
To calculate it, we need to do the following: 
We have an example:

A = 1720.32

B = 1516.18

```
1720.32 - 1516.18 = 204.14

204.14 ÷ 600 = 0.3402333333

10^(-0.3402333333) = 0.4568426759

1 + 0.4568426759 = 1.4568426759

1 ÷ 1.4568426759 = 0.6864159161
```

Now we have a number with many digits, but we will take three digits after the decimal point, which are: 
**0.686**
Now, if we find the last number to be 5 or higher, we will increase the points. I mean 5, 6, 7, 8, 9, so we will increase the points like this: 

Before:
**0.68**

Now: 
**0.69**

Also, the WE we obtained will be taken by the team with the most points, and since we had Team A, they will take the WE we calculated

And now we will calculate:

1720.32 + 10 x (1 - 0.69) = 1723.42

However, there is another method for calculating points that is 100% accurate, and we use it on our website. The method I gave you is not 100% accurate; even if, for example, we calculated it and found 1723.42, FIFA will either decrease or increase it, making it 1723.45. 

## What is the I that tournaments use?!:
- **World Cup: I = 50, 60**

- **AFCON, UEFA, CONMEBOL, CONCACAF, AFC, OFC CUPS: I = 35, 40**

- **UEFA Nations League, CONCACAF NATIONS LEAGUE: I = 15, 25

- **Friendly Matches At these times:**
```
For 2026:

21 December 2025 ------> 18 January 2026 (AFCON CUP)

23 March 2026 ------> 31 March 2026 (2 Max Number of Matches Per Team)

1 June 2026 ------> 9 June 2026 (2 Max Number of Matches Per Team)

11 June 2026 ------> 19 July 2026 (FIFA WORLD CUP)

21 September 2026 ------> 6 October 2026 (4 Max Number of Matches Per Team)

9 November 2026 ------> 17 November 2026 (2 Max Number of Matches Per Team)
```

- **Friendly Matches Outside the times above: I = 5**

- **Arab Cup: I = 5 (at fifa arab cup 2021 it was I = 15, 25, however in today arab cup its I = 5, but most websites thinks its I = 10, 15, 25)**


