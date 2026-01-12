# Subgoal-Guided Policy Heuristic Search with Learned Subgoals
This repo contains training and test results for $\text{LevinTS}(\pi^{\text{SG}})$ and $\text{PHS}^*(\pi^{\text{SG}})$ from [Subgoal-Guided Policy Heuristic Search with Learned Subgoals](https://icml.cc/virtual/2025/poster/45623). 
Jake Tuero and Michael Buro and Levi Lelis (2025). 
Subgoal-Guided Policy Heuristic Search with Learned Subgoals.
*Forty-second International Conference on Machine Learning*.

Problems used are from the [Boxoban](https://github.com/google-deepmind/boxoban-levels) dataset. 

## Training and Testing Procedure

### Sokoban Unfiltered
- The first 50,000 unfiltered problems were used during training, first 1,000 problems used in testing. 
- For each seed, a random split of 49,000 training problems and 1,000 validation problems chosen. 
- An initial budget of 4000 node expansions with inference batch size of 32. 


### Sokoban Medium
- The first 450,000 medium problems used during training, and all hard problems used in testing.
- For each seed, a random split of 449,000 training problems and 1,000 validation problems chosen.
- An initial budget of 20,000 node visits with inference batch size of 32.

## Results
The plot `png`/`pdf`, and summary data tables in `csv` format are in the `./data` and `./assets` folders.
The time listed is the sum of time each algorithm uses on each problem, which accounts for how many threads are used during training.

### Training Curves
![soko_train](./assets/soko_train.png)

### Test - Unfiltered
|Algorithm          |Num Solved|Expansions|Expansions|Solution Cost|Solution Cost|Time (s)|Time (s)|
|-------------------|----------|----------|----------|-------------|-------------|--------|--------|
|                   |          |mean      |sem       |mean         |sem          |mean    |sem     |
|LevinTS$(\pi^{SG})$|1,000.0   |2,204.16  |317.25    |35.87        |0.25         |2.54    |0.18    |
|PHS$(\pi^{SG})$    |1,000.0   |1,448.10  |180.92    |34.85        |0.26         |1.88    |0.16    |

### Test - Hard
|Algorithm          |Num Solved|Expansions|Expansions|Solution Cost|Solution Cost|Time (s)|Time (s)|
|-------------------|----------|----------|----------|-------------|-------------|--------|--------|
|                   |          |mean      |sem       |mean         |sem          |mean    |sem     |
|PHS$(\pi^{SG})$    |3,308.0   |41,065.93 |1,724.99  |67.45        |0.43         |56.02   |2.29    |
