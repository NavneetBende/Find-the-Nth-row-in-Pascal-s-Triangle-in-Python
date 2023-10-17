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
