# Arrays in Swift

### Declaration

To declare in empty array in Swift you cannot say e.g. "var arr = []", but you have to declare the value type that you will use inside.
```swift
var arr = [String]()
var array = [Any]()

class Car {
var licencePlate = "XCNSF"
var brand = "Volkswagen"
}

var carArray = [Car]()
```


### Methods

```swift
var arr = [Any]()

// To add values to your array
arr.append("test")  // from now on the array only takes values of type String
arr += ["One"] // also a possible way to add single values
arr += ["Two","Three"] // you can even add whole arrays 


// To remove elements from your array
arr.remove(at: 0) // remove an element at index 0 (-> the first element in the array)


// To get the length of the array
arr.count // returns an Int
```
