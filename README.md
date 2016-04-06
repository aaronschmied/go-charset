# go-charset
*Automatically exported from [code.google.com/p/go-charset](https://code.google.com/p/go-charset)*

Converts a string from UTF-8 to ISO-8859-1.

```go
import (
	"bytes"
	"fmt"

	"github.com/aaronschmied/go-charset/charset"
	_ "github.com/aaronschmied/go-charset/data"
)
```
```go
func toISO88591(utf8 string) (string, error) {
	buf := new(bytes.Buffer)

	w, err := charset.NewWriter("latin1", buf)
	if err != nil {
		return "", err
	}
	fmt.Fprintf(w, utf8)
	w.Close()
	return buf.String(), nil
}
```

