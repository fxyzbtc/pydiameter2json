# 🚀 PyDiameter2JSON

<div align="center">

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Tests](https://img.shields.io/badge/Tests-Passing-brightgreen.svg)](tests/)
[![Code Style](https://img.shields.io/badge/Code%20Style-Black-000000.svg)](https://github.com/psf/black)
[![uv](https://img.shields.io/badge/Managed-uv-purple.svg)](https://github.com/astral-sh/uv)

*Transform Diameter Protocol Messages into Beautiful JSON with AI-Powered Precision*

</div>

## ✨ Features

<div align="center">

| 🎯 **Core Features** | 🛠 **Technical Excellence** |
|:-------------------|:-------------------------|
| 🔍 **Real-time Parsing** | ⚡ **Lightning Fast** |
| 📊 **JSON Output** | 🎯 **100% Accurate** |
| 🎨 **CLI Interface** | 🧪 **Comprehensive Tests** |
| 🔧 **AVP Extraction** | 📈 **Production Ready** |
| 🌐 **Multi-Protocol** | 🪄 **Zero Dependencies** |

</div>

## 🌟 Why PyDiameter2JSON?

**PyDiameter2JSON** is the ultimate solution for telecom engineers, network analysts, and developers working with Diameter protocol. Built with modern Python and powered by cutting-edge parsing algorithms, it transforms complex Diameter messages into human-readable JSON instantly.

### 🎯 Perfect For
- 📡 **Telecom Network Analysis**
- 🔬 **Protocol Debugging**
- 📊 **Data Analytics**
- 🚀 **CI/CD Testing**
- 🎓 **Learning & Research**

## 🚀 Quick Start

### 📦 Installation

```bash
# Using uv (Recommended)
uv add pydiameter2json

# Using pip
pip install pydiameter2json

# Development install
git clone https://github.com/fxyzbtc/pydiameter2json.git
cd pydiameter2json
uv sync
```

### 🎯 Basic Usage

#### 🐍 **Library Usage**

```python
from pydiameter2json import message_to_json, avp_to_json

# Parse complete Diameter messages
message_hex = "0100006c80000118..."
json_output = message_to_json(message_hex)
print(json_output)
# → [{"code": 264, "name": "Origin-Host", "value": "..."}, ...]

# Parse individual AVPs
avp_hex = "0000010840000031..."
avp_json = avp_to_json(avp_hex)
print(avp_json)
# → {"code": 264, "name": "Origin-Host", "value": "..."}
```

#### 🖥️ **CLI Magic**

```bash
# Parse Diameter messages
pydiameter2json message2json "0100006c80000118..."

# Parse individual AVPs
pydiameter2json avp2json "0000010840000031..."

# Get help
pydiameter2json --help
```

### 🔍 **Real Examples**

#### 📊 **Gx Interface Message**
```bash
# Device-Watchdog-Request parsing
pydiameter2json message2json "0100006c8000011800000000a3734495a375f3e40000010840000031707473642d362e6d6f64756c652d322e54504550545330312e74616977616e6d6f62696c652e636f6d000000000001284000001874616977616e6d6f62696c652e636f6d000001164000000c5416d236"

# Output:
# ├── (264, 49), Origin-Host, ptsd-6.module-2.TPEPTS01.taiwanmobile.com
# ├── (296, 24), Origin-Realm, taiwanmobile.com
# └── (278, 12), Origin-State-Id, 1410781750
```

#### 🔧 **Individual AVP**
```bash
# Origin-Host AVP parsing
pydiameter2json avp2json "0000010840000031707473642d362e6d6f64756c652d322e54504550545330312e74616977616e6d6f62696c652e636f6d000000"

# Output:
# └── (264, 49), Origin-Host, ptsd-6.module-2.TPEPTS01.taiwanmobile.com
```

## 🧪 **Testing**

<div align="center">

### ✅ **Test Suite**

```bash
# Run all tests
uv run pytest tests/ -v

# Run with coverage
uv run pytest tests/ --cov=pydiameter2json --cov-report=html

# Run specific test
uv run pytest tests/test_message_parser.py::TestDiameterMessageParsing::test_origin_host_avp -v
```

### 🎯 **Test Coverage**
- ✅ **Gx Interface Messages**
- ✅ **AVP Extraction**
- ✅ **Error Handling**
- ✅ **Edge Cases**
- ✅ **Performance**

</div>

## 📚 **API Reference**

### `message_to_json(hex_string: str) → str`
Parse complete Diameter message from hex string to JSON.

**Parameters:**
- `hex_string` (str): Hexadecimal representation of Diameter message

**Returns:**
- `str`: JSON formatted string with parsed AVPs

### `avp_to_json(hex_string: str) → str`
Parse individual AVP from hex string to JSON.

**Parameters:**
- `hex_string` (str): Hexadecimal representation of AVP

**Returns:**
- `str`: JSON formatted string with AVP details

## 🛠️ **Development**

### 🏗️ **Setup Development Environment**

```bash
# Clone repository
git clone https://github.com/fxyzbtc/pydiameter2json.git
cd pydiameter2json

# Install with dev dependencies
uv sync --dev

# Install pre-commit hooks
uv run pre-commit install
```

### 🧪 **Running Tests**

```bash
# All tests
uv run pytest

# With coverage
uv run pytest --cov=pydiameter2json

# Performance tests
uv run pytest tests/ -k performance
```

## 🎯 **Contributing**

We love contributions! Here's how to get started:

### 🚀 **Quick Contribution Guide**

1. **🍴 Fork the repository**
2. **🌿 Create feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **🧪 Add tests**
   ```bash
   uv run pytest tests/
   ```
4. **🎨 Format code**
   ```bash
   uv run black .
   uv run ruff check --fix .
   ```
5. **📤 Push and create PR**

### 📋 **Contributing Guidelines**
- ✅ **Tests required** for new features
- ✅ **Documentation** updates for API changes
- ✅ **Code style** enforced by Black & Ruff
- ✅ **Conventional commits** preferred

## 📄 **License**

**MIT License** - see [LICENSE](LICENSE) file for details.

## 🌟 **Support**

<div align="center">

### 📞 **Get Help**

- 🐛 **Report bugs**: [GitHub Issues](https://github.com/fxyzbtc/pydiameter2json/issues)
- 💡 **Feature requests**: [GitHub Discussions](https://github.com/fxyzbtc/pydiameter2json/discussions)
- 📧 **Email**: [Issues Page](https://github.com/fxyzbtc/pydiameter2json/issues)

### 🔗 **Links**

| 🎯 **Resource** | 🔗 **Link** |
|:----------------|:------------|
| 📖 **Documentation** | [GitHub Wiki](https://github.com/fxyzbtc/pydiameter2json/wiki) |
| 🏠 **Homepage** | [GitHub Repository](https://github.com/fxyzbtc/pydiameter2json) |
| 🐛 **Issue Tracker** | [GitHub Issues](https://github.com/fxyzbtc/pydiameter2json/issues) |
| 📊 **Releases** | [GitHub Releases](https://github.com/fxyzbtc/pydiameter2json/releases) |

</div>

---

<div align="center">

**⭐ Star this repository if you find it helpful!**

*Made with ❤️ by the PyDiameter2JSON team*

</div>
