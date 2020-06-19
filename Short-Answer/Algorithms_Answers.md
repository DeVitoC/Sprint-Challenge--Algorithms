#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) O(n) While the "while" loop tests for n*n*n, the count variable increases by n*n, which means there will be n total loops. 
one time through n number of iterations is O(n) since it will increase linearly, or proportionally to n.


b)O(nlogn) This is nested loops. The outer "for" loop loops through n, while the inner "while" loop iterates through only a 
relatively small portion of n, increasing much slower than the increase in n. This means it is n * logn for O(nlogn)


c) O(n) this goes iteratively through each bunny which is a straightforward O(n)

## Exercise II

This would be an ideal situation for a binary search. I would start by checking if an egg is broken when dropped from the n/2 floor.
If this egg breaks, I would then set this floor as my max range and try dropping an egg off of the floor midway from the ground to this 
new max range, or n/4.
If instead the egg did not break, I would set this floor as the min range and try dropping an egg off the floor midway from this floor 
to the top floor or 3n/4.
I would continue in this pattern until I find the highest floor that an egg does not break when dropped from. One way I would know I have
reached this limit is when the min is equal (or greater) than the max. 

A method to accomplish this would look something like:

method testFloor(n)
    minlevel = 1 (assuming in this case there is no 0th floor)
    maxlevel = n
    midlevel = minlevel + maxlevel / 2
    while minlevel is < maxlevel
        if (droppedEggBreaks) 
            maxlevel = midlevel
        else
            minlevel = midlevel
    return midlevel
    
This solution would result in an O(logn) runtime because as n increases would increase at a much slower pace. In order to add an iteration
to the loop, n would need to double.