# Impundulu Bloodline Submod

A submod for **Crusader Kings III: Princes of Darkness** that expands the Impundulu vampire bloodline.

Thematically rooted in Southern African folklore, this submod explores the ancient covenant between the Impundulu vampires and the Bomkazi — mortal life-witches bound to them across generations.

---

## Requirements

- **Crusader Kings III** v1.18.*
- **Princes of Darkness** mod (must load before this submod)

---

## Installation

1. Place the `impundulu_submod` folder in your CK3 mod directory.
2. Place `impundulu_submod.mod` in the same directory as other `.mod` files.
3. In the CK3 launcher, enable **both** Princes of Darkness and this submod.
4. **Load order:** This submod should be loaded **after** Princes of Darkness.

---

## Features

### Enhanced House Modifier

- Overrides the base Impundulu house modifier with improved values (Wraith MaA maintenance reduction, Learning bonus).
- Upgradeable via the Guardian of the Passage mini-objective (removes maluses).

---

### Bomkazi Cultivation

A multi-step progression to seek out and cultivate mortal witch companions for the Impundulu.

- **Choose a cultivation focus:** Scholar (intellect), Healer (health), or Seer (intrigue)
- **Weighted outcomes:** Full success (Bomkazi Witch), partial success (Apprentice), or failure with retry
- Cultivated witches join the court as high-learning/intrigue characters
- Triggers at game start for Impundulu players and can recur every 5-40 years

**New Traits:**

| Trait | Bonuses |
|-------|---------|
| Bomkazi Witch | Learning +2, Health +0.5, Piety +0.1/month, Opinion +10 |
| Bomkazi Apprentice | Learning +1, Health +0.25 |

---

### Major Objective: Cure the Withering Blood

A branching clan objective investigating the decline of the Bomkazi bloodline with two mutually exclusive paths.

**Requirements:**
- Playable Impundulu vampire and house head
- Realm size 20+
- A Bomkazi courtier
- Knowledge of a necromancy path beyond Cenotaph/Haunting (Giovanni, Cappadocian, Harbinger, Lamia, Nagaraja, or Rosselini)

**Branch A — Covenant Renewed:** Preserve and strengthen the Bomkazi bond. Dynasty gains Wraith MaA bonuses (-15% maintenance, +15% damage, +15% toughness).

**Branch B — The Ishologu Rite:** Sever the Bomkazi dependency. Character gains stress reduction (-50%) and scheme success (+10%), at the cost of faith opinion (-10).

The choice is permanent, globally locks the decision, and notifies all vampire players.

---

### Necromancy Knowledge Exchange

A diplomatic character interaction to learn necromancy paths from other vampires.

- **Cost:** 500 prestige
- **Target:** Non-Impundulu necromantic vampire with opinion 20+
- **Negotiation options:**
  - **Offer Gold** (200g) — Straightforward transaction
  - **Offer Favor** — Target gains a hook over the player
  - **Share Secrets** — Mutual exchange of necromantic knowledge
- **Result:** Learn the target's necromancy path
- **Cooldown:** ~20 years
- Supports all PoD necromancy paths (Giovanni, Cappadocian, Harbinger, Lamia, Nagaraja, Rosselini)

---

### Dynasty Legacy Track (5 Tiers)

| Tier | Name | Key Bonuses |
|------|------|-------------|
| 1 | Communion of Life and Death | Necromancy XP +25% |
| 2 | Walkers Between Worlds | Wraith MaA damage/toughness +30%, Learning +1 |
| 3 | Masters of the Cenotaph | Domain limit +1; unlocks Shew-Stone and Nightmare Drums crafting |
| 4 | Keepers of the Passage | Learning per piety +1, same-faith opinion +10; unlocks Witch Eye crafting |
| 5 | Legacy of the Lightning Bird | Monthly prestige +25%, Wraith MaA max size +2 (requires major objective completion) |

---

### Craftable Artifacts (3)

Three unique necromantic artifacts, each with a ritual crafting event chain.

| Artifact | Type | Cost | Key Bonuses | Requirement |
|----------|------|------|-------------|-------------|
| **Shew-Stone** | Trinket | 150g + 100 piety | Intrigue +2, scheme discovery +15% | Cenotaph Path + Legacy Tier 3 |
| **Nightmare Drums** | Regalia | 200g + 150 prestige | Dread baseline +10, hostile scheme success +10% | Haunting Path 3+ + Legacy Tier 3 |
| **Witch Eye** | Trinket | 250g + 200 piety | Necromancy XP +50%, scheme discovery +20%, attraction -15, health -0.1 | Advanced Necromancy + Legacy Tier 4 |

The Witch Eye is limited to one and inflicts a permanent scarring modifier.

---

### Flavor Events (4)

- **The Blood Runs Thin** — Periodic reminder of the Bomkazi bloodline's decline (~4% yearly chance, before objective completion)
- **The Necromancer's Offer** — Hints at the knowledge exchange interaction when a valid target exists (~15% yearly chance)
- **Grief of the Founder** — One-time early-game event for the Impundulu founder or their direct children, reflecting on the original covenant

---

## File Structure

```
impundulu_submod/
├── common/
│   ├── decisions/              # Objective, artifact, and knowledge exchange decisions
│   ├── dynasty_legacies/       # Legacy track definition
│   ├── dynasty_perks/          # 5-tier legacy perks
│   ├── modifiers/              # All gameplay modifiers
│   ├── on_action/              # Event triggers (game start, death, yearly pulse)
│   ├── opinion_modifiers/      # Opinion effects from interactions
│   ├── scripted_effects/       # Objective completion and artifact crafting effects
│   ├── scripted_triggers/      # Custom condition checks
│   └── traits/                 # Bomkazi Witch and Apprentice traits
├── events/
│   ├── IMP_artifacts/          # Artifact crafting ritual events
│   ├── IMP_flavor/             # Bomkazi cultivation, flavor, and knowledge exchange events
│   └── IMP_objectives/         # Objective completion events
├── gfx/
│   └── interface/icons/dynasty/  # Legacy track icon (.dds)
├── localization/english/
│   ├── decisions/              # Decision and tooltip text
│   ├── dynasty_legacies/       # Legacy tier names and descriptions
│   ├── event_localization/     # Event titles, descriptions, and options
│   ├── modifiers/              # Modifier display names
│   └── IMP_interactions_l_english.yml
└── descriptor.mod
```

---

## Content Summary

| Category | Count | Details |
|----------|-------|---------|
| New Traits | 2 | Bomkazi Witch, Bomkazi Apprentice |
| Events | 16+ | 6 cultivation, 4 flavor, 2 objective, 3 artifact, 3 knowledge exchange |
| Decisions | 6 | 1 major objective, 1 mini-objective, 3 artifact crafting, 1 knowledge exchange |
| Artifacts | 3 | Shew-Stone, Nightmare Drums, Witch Eye |
| Legacy Tiers | 5 | Full dynasty legacy track |
| Modifiers | 8+ | Dynasty, character, artifact, and opinion modifiers |

---

## Known Limitations

- AI will not use artifact crafting decisions, knowledge exchange, or cultivation decisions (AI frequency set to 0).
- The Bomkazi cultivation chain creates generic characters.
- PoD updates that rename triggers, modifiers, or necromancy flags may break this submod.

---

## Compatibility

- **Required:** Princes of Darkness mod for CK3
- **CK3 Version:** 1.18.*
- **File prefix:** All files use the `IMP_` prefix to avoid collisions with PoD or other submods.

