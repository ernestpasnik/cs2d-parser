# CS2D Parser

**Parse and export CS2D stats in multiple formats: HTML, JSON, CSV, Markdown, or XML.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE) [![Release](https://github.com/ernestpasnik/cs2d-parser/actions/workflows/rust.yml/badge.svg?branch=main)](https://github.com/ernestpasnik/cs2d-parser/actions/workflows/rust.yml)

---

## 📊 Overview

This tool parses CS2D server statistics and exports them in your preferred format. It supports:
- **HTML** (interactive tables)
- **JSON** (structured data)
- **CSV** (spreadsheet-friendly)
- **Markdown** (documentation-friendly)
- **XML** (legacy systems)

Use `-h` or `--help` to see all available options.

---

## 🧪 Demo Outputs

See example outputs in the [`/example-output`](example-output) directory:
- [HTML Example](example-output/demo.html)
- [Markdown Example](example-output/demo.md)
- [CSV Example](example-output/demo.csv)
- [XML Example](example-output/demo.xml)
- [JSON Example](example-output/demo.json)

---

## ⚙️ Usage

### Basic Syntax

```bash
cs2d-parser [OPTIONS] <folder> <output>
```

### Arguments

| Argument   | Description                                      |
|------------|--------------------------------------------------|
| `<folder>` | Path to the folder containing `userstats.dat`    |
| `<output>` | Output file (must end with `.html`, `.json`, etc.)|

### Options

| Option               | Description                                                                                     | Default       |
|----------------------|-------------------------------------------------------------------------------------------------|---------------|
| `-s, --sort <sort>`   | Sort leaderboard: `0`=score+kills-deaths, `1`=assists+kills-deaths, `2`=score+assists+deaths      | `1`           |
| `-l, --limit <limit>` | Limit the number of players in the output                                                      | `100`         |
| `-t, --title <title>` | Title for HTML/Markdown reports                                                                  | `"CS2D Server"`|
| `-p, --pretty-print` | Pretty-print JSON output for readability                                                        | Disabled      |
| `-w, --watch`        | Monitor `userstats.dat` for changes and regenerate output automatically                          | Disabled      |
| `-h, --help`         | Print help                                                                                      |               |
| `-V, --version`      | Print version                                                                                   |               |

---

## 💡 Examples

### Generate a JSON Report (Windows)
```bash
cs2d-parser.exe "C:\Program Files (x86)\Steam\steamapps\common\CS2D\sys\stats" "report.json"
```

### Generate an HTML Report with Custom Title (Linux)
```bash
./cs2d-parser "/home/cs2d/sys/stats" "/var/www/html/dm.html" --title "Deathmatch Server"
```

### Monitor for Changes and Auto-Regenerate (macOS)
```bash
./cs2d-parser ~/Library/Application\ Support/CS2D/stats ~/Desktop/report.html --watch
```

---

## 📦 Installation

### Prebuilt Binaries
Download the latest release for your platform from the [Releases](https://github.com/ernestpasnik/cs2d-parser/releases) page.

### From Source
1. Install [Rust](https://www.rust-lang.org/tools/install).
2. Clone this repository:
   ```bash
   git clone https://github.com/ernestpasnik/cs2d-parser.git
   ```
3. Build and install:
   ```bash
   cd cs2d-parser
   cargo build --release
   ```

---

## 📄 License

This project is open-source and licensed under the **[MIT License](LICENSE)**.

---

## 🤝 Contributing

Contributions are welcome! Open an issue or submit a pull request.