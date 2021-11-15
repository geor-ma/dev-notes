# Golang notes

### Pointers

```
package main

import (
	"fmt"
)

func main() {
	firstName := "Arthur"
	fmt.Println(firstName)
	fmt.Println("addressof operator &", &firstName)

	ptr := &firstName // ptr has the address
	fmt.Println(ptr, *ptr) // dereferencing with *

	firstName = "Pat"
	fmt.Println(ptr, *ptr)
}

```
### References
- https://github.com/a8m/golang-cheat-sheet
- https://devhints.io/go
- https://gobyexample.com/
- https://go.dev/blog/playground
