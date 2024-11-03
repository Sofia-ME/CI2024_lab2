This notebook presents two approaches to solve the Traveling Salesperson Problem (TSP) using geodesic distance measurements and optimization techniques. The two methods used are:

- Nearest Neighbor (faster but approximate solution)
- Vector Bearing and Mutation (more accurate but computationally intensive solution)

Solution Details
1. Nearest Neighbor Solution
The Nearest Neighbor approach provides a fast solution by visiting the closest unvisited city at each step. The method calculates the geodesic distance from the current city to all unvisited cities and identifies the closest one. The algorithm iterates until all cities are visited, then returns to the starting city to close the route. This solution is beneficial for quick estimates but may not yield the optimal. The code was inspired by the lectures and course materials presented in the Computational Intelligence course (01URROV)

2. Vector Bearing and Mutation Solution
The Vector Bearing and Mutation approach uses a more complex and accurate algorithm by calculating vectors (bearing and distance) from the start city to all others. Cities are sorted by bearing to create a roughly circular route and the algorithm finds the two cities with the largest bearing difference to establish an initial path. It then refines the solution using mutation to achieve a more optimized route. Each solution's execution time will depend on the dataset size and parameters for max_iterations and sample_size. 


Usage Guide
To apply the TSP solutions, you can import a dataset (CSV file) of cities for a specific country. Then, select a random starting city and run both solutions.



Country |	Nearest Neighbor Distance (km) |	 Time    |	Vector Bearing and Mutation Distance (km)	| Time 
Vanuatu	|           1040.39	             |   0.0 s   |	                 907.09                 	| 0.0 s
Italy	  |           5104.46	             |   0.5 s   |                  4584.74	                  | 41.5 s
USA   	|           48914.94	           |   27.3 s	 |                  52119.31	                | 73 min 16 s
Russia	|           44115.63	           |   6.9 s	 |                  40762.09	                | 17 min 45 s
China 	|           63550.88	           |  2min 17s |	                216137.81                 | 54 min 9 s                 

Note: For a fair comparison, both solutions start at the same randomly selected city for each country.
Note 2: For the USA and China cases, the first solution performed better than the second, indicating that there is still room for improvement in the parameters and/or the algorithm

