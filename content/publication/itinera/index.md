---
title: "Synergizing Spatial Optimization with Large Language Models for Open-Domain Urban Itinerary Planning"
weight: 5

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- Yihong Tang*
- admin_star
- Ao Qu*
- Yihao Yan*
- Kebing Hou
- Dingyi Zhuang
- Xiaotong Guo
- Jinhua Zhao
- Zhan Zhao
- Wei Ma

# Author notes (optional)
author_notes:
- 
- 
- 
- 

date: "2024-02-11T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2024-02-11T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication: Preprint
publication_short: Preprint

abstract: "In this paper, we for the first time propose the task of Open-domain Urban Itinerary Planning (OUIP) for citywalk, which directly generates itineraries based on users' requests described in natural language. OUIP is different from conventional itinerary planning, which limits users from expressing more detailed needs and hinders true personalization. Recently, large language models (LLMs) have shown potential in handling diverse tasks. However, due to non-real-time information, incomplete knowledge, and insufficient spatial awareness, they are unable to independently deliver a satisfactory user experience in OUIP. Given this, we present ItiNera, an OUIP system that synergizes spatial optimization with Large Language Models (LLMs) to provide services that customize urban itineraries based on users' needs. Specifically, we develop an LLM-based pipeline for extracting and updating POI features to create a user-owned personalized POI database. For each user request, we leverage LLM in cooperation with an embedding-based module for retrieving candidate POIs from the user's POI database. Then, a spatial optimization module is used to order these POIs, followed by LLM crafting a personalized, spatially coherent itinerary. To the best of our knowledge, this study marks the first integration of LLMs to innovate itinerary planning solutions. Extensive experiments on offline datasets and online subjective evaluation have demonstrated the capacities of our system to deliver more responsive and spatially coherent itineraries than current LLM-based solutions. Our system has been deployed in production at the TuTu online travel service and has attracted thousands of users for their urban travel planning."



# Summary. An optional shortened abstract.
summary: 

tags: []

# Display this page in the Featured widget?
featured: false

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://arxiv.org/abs/2402.07204'
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

