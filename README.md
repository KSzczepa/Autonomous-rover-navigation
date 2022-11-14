<h1>Autonomous-rover-navigation</h1>
<p>Main goal of the project was to design a decision-making mechanism to enable autonomous an autonomous agent to take advantage of the opportunities offered by crowdsourcing in a navigation task. The project is exactly focused on designing a navigation algorithm for an autonomous rover that needs to navigate an uncertain environment.</p>
<h2>Setup of the project</h2>
<p>The setup is as follows: an agent wants to navigate a 3-square wide grid, from bottom left to top right. The fields are numbered from 0 to 9. The middle square is an obstacle, represented by a very negative reward. The goal is to compare sources, coded as probability mass functions (pmfs), in order to select the best one at each step. For convenience, instead of using the whole state space as support for the pmfs, we reduce it to five possible actions: stay in place, move left, upwards, right downwards. The same principle was applied to reward lists.</p>
<p>The source code also contains the DKL function, or Kullback-Leibler divergence, which is a measure of how one probability distribution is different from a second, reference probability distribution.</p>
<h2>Implementation of the greedy version of the algorithm (WP 1,2)</h2>
<p>The problem is the uncertain environment in which the robot moves, containing obstacles. The agent must be able to collect information from third parties and re-use such information to achieve the destination. The agent must be also able to avoid obstacles in an uncertain surface.
A greedy algorithm was used to program the robot, which, in order to determine the solution at each step, makes the most promising partial solution choice at that time. It used the sources collected, compared with the target behaviour and analysed taking into account the cost function.</p>
<h2>Ilustrating the results (WP3)</h2>
<p>The Greedy algorithm is not a predictive algorithm, but in the case of a small grid it proved sufficient for the agent to reach the target, regardless of the location of the obstacle. To illustrate results performed a numerical and graphical simulation, library "Pygame" was used to represent the graphical results.</p>
<img src=''/>
<img src=''/>
<h2>Implementation of the routines to scale-up the problem to larger grids (WP4)</h2>
<p>Extended verison of the project allows the user to generate an arbitrarily large grid and random obstacle’s positions or declare obstacles on specific fields. A size of grid is defined by user. In this version of the algorithm, the return_target(x) function has been modified to be universal, regardless of the grid size, but considers the grid as square. It uses the new target_direction() function, which contains all the calculations. Also modified the return_reward() function to be independent of the number of obstacles.</p>
<h2>implementation of a receding horizon version of the algorithm (WP5)</h2>
<p>In this part of the project the receding horizon version of the algorithm is implemented, which is a predictive algorithm. A property of predictive control is its repetitive mode of operation. It is possible to determine a sequence of future controls, but only the first step of this sequence is used, so that in the next step the whole calculation is repeated. In the main loop, we calculate the weights for control through a receding horizon and choose a policy. The idea is that we restric the state space to the relative states available to us and use crowdsourcing on this new state space.</p>
<h2>Tools</h2>
<ul>
<li>Python language</li>
<li>Jupyter Notebook</li>
<li>Pygame library</li>
</ul>