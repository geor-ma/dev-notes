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

// output
Arthur
addressof operator & 0xc0000a6210
0xc0000a6210 Arthur
0xc0000a6210 Pat

```

### constants

```
package main

import (
	"fmt"
)

func main() {

	const c = 3 // type of c is not specified, implicitly types, compiler interprets as appropriate during run time
	fmt.Println(c)

	fmt.Println(c + 3)
	fmt.Println(c + 1.2)

	const c1 int = 5 // int type
	fmt.Println(c1 + 3)
	fmt.Println(float32(c1) + 1.2) //type convertion

}

//output
3
6
4.2
8
6.2

```

### References
- https://github.com/a8m/golang-cheat-sheet
- https://devhints.io/go
- https://gobyexample.com/
- https://go.dev/blog/playground
