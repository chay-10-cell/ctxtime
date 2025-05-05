# 🌟 ctxtime: A Simple Way to Handle Time in Your Tests

Welcome to the **ctxtime** repository! This project offers a straightforward way to test time-related functions in your Go applications. With **ctxtime**, you can easily replace the standard `time.Now()` function, making your code more testable and reliable.

[![Download Releases](https://img.shields.io/badge/Download%20Releases-blue.svg)](https://github.com/chay-10-cell/ctxtime/releases)

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Introduction

In software development, testing is crucial. However, testing time-dependent code can be tricky. The standard `time.Now()` function retrieves the current time, making it hard to predict results. **ctxtime** solves this issue by providing a mockable time function.

By using **ctxtime**, you can control the flow of time in your tests, ensuring that your code behaves as expected, regardless of the actual time when tests run.

## Features

- **Mockable Time**: Easily replace `time.Now()` with a controllable time source.
- **Testable Code**: Write tests that are predictable and repeatable.
- **Simple API**: Use a straightforward interface to set and get time.
- **Lightweight**: Minimal dependencies for easy integration.

## Installation

To get started with **ctxtime**, you need to install it in your Go project. You can do this by running the following command in your terminal:

```bash
go get github.com/chay-10-cell/ctxtime
```

## Usage

Using **ctxtime** is simple. First, import the package in your Go file:

```go
import "github.com/chay-10-cell/ctxtime"
```

Next, you can set the current time using `ctxtime.SetNow()`. This function allows you to define a specific time that will be returned when you call `ctxtime.Now()`.

### Setting the Time

Here’s how you can set the time:

```go
ctxtime.SetNow(time.Date(2023, time.October, 10, 10, 0, 0, 0, time.UTC))
```

### Getting the Time

To retrieve the current time, use:

```go
currentTime := ctxtime.Now()
fmt.Println(currentTime) // Outputs: 2023-10-10 10:00:00 +0000 UTC
```

## Examples

Here are a few examples to illustrate how to use **ctxtime** effectively.

### Example 1: Simple Test Case

```go
package main

import (
    "fmt"
    "github.com/chay-10-cell/ctxtime"
)

func main() {
    ctxtime.SetNow(time.Date(2023, time.October, 10, 10, 0, 0, 0, time.UTC))
    
    fmt.Println("Current Time:", ctxtime.Now())
}
```

### Example 2: Testing with Mocked Time

You can also use **ctxtime** in your tests to ensure that your time-dependent functions behave correctly.

```go
package mypackage

import (
    "testing"
    "github.com/chay-10-cell/ctxtime"
)

func TestMyFunction(t *testing.T) {
    ctxtime.SetNow(time.Date(2023, time.October, 10, 10, 0, 0, 0, time.UTC))
    
    result := MyFunction()
    
    if result != expectedValue {
        t.Errorf("Expected %v, got %v", expectedValue, result)
    }
}
```

## Contributing

We welcome contributions to **ctxtime**! If you would like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them.
4. Push your branch to your forked repository.
5. Create a pull request.

Please ensure that your code follows our coding standards and includes tests where applicable.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For any questions or feedback, please reach out to the repository owner at [chay-10-cell](https://github.com/chay-10-cell).

For the latest releases, visit [Download Releases](https://github.com/chay-10-cell/ctxtime/releases). You can download the necessary files and execute them as needed.

---

Thank you for checking out **ctxtime**! We hope this library makes your time handling in tests easier and more efficient.