# stop

Stock position / portfolio tracker for status bars

![stop](images/stop.png)

## Dependencies

- [yfinance](https://github.com/ranaroussi/yfinance)

## Installation

### Arch-based distributions

- [stop](https://aur.archlinux.org/packages/stop) is available in AUR.

## Configuration

Supported configuration options:

- custom ticker display value (legend)
- percent change display
- delay between checks
- automatic ticker rotation
- colors:
    - background
    - foreground
    - ticker highlight
    - gain accent
    - loss accent
- plaintext mode
- one-shot mode
- decimal rounding
- historical difference:
    - day: `[ .. ]`
    - week: `{ .. }`
    - month: `( .. )`
    - year: `< .. >`
    - 5 years: `| .. |`
    - share price: `> .. <`
- special `TOTAL` ticker for portfolio tracking
    - snapshot mode
- thousand separator
- custom padding
- value concealment
- custom URL opener
- configuration file (`~/.config/stop.conf`):

    ```
    [tickers]
    <ticker>: [[<legend>:]<price-per-share>:<shares>]
    ```

See `stop -h` for more info.

### Example polybar config

```ini
[module/stop]
type = custom/script
exec = stop NVDA MSFT
tail = true

label = %output%

click-left = kill -USR1 %pid%
click-right = kill -USR2 %pid%
```
