<!-- [![Build Status](https://travis-ci.org/gojp/japanese.svg?branch=master)](https://travis-ci.org/gojp/japanese)  -->
![Github CI/CD](https://github.com/daffychuy/japanese/actions/workflows/go.yml/badge.svg) [![Go Report Card](https://goreportcard.com/badge/github.com/daffychuy/japanese)](https://goreportcard.com/report/github.com/daffychuy/japanese) [![GoDoc](https://godoc.org/github.com/daffychuy/japanese?status.svg)](https://pkg.go.dev/github.com/daffychuy/japanese)
## Note: This is a fork of https://github.com/gojp/japanese, including fixes
To use this package
```
go get github.com/daffychuy/japanese
```

# Japanese

A Go (golang) package for generating the different possible word forms and conjugations in Japanese. 

This is still in the experimental stage. However, later extensions might also include basic grammar parsing, analysis and translation. 

## Where this is aiming

A `GetRoot` function that takes a string and returns one or more root forms, along with the rule used to transform it to root form. For example:

```
>>> roots := japanese.Analyze("食べない")
>>> root := roots[0]
>>> fmt.Println(root.Root, root.DictionaryForm, root.Rule)
食べ 食べる negative
```

## Examples
For the most comprehensive examples, see the `words_test.go` file. 

For the impatient, here's an example of usage right now (subject to change in the future):

    func main() {
        taberu := Verb{Verb{Word{"食べる", "たべる"}}
        kau := Verb{Verb{Word{"買う", "かう"}}
        matsu := Verb{Word{"待つ", "まつ"}}

        fmt.Println(taberu.Negative()) // prints 食べない
        fmt.Println(kau.Negative())    // prints 買わない
        fmt.Println(matsu.Negative())  // prints 待たない
    }
