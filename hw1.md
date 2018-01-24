1-1.
- store `v` - initializaton value
- array of size `n`: `A[n]`

array:
O(1) : read, write, insert @ ends, delete @ ends
O(N) : insert @ mid, delete @ mid

linked list:
O(1) : insert, delete
O(N) : seek to position

a:
- store bitstream `b` initialized to all off (zero)
        - bitwise OR `b` to on with `2^i` for position `i`
- read from `A[i]`
        - if bit `b[i]` is off
                - set `b[i]` on
                - initialize `A[i] = v`
        - read `A[i]`
- write to `A[i]`
        - set `b[i]` on
        - write `A[i]`

b:
- store int `last`:  holds the largest `i` requested, must be `&le;
O(n) words`
- on first read/write of `A[i<sub>0</sub>]`:
        - set `last = i<sub>0</sub>`
        - allocate a linked list of `i<sub>0</sub>` nodes
                - for every element `e<sub>x</sub> &lt; i<sub>0</sub>`:
                        - create `e<sub>x</sub>` as a normal linked
                        list element, including links to other
                        elements
                        - set `A[e<sub>x</sub>]` to the address of
                        `e<sub>x</sub>`
                        - initialize the value of `e<sub>x</sub>` to `v`
                - for element `e<sub>i<sub>0</sub></sub>`:
                        - if read, set `A[e<sub>i<sub>0</sub></sub> =
                        e<sub>i<sub>0</sub></sub> = v` and return `v`
                        - if write, set `A[e<sub>i<sub>0</sub></sub> =
                        e<sub>i<sub>0</sub></sub>` to the value to
                        write
- every read/write thereafter of `i<sub>x</sub> &le n`:
        - if `i<sub>x</sub> < last`
                - read/write `A[i<sub>x</sub>]`
        - otherwise:
                - create new array `A[i<sub>x</sub>]`
                - copy elements up to `A[last]` into `A[i<sub>x</sub>]`
                - starting at `A[last]` of the new array, append to
                linked list as described above
                - set `last = i<sub>x</sub>`

1-2.

A[n]:


|  op#  |  0  |  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9 | 10 | 11 | 12 | 13 | 14 | 15 | 16  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A           | (0) | (1) | (1,0) | (1,1) | (1,0,0) | (1,0,1) | (1,1,0) | (1,1,1) | (1,0,0,0)  | (1,0,0,1) | (1,0,1,0) | (1,0,1,1) | (1,1,0,0) | (1,1,0,1) | (1,1,1,0) | (1,1,1,1) | (1,0,0,0,0) |
| num toggled| 0 | 1 |  2  |  1  |   3   |   1   |   2   |   1   | 4 |    1    |    2    |    1    |    3    |    1    |    2    |    1 | 5 |
| cumulative | 0 | 1 |  3  |  4  |   7   |   8   |  10   |  11   | 15 |   16    |   18    |   19    |   22    |   23    |   25    |   26 | 31 |
| new toggled| 2 | 2 |  2  |  2  |   2   |   2   |   2   |   2   | 2 |    2    |    2    |    2    |    2    |    2    |    2    |    2 | 2 |
| new cumulative | 0 | 2 |  4  |  6  |   8   |   10   |  12   |  14   | 16 |   18    |   20    |   22    |   24    |   26    |   28    |   30 | 32 |

| op# | 0   | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |  --- |
| A   | (0) | | | | | | --- | --- | --- | --- | --- | --- | --- | --- | --- |--- | ---|
