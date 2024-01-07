# Pythagorean-Triplet
Given an array arr of n integers. Find if there is a triplet (a, b, c) from the array (where a, b, and c are on different indexes) that satisfies a2 + b2 = c2.      If such a triplet exists, Print "Yes" else "No".

def is_pythagorean_triplet(arr):
    n = len(arr)
    
   
    arr = [x**2 for x in arr]
    
    
    arr.sort()
    
    for i in range(n - 1, 1, -1):
        left = 0
        right = i - 1
        
        while left < right:
            if arr[left] + arr[right] == arr[i]:
                return "Yes"
            elif arr[left] + arr[right] < arr[i]:
                left += 1
            else:
                right -= 1
    
    return "No"


n = int(input())
arr = list(map(int, input().split()))


result = is_pythagorean_triplet(arr)
print(result)
