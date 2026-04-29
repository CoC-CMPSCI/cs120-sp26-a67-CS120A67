# A67: Recursion — Tower of Hanoi

**Code your program here:** [https://classroom.github.com/a/W9ITXq6h](https://classroom.github.com/a/W9ITXq6h)

---

## 3. Elaborate on Errors and Troubleshooting

- Programming algorithms used
- Errors encountered and troubleshooting steps taken
- Error experiences and lessons learned (how you identified and fixed each error)
- Why is the number of calls always 2ⁿ - 1? Explain how each recursive call spawns two more calls, and how the base case stops the recursion.

---

## [Programming Assignment Guide]

**Read the Assignment Directions below, then complete the following `main.cpp` in your cloned Repository.**

**Assignment Directions:**

In this assignment, you will complete one function in `main.hpp`. **Do NOT edit `main.cpp`**.

Tower of Hanoi
Move **n** disks from peg **from** to peg **to** using peg **aux** as a helper.

**Rules:**

- Move only one disk at a time
- Never place a larger disk on a smaller disk

  ```cpp
static int count = 0;
count++;                          // count this call
if (n == 1) return count;         // base case
hanoi(n-1, from, aux, to);        // move top n-1 to aux
hanoi(n-1, aux, to, from);        // move n-1 from aux to to
return count;
```

    | n | Total calls | Formula |
|---|---|---|
| 1 | 1 | 2¹ - 1 |
| 2 | 3 | 2² - 1 |
| 3 | 7 | 2³ - 1 |
| 4 | 15 | 2⁴ - 1 |

    **Each test runs in a separate process** — the static count resets to 0 each time.

| n | Total calls | Formula |  |
|---|---|---|---|
| 1 | 1 | 2¹ - 1 |  |
| 2 | 3 | 2² - 1 |  |
| 3 | 7 | 2³ - 1 |  |
| 4 | 15 | 2⁴ - 1 | 2⁴ - 1 |
| 4 | 15 | 2⁴ - 1 | 2⁴ - 1 |

**To compile and run:**

```cpp
g++ main.cpp
./a.out
```

**To run tests:**

```cpp
make test
make test ARGS="[T1]"
```

**How to compile and run your program:**

- To compile your program in VS Code, open the new terminal (ctrl-`) and type: `g++ main.cpp -o main`
- To run your program: `./main`

**How to test your program:**

- To run all tests: `make test`
- To run a specific test (e.g., T1): `make test ARGS="[T1]"`

**[Expected Output]**

*Your output should contain the correct values. The exact wording or formatting may differ — tests check values only, not the entire output.*

Example run

```cpp
hanoi(3) moves = 7
hanoi(4) moves = 15
```

**How to pass the test:**

Test items: **compile, run, T1, T2, T3, T4**

| Test | Input | Expected Values (checked by test) | Points |
|---|---|---|---|
| T1 | hanoi(1,'A','C','B') | 1 | 15 |
| T2 | hanoi(2,'A','C','B') | 3 | 15 |
| T3 | hanoi(3,'A','C','B') | 7 | 15 |
| T4 | hanoi(4,'A','C','B') | 15 | 15 |
| T5 | hanoi(5,'A','C','B') | 31 | 15 |
| T6 | hanoi(6,'A','C','B') | 63 | 15 |

To test your program, type the command in your terminal: `make test`

**Make sure that your program passes the test and there is ✓ in your GitHub Classroom Repository.**

