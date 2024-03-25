# stop

Stock position tracker for status bars

![stop](images/stop.png)

### Example polybar config

```ini
[module/stop]
type = custom/script
exec = stop NVDA MSFT
tail = true

label = %output:-88%

click-left = kill -USR1 %pid%
```
