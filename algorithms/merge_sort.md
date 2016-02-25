# Merge Sort

*From: [Wikipedia](https://en.wikipedia.org/wiki/Merge_sort)*

> An efficient, general-purpose, comparison-based sorting algorithm. Most implementations produce a stable sort. Mergesort is a divide and conquer algorithm.

| x                           | y                                        |
|-----------------------------|------------------------------------------|
| Class                       | Sorting algorithm                        |
| Data structure              | Array                                    |
| Worst case performance      | O(n log n)                               |
| Best case performance       | O(n log n) typical, O(n) natural variant |
| Average case performance    | O(n log n)                               |
| Worst case space complexity | О(n) total, O(n) auxiliary               |

![Merge Sort Gif](https://upload.wikimedia.org/wikipedia/commons/c/c5/Merge_sort_animation2.gif)

## Example

An example of merge sort. First divide the list into the smallest unit, then compare each element with the adjacent list to sort and merge the two adjacent lists. Finally all the elements are sorted and merged.

![Merge Sort Gif](https://upload.wikimedia.org/wikipedia/commons/c/cc/Merge-sort-example-300px.gif)

## Example

```ruby
def mergesort(array)
    if array.count <= 1
        # Array of length 1 or less is always sorted
        return array
    end

    # Apply "Divide & Conquer" strategy

    # 1. Divide
    mid = array.count / 2
    part_a = mergesort array.slice(0, mid)
    part_b = mergesort array.slice(mid, array.count - mid)

    # 2. Conquer
    array = []
    offset_a = 0
    offset_b = 0
    while offset_a < part_a.count && offset_b < part_b.count
        a = part_a[offset_a]
        b = part_b[offset_b]

        # Take the smallest of the two, and push it on our array
        if a <= b
            array << a
            offset_a += 1
        else
            array << b
            offset_b += 1
        end
    end

    # There is at least one element left in either part_a or part_b (not both)
    while offset_a < part_a.count
        array << part_a[offset_a]
        offset_a += 1
    end

    while offset_b < part_b.count
        array << part_b[offset_b]
        offset_b += 1
    end

    return array
end
```
