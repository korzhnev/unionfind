# unionfind
Golang implementation of optimized Union-Find data structure 

## Install
`go get github.com/korzhnev/unionfind`

## Usage
```go
// Omit error handing for short

// Initialize n items
uf, _ := unionfind.New(10)

// Add connection between p and q
uf.Union(4, 3)
uf.Union(3, 8)
uf.Union(6, 5)
uf.Union(9, 4)
uf.Union(2, 1)

notConnected, _ := uf.Connected(0,7)
fmt.Println(notConnected) // prints false

connected, _ := uf.Connected(8,9) 
fmt.Println(connected) // prints true
```

## API

#### `uf, err = unionfind.New(n)`
Create a new UnionFind structure with size n.

#### `err = uf.Union(p, q)`
Add connection between p and q.

#### `root, err = uf.Root(i)`
Find root of i.

#### `connected, err = uf.Connected(p, q)`
Check whether p and q are in the same component

## Theory
**Union–find data structure** is a data structure that tracks a set of elements partitioned into a number of 
disjoint (non-overlapping) subsets. It provides near-constant-time operations to add new sets, to merge existing sets, 
and to determine whether elements are in the same set. 

See for more details:
- https://en.wikipedia.org/wiki/Disjoint-set_data_structure
- https://www.coursera.org/learn/algorithms-part1