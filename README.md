# Swift Sorting Algorithm
### Insertion Sort
```swift
//insertion sort - rank items by comparing each key in the list.
func insertionSort() {
    var x, y, key : Int
    for (x = 0; x < numberList.count; x++) {
    
        //obtain a key to be evaluated
        key = numberList[x]
        
        //iterate backwards through the sorted portion
        for (y = x; y > -1; y--) {
            if (key < numberList[y]) {
            
            //remove item from original position
            numberList.removeAtIndex(y + 1)
            
            //insert the number at the key position
            numberList.insert(key, atIndex: y)
            }
        } //end for
    } //end for
} //end function
```

### Optimized Insertion Sort
```swift
func insertionSort(_ array: [Int]) -> [Int] {
    var a = array			 // 1
    for x in 1..<a.count {		 // 2
        var y = x
        while y > 0 && a[y] < a[y - 1] { // 3
            a.swapAt(y - 1, y)
            y -= 1
        }
    }
    return a
}
```

### Bubble sort
```swift
var array = [5,3,4,6,8,2,9,1,7,10,11]
var sortedArray = NSMutableArray(array: array)
var sortedAboveIndex = array.count
var swaps = 0
var somethingSwapped = false
		
repeat {
    somethingSwapped = false
    for i in 1..<array.count {
        if  (sortedArray[i - 1] as! Int) > (sortedArray[i] as! Int) {
        sortedArray.exchangeObject(at: i, withObjectAt: i-1)
        somethingSwapped = true
        swaps += 1
        }
    }
} while (somethingSwapped)
```

### Optimized Bubble sort 
```swift
var array = [5,3,4,6,8,2,9,1,7,10,11]
var sortedArray = NSMutableArray(array: array)
var sortedAboveIndex = array.count
var swaps = 0

repeat {
    var lastSwapIndex = 0
  
    for i in 1..<sortedAboveIndex {
        if  (sortedArray[i - 1] as! Int) > (sortedArray[i] as! Int) {
            sortedArray.exchangeObject(at: i, withObjectAt: i-1)
            lastSwapIndex = i
            swaps += 1
        }
    }
    sortedAboveIndex = lastSwapIndex
} while (sortedAboveIndex != 0)
```
