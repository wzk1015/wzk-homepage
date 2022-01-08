---
title: "Confidence-aware Non-repetitive Multimodal Transformers for TextCaps"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin
- Renda Bao
- Qi Wu
- Si Liu*

# Author notes (optional)
author_notes:
- 
- 
- 
- 

date: "2021-02-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2021-02-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *AAAI 2021*
publication_short: In *AAAI 2021*

abstract: When describing an image, reading text in the visual scene is crucial to understand the key information. Recent work explores the TextCaps task, i.e. image captioning with reading Optical Character Recognition (OCR) tokens, which requires models to read text and cover them in generated captions. Existing approaches fail to generate accurate descriptions because of their (1) poor reading ability; (2) inability to choose the crucial words among all extracted OCR tokens; (3) repetition of words in predicted captions. To this end, we propose a Confidence-aware Non-repetitive Multimodal Transformers (CNMT) to tackle the above challenges. Our CNMT consists of a reading, a reasoning and a generation modules, in which Reading Module employs better OCR systems to enhance text reading ability and a confidence embedding to select the most noteworthy tokens. To address the issue of word redundancy in captions, our Generation Module includes a repetition mask to avoid predicting repeated word in captions. Our model outperforms state-of-the-art models on TextCaps dataset, improving from 81.0 to 93.0 in CIDEr. Our source code is publicly available.



# Summary. An optional shortened abstract.
summary: 

tags: []

# Display this page in the Featured widget?
featured: false

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://arxiv.org/pdf/2012.03662.pdf'
url_code: 'https://github.com/wzk1015/CNMT'
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

