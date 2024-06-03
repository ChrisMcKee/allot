# allot 
[![MIT License](https://img.shields.io/github/license/chrismckee/allot.svg?maxAge=3600)](https://github.com/chrismckee/allot/blob/master/LICENSE.md) [![GoDoc](https://godoc.org/github.com/chrismckee/allot?status.svg)](https://godoc.org/github.com/chrismckee/allot) 
[![Go Report Card](https://goreportcard.com/badge/github.com/chrismckee/allot)](https://goreportcard.com/report/github.com/chrismckee/allot)


**allot** is a small `Golang` library to match and parse commands with pre-defined strings. For example use **allot** to define a list of commands your CLI application or Slackbot supports and check if incoming requests are matching your commands.

The **allot** library supports placeholders and regular expressions for parameter matching and parsing.

## Usage

```go
cmd := allot.NewCommand("revert <commits:integer> commits on <project:string> at (stage|prod)")
match, err := cmd.Match("revert 12 commits on example at prod")

if (err != nil)
  commits, _ = match.Integer("commits")
  project, _ = match.String("project")
  env, _ = match.Match(2)

  fmt.Printf("Revert \"%d\" on \"%s\" at \"%s\"", commits, project, env)
} else {
  fmt.Println("Request did not match command.")
}
```

## Examples

See the [hanu Slackbot](https://github.com/chrismckee/hanu) framework for an use-case for **allot**:

## Credits
 * [Go coverage script from Mathias Lafeldt](https://mlafeldt.github.io/blog/test-coverage-in-go/)
