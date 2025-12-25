# FIFA Ranking:
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
FIFA World Cup final competition matches from QF stage onwards: I = 68
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
