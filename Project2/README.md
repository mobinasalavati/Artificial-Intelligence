# Project 2 – Adversarial Search & Genetic Algorithms

Computer Assignment 2 for the Artificial Intelligence course (University of Tehran, Spring 1401 / 2022).
Instructors: Dr. Fadaee & Dr. Yaghoobzadeh.

This assignment has two independent parts: a Connect 4 game-playing agent (adversarial search) and
a genetic-algorithm-based substitution cipher decoder.

## Part 1 – Connect 4 AI (`AI-CA2-Game.ipynb`)

An agent that plays Connect 4 (6x7 board by default, also tested on 7x8 and 7x10) against a
provided opponent by completing the `get_your_input` function of the given game skeleton.

- **Minimax** search to choose the best column to play, with a custom heuristic that scores board
  windows of 4 cells (favoring center-column pieces and rewarding/penalizing near-complete lines).
- **Alpha-beta pruning** added on top of minimax to cut down the search tree and speed up move
  selection.
- Benchmarked at depths 1, 3, 5 (and 7 with pruning) across the three board sizes, recording
  execution time, nodes explored, and win rate (computed over 200 games per configuration).
- With depth 3 on the standard 6x7 board, the agent reaches a ~0.99 win rate.
- Written-up analysis of heuristic design, admissibility/consistency trade-offs, the effect of
  search depth on performance, and the impact of child-node ordering when pruning.

## Part 2 – Genetic Substitution-Cipher Decoder (`CA2-Genetic.ipynb`)

A `Decoder` class that recovers the key of a Vigenère-style substitution cipher (14-character key,
~10²⁰ possible keys) using a genetic algorithm instead of brute force. Constructed with a reference
text, the encoded text, and the key length; `decode()` returns the deciphered text.

- **Dictionary construction**: the reference text is cleaned (punctuation/stopword handling) into a
  word dictionary used to score candidate decodings.
- **Chromosome design**: each chromosome is a candidate 14-letter key, with each letter treated as
  a gene.
- **Initial population**: a configurable number of random chromosomes (`POPULATION_SIZE`).
- **Fitness function**: decodes the ciphertext with a candidate key and scores it by how many
  resulting words match the reference dictionary.
- **Crossover & mutation**: `crossover` combines two parent chromosomes into offspring; mutation
  randomly perturbs genes; an elitism rate carries top chromosomes forward unchanged.
- Includes benchmarks of running time vs. population size (50–400) and vs. elitism rate (0.2–0.6),
  plus written answers on population size trade-offs, why both crossover and mutation are needed,
  and ways to speed up convergence.

## Tech stack

- Python, Jupyter Notebook
- `math`, `random`, `time` (no external ML/search libraries — algorithms implemented from scratch)

## Files

- `AI-CA2-Game.ipynb` — Connect 4 minimax / alpha-beta agent, benchmarks, and analysis
- `CA2-Genetic.ipynb` — genetic algorithm cipher `Decoder`, benchmarks, and analysis

## License

MIT
