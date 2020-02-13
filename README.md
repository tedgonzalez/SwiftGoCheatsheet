# SwiftGoCheatsheet

## Print
#### Go
```go
fmt.Println()
```

#### Swift
```swift
print()
```
## Constants

#### Go
```go
const s string = "constant"
```

#### Swift
```swift
let string = "constant"
```

## For Loop
#### Go
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
#### Go
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
#### Go
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
#### Go
```go
var a [5]int // [0 0 0 0 0]
```
#### Swift
```swift
var a = []
```

#### Go
```go
fmt.Println("len:" len(a)) // len: 5
```
#### Swift
```swift
print("len: \(a.count)") // len: 5
```

#### Go
```go
b := [5]int{1, 2, 3} // [1, 2, 3]
```

#### Swift
```swift
let b = [1, 2, 3] // [1, 2, 3]
```

#### Go
```go
var twoD [2][3]int
for i := 0; i < 2; i++ {
    for j := 0; j < 3; j++ {
        twoD[i][j] = i + j
    }
}
fmt.Println("2d: ", twoD)
```
#### Swift
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
#### Go
```go
s := make([]string, 3) // [   ]
s[0] = "a"
s[0:2] // [a  ] 
```
#### Swift
```swift
s = []
```
### Maps
#### Go
```go
n := map[string]int{"foo": 1, "bar": 2}
m := make(map[string]int)
m["k1"] = 7
m["k2"] = 13
fmt.Println("map:", m) // map[k1:7 k2:13]
delete(m, "k2")
```

#### Swift
```swift
let n = ["foo": 1, "bar": 2]
var m: [String: Int] = [:]
m["k1"] = 7
m["k2"] = 13
print("map:", m) // [ "k1":7, "k2":13 ]
m.removeValue(forKey: "k2")
```

#### Go
```go
value, isPresent := m["k1"]
//value: 7, isPresent: true

value, isPresent := m["k2"]
//value: 0, isPresent: false
```
#### Swift
```swift
let isPresent = m["k2"] != nil
```

### Range
#### Go
```go
nums := []int{2, 3, 4}
sum := 0
for index, value := range nums {
    sum += value
}
// sum: 9
```
#### Swift
```swift
for i in 2...4 {
}
```
#### Go
```go
someMap := map[string]string{"a": "apple", "b": "banana"}
for key := range someMap {}
for key, value := range someMap {}
for i, unicodeDecimalValue := range "go" {}
```

### Pointers
#### Go
```go
func zeroptr(iptr *int) {
    *iptr = 0
}
i := 1
zeroptr(&i)
fmt.Println("zeroptr:", i)  // 0
fmt.Println("pointer:", &i) // 0x42131100
```

### Structs
#### Go
```go
type person struct {
    name string
    age  int
}
p := person{name: name}
```

## Functions
#### Go
```go
func plus(a int, b int) int { }
func plus(a, b int) int { }
```
#### Swift
```swift
func plus(a: Int, b: Int) -> Int { }
```

### Multiple return values
#### Go
```go
func vals() (int, int) {
    return 3, 7
}
```
#### Swift
```swift
func vals() -> (Int, Int) {
    return (3, 7)
}
```

### Variadic functions
#### Go
```go
func sum(nums ...int) {
    fmt.Print(nums, " ")
}
sum(1, 2) // [1 2]
sum(1, 2, 3) // [1 2 3]
 ```

### Closures

#### Go
```go
func intSeq() func() int {
    i := 0
    return func() int {
        i++
        return i
    }
}
```
#### Swift
```swift
func intSeq() -> (() -> Int) {
    var i = 0
    return func() -> Int {
        i++
        return i
    }
}
```

### Methods
#### Go
```go
type rect struct {
    width, height int
}
func (r *rect) area() int {
    return r.width * r.height
}
func (r rect) perim() int {
    return 2*r.width + 2*r.height
}
r := rect{width: 10, height: 5}
r.area()
r.perim()
```

## Interfaces
#### Go
```go
package main

import (
    "fmt"
    "math"
)

type geometry interface {
    area() float64
    perim() float64
}

type rect struct {
    width, height float64
}
type circle struct {
    radius float64
}

func (r rect) area() float64 {
    return r.width * r.height
}
func (r rect) perim() float64 {
    return 2*r.width + 2*r.height
}

func (c circle) area() float64 {
    return math.Pi * c.radius * c.radius
}
func (c circle) perim() float64 {
    return 2 * math.Pi * c.radius
}

func measure(g geometry) {
    fmt.Println(g)
    fmt.Println(g.area())
    fmt.Println(g.perim())
}

func main() {
    r := rect{width: 3, height: 4}
    c := circle{radius: 5}

    measure(r)
    measure(c)
}
```

## Errors

