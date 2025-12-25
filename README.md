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

- **UEFA Nations League, CONCACAF NATIONS LEAGUE: I = 15, 25**

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

## How to EDIT The Code:
To change the position or ranking of any team, simply delete the line containing it and move it down or up depending on its number of points and the points of the other teams next to it. Example:
We calculated the points of the Moroccan national team against the Comoros national team in the Africa Cup of Nations and obtained +4.05. This means their points: 1720.39 Morocco is ranked 11th globally, while Croatia is ranked 10th globally, but with a points difference of approximately: 1716.88 This means we will drop the Croatian national team from 10th place to 11th rank here the example:

```js
{ rank: 9, name: "Germany", code: "GER", points: 1724.15, change: "same", changeValue: 1, pointsChange: 0 },
{ rank: 10, name: "Morocco", code: "MAR", points: 1720.39, change: "up", changeValue: 1, pointsChange: +4.05 },
{ rank: 11, name: "Croatia", code: "CRO", points: 1716.88, change: "down", changeValue: 1, pointsChange: 0 },
```
Morocco's ranking will be increased because they moved from 11th to 10th place, meaning they improved. Germany will remain in its current position. However, don't forget to include how many points you gained or lost in PointsChange

### The Matches:
Now, to add a match to the code, I will explain how, For example, we have the match between Morocco and Comoros, and we calculated the equation and everything, But we would like to add information such as how many points Morocco gained, how many points Comoros lost, the type of tournament, who won it, and so on...:

- Here we have the match history (time)

```html
<div class="date-title">21 December 2025</div>
```

- Now you should put this under the match date, like this: 

```html
<div class="date-title">21 December 2025</div>
<div class="matches-list"> <!-- this one -->
```

Now, how do we add the teams that will face each other? We'll explain everything to you now:
```html
                <div class="date-title">21 December 2025</div>
                <div class="matches-list">
                    <div class="match-card">
                        <div class="team-section">
                            <div class="team-change positive">+4.05</div>
                            <div class="team-flag-large">
                                <span class="fi fi-ma"></span>
                            </div>
                            <div class="team-name-large">Morocco</div>
                        </div>
                        
                        <div class="match-center">
                            <div class="match-score">2 - 0</div>
                            <div class="match-type">Africa Cup of Nations | Group Stage</div>
                            <div class="ended-match">Ended with Morocco Victory</div>
                        </div>
                        
                        <div class="team-section">
                            <div class="team-change negative">-4.05</div>
                            <div class="team-flag-large">
                                <span class="fi fi-km"></span>
                            </div>
                            <div class="team-name-large">Comoros</div>
                        </div>
            </div>
```
Now, this is the full code for the game called fi-fi-ma. "Ma" is the flag of Morocco. To find the flags of other countries, go below and you will find the names of the countries (three letters each) along with a definition of the continents. 

I hope you understand how the website works. I put a lot of effort into writing the schedule and setting up the site, calculating every single match without forgetting anything. I might be late in calculating one or two matches, which is normal because I have other circumstances

### About Me:
- Zakaria: 23YO
- Made with ❤
- You can contribute by accurately calculating the national team's points. 