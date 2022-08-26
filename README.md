# Unbeatable-tic_tac_-toe
This is a game that you cant beat. It doesn't use any machine learning just simple basic python codes....If you have anything to contribute please share....
"""
Find the pivot or the smallest number in the rotated list.
The two sides on the rotated list will be sorted.
use the function that runs a normal binary search to find the target position on the most suitable side from the pivot

"""
def pivot_finder(rot, target):
    len_list = len(rot)
    low,high = 0, len_list-1
    while low<=high:
        mid = (low+high)//2
        if rot[mid-1] >rot[mid]:
            if target > rot[len_list-1]:
                return target_finder(rot, target, 0, mid-1)
            else:
                return target_finder(rot, target, mid+1, len_list-1 )
        elif rot[mid]<rot[len_list-1]:
            high = mid-1
        elif rot[mid]>rot[len_list-1]:
            low = mid+1
    return -1
def target_finder(rot, target, low, high):
    print(rot)
    while low<=high:
        mid = (low+high)//2
        if rot[mid] == target:
            return mid
        elif rot[mid]>target:
            high = mid-1
        elif rot[mid]< target:
            low = mid+1
    return -2


print(pivot_finder([1,3], 1))
