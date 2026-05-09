---
license: cc-by-4.0
language:
- en
tags:
- text-to-image
- jailbreak
- safety
- adversarial
- NSFW
- modifiers
pretty_name: Malicious Modifier Dataset (MMD)
size_categories:
- n<1K
task_categories:
- text-to-image
---

# Malicious Modifier Dataset (MMD)

Part of the **ModX** project:  
> *Modifier Unlocked: Jailbreaking Text-to-Image Models Through Prompts*  
> Shuofeng Liu, Mengyao Ma, Minhui Xue, Guangdong Bai  
> IEEE S&P 2025

## Dataset Description

The **Malicious Modifier Dataset (MMD)** is a curated collection of 717 prompt modifiers that have been identified as capable of adjusting text-to-image (T2I) model outputs toward NSFW (Not-Safe-for-Work) content. The modifiers are collected through art-related websites (DeviantArt, Saatchi Art, and Dark Art Movement), NSFW image-generating prompts from PromptHero, CLIP Interrogator's outputs of 600 NSFW images from Reddit and 4chan. 

This dataset is constructed to support research into the vulnerability of T2I models under modifier-based jailbreaking and to facilitate future work on safety evaluation and defense for T2I models.

**NOTE: THIS DATASET IS USED FOR REASEARCH PURPOSE ONLY!**

## Dataset Structure

| Category | Count | Description |
|----------|------:|-------------|
| Artist | 157 | Artist names / artistic styles with NSFW tendencies |
| Flavor | 267 | Aesthetic descriptors (mood, tone, texture, atmosphere) |
| Medium | 82 | Art media and rendering styles |
| Movement | 116 | Art movements and visual subcultures |
| Trending | 95 | Platform-based and trend-driven style descriptors |
| **Total** | **717** | |

### Files

- `MMD.csv` — flat table with two columns: `modifier`, `category`
- `MMD.json` — modifiers grouped by category

## Usage

```python
import json

with open("MMD.json") as f:
    mmd = json.load(f)

# Access by category
artists = mmd["Artist"]
flavors = mmd["Flavor"]
```

```python
import pandas as pd

df = pd.read_csv("MMD.csv")
print(df.groupby("category").size())
```

## Ethical Statement

This dataset is released **for security and safety research purposes only**. It is intended to help researchers understand vulnerabilities in T2I model safety mechanisms and to develop better defenses. The authors do not condone the use of this dataset to generate harmful, offensive, or illegal content. Users of this dataset are expected to comply with applicable laws and the terms of service of any T2I platform they interact with.

## Citation

```bibtex
@inproceedings{liu2025modifier,
  title={Modifier unlocked: Jailbreaking text-to-image models through prompts},
  author={Liu, Shuofeng and Ma, Mengyao and Xue, Minhui and Bai, Guangdong},
  booktitle={2025 IEEE Symposium on Security and Privacy (SP)},
  pages={355--372},
  year={2025},
  organization={IEEE}
}
```

## Contact

Shuofeng Liu — [shuofeng.liu@uq.edu.au](mailto:shuofeng.liu@uq.edu.au)
