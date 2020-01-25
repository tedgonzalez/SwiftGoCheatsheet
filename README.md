# SwiftGoCheatsheet

## Print
```go
fmt.Println()
```

```swift
print()
```
## Constants

```go
const s string = "constant"
```

```swift
let string = "constant"
```

## For
```go
for {}
for i <= 3 {
    continue // next iteration
}

for j := 7; j <= 9; j++ {
    break // end loop
}
```
## If/Else
```go
// any variables declared are available in all branches
if num := 9; num < 0 {
    fmt.Println(num, "is negative")
} else if num < 10 {
    fmt.Println(num, "has 1 digit")
} else {
    fmt.Println(num, "has multiple digits")
}
```

## Switch
```go
whatAmI := func(i interface{}) {
    switch t := i.(type) {
    case bool:
        fmt.Println("I'm a bool")
    case int:
        fmt.Println("I'm an int")
    default:
        fmt.Printf("Don't know type %T\n", t)
    }
}
```

## Data types
### Arrays
```go
var a [5]int // [0 0 0 0 0]
```
```swift
var a = []
```

```go
fmt.Println("len:" len(a)) // len: 5
```
```swift
print("len: \(a.count)") // len: 5
```

```go
b := [5]int{1, 2, 3} // [1, 2, 3]
```

```swift
let b = [1, 2, 3] // [1, 2, 3]
```

```go
var twoD [2][3]int
for i := 0; i < 2; i++ {
    for j := 0; j < 3; j++ {
        twoD[i][j] = i + j
    }
}
fmt.Println("2d: ", twoD)
```
```swift
var twoD: [[Int]] = []
for i in 0..<2 {
    var array: [Int] = []
    for j in 0..<3 {
        array.append(i+j)
    }
    twoD.append(array)
}
```

### Slices
```go
s := make([]string, 3) // [   ]
s[0] = "a"
s[0:2] // [a  ] 
```

### Maps
```go
n := map[string]int{"foo": 1, "bar": 2}
m := make(map[string]int)
m["k1"] = 7
m["k2"] = 13
fmt.Println("map:", m) // map[k1:7 k2:13]
delete(m, "k2")
```

```swift
let n = ["foo": 1, "bar": 2]
var m: [String: Int] = [:]
m["k1"] = 7
m["k2"] = 13
print("map:", m) // [ "k1":7, "k2":13 ]
m.removeValue(forKey: "k2")
```

```go
value, isPresent := m["k1"]
//value: 7, isPresent: true

value, isPresent := m["k2"]
//value: 0, isPresent: false
```
```swift
let isPresent = m["k2"] != nil
```

```go

```
## Range