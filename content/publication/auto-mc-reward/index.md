---
title: "Auto MC-Reward: Automated Dense Reward Design with Large Language Models for Minecraft"
weight: 4

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- Hao Li
- Xue Yang
- admin
- Xizhou Zhu
- Jie Zhou
- Yu Qiao
- Xiaogang Wang
- Hongsheng Li
- Lewei Lu
- Jifeng Dai

# Author notes (optional)
author_notes:
- 
- 
- Equal Contribution
- 

date: "2023-12-14T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2023-12-14T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *CVPR 2024*
publication_short: In *CVPR 2024*

abstract: "Traditional reinforcement-learning-based agents rely on sparse rewards that often only use binary values to indicate task completion or failure. The challenge in exploration efficiency makes it difficult to effectively learn complex tasks in Minecraft. To address this, this paper introduces an advanced learning system, named Auto MC-Reward, that leverages Large Language Models (LLMs) to automatically design dense reward functions, thereby enhancing the learning efficiency. Auto MC-Reward consists of three important components: Reward Designer, Reward Critic, and Trajectory Analyzer. Given the environment information and task descriptions, the Reward Designer first design the reward function by coding an executable Python function with predefined observation inputs. Then, our Reward Critic will be responsible for verifying the code, checking whether the code is self-consistent and free of syntax and semantic errors. Further, the Trajectory Analyzer summarizes possible failure causes and provides refinement suggestions according to collected trajectories. In the next round, Reward Designer will take further refine and iterate the dense reward function based on feedback. Experiments demonstrate a significant improvement in the success rate and learning efficiency of our agents in complex tasks in Minecraft, such as obtaining diamond with the efficient ability to avoid lava, and efficiently explore trees and animals that are sparse on the plains biome."



# Summary. An optional shortened abstract.
summary: 

tags: []

# Display this page in the Featured widget?
featured: false

# Custom links (uncomment lines below)
links:
- name: Demo
  url: https://yangxue0827.github.io/auto_mc-reward.html

url_pdf: 'https://arxiv.org/abs/2312.09238'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
#  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/pLCdAaMFLTE)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

