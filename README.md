# log.sh
A logging library for POSIX sh and other shells (Bash, Zsh, Dash).

![Preview](/assets/preview.png)<br  />
<sub>Taken inside [Termux](https://termux.dev) app with font JetBrains Mono and [Catppuccin](https://github.com/Catppuccin) Mocha theme and background.</sub>

## Installation
Drop [log.sh](/log.sh) into the same directory as your script and source it.
```sh
source ./log.sh # can be /path/to/log.sh if you place it somewhere
```

## Usage
After sourcing, a `log` function is available in your script. `log` function takes first argument as log mode and the rest of the arguments are the messages, if first argument are not an uppercase mode name or not a mode, the log mode will be set to `TRACE` and make the first argument of the function as one of the messages.

  - Available log modes:
    - `TRACE`
    - `DEBUG`
    - `INFO`
    - `WARN`
    - `ERROR`
    - `FATAL`

## Additional options
log.sh provide way to set additional options, by setting variable to a certain value.

### `LOG_NOCOLOR`
Default: `""`

Whether colors are disabled or not. If set to anything besides null string or empty string, disable ansi-coloring when printed to stdout. This is useful if your terminal doesn't support ansi-coloring.

### `LOG_FILE`
Default: `""`

The path of the file where the log should be stored. By default, it is set to null string (no file are written), but if set, log.sh will write logs into the file.

### `LOG_LEVEL`
Default: `"TRACE"`

The minimum level to log. Any log level that is lower than `LOG_LEVEL` is ignored and no text is printed or written. By default the value is set to `"TRACE"`, the lowest log level, as no log messages are ignored.

The level of each log modes, starting from the lowest: `"TRACE"` `"DEBUG"` `"INFO"` `"WARN"` `"ERROR"` `"FATAL"`

## License

log.sh are licensed under MIT license, see [LICENSE](/license) file for more details.
