# shtimer

Lightweight terminal timer with an ASCII countdown visualizer and repeating alarm.

## Features

- Run durations like `1m`, `30s`, `2h`, and `1h 2m 30s`
- Animated stacked countdown for hours, minutes, and seconds
- Repeating alarm until `Ctrl+C`
- No build step and no external dependencies beyond common Linux audio tools

## Usage

```bash
./shtimer 1m
./shtimer 2h
./shtimer 1h 2m 30s
```

Accepted units:

- `s` for seconds
- `m` for minutes
- `h` for hours

## Install

To use it as `shtimer` instead of `./shtimer`:

```bash
mkdir -p ~/.local/bin
cp shtimer ~/.local/bin/shtimer
chmod +x ~/.local/bin/shtimer
```

Make sure `~/.local/bin` is in your `PATH`, then run:

```bash
shtimer 1m
shtimer 2h
```

## Alarm Behavior

When the countdown reaches zero, the script tries these playback methods in order:

1. `canberra-gtk-play`
2. `speaker-test`
3. Terminal bell fallback

## Controls

- `P` pauses or resumes the countdown
- `Ctrl+C` stops the alarm after the timer reaches zero

## Notes

- The visualizer is designed for a terminal session with ANSI cursor control.
- If your filesystem is mounted with `noexec`, run it with `bash shtimer 1m` or move it into an executable location such as `~/.local/bin`.
