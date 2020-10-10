#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) O(n)
There is one 'while' loop containing a single operation. The number of times the operation will run is determined by the size of the input 'n'.

b) O(n log n)
The outer 'for' loop runs the same operation over and over, and inside the 'while' loop, 'j' is multiplied by 2 each time it is run, decreasing the number of times it has to run logarithmically.

c)O(n)
The loop is recursive but only calls itself one time before reaching its base case. If you replace bunnies with 'n', this makes it O(n) 

## Exercise II
This would be a binary search problem. Assume a building (array) with a given number of floors 'n' (we will use an odd number simply because it is easier to find the middle floor, so assuming 7 floors, we will begin with the 4th floor), and the floor we are looking for is 'f'.

If an egg is dropped from the fourth floor and breaks, we know we can ignore all higher floors (because if the egg breaks when dropped from the fourth floor, it will certainly break from any higher floor that is higher).

If the egg then breaks on the third floor, we go down to the second floor and try again, then to the first, if necessary.

If, on the other hand, the egg does not break when dropped from the fourth floor, we know already that it will not break if dropped from any lower floors and we must go up, first to the fifth floor. If this magic egg manages to not break when dropped from the fifth floor, then we go up to the sixth, and eventually up to the seventh, if it does not break when dropped from the sixth.

A binary search has a runtime complexity of O(log n) because the number of operations it performs increases as a logarithmic function of the input size (meaning it grows very slowly, so as the input gets larger, the number of operations does not increase by very much).

PSEUDOCODE
def drop_eggs(number_of_floors, floor_f):
    bottom_floor = 0
    top_floor = len(number_of_floors) -1
    mid = (top + bottom)//2

    if floor_f == number_of_floors[mid]:
        return mid
    
    elif floor_f < number_of_floors[mid]:
        return drop_eggs(number_of_floors[:mid])
    else:
        return drop_eggs(number_of_floors[mid:])


