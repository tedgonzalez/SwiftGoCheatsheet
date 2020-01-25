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

## Arrays
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