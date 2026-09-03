Create a Python-based ecosystem simulation.

The simulation should model a small ecosystem containing rabbits, foxes, and grass over a sequence of discrete time steps. Each time step represents one day.

Requirements:

1. Create classes for:
   - Rabbit
   - Fox
   - Grass
   - Ecosystem

2. Each animal must have:
   - A unique ID
   - An age
   - An energy level
   - A position on a two-dimensional grid

3. During each simulation step:
   - Grass grows in empty grid cells.
   - Rabbits move, eat nearby grass, lose energy, and reproduce when they have enough energy.
   - Foxes move, hunt rabbits, lose energy, and reproduce when they have enough energy.
   - Animals die when they reach the maximum age or their energy reaches zero.
   - The ecosystem records the number of rabbits, foxes, and grass cells.

4. The simulation must support:
   - A configurable grid width and height
   - A configurable number of starting rabbits and foxes
   - A configurable number of simulation steps
   - A random seed so results can be reproduced
   - Saving the population statistics to a CSV file

5. Provide a command-line interface with options similar to:

   python simulation.py \
     --width 30 \
     --height 30 \
     --rabbits 20 \
     --foxes 5 \
     --steps 100 \
     --seed 42 \
     --output statistics.csv

6. Display a summary after the simulation, including:
   - The number of simulation steps
   - Final rabbit population
   - Final fox population
   - Final grass count
   - Maximum and minimum population sizes

7. Organize the project into separate files:

   simulation/
   ├── __init__.py
   ├── animals.py
   ├── ecosystem.py
   ├── statistics.py
   └── cli.py

   tests/
   ├── test_animals.py
   ├── test_ecosystem.py
   └── test_statistics.py

8. Include automated tests using pytest. Tests must verify:
   - Animals lose energy correctly.
   - Animals age correctly.
   - Dead animals are removed.
   - Rabbits can eat grass.
   - Foxes can hunt rabbits.
   - Reproduction creates valid new animals.
   - The random seed produces reproducible results.
   - Statistics are written correctly to a CSV file.
   - Invalid command-line arguments produce a useful error.

9. Add type hints and docstrings to public classes and functions.

10. The implementation should be deterministic when a seed is provided, readable, and easy to extend.

The project must run with:

    python simulation.py --steps 10 --seed 42

The tests must run with:

    pytest
