---
title: Wordle Solver
summary: Solvers for the popular game Wordle
tags:
- Friend
- Personal
date: "2020-12-01T00:00:00Z"
weight: 6

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: 
  focal_point: Smart

url_code: "https://github.com/LittleNyima/wordle-solver"
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



> Open source solvers for popular game *Wordle* - **Welcome to contribute!**
>
> This a project created by LittleNyima - good job!
>
> And the README below is the Feb 9th version, might be a lot of commits behind the repo - **go check latest update [here](https://github.com/LittleNyima/wordle-solver)**



# Wordle Solver

Implementation of [Wordle - A daily word game (powerlanguage.co.uk)](https://www.powerlanguage.co.uk/wordle/) game and a framework of evaluating Wordle solvers.



## :trophy: Leaderboard

| Solver                                               | Contributor                                   | Last Update (UTC+8) | Success%   | Average Tries | Time Cost \* |
| ---------------------------------------------------- | --------------------------------------------- | ------------------- | ---------- | ------------- | ------------ |
| [TheGreatWzk](solver/TheGreatWzkSolver.py)           | [wzk1015](https://github.com/wzk1015)         | 2022-02-09 21:25    | 97.93      | 3.8907        | 13.4844      |
| [RandomPruning](solver/RandomPruningWordleSolver.py) | [LittleNyima](https://github.com/LittleNyima) | 2022-02-09 19:31    | 98.36 \*\* | 4.1093 \*\*   | 27.1875      |

> \* The time cost is evaluated using [`time.process_time`](https://docs.python.org/3/library/time.html#time.process_time) api on my PC (Intel(R) Core(TM) i7-8750H CPU @ 2.20GHz). It reflects the performance of the algorithm, but it may not be accurate.
>
> \*\* Because of usage of random algorithms, the performance may vary depending on selected random seed.

Please refer to the complete leaderboard [here](LEADERBOARD.md).

## :monkey: Examples

- You can play the game manually:

  ```python
  from wordle import WordleGame, WordleDictionary
  
  with WordleGame(WordleDictionary()).new_game() as game:
      res, attempts = "00000", 0
      while not res == "22222":
          guess = input("Please make your guess: ").strip()
          res, attempts = game.guess(guess)
  ```

- You can implement your own solver and evaluate it using profiler:

  ```python
  import random
  from wordle import WordleDictionary, WordleProfiler, BaseWordleSolver
  
  class RandomWordleSolver(BaseWordleSolver):
      def __init__(self, dictionary):
          super().__init__(dictionary)
      def before_guess(self):
          pass
      def guess(self):
          return random.choice(self.dictionary)
      def after_guess(self, result):
          pass
  
  dictionary = WordleDictionary()
  profiler = WordleProfiler(dictionary)
  solver = RandomWordleSolver(dictionary)
  print(profiler.evaluate_once(solver))
  ```

## :running: Run

If you use ipython, for example:

```shell
ipython solver/TheGreatWzkSolver.py
```

Or you should install the package first then you can run your code:

```shell
python setup.py install
python solver/TheGreatWzkSolver.py
```

## :raising_hand: Contribution

Welcome to create pull requests and contribute your own solver!
