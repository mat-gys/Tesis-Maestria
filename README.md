[![DOI](https://zenodo.org/badge/506765367.svg)](https://zenodo.org/badge/latestdoi/506765367)


In this repository, you'll find the replication files for my paper:

# Momentum-stopping: Effects on Performance

## Data
The file `parsed` in the `ouput` folder has all the data necessary to run the dofile regressions.

Individual parsed files containing match information, downloaded from [HLTV](https://www.hltv.org/results), were too large to include in github. 

I've made copies of every main file in the version used to create this paper; they are available in the `output` folder.

## Code
There are some pre-requisites to be able to run the pyhton code:
- [Golang](https://go.dev/dl/): this is necessary for the Awpy library to work. Newest `awpy` version requires Go version 1.18 or above. Make sure to add Go to PATH.
- [Awpy library](https://awpy.readthedocs.io/en/latest/installation.html): this is the main library used to parse the demo files. The author is [Peter Xenopoulos](http://www.peterxeno.com/), who was very kind to not only make the library public but also to help me when I run into some trouble using it. I ran all my code using version 1.2.3 of the awpy library.

Once both are installed, you should be able to run `parser.py`, provided in the folder `code`.
#### parser.py
---

The first code block defines some functions to be used later. The `generate_vector_State()` function was given to me by Peter Xenopoulos, I only made a couple of minor modifications.

After that, there are two main code blocks. The first one goes through all the demo files and parses them, creating a `.json` file for each demo. The second block gathers match and round characteristics, including chat messages where the word pause or tech was used, and writes to `parsed.xlsx`.

#### main.do
---
The `main.do` file contain the code used to clean de data and create the tables/ figures in the paper. All tables and figures are exportex as .tex files onto the `output` folder.

## Data structure example
The file `Data structure example.png` is an image that displays a visualization of the data structure that the awpy library produces. The example is reduced to the minimum information required to understand the structure. Every frame contains more information on every player of each team.
