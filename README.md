# [go.emoji](https://github.com/minhjh/go.emoji)

[![GoDoc](https://godoc.org/github.com/minhjh/go.emoji?status.svg)](https://godoc.org/github.com/minhjh/go.emoji)
[![](https://goreportcard.com/badge/github.com/minhjh/go.emoji)](https://goreportcard.com/report/github.com/minhjh/go.emoji)

This Package `emoji` is designed to recognize and parse every indivisual Unicode Emoji characters from a string.

## Example

```go
func main() {
	printf := fmt.Printf

	s := "👩‍👩‍👦🇨🇳"
	i := 0

	final := emoji.ReplaceAllEmojiFunc(s, func(emoji string) string {
		i++
		printf("%02d - %s - len %d\n", i, emoji, len(emoji))
		return fmt.Sprintf("%d-", i)
	})

	printf("final: <%s>\n", final)
}

// Output:
// 01 - 👩‍👩‍👦 - len 18
// 02 - 🇨🇳 - len 8
// final: <1-2->
```
