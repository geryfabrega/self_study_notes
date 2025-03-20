```
# to do a topological sort you must flip your list and track in bound connections. 
A->B
B->C
C->D

See this above? translate this to look like this


B=[A]
C=[B]
D=[C]

Notice we now have an adjancey list? 

Also add in bound connections in a hashmap or array

A = 1
B = 1
C = 1
D = 0


Now DSF on anything that does not have an in bound connection

stack = [D]
Do.... DFS

now as we are traversing, when you look at the neighbors of D, decrement the inbound


for neigh in D:
	inBound[neigh] -= 1
	if inound[neigh] == 0:
		stack.append(neigh)

```
At this point you will be able to touch every item you physcially can try to touch.