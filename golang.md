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

```
package main

import (
	"fmt"
)

func main() {
	p := getPointer()
	fmt.Println(p, *p) // output - 0xc00010a000 234
	
	a := new(int)
	*a = 123
	fmt.Println(a, *a) // 0xc00010a008 123
}

func getPointer() (*int){
	a := 234
	return &a
}

// output
0xc00010a000 234
0xc00010a008 123

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

### iota

```
package main

import (
	"fmt"
)

const (
	first  = iota + 6 // iota starts with 0
	second = iota     // iota automatically increments by 1
	third             // automatically adjusted - output is 2
)

const (
	fourth = iota //resets back to 0
)

func main() {

	fmt.Println(first, second, third, fourth)

}


//output
6 1 2 0
```

### References
- [go.dev](https://go.dev)
- [go cheatsheet 1](https://github.com/a8m/golang-cheat-sheet)
- [go cheatsheet 2](https://devhints.io/go)
- [go by example](https://gobyexample.com/)
- [go playground](https://go.dev/blog/playground)
