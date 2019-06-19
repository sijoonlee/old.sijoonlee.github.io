---
layout: page
permalink: /algorithm-study/Create-Maze
---

<html>
<body>
<div style="display:flex; justify-content:center;">
	<canvas id="myCanvas" width="540" height="540"
		style="border:1px solid #d3d3d3; margin: 20px;">
	Your browser does not support the canvas element.
	</canvas>
</div>
<div style="display:flex; justify-content:center;">
	<button id = "drawMaze">Generate Maze!</button>
</div>
<script src="/assets/js/maze.js"></script>
</body>
</html>



## Maze-Creation Algorithm

This is a variant of Depth First Algorithm(DFS).

In contrast with DFS that usually implements stack structure(LIFO),

this algorithm utilizes Heap structure.

### Explanation
- The grid is the rectangle with vertices in it.  
- The algorithm navigates the grid by stepping from one vertex to the nearest vertex, which is one step next to the vertex  
- When the algorithm steps through, it assigns "key" value to the four nearest vertices(north, south, east, west) based upon the key value of the vertex it is stepping on, and it puts the four vertices into Heap data structure  
- By using the key values, max-heap extracts the vertex with maximum key value, which is the next vertex to be stepped on.
- The value can be updated as the navigation propargates
- But the values are not updated for the vertices that were already visited 
- The visited vertices are added into another array structure to keep track of the path that the algorithm steps through

### Example
- 2X4 Grid
- Navigation starts at (0,1)
- Key values are shown in Red
![maze](/algorithm-study/Create-Maze/maze.png)




