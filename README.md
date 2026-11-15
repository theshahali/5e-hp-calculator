# 5e Hit Point (HP) & Character Stat Math Reference (2024 & 2014 SRD)

Quick formula reference and interactive calculators for fifth edition tabletop character creation and level-up math.

🔗 **Live Web App (Offline PWA):** **[https://5ehp.app](https://5ehp.app/)**

---

## Interactive Calculators
- **[5e HP & Multiclass Calculator](https://5ehp.app/)** — Level 1–20 Max HP, Fixed Average vs. Rolled Hit Dice, Tough Origin Feat, Dwarf, Draconic Resilience, and *Aid*.
- **[5e 27-Point Buy & Standard Array Calculator](https://5ehp.app/point-buy/)** — 2024 Background (`+2/+1` or `+1/+1/+1`) and 2014 Racial ability score builder.
- **[5e Armor Class (AC) Calculator](https://5ehp.app/ac/)** — Light, Medium, and Heavy armor, Shields, Barbarian/Monk Unarmored Defense, and *Mage Armor*.
- **[5e Short Rest Hit Dice Calculator](https://5ehp.app/hit-dice/)** — Single-class and multiclass Hit Dice pools (`d6`, `d8`, `d10`, `d12`) with 2024 vs. 2014 Long Rest recovery.
- **[5e Temporary HP & Effective HP Calculator](https://5ehp.app/temp-hp/)** — Non-stacking Temp HP rules, *Aid* max-HP buffs, Damage Resistance, and Concentration DC checks.

---

## Core 5e HP Formula (JavaScript Snippet)

```js
const HIT_DIE = { d6: 6, d8: 8, d10: 10, d12: 12 };

function calcFixedAverageHP(dieSize, level, conMod, hasTough = false, isDwarf = false) {
  const fixedAvg = dieSize / 2 + 1; // d6=4, d8=5, d10=6, d12=7
  const lvl1Base = Math.max(1, dieSize + conMod);
  const laterBase = Math.max(1, fixedAvg + conMod) * (level - 1);
  const perLevelBonuses = ((hasTough ? 2 : 0) + (isDwarf ? 1 : 0)) * level;
  return lvl1Base + laterBase + perLevelBonuses;
}
```

## License
Formulas follow the 5e System Reference Document (SRD 5.1 & 5.2) under Creative Commons Attribution 4.0 (CC-BY-4.0).
