# Binary Search Algorithm 

Two approches - recurisive and iterative.

# Iterative approach
def iterative(list, first, last, x):

    while first <= last:

        mid = (first + last) // 2

        if list[mid] == x:
            return mid

        elif list[mid] > x:
            last = mid - 1

        elif list[mid] < x:
            first = mid + 1

        else:
            return -1

# Recursive approach
def recursive(list, first, last, x):

    while first <= last:

        mid = (first + last) // 2

        if list[mid] == x:
            return mid

        elif list[mid] > x:
            return recursive(list, first, mid-1, x)

        elif list[mid] < x:
            return recursive(list, mid+1, last, x)

        else:
            return -1


arr = [2,3,4,5,6,7,8,9,10]
first = 0
last = len(arr) - 1
target = int(input("Enter a number you're looking for: "))

result = recursive(arr, first, last, target)
if result != -1:
    print(f"Number found at position {result}")
else:
    print("Not found")




