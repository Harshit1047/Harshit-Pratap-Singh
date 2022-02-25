
# Problem1 & Problem2





## Problem1


Merge two sorted array by removing their duplicates.


## Approach
Take two input array give name as arrayA and arrayB (It may be sorted or unsorted). In first stept merge the given two input array into single unsorted array then remove duplicates from merged array by using HashSet.

## Output

<img width="662" alt="image" src="https://user-images.githubusercontent.com/86252946/155664452-235c272f-8d9c-405c-b0c4-d8ba4e8c62a5.png">


## Problem2


To check if keyword are found in the list or not. If found return the smallest unique prefix that identifies the keyword.

## Approach
Create a trie of all words where frequency will be the number of times node is visited during the insertion of elements.Then, check if keyword is there or not. If there then find the character which is nearest to the root with frequency as 1. We can traverse Trie starting from root.  If frequency is 1 then print all characters from root to this node and don’t traverse down this node.

## Time Complexity

O(N)


## Output

<img width="662" alt="image" src="https://user-images.githubusercontent.com/86252946/155668015-d9479507-82ba-4b13-9ede-9e7db49c010c.png">





