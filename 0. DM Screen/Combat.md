```encounter
name: Example
creatures:
 - 3: Goblin, 5, 15, 2, 25 # 1 goblin with HP: 7, AC: 15, MOD: 2 worth 25 XP will be added.
```

```encounter-table
name: Encounter Name
creatures:
  - 1: My Monster          # 1 monster named My Monster will be added, with no HP, AC or modifier.
  - 1d6: Goblin, 7, 15, 2        # 1 goblin with HP: 7, AC: 15, MOD: 2 will be added.
  - Goblin, 5, 15, 2, 25      # 1 goblin with HP: 7, AC: 15, MOD: 2 worth 25 XP will be added.
```

```encounter-table
name: Encounter Name
creatures:
  - 1: My Monster          # 1 monster named My Monster will be added, with no HP, AC or modifier.
  - 1d6: Goblin, 7, 15, 2        # 1 goblin with HP: 7, AC: 15, MOD: 2 will be added.
  - Goblin, 5, 15, 2, 25      # 1 goblin with HP: 7, AC: 15, MOD: 2 worth 25 XP will be added.
```

```encounter
name: Weak Party
creatures:
 - 1: Thug
 - 2: Goblin, 5, 15, 2, 25      # 1 goblin with HP: 7, AC: 15, MOD: 2 worth 25 XP will be added.

---

name: Strong Party
creatures:
 - 1: Thug
 - 5: Bandit

---

name: Very Strong Party
creatures:
 - 2: Thug
 - 4: Bandit

```

```encounter-table
name: Weak Party
creatures:
 - 1: Thug
 - 2: Goblin, 5, 15, 2, 25      # 1 goblin with HP: 7, AC: 15, MOD: 2 worth 25 XP will be added.

---

name: Strong Party
creatures:
 - 1: Thug
 - 5: Bandit

---

name: Very Strong Party
creatures:
 - 2: Thug
 - 4: Bandit

```
