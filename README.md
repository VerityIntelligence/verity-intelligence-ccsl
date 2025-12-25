# verity-intelligence-ccsl
Security infrastructure company building verifiable execution system



# CCSL - Central Compute Self-Processing Language

[![CI Status](https://github.com/verity-intelligence/ccsl/workflows/CCSL%20CI%2FCD/badge.svg)](https://github.com/verity-intelligence/ccsl/actions)
[![CCSL Self-Verification](https://github.com/verity-intelligence/ccsl/workflows/CCSL%20Self-Verification/badge.svg)](https://github.com/verity-intelligence/ccsl/actions)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)

**Version 0.1.0** | **Apache 2.0 License** | **[Verity Intelligence](https://verityintelligenceinc.com)**

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

## 🚀 Quick Start

```python
from ccsl import Policy, VerifiedExecutor, Compartment

# 1. Define a policy
policy = Policy(compartment=Compartment.PUBLIC)
policy.add_forbidden_operation("eval")
policy.add_forbidden_operation("exec")
policy.set_required_trust_level(5)

# 2. Create verified executor
executor = VerifiedExecutor(policy)

# 3. Write code to verify
code = """
def greet(name):
    return f"Hello, {name}!"

result = greet("World")
print(result)
"""

# 4. Execute with verification
result = executor.execute(code)
print(f"Execution result: {result}")
print(f"Verification status: {result.verification.is_verified}")
```

## 🔐 Self-Verification

CCSL uses its own verification framework to ensure code quality:

```bash
# Run CCSL self-verification
make self-verify

# Or manually
python scripts/ccsl_cleanup.py
```

This will:
- ✅ Format Python and Rust code
- ✅ Verify policy compliance
- ✅ Check for forbidden operations
- ✅ Generate verification report

## 📚 Core Components

### Policy Engine
Define security policies with compartment-based access control:
- **PUBLIC** (Trust Level 0-4) - Untrusted code, strict sandboxing
- **PRIVATE** (Trust Level 5-9) - Semi-trusted code, limited access
- **ADMIN** (Trust Level 10) - Fully trusted code, unrestricted

### Static Analyzer (Mini-BEV)
AST-based code analysis detecting:
- Forbidden operations (eval, exec, compile)
- Unsafe subprocess calls
- Policy violations
- Trust level requirements

### SAF v2 (Structured Audit Format)
Cryptographic attestation with:
- Ed25519 digital signatures
- Multi-party verification (m-of-n threshold)
- Tamper-evident records
- Comprehensive metadata

### Chain-of-State Ledger
Immutable execution history:
- Hash-linked state transitions
- Cryptographic verification
- Audit trail generation
- State integrity validation

### Verified Executor
Secure execution pipeline:
- Pre-execution verification
- Sandboxed runtime
- Post-execution validation
- Result attestation

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────┐
│              Code Submission                     │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│         Static Analysis (Mini-BEV)              │
│  • AST inspection                                │
│  • Forbidden operation detection                 │
│  • Trust level computation                       │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│            Policy Verification                   │
│  • Compartment checks                            │
│  • Operation validation                          │
│  • Trust requirements                            │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼ [PASS]
┌─────────────────────────────────────────────────┐
│       SAF v2 Record Generation                   │
│  • Ed25519 signature                             │
│  • Multi-party attestation                       │
│  • Metadata collection                           │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│     Ledger Entry (Chain-of-State)               │
│  • Hash-linked state                             │
│  • State transition                              │
│  • Cryptographic proof                           │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│         Verified Execution                       │
│  • Sandboxed runtime                             │
│  • Result validation                             │
│  • Attestation                                   │
└─────────────────────────────────────────────────┘
```

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

Before submitting a PR:

```bash
# 1. Run self-verification
make self-verify

# 2. Run tests
pytest tests/ -v

# 3. Check formatting
black --check ccsl/
flake8 ccsl/

# 4. Type checking
mypy ccsl/
```

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

## 🔒 Security

For security vulnerabilities, please email security@verityintelligenceinc.com instead of opening a public issue.

See [SECURITY.md](SECURITY.md) for our security policy.

## 📖 Documentation

- **[Technical Whitepaper](./whitepaper/WHITEPAPER.md)** - Complete specification
- **[API Reference](https://docs.verityintelligenceinc.com)** - Full API documentation
- **[Contributing Guide](CONTRIBUTING.md)** - Development guidelines
- **[Security Policy](SECURITY.md)** - Security practices
- **[Changelog](CHANGELOG.md)** - Version history

## 🛣️ Roadmap

- ✅ **Phase 0.1** - Prototype (Complete)
- 🔨 **Phase 0.3** - Multi-agent support (In Development)
- 📋 **Phase 0.6** - Formal specification (Planned)
- 🎯 **Phase 1.0** - General availability (Future)

## 📄 License

Apache 2.0 - See [LICENSE](LICENSE) for details.

## 🔗 Links

- **Website**: https://verityintelligenceinc.com
- **GitHub**: https://github.com/verity-intelligence/ccsl
- **Discord**: https://discord.gg/verity-intelligence
- **X/Twitter**: https://x.com/VerityIntelligence

## 💬 Contact

- **General**: hello@verityintelligenceinc.com
- **Enterprise**: enterprise@verityintelligenceinc.com
- **Research**: research@verityintelligenceinc.com
- **Security**: security@verityintelligenceinc.com

## 🙏 Acknowledgments

CCSL builds on decades of research in:
- Programming language theory
- Cryptographic verification
- Distributed systems
- Formal methods

Special thanks to the open source community and security researchers who inspire our work.

---

**"Exploration Builds Capability."**

© 2025 Verity Intelligence. All rights reserved.
