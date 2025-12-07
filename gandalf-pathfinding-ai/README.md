# Gandalf Pathfinding AI: Search Algorithms for Fellowship Navigation

A comprehensive artificial intelligence project implementing multiple search algorithms to solve a complex pathfinding problem inspired by The Lord of the Rings. Gandalf must strategically guide Fellowship members through orc-controlled territories using optimal search strategies.

## Project Overview

This project demonstrates the practical application of AI search algorithms in solving a multi-agent pathfinding problem with constraints and obstacles. The implementation includes both uninformed and informed search techniques with detailed performance analysis.

### Problem Domain
- **Setting**: Middle-earth inspired grid-based pathfinding
- **Objective**: Guide Fellowship members to safety while avoiding orc detection
- **Constraints**: Limited movement in surveillance zones, single-member transport
- **Challenge**: Find optimal paths while minimizing time and computational resources

## Key Features

- **Multiple Search Algorithms**: BFS, IDS, A*, Weighted A*
- **Performance Optimization**: Efficient data structures and algorithm implementations
- **Comprehensive Analysis**: Detailed timing, memory usage, and optimality comparisons
- **Educational Value**: Clear explanations of search algorithm principles
- **Professional Documentation**: Complete project documentation in multiple languages

## Algorithms Implemented

### Uninformed Search
- **Breadth-First Search (BFS)**: Guarantees optimal solution, explores level-by-level
- **Iterative Deepening Search (IDS)**: Optimal solution with linear space complexity

### Informed Search  
- **A* Search**: Heuristic-guided optimal search with multiple heuristic functions
- **Weighted A* Search**: Fast approximate search with tunable optimality trade-offs

## Project Structure

```
gandalf-pathfinding-ai/
│
├── README.md                     # Main project documentation
├── src/                          # Source code directory
│   ├── AI_CA1_English.ipynb     # Main implementation (English)
│   ├── AI_CA1.ipynb             # Original implementation (Persian)
│   └── requirements.txt         # Python dependencies
├── docs/                        # Documentation
│   ├── problem-statement.pdf    # Original assignment (AI-CA1-Spring 1401.pdf)
│   ├── performance-analysis.md  # Detailed performance results
│   └── algorithm-explanation.md # Algorithm theory and implementation
├── test-cases/                  # Test data
│   ├── test_00.txt
│   ├── test_01.txt
│   ├── test_02.txt
│   └── test_03.txt
├── results/                     # Output and analysis
│   ├── performance-tables.md
│   └── execution-logs/
└── LICENSE                      # MIT License
```

## Quick Start

### Prerequisites
```bash
Python 3.7+
Jupyter Notebook
```

### Installation
```bash
git clone https://github.com/yourusername/gandalf-pathfinding-ai.git
cd gandalf-pathfinding-ai
pip install -r src/requirements.txt
```

### Running the Code
```bash
# Open Jupyter notebook
jupyter notebook src/AI_CA1_English.ipynb

# Or run specific test case
python src/main.py test-cases/test_01.txt
```

## Performance Highlights

| Algorithm | Optimality | Time Complexity | Space Complexity | Best Use Case |
|-----------|------------|-----------------|------------------|---------------|
| BFS | ✓ Optimal | O(b^d) | O(b^d) | Small search spaces |
| IDS | ✓ Optimal | O(b^d) | O(bd) | Memory-constrained systems |
| A* | ✓ Optimal | O(b^d) | O(b^d) | General-purpose optimal search |
| Weighted A* | Sub-optimal | O(b^d) | O(b^d) | Time-critical applications |

### Benchmark Results Summary
- **Test Cases**: 4 comprehensive scenarios with varying complexity
- **Performance Metrics**: Execution time, states explored, memory usage, solution quality
- **Optimal Solutions**: BFS, IDS, and A* all guarantee optimal paths
- **Speed Champion**: Weighted A* with 5-10x faster execution

## Technical Highlights

### State Representation
- Efficient 3-tuple state encoding
- Optimized state hashing for fast duplicate detection
- Memory-efficient Fellowship member tracking

### Heuristic Functions
- **h1**: Counting heuristic (most effective)
- **h2**: Manhattan distance heuristic  
- **h3**: Euclidean distance heuristic
- All heuristics proven admissible and consistent

### Optimizations Applied
- Advanced data structure usage (sets, deques, heaps)
- Efficient state transition algorithms
- Memory management optimizations
- Algorithm-specific performance tuning

## Educational Value

This project serves as an excellent educational resource for:
- **Computer Science Students**: Understanding search algorithm implementation
- **AI Researchers**: Practical applications of informed vs uninformed search
- **Algorithm Analysis**: Detailed performance comparison and optimization techniques
- **Problem-Solving**: Complex constraint satisfaction and pathfinding

## Research Applications

The algorithms and optimizations in this project are applicable to:
- **Robotics**: Path planning for autonomous vehicles
- **Game Development**: AI for strategic games and navigation
- **Logistics**: Route optimization and resource allocation  
- **Network Routing**: Optimal path selection in computer networks

## Contributing

We welcome contributions in the following areas:
- Additional search algorithms (Dijkstra, Bidirectional search)
- Enhanced heuristic functions
- Visualization tools and GUI interfaces
- Performance optimizations and parallel implementations
- Extended test cases and benchmark suites

### How to Contribute
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Academic Context

- **Course**: Artificial Intelligence (Spring 1401/2022)
- **Institution**: [University Name]
- **Instructors**: Dr. Fadaei and Dr. Yaghobzadeh  
- **Project Designers**: Arash Rasouli, Sajjad Alizadeh, Sina Negarandeh
- **Assignment**: Computer Assignment 1 (CA1)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for complete details.

## Citation

If you use this project in your research or educational work, please cite:

```bibtex
@software{gandalf_pathfinding_ai,
  title={Gandalf Pathfinding AI: Search Algorithms for Fellowship Navigation},
  author={[Your Name]},
  year={2024},
  url={https://github.com/yourusername/gandalf-pathfinding-ai},
  note={AI Search Algorithms Implementation and Analysis}
}
```

## Acknowledgments

- **Inspiration**: J.R.R. Tolkien's The Lord of the Rings
- **Academic Support**: AI course instructors and teaching assistants
- **Community**: Open source contributors and algorithm researchers
- **Tools**: Python ecosystem, Jupyter notebooks, and scientific computing libraries

---

**Star this repository if you find it useful for learning AI search algorithms!**

For questions, suggestions, or collaboration opportunities, please open an issue or contact the maintainers.

**Keywords**: Artificial Intelligence, Search Algorithms, Pathfinding, BFS, A-star, Heuristic Search, Algorithm Analysis, Computer Science, Educational Project