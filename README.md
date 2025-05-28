# Go CLI Example

A simple command-line interface application built with Go and the [Cobra](https://github.com/spf13/cobra) library.

## Description

This project demonstrates how to create a command-line application in Go using the Cobra framework. The application includes a root command and a "hello" subcommand that can be extended to build more complex CLI tools.

## Features

- Simple command structure using Cobra
- Extensible design for adding new commands
- Command flags support
- Clean separation of command logic

## Installation

### Prerequisites

- Go 1.24.3 or higher

### Building from source

1. Clone the repository:
```bash
git clone https://github.com/yourusername/go-cli-example.git
cd go-cli-example
```

2. Build the application:
```bash
go build -o cli
```

3. Run the application:
```bash
./cli
```

## Usage

### Basic Commands

- Root command:
```bash
./cli
```

- Hello command:
```bash
./cli hello
```

### Flags

The root command includes a toggle flag:
```bash
./cli --toggle
./cli -t
```

## Project Structure

- `main.go`: Entry point of the application
- `cmd/`: Package containing all CLI commands
  - `root.go`: Root command definition
  - `hello.go`: Hello subcommand definition

## Extending the CLI

To add new commands to the CLI:

1. Create a new file in the `cmd` directory
2. Define your command using the Cobra framework
3. Add your command to the root command in the `init()` function

Example:
```go
var newCmd = &cobra.Command{
    Use:   "new",
    Short: "A new command",
    Run: func(cmd *cobra.Command, args []string) {
        fmt.Println("new command called")
    },
}

func init() {
    rootCmd.AddCommand(newCmd)
}
```

## License

This project is licensed under the terms of the license file included in the repository.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.