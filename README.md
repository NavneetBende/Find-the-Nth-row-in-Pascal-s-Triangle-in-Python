# Find-the-Nth-row-in-Pascal-s-Triangle-in-Python

Nth row of Pascal’s Triangle in Python
Here, on this page, we will discuss the program to find the Nth row of Pascal’s Triangle in Python Programming language. We are given a non-negative integer and we need to print the Nth row. We are assuming a zero-based starting of the rows

Nth row of Pascal’s Triangle
Method 1 (Using recursion):
Create a recursive function say getRow(int index).
Declare a vector say cur_row
Now, as the 1-st element of every row is 1 so, push 1 in cur_row vector.
Check if index == 0, then return cur_row.
Create a vector to hold the previous row, say prev and set prev = getRow(index-1)
Run a loop from [1, prev.size())
Take variable say curr = prev[i-1] + prev[i]
and push it to cur_row
As the last element of every row is 1 so again push 1 to cur_row vector.
And return cur_row

N row of Pascal’s Triangle
Python Code
Run

def getRow(rowIndex):

    cur_row = []

    cur_row.append(1)

    if rowIndex == 0:
        return cur_row

    prev = getRow(rowIndex - 1)

    for i in range(1, len(prev)):
        curr = prev[i - 1] + prev[i]
        cur_row.append(curr)

    cur_row.append(1)

    return cur_row


n = 2
arr = getRow(n)

for i in range(len(arr)):

    if i == (len(arr) - 1):
        print(arr[i])
    else:
        print(arr[i], end=" ")
Output
1 2 1
Method 2 :
In this method, we will discuss the efficient way to find the Nth row of the triangle.

Nth row = nC 0 nC1 nC2 … nCn
So, by using the above concept to find the nth row.
nCr = (nCr-1 * (n – r + 1))/r
Take a variable say prev=1 (as, nC0=1)and print prev.
Now, Run a loop from [1, N], take a variable say curr, and set curr = (prev * (N – i + 1)) / i;
And, Print Curr.
Python Code
Run
def getrow(N):
    prev = 1
    print(prev, end=" ")

    for i in range(1, N + 1):
        curr = (prev * (N - i + 1)) // i
        print(curr, end=" ")
        prev = curr


N = 2
getrow(N)
Output
1 2 1
