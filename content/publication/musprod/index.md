---
title: "Video Background Music Generation: Dataset, Method and Evaluation"
weight: 3

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- Le Zhuo
- admin
- Baisen Wang
- Yue Liao
- Chenxi Bao
- Stanley Peng
- Songhao Han
- Aixi Zhang
- Fei Fang
- Si Liu

# Author notes (optional)
author_notes:
- 
- Co-first author
- 
- 

date: "2022-11-22T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2022-11-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *ICCV 2023*
publication_short: In *ICCV 2023*

abstract: Music is essential when editing videos, but selecting music manually is difficult and time-consuming. Thus, we seek to automatically generate background music tracks given video input. This is a challenging task since it requires plenty of paired videos and music to learn their correspondence. Unfortunately, there exist no such datasets. To close this gap, we introduce a dataset, benchmark model, and evaluation metric for video background music generation. We introduce SymMV, a video and symbolic music dataset, along with chord, rhythm, melody, and accompaniment annotations. To the best of our knowledge, it is the first video-music dataset with high-quality symbolic music and detailed annotations. We also propose a benchmark video background music generation framework named V-MusProd, which utilizes music priors of chords, melody, and accompaniment along with video-music relations of semantic, color, and motion features. To address the lack of objective metrics for video-music correspondence, we propose a retrieval-based metric VMCP built upon a powerful video-music representation learning model. Experiments show that with our dataset, V-MusProd outperforms the state-of-the-art method in both music quality and correspondence with videos. We believe our dataset, benchmark model, and evaluation metric will boost the development of video background music generation.



# Summary. An optional shortened abstract.
summary: 

tags: []

# Display this page in the Featured widget?
featured: false

# Custom links (uncomment lines below)
links:
- name: Demo
  url: https://drive.google.com/drive/folders/1ASY44xqWGZgKkcHhpzWlOhIbUIMe_epQ?usp=sharing

url_pdf: 'https://arxiv.org/pdf/2211.11248.pdf'
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

