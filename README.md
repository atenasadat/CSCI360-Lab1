#CSCI36: Lab 1

## Introduction to Artificial Intelligence

-----

### Setting up the environment

First, you need to initialize your repository using the following command.
Follow the command line instruction below to initialize your repository
locally. 

```
git clone YOUR-GITHUB-REPO-HERE

conda env create -n Lab1 python=3.8

pip install -r requirements.txt

```
Replace `YOUR-GITHUB-REPO-HERE` with the URL that GitHub
generates for your repository.

### Implementation:

The only file you need to implement is ['Lab1.py']('Lab1.py). Grading is based on your code in this file.

You are provided with [`lab1_utils.py`](`lab1_utils.py`) which contains
the `TextbookStack` class. The constructor for this class expects two
lists that represent the order. The first list, `initial_order`, is a
list of length `n` that expects each integer `[0, n-1]` to be present
once, The second list `, initial_orientation`, should be a list of length
`n` of exclusively `0`s and `1`s. Will represent the Textbook facing up.

Here is an example:
```
>>> from lab1_utils import TextbookStack

# Construct a stack of books in reverse order
>>> stack = TextbookStack(initial_order=[2, 1, 0], initial_orientations=[0, 0, 0])
>>> print(stack)
TextbookStack:
 	 order: [2 1 0]
	 orientations:[0 0 0]
```


You can access the current order and orientation of the books by
accessing the attributes `TextbookStack.order` and
`TextbookStack.orientations` respectively.

```
>>> stack.order
array([2, 1, 0])
>>> stack.orientations
array([0, 0, 0])
```

Calling the command `flip_stack(position)` will flip the books up to the
`position`. For example, if you want to flip the top book of your `stack.`
you should call `stack.flip_stack(1)`.

```
>>> stack.flip_stack(2)
>>> stack.order
array([1, 2, 0])
>>> stack.orientations
array([1, 1, 0])
```

You can make a copy of a stack by invoking the `.copy()`. This will
create a new object with the same current order and orientations as the
stack from which you invoked the method. You can use `==` to compare the
equivalence of two stacks.

```
>>> new_stack = stack.copy()
>>> new_stack == stack
True
>>> new_stack.flip_stack(3)
>>> new_stack == stack
False
```


Finally, you can check if the stack is ordered by invoking the
`check_ordered`

```
>>> stack.check_ordered()
False
>>> stack.flip_stack(2)
>>> stack.flip_stack(3)
>>> stack.check_ordered()
True
```
All of your algorithms should be contained in the designated blocks
inside of `breadth_first_search` and `depth_first_search` and should
return the sequence of flips that your search algorithms find.

## Testing Your Code:

We have given you example tests that you can run from the terminal by
invoking:

```
python test.py
```

from inside your the directory. These are starting points that reflect
the same type of tests that we will run in order to evaluate and grade
the correctness of your algorithm.


-----

### How we will grade:

Grading for this lab consists of two main parts:
Algorithmes soundness(60 pts) :
Full implementation of the DFS algorithm with comprehensible comments (30 pts)
Full implementation of the BFS algorithm with comprehensible comments (30 pts)

Passing multiple testcases(40 pts):
We have  4 test cases (2 for each algorithm). Your code must pass all the test cases to get the full grade of this section. Each test case has 10 pts.

