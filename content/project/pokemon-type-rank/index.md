---
title: Pokemon Types PageRank
summary: Use PageRank to rank the Pokemon types according to the Type Chart
tags:
- Personal
date: "2023-03-14T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: 
  focal_point: Smart

url_code: "https://github.com/wzk1015/Pokemon-Types-PageRank"
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---



# Pokemon Types PageRank

Use PageRank to rank the Pokemon types according to the [Type Chart](https://bulbapedia.bulbagarden.net/wiki/Type#Type_chart).



## Mode

### regular

Calculate the overall rank of all types. 

Use the regular Type Chart directly to calculate PageRank scores.

```python
[('Steel', 0.0454),
 ('Ghost', 0.0508),
 ('Fairy', 0.052),
 ('Poison', 0.0525),
 ('Electric', 0.0528),
 ('Fire', 0.0537),
 ('Normal', 0.0542),
 ('Water', 0.0549),
 ('Flying', 0.0553),
 ('Dark', 0.0563),
 ('Dragon', 0.0565),
 ('Ground', 0.0569),
 ('Bug', 0.0573),
 ('Fighting', 0.0575),
 ('Psychic', 0.0591),
 ('Rock', 0.0611),
 ('Grass', 0.0616),
 ('Ice', 0.062)]
```



### attack

Calculate the attack rank of all types. 

For each type, build a separate graph by the Type Chart except for its **defense** (a **column** in the Type Chart), and only keep its own PageRank score.

```python
[('Ground', 0.0632),
 ('Fire', 0.0606),
 ('Rock', 0.0605),
 ('Ice', 0.0602),
 ('Water', 0.06),
 ('Fighting', 0.0582),
 ('Fairy', 0.0575),
 ('Flying', 0.0573),
 ('Steel', 0.0573),
 ('Dark', 0.057),
 ('Psychic', 0.0554),
 ('Grass', 0.0549),
 ('Electric', 0.0545),
 ('Ghost', 0.0526),
 ('Poison', 0.052),
 ('Bug', 0.0518),
 ('Dragon', 0.05),
 ('Normal', 0.0484)]
```



### defense

Calculate the defense rank of all types. 

For each type, build a separate graph by the Type Chart except for its **attack** (a **row** in the Type Chart), and only keep its own PageRank score.

```python
[('Steel', 0.0467),
 ('Ghost', 0.0485),
 ('Fairy', 0.0525),
 ('Normal', 0.0537),
 ('Poison', 0.0538),
 ('Dragon', 0.0538),
 ('Electric', 0.0542),
 ('Fire', 0.0554),
 ('Flying', 0.0558),
 ('Water', 0.0564),
 ('Bug', 0.0574),
 ('Ground', 0.0575),
 ('Fighting', 0.058),
 ('Dark', 0.058),
 ('Psychic', 0.0606),
 ('Rock', 0.0618),
 ('Grass', 0.0634),
 ('Ice', 0.0638)]
```



### inverse

Calculate the [Inverse Battle](https://bulbapedia.bulbagarden.net/wiki/Inverse_Battle) rank of all types. Note that the rank is not the direct reverse of the regular mode.

All the values in the Type Chart are converted from [2, 1, 0.5, 0] to [0.5, 1, 2, 2] respectively.

 ```python
 [('Ice', 0.0471),
  ('Psychic', 0.0511),
  ('Normal', 0.0516),
  ('Bug', 0.053),
  ('Fighting', 0.0532),
  ('Rock', 0.0535),
  ('Grass', 0.0538),
  ('Ground', 0.0539),
  ('Dark', 0.0539),
  ('Flying', 0.0553),
  ('Dragon', 0.056),
  ('Ghost', 0.0561),
  ('Fairy', 0.0563),
  ('Electric', 0.0566),
  ('Water', 0.0581),
  ('Poison', 0.0585),
  ('Fire', 0.0603),
  ('Steel', 0.0716)]
 ```



## References

[Type Tier List by Luke4ever (for Nuzlocke and PVE)](https://www.bilibili.com/video/BV1jg411X7Jf)

[Type Chart](https://bulbapedia.bulbagarden.net/wiki/Type#Type_chart)

[Inverse Battle](https://bulbapedia.bulbagarden.net/wiki/Inverse_Battle)

[PageRank Implementation](https://github.com/cystanford/PageRank)
