# verity-intelligence-ccsl
Security infrastructure company building verifiable execution system

markdown
# CCSL - Central Compute Self-Processing Language

[![CI Status](https://github.com/verity-intelligence/ccsl/workflows/CCSL%20CI%2FCD/badge.svg)](https://github.com/verity-intelligence/ccsl/actions)
[![CCSL Self-Verification](https://github.com/verity-intelligence/ccsl/workflows/CCSL%20Self-Verification/badge.svg)](https://github.com/verity-intelligence/ccsl/actions)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)

**Version 0.1.0** | **Apache 2.0 License** | **[Verity Intelligence](https://verity-intelligence.com)**

Verification-first execution framework for planetary-scale AI infrastructure.

## 🚀 Overview

CCSL is a verifiable execution-integrity framework designed to guarantee that digital agents, autonomous systems, and computational processes behave exactly as specified. Code cannot execute until its behavior is proven compliant with policy.

### Core Innovation

**CCSL treats verification as a prerequisite rather than an audit step.**

## ✨ Key Features

- **🔒 Pre-Runtime Verification** - Code verified before execution
- **⚡ Policy-Embedded Security** - Policies compiled into execution
- **🛡️ Multi-Party Attestation** - Distributed trust through threshold signatures
- **🔍 Cryptographic Audit Trail** - SAF v2 records with Ed25519 signatures
- **📊 Chain-of-State Ledger** - Immutable, hash-linked execution history
- **🌍 Planetary Scale** - Designed for billions of devices

## 📦 Installation
```bash
pip install ccsl
```

Or install from source:
```bash
git clone https://github.com/verity-intelligence/ccsl.git
cd ccsl
pip install -e .
```

## 🎯 Quick Start
```python
from ccsl import Policy, Compartment, VerifiedExecutor

# Create policy
policy = Policy(name="demo", compartment=Compartment.PUBLIC)

# Create executor
executor = VerifiedExecutor(policy)

# Execute verified code
code = """
data = "user input"
clean = sanitize(data)
print(f"Processed: {clean}")
"""

result = executor.run(code)
print(f"Success: {result.success}")
print(f"Trust Level: {result.analysis.trust_level}")
print(f"SAF ID: {result.saf_record.saf_id}")
```

## 📚 Examples

See `examples/basic_usage.py` for comprehensive demonstrations:

- ✅ Simple verified execution
- ✅ Policy violation detection
- ✅ Sanitization requirements
- ✅ Multi-party verification
- ✅ Chain-of-state ledger

Run examples:
```bash
python examples/basic_usage.py
```

## 🏗️ Architecture

CCSL consists of four layers:

1. **Language Layer** - Explicit policies and compartments
2. **Verification Layer** - Static analysis and policy compilation
3. **Execution Layer** - Sandboxed, deterministic runtime
4. **Attestation Layer** - SAF v2 with Ed25519 multi-signatures

## 🔐 Security

- **Ed25519 Signatures** - 256-bit security level
- **SHA-256 Hashing** - Collision-resistant state tracking
- **Deterministic Execution** - Reproducible verification
- **Multi-Party Trust** - Threshold signature requirements

## 🤖 CCSL Self-Verification

CCSL uses its own verification framework to ensure code quality and security in its own codebase!

### How It Works

1. **CCSL verifies CCSL** - The static analyzer checks its own code
2. **Policy enforcement** - CCSL's policies apply to itself
3. **Cryptographic attestation** - Every formatting operation is verified
4. **Automated cleanup** - GitHub Actions runs CCSL self-verification

### Usage
```bash
# Verify code (no formatting)
make verify

# Format code (no verification)
make format

# Complete self-verification (format + verify)
make self-verify

# Or use the Python script directly
python scripts/ccsl_cleanup.py
python scripts/ccsl_cleanup.py --verify-only
python scripts/ccsl_cleanup.py --json > report.json
```

### CI/CD Integration

CCSL automatically verifies itself on every push:

- ✅ Code is formatted with Black, isort, Ruff
- ✅ Rust code formatted with cargo fmt, clippy
- ✅ All code verified using CCSL's own analyzer
- ✅ Violations are reported and blocked
- ✅ Verification report uploaded as artifact

This ensures that CCSL's codebase meets its own security and quality standards!

## 🤝 Contributing

**Contributions welcome!** We'd love your help making CCSL better.

### Before Submitting PRs

Please run these commands to ensure your code meets our standards:
```bash
# Python formatting and linting
ruff check --fix .
black --line-length 100 .
isort --profile black --line-length 100 .

# Rust formatting (if modifying Rust code)
cargo fmt --all
cargo clippy --fix --allow-dirty

# Or use our self-verification tool
make self-verify
python scripts/ccsl_cleanup.py
```

### Contribution Process

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Run formatting and tests
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to your branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

### Areas We Need Help

- 🐛 Bug fixes and testing
- 📚 Documentation improvements
- 🚀 Performance optimizations
- 🔧 New features from the roadmap
- 🌍 Multi-language support
- 📊 Example applications

All contributors will be recognized in our [CONTRIBUTORS.md](CONTRIBUTORS.md) file.

## 📖 Documentation

- **[Technical Whitepaper](https://verity-intelligence.com/whitepaper.html)** - Complete specification
- **[API Reference](https://docs.verity-intelligence.com)** - Full API documentation
- **[GitHub](https://github.com/verity-intelligence/ccsl)** - Source code

## 🛣️ Roadmap

- ✅ **Phase 0.1** - Prototype (Complete)
- 🔨 **Phase 0.3** - Multi-agent support (Q2 2025)
- 📋 **Phase 0.6** - Formal specification (Q3 2025)
- 🎯 **Phase 1.0** - General availability (Q1 2026)

## 📄 License

Apache 2.0 - See [LICENSE](LICENSE) for details.

## 🔗 Links

- **Website**: https://verity-intelligence.com
- **GitHub**: https://github.com/verity-intelligence/ccsl
- **Discord**: https://discord.gg/verity-intelligence
- **X/Twitter**: https://x.com/VerityIntelligence

## 💬 Contact

- **General**: hello@verity-intelligence.com
- **Enterprise**: enterprise@verity-intelligence.com
- **Research**: research@verity-intelligence.com

---

**"Exploration Builds Capability."**

© 2025 Verity Intelligence. All rights reserved.





