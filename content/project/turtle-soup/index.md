---
title: GPT Turtle Soup
summary: "AI for playing the turtle soup game: create problems, guess and judge"
tags:
- Personal
date: "2023-12-01T00:00:00Z"
weight: 8

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: 
  focal_point: Smart

url_code: "https://github.com/wzk1015/GPT-turtlesoup"
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



# GPT海龟汤

使用ChatGPT来玩海龟汤，既能出题，又能当玩家，还能当裁判

还可以玩猜人物游戏！

> 仍在开发中，目前海龟汤生成的题目效果较为一般



## 配置

```bash
pip install openai
```

新建`openai_key.txt`并将api key保存在txt内



## 海龟汤

人类出题，GPT当玩家，人类当裁判（享受智商压制GPT的快感）

```bash
python play.py --problem_path "problem.txt" --gpt_play
```

人类出题，GPT当玩家，GPT当裁判（看两个GPT为你的题目焦头烂额）

```bash
python play.py --problem_path "problem.txt" --gpt_play --gpt_judge
```

GPT出题，GPT当玩家，GPT当裁判（全自动化看三个GPT对抗）

```bash
python play.py --gpt_problem --gpt_judge --gpt_play
```

GPT出题，人类当玩家，GPT当裁判（再也不用自己找海龟汤了）

```bash
python play.py --gpt_problem --gpt_judge
```



如果采用人类出题，应当在`problem.txt`中第一行写题目，第二行写答案。

### 示例

```
GPT作为玩家
GPT作为裁判
题目: 一女子某晚进了公厕，里面的灯很昏暗,只见厕所里刚好还有一人，女子打了声招呼便匆忙地进了隔间，第二天，警察因昨晚相同时间厕所发生了杀人案而找上她，质问了她当时为什么没有报警，请推理。
    
问: "那个晚上，厕所里面除了女子还有被杀的人以外，还有其他人在场吗？"
答: 是
问: "那个晚上，女子所看见的其他人，是不是就是被杀的那个人?"
答: 不是
问: "那个晚上，女子所看见的其他人，是不是杀人犯？"
答: 是
问: "那晚女子进入厕所时，是否注意到了任何异常的情况或者声音？"
答: 不是
问: "那个晚上，女子与杀人犯是否有任何交流或者接触？"
答: 是
问: "女子是否知道那个人是杀人犯？"
答: 不是
问: "女子和被杀的人之间，有没有什么关系？"
答: 不相关
问: "女子和杀人犯之间，有没有什么关系？"
答: 不相关
问: "杀人案发生的地点，是在女子进厕所的那个隔间吗？"
答: 不是
问: "女子是否看到了杀人案发生的现场？"
答: 不是
问: "女子是否听到了杀人案发生的声音？"
答: 不是
问: "女子进入厕所后，是不是立刻就进了隔间？"
答: 是

……（略）
```





## 猜人物

在上一部分的命令后加上`--game guess_person`即可！

如果采用人类出题，在`problem.txt`中直接写明答案。

### 示例

```
GPT作为玩家
GPT作为裁判
GPT生成题目...
贝多芬
问: 他是政治家吗？
答: 不是
问: 他是体育界的人物吗？
答: 不是
问: 他是娱乐圈的人物吗？
答: 是
问: 他是演员吗？
答: 不是
问: 他是音乐家吗？
答: 是
问: 他是流行音乐领域的吗？
答: 不是
问: 他是古典音乐领域的吗？
答: 是
问: 他是作曲家吗？
答: 是
问: 他是贝多芬吗？
答: 成功
成功！
答案: 贝多芬
```

