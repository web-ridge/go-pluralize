# Forked to fix version issues

https://github.com/web-ridge/go-pluralize/issues/9

# go-pluralize

[![Build Status](https://travis-ci.org/gertd/go-pluralize.svg?branch=master)](https://travis-ci.org/gertd/go-pluralize)
[![Go Report Card](https://goreportcard.com/badge/github.com/web-ridge/go-pluralize)](https://goreportcard.com/report/github.com/web-ridge/go-pluralize)
[![GoDoc](https://godoc.org/github.com/web-ridge/go-pluralize?status.svg)](https://godoc.org/github.com/web-ridge/go-pluralize)

Pluralize and singularize any word

# Acknowledgements

> The go-pluralize module is the Golang adaptation of the great work from [Blake Embrey](https://www.npmjs.com/~blakeembrey) and other contributors who created and maintain the NPM JavaScript [pluralize](https://www.npmjs.com/package/pluralize) package.
> The originating Javascript implementation can be found on https://github.com/blakeembrey/pluralize
>
> Without their great work this module would have taken a lot more effort, **thank you all**!

# Version mapping

The latest go-pluralize version is compatible with [pluralize](https://www.npmjs.com/package/pluralize) version 8.0.0 commit [#e507706](https://github.com/blakeembrey/pluralize/commit/e507706be779612c06ebfd6043163e063e791d79)

| go-pluralize version                                                                         | NPM Pluralize Package version                                                                                             |
| -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| 0.1.2 - Apr 1, 2020 [v0.1.2](https://github.com/web-ridge/go-pluralize/releases/tag/v0.1.2)  | 8.0.0 - Mar 14, 2020 [#e507706](https://github.com/blakeembrey/pluralize/commit/e507706be779612c06ebfd6043163e063e791d79) |
| 0.1.1 - Sep 15, 2019 [v0.1.1](https://github.com/web-ridge/go-pluralize/releases/tag/v0.1.1) | 8.0.0 - Aug 27, 2019 [#abb3991](https://github.com/blakeembrey/pluralize/commit/abb399111aedd1d62dd418d7e0217d85f5bf22c9) |
| 0.1.0 - Jun 12, 2019 [v0.1.0](https://github.com/web-ridge/go-pluralize/releases/tag/v0.1.0) | 8.0.0 - May 24, 2019 [#0265e4d](https://github.com/blakeembrey/pluralize/commit/0265e4d131ecad8e11c420fa4be98b75dc92c33d) |

# Installation

To install the go module:

    go get -u github.com/web-ridge/go-pluralize

To lock down a specific the version:

    go get -u github.com/web-ridge/go-pluralize@0.1.2

Download the sources and binaries from the latest [release](https://github.com/web-ridge/go-pluralize/releases/latest)

# Usage

## Code

    import pluralize "github.com/web-ridge/go-pluralize"

    word := "Empire"

    pluralize := pluralize.NewClient()

    fmt.Printf("IsPlural(%s)   => %t\n", input, pluralize.IsPlural(word))
    fmt.Printf("IsSingular(%s) => %t\n", input, pluralize.IsSingular(word))
    fmt.Printf("Plural(%s)     => %s\n", input, pluralize.Plural(word))
    fmt.Printf("Singular(%s)   => %s\n", input, pluralize.Singular(word))

## Result

    IsPlural(Empire)   => false
    IsSingular(Empire) => true
    Plural(Empire)     => Empires
    Singular(Empire)   => Empire

# Pluralize Command Line

## Installation

    go get -x github.com/web-ridge/go-pluralize/cmd/pluralize

## Usage

### Help

    pluralize -help
    Usage of ./bin/pluralize:
      -cmd string
            command [All|IsPlural|IsSingular|Plural|Singular] (default "All")
      -version
            display version info
      -word string
            input value

### Word with All Commands

    pluralize -word Empire

    IsPlural(Empire)   => false
    IsSingular(Empire) => true
    Plural(Empire)     => Empires
    Singular(Empire)   => Empire

### Is Word Plural?

    pluralize -word Cactus -cmd IsPlural

    IsPlural(Cactus)   => false

### Is Word Singular?

    pluralize -word Cacti -cmd IsSingular

    IsSingular(Cacti)  => false

### Word Make Plural

    pluralize -word Cactus -cmd Plural

    Plural(Cactus)     => Cacti

### Word Make Singular

    pluralize -word Cacti -cmd Singular

    Singular(Cacti)    => Cactus
