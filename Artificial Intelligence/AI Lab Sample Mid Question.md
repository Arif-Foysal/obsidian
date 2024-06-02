#artificial-intellegence #uiu #questionBank 

>Topic: [[Python]], A star, Hill climbing

You are creating a program for a mouse. The mouse can move in eight directions: 

`Up, Down, Right, Left, Up-Right, Up-Left, Bottom-Left, Bottom-Right`

The mouse is in a certain position on a mousepad. The mousepad coordinate starts from (0,0) in the top left corner and ends at (100,100) in the bottom right corner. A move in the mouse is defined as a unit change in a certain direction. Now, create a class for the Mouse with appropriate methods and variables.

```Python
class Mouse:  
    def __init__(self, x, y):  
        self.x = x  
        self.y = y  
     
    def move(direction):  
        if direction == 'UP':  
            self.y -= 1  
        elif direction == 'UP-RIGHT':  
            self.y -= 1  
            self.x += 1  
        elif direction == 'UP-LEFT':  
            self.y -= 1  
            self.x -= 1  
        elif direction == 'BOTTOM':  
            self.y += 1  
        elif direction == 'BOTTOM-LEFT':  
            self.x -= 1  
            self.y += 1  
        elif direction == 'BOTTOM-RIGHT':  
            self.y += 1  
            self.x += 1  
        else:  
            return
```
  

Difference between A Star and [[Dijkstra's Algorithm]]

Why is [[Hill Climbing Search]] an incomplete algorithm? How does the simulated annealing technique work to make it better?

  

Which algorithm would you choose to design Google Maps: A star, Dijkstra, or BFS? Give a proper explanation.