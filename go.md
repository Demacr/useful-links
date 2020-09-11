# GO
## Libraries
### Crypto
[Hashing and checking hashes](https://medium.com/@jcox250/password-hash-salt-using-golang-b041dc94cb72)

## HighLoad
### Patterns
[1M rps golang](https://habr.com/ru/post/262045/)

## Templating
### Howtos
[Cheatsheet](https://curtisvermeeren.github.io/2017/09/14/Golang-Templates-Cheatsheet)

## Flags
### pflag
```go
func main() {
  var msg string
  verbose := pflag.BoolP("verbose", "v", false, "verbose output")
  pflag.StringVar(&msg, "msg", "hello world", "message to print")
  pflag.Parse()
  if *verbose {
    fmt.Println("you say:", msg)
  } else {
    fmt.Println(msg)
  }
  
  # --msg=one # one
  # --msg     # bye
  # [none]    # hello
  pflag.StringVar(&msg, "msg", "hello", "message to print")
  pflag.Lookup("msg").NoOptDefVal = "bye"
}
```
