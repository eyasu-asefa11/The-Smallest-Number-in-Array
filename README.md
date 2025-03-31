# The-second or the third largest elemennt
#include <iostream>
#include <vector>
#include <algorithm>

int findKthLargestSorting(std::vector<int>& arr, int k) {
    std::sort(arr.begin(), arr.end(), std::greater<int>()); //Sort in descending order
    if (k <= arr.size()) {
        return arr[k - 1];
    } else {
        return -1; //k is larger than the array size, indicate error
    }
}

int main() {
    std::vector<int> data = {3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5};
    int secondLargest = findKthLargestSorting(data, 2);
    int thirdLargest = findKthLargestSorting(data,3);
    std::cout << "Second largest: " << secondLargest << std::endl;
    std::cout << "Third largest: " << thirdLargest << std::endl;
    return 0;
} 

▎Algorithm to Find the k-th Largest Element Using Sorting

1. Input:
  • An array of integers arr.

   • An integer k, which indicates the position of the largest element to find (e.g., 1 for the largest, 2 for the second largest, etc.).

2. Sort the Array:

   • Use a sorting algorithm to sort the array arr in descending order. This can be achieved using a standard library sort function with a comparator that sorts elements from largest to smallest.

3. Check Validity of k:

   • If k is less than or equal to the size of the array, proceed to the next step.

   • If k is greater than the size of the array, return an error value (e.g., -1) indicating that k is out of bounds.

4. Return the k-th Largest Element:

   • Access the element at index k-1 of the sorted array (since array indexing starts from 0) and return this value as the k-th largest element.

5. Output:

   • Print or return the found k-th largest element.

▎Pseudocode

Here is a pseudocode representation of the above algorithm:

FUNCTION findKthLargestSorting(arr: List of Integers, k: Integer) -> Integer
    SORT arr IN DESCENDING ORDER
    IF k <= LENGTH(arr) THEN
        RETURN arr[k - 1]
    ELSE
        RETURN -1 // Error: k is larger than array size
END FUNCTION

FUNCTION main()
    data = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
    secondLargest = findKthLargestSorting(data, 2)
    thirdLargest = findKthLargestSorting(data, 3)
    PRINT "Second largest: " + secondLargest
    PRINT "Third largest: " + thirdLargest
END FUNCTION


▎Explanation of Key Components

• Sorting: The sorting step ensures that we can easily access the k-th largest element by simply indexing into the sorted array.

• Error Handling: The check for k ensures that we do not attempt to access an index that does not exist, preventing potential runtime errors.

• Output: The results are printed to the console for user feedback.

This algorithm is straightforward and leverages sorting to simplify finding the k-th largest element, but keep in mind that sorting has a time complexity of O(n log n), which may not be optimal for very large datasets if you only need to find a single k-th largest element. Alternative methods like using a min-heap or quickselect can achieve this in average O(n) time complexity.
