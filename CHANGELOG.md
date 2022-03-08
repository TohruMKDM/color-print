# Changelog

## 2.0.3
- Fix a small oversight in `formatter.lua`

## 2.0.2
- Made formatter a callable table. `formatter.bold('example') == formatter('bold', 'example')`

## 2.0.1
- Fix issue in package.lua (thanks lit)

## 2.0.0
- Rewrote the package
- Added `dump` to aid in printing large tables
- Added `colorize` which allows you to get colored strings without printing them
- Added `formatter` which allows you to format text such as underlining or boldening
- Improved the printing algorithm to allow printing colored text alongside uncolored text

## 1.0.2
- Fixed a small oversight in `color-print.lua`

## 1.0.1
- Initial release

## 1.0.0
- Published wrong package to lit.