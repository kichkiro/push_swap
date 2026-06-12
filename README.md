<img src="https://github.com/kichkiro/kichkiro/blob/main/assets/banner_push_swap.jpg?raw=true" width="100%"/>

# Push Swap

<i>
    "The Push swap project is a very simple and a highly straightforward algorithm project: data must be sorted.
    <br>You have at your disposal a set of integer values, 2 stacks, and a set of instructions
    to manipulate both stacks.
    <br>Your goal? Write a program in C called push_swap which calculates and displays
    on the standard output the smallest program, made of Push swap language instructions,
    that sorts the integers received as arguments.
    <br>Easy?
    <br>We’ll see.."
</i>

#### <i>[subject](_subject/en.subject.pdf) v.6</i>

<details>
<summary><i><b>Project Structure  📂</b></i></summary>
	
```js
├── README.md
├── LICENSE
├── Dockerfile
├── project
│   ├── Makefile
│   ├── include
│   │   └── push_swap.h
│   ├── lib
│   │   └── libft
│   └── src
│       ├── push_swap.c
│       ├── perform_actions.c
│       ├── algorithm_short.c
│       ├── algorithm_long.c
│       ├── find_best_path.c
│       ├── checker.c  
│       └── lst
│           ├── t_stack_add_back.c
│           ├── t_stack_check_dup.c
│           ├── t_stack_del_last.c
│           ├── t_stack_free.c
│           ├── t_stack_from_arr.c
│           ├── t_stack_head.c
│           ├── t_stack_index_data.c
│           ├── t_stack_is_sorted.c
│           ├── t_stack_last.c
│           ├── t_stack_max.c
│           ├── t_stack_min.c
│           ├── t_stack_new.c
│           ├── t_stack_n_is_inside.c
│           ├── t_stack_second_min.c
│           ├── t_stack_set_to_head.c
│           ├── t_stack_size.c
│           └── t_stack_to_arr.c
└── _subject
    ├── checker_linux
    ├── checker_Mac
    └── en.subject.pdf
```
</details>

## 📌 - Key Topics
### Sorting Algorithms
A comprehensive analysis of classical and advanced sorting algorithms, including but not limited to Quick Sort, Merge Sort, Bubble Sort, and Insertion Sort. The focus will be on the theoretical underpinnings of algorithm complexity, specifically Big O notation, average and worst-case performance scenarios, and stability. Emphasis will also be placed on the practical implications of choosing specific algorithms based on data characteristics, as well as the trade-offs between time complexity and space complexity.

### Stack Data Structure
In-depth exploration of stack operations such as push, pop, swap, rotate, and reverse rotate, crucial for manipulating the data during the sorting process. The discussion will include the LIFO (Last In, First Out) principle governing stacks, their implementation in C, and the memory management practices necessary to avoid leaks. Consideration will be given to how the stack structure can influence algorithm efficiency, particularly in terms of managing intermediate states and minimizing the number of operations required to achieve a sorted output. Techniques for optimizing stack utilization and ensuring compliance with project specifications will also be covered.

## 🛠️ - Usage

```sh
git clone --recurse-submodules https://github.com/kichkiro/push_swap.git
cd push_swap/
docker build -t push_swap:42 .
docker run -d --name push_swap push_swap:42
```
Now you can enter in the container and start sorting the numbers.

```sh
docker exec -it push_swap bash
./push_swap 1 3 5 4 2
```
The output contains the operations needed to sort the stack.

## 🔄 - Allowed operations

The goal is to sort in ascending order numbers into stack a. To do so, only the following operations are allowed:

- sa (swap a): Swap the first 2 elements at the top of stack a.
Do nothing if there is only one or no elements.
- sb (swap b): Swap the first 2 elements at the top of stack b.
Do nothing if there is only one or no elements.
- ss : sa and sb at the same time.
- pa (push a): Take the first element at the top of b and put it at the top of a.
Do nothing if b is empty.
- pb (push b): Take the first element at the top of a and put it at the top of b.
Do nothing if a is empty.
- ra (rotate a): Shift up all elements of stack a by 1.
The first element becomes the last one.
- rb (rotate b): Shift up all elements of stack b by 1.
The first element becomes the last one.
- rr : ra and rb at the same time.
- rra (reverse rotate a): Shift down all elements of stack a by 1.
The last element becomes the first one.
- rrb (reverse rotate b): Shift down all elements of stack b by 1.
The last element becomes the first one.
- rrr : rra and rrb at the same time.


## 📈 - Sorting Algorithms

### Algorithm for numbers >= 2 && <= 5

The algorithm works as follows:
- If the number of elements is greater than 3, the smallest excess 
    elements are transferred to stack 'b' in the least number of actions and
    sorted in descending order;
- When there are 3 or less elements in stack 'a', the goal of the 
    algorithm is to locate the largest element and move it with a single 
    action to the last node;
- If the element at the first node is greater than the second element they 
    are swapped;
- Finally (if there are elements in stack 'b') the two stacks are merged.

### Algorithm for numbers > 5

The algorithm is divided into three steps:
- In the first phase all the elements that are not part of the longest 
    incremental subsequence are transferred to stack 'b';
- As long as stack 'b' is not empty, each time the element that "costs" 
    less in terms of actions is identified and transferred;
- Finally, if the smallest element is not on the first node, the list is
	    rotated.

## 📉 - Benchmark

[push_swap_visualizer](https://github.com/o-reo/push_swap_visualizer)

<img src="https://github.com/kichkiro/kichkiro/blob/main/assets/push_swap_visualizer.gif?raw=true" alt="push_swap_visualizer" width="100%"/>

[push_swap_tester](https://github.com/LeoFu9487/push_swap_tester)

<img src="https://github.com/kichkiro/kichkiro/blob/main/assets/push_swap_tester.png?raw=true" alt="push_swap_tester" width="100%"/>

## ⚖️ - License

See [LICENSE](LICENSE)