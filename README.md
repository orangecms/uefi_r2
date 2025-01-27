[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](http://www.gnu.org/licenses/gpl-3.0)

# uefi_r2

Tools for analyzing UEFI firmware using radare2

# Dependencies

## radare2

```
radare2 4.5.0-git 24764 @ linux-x86-64 git.4.4.0-225-g1cb18df8b
commit: 1cb18df8b4dfd2ec98ca6697b5efb9381e1d2f40
```

# Installation

```bash
python setup.py install
```

# Example

### With script

```
./uefi_r2_analyzer.py analyze-image {image_path} -o out.json
./uefi_r2_analyzer.py scan --rule {rule_path} {image_path}
```

### From code

```python
from uefi_r2.uefi_analyzer import UefiAnalyzer

...
summary = UefiAnalyzer.r2_get_summary(image_path, debug=True)
```

```python
from uefi_r2.uefi_analyzer import UefiAnalyzer
from uefi_r2.uefi_scanner import UefiRule, UefiScanner

...
uefi_analyzer = UefiAnalyzer(image_path)
uefi_rule = UefiRule(rule)
scanner = UefiScanner(uefi_analyzer, uefi_rule)
result = scanner.result
```