```ascii
  ██████  ███████ ███    ██ ███████ ███████ ██ ███████ 
 ██       ██      ████   ██ ██      ██      ██ ██      
 ██   ███ █████   ██ ██  ██ █████   ███████ ██ ███████ 
 ██    ██ ██      ██  ██ ██ ██           ██ ██      ██ 
  ██████  ███████ ██   ████ ███████ ███████ ██ ███████ 
```

<div align="center">

# Security Researcher | Software Engineer | OSINT Developer

[![Location](https://img.shields.io/badge/Location-Uruguay-00A3E0?style=flat-square)]()
[![Status](https://img.shields.io/badge/Status-Building_Security_Tools-00D26A?style=flat-square)]()
[![Email](https://img.shields.io/badge/Email-genzt.dev%40pm.me-8B89CC?style=flat-square&logo=protonmail&logoColor=white)](mailto:genzt.dev@pm.me)

**21 years old | Self-taught cybersecurity professional**  
**Certifications:** OWASP | GDPR | ISO 27001

</div>

## About Me

```python
class Genesis:
    def __init__(self):
        self.role = "Security Researcher & Software Engineer"
        self.location = "Uruguay"
        self.age = 21
        self.background = "Self-taught cybersecurity professional"
        
        self.core_expertise = {
            "security_research": [
                "Open Source Intelligence (OSINT)",
                "Endpoint Detection & Response (EDR)",
                "Threat Intelligence Analysis",
                "Malware Behavioral Analysis",
                "Penetration Testing Methodologies",
                "Vulnerability Research & Discovery",
                "Security Tool Architecture",
                "Operational Security (OpSec)"
            ],
            "software_development": [
                "Security Framework Architecture",
                "System-Level Programming (C/C++)",
                "High-Performance Computing",
                "API Design & Integration",
                "Algorithm Implementation & Optimization",
                "Performance Profiling & Tuning",
                "Database Architecture & Query Optimization",
                "Automation & Scripting"
            ],
            "programming_languages": {
                "expert": ["Python", "Bash"],
                "advanced": ["C", "C++", "Assembly"],
                "proficient": ["C#", "JavaScript", "TypeScript", "Ruby"]
            }
        }
        
        self.active_projects = [
            "nexus-intelligence",       # OSINT framework
            "threat-detection-suite",   # EDR system
            "calcx-advanced"            # Mathematical engine
        ]
        
        self.certifications = [
            "OWASP - Web Application Security (2025)",
            "GDPR - Data Privacy & Protection (2024)",
            "ISO 27001 - Information Security Management (2025)"
        ]
        
        self.goals_2025 = [
            "Expand OSINT framework with 100+ new platforms",
            "Develop advanced threat detection algorithms",
            "Contribute to major open-source security projects",
            "Publish security research papers",
            "Build machine learning models for threat intelligence"
        ]
    
    def get_learning_path(self):
        return [
            "Advanced exploitation techniques",
            "Malware analysis methodologies (static & dynamic)",
            "Reverse engineering for x86/x64 binaries",
            "Cloud security architecture (AWS, GCP, Azure)",
            "Container security and Kubernetes hardening",
            "Network protocol analysis and packet crafting",
            "Cryptographic systems implementation",
            "Zero-trust architecture design"
        ]
    
    def get_technical_interests(self):
        return [
            "OSINT methodology development and automation",
            "EDR evasion techniques and detection logic",
            "Living-off-the-land binary (LOLBin) abuse patterns",
            "Behavioral malware analysis and heuristics",
            "Privacy-preserving technologies",
            "Threat intelligence correlation",
            "Security tool development",
            "Digital forensics and incident response"
        ]
```

## Featured Projects

### Nexus Intelligence Framework

**Advanced OSINT Platform for Security Professionals**

Modular intelligence gathering framework implementing automated reconnaissance across digital footprints. The platform combines GitHub profiling, domain infrastructure analysis, breach correlation, and social media enumeration with weighted risk assessment for identity verification and threat assessment.

**Technical Architecture**

Seven-module sequential intelligence pipeline:

**HTTPEngine** - Production request handler
- Connection pooling: 30 persistent connections eliminate TCP handshake overhead (~40ms reduction)
- Automatic retry: 5 attempts with exponential backoff (2s, 4s, 8s, 16s, 32s)
- User-agent rotation: 6 browser signatures for fingerprint evasion
- Response caching: TTL-based storage with 3600-second expiration
- Rate limiting: X-RateLimit-Remaining and X-RateLimit-Reset tracking
- Proxy support: HTTP, HTTPS with round-robin rotation
- Statistics: request count, failure rate, cache hit ratio

**GitHubIntel** - Comprehensive profile extraction
- User profile: login, name, company, blog, location, email, bio, Twitter
- Repository analysis: 42 repos with stars, forks, language statistics
- Commit forensics: Email extraction from author metadata and Co-authored-by parsing
- Event timeline: PushEvent, PullRequestEvent, IssuesEvent, ForkEvent, WatchEvent
- Gist discovery: Public gist enumeration with file listings
- Organization mapping: Membership detection and role identification
- Credential scanning: AWS keys (AKIA*), GitHub tokens (ghp_*), RSA private keys
- Risk indicators: Admin/root mentions, privilege escalation patterns
- Statistics: Language distribution, repository quality metrics, fork-to-star ratios

**DomainIntel** - Infrastructure reconnaissance
- DNS enumeration: A, AAAA, MX, NS, TXT, CNAME records
- Email security: SPF, DMARC, DKIM policy detection
- WHOIS parsing: Registrant, registrar, creation/expiration dates
- Vulnerability assessment: Missing SPF/DMARC, DNSSEC detection
- Mail server analysis: MX priority ordering, hostname extraction
- Security policy evaluation: SPF syntax validation, DMARC parsing

**BreachIntel** - Data breach correlation
- Have I Been Pwned API v3 integration
- Per-email breach checking with cache
- Breach name extraction from JSON responses
- Batch processing: Multiple email verification
- HTTP status handling: 200 (found), 404 (clean)

**SocialIntel** - Cross-platform enumeration
- 20 platforms: GitHub, GitLab, Twitter, LinkedIn, Reddit, Instagram, TikTok, YouTube, Twitch, Mastodon, StackOverflow, HackerOne, Bugcrowd, Dev.to, Medium, CodePen, Patreon, Behance, Dribbble, Discord
- HTTP validation: 200 (exists), 404 (not found), 3xx (redirect)
- Sequential checking with error isolation
- Per-platform timeout configuration

**RiskScorer** - Multi-factor weighted assessment
- Seven-factor model: Exposed emails (20%), email breaches (25%), public repos (15%), activity patterns (10%), network size (10%), code vulnerabilities (10%), domain vulnerabilities (10%)
- Score range: 0-100 with four-tier classification
- Risk levels: CRITICAL (80-100), HIGH (60-79), MEDIUM (40-59), LOW (0-39)
- Factor breakdown for transparency

**ExportManager** - Multi-format reports
- JSON: 2-space indent, UTF-8, datetime conversion
- CSV: Nested flattening with dot notation
- HTML: Jinja2 templates with color-coded risk levels
- XML: ElementTree-based hierarchical structure

**Key Implementation Details**

Credential pattern scanning (regex-based):
```python
PATTERNS = {
    'AWS_ACCESS_KEY': r'AKIA[0-9A-Z]{16}',
    'GITHUB_TOKEN': r'ghp_[a-zA-Z0-9]{36}',
    'RSA_PRIVATE_KEY': r'-----BEGIN RSA PRIVATE KEY-----',
    'OPENSSH_PRIVATE_KEY': r'-----BEGIN OPENSSH PRIVATE KEY-----'
}
```

Risk scoring algorithm:
```python
# Factor 1: Exposed Emails (20% weight)
email_score = min(email_count * 15, 100)

# Factor 2: Email Breaches (25% weight)
breach_score = min(breached_count * 30, 100)

# Factor 3: Public Repos (15% weight)
repo_score = min(repo_count * 5, 100)

# Weighted total
total_score = sum(score * weight for score, weight in factors)
```

**Performance Metrics**

Benchmarked on Ubuntu 22.04, Intel Core i7-11700K, 32GB RAM:

| Operation | Time | API Calls | Memory |
|-----------|------|-----------|--------|
| Single username lookup | 2.3s | 15 | 25MB |
| GitHub full analysis | 5.1s | 30 | 35MB |
| Social media scan (20) | 45s | 20 | 50MB |
| DNS enumeration | 3.2s | 20 | 15MB |
| Complete investigation | 60s | 400+ | 75MB |

**Technology Stack**

Python 3.8+ | requests 2.31.0 | urllib3 2.2.1 | dnspython 2.6.0 | BeautifulSoup 4.12.3 | Jinja2 3.1.3 | Rich 13.7.0 | python-whois 0.8.0

**Repository:** [github.com/genesisgzdev/nexus-intelligence](https://github.com/genesisgzdev/nexus-intelligence)

### Threat Detection Suite

**Advanced EDR Framework for Windows Systems**

Endpoint detection and response system implementing automated threat identification with active remediation. Addresses sophisticated malware including rootkits, LOLBin attacks, persistence mechanisms, and command-and-control infrastructure through behavioral analysis and heuristic detection.

**Detection Engine Architecture**

Seven-phase sequential analysis with automated response capabilities:

**Phase 1: Process Behavior Analysis**
- DLL injection detection via EnumProcessModules
- High severity: 80+ loaded modules
- Critical: 120+ modules triggers automatic termination
- Suspicious process name patterns (audio, media, svchost)
- AMSI bypass detection via non-standard DLL extensions (.dat, .enc, .tmp)

**Phase 2: API Hook Detection**
- Six-pattern multi-signature engine:
  - Short JMP (0xEB): 2-byte relative jump
  - Long JMP (0xE9): 5-byte relative jump (Detours pattern)
  - PUSH+RET (0x68...0xC3): 6-byte trampoline
  - MOV R11 (0x49 0xBB): 12-byte x64 register trampoline
  - RIP-relative JMP (0xFF 0x25): 6-byte position-independent
  - RIP-relative CALL (0xFF 0x15): 6-byte call forwarding
- Monitors five critical kernel32 APIs: CreateProcessA, CreateRemoteThread, WriteProcessMemory, LoadLibraryA, SetWindowsHookExA
- Memory integrity verification via ReadProcessMemory

**Phase 3: Memory Anomaly Detection**
- VirtualQueryEx-based executable region enumeration
- PAGE_EXECUTE_READWRITE and PAGE_EXECUTE_WRITECOPY detection
- NOP sled identification: 10+ consecutive 0x90 bytes
- Automatic process termination on shellcode detection
- Minimum region size filtering (4KB) for false positive reduction

**Phase 4: Registry Persistence Monitoring**
- Six registry paths: HKCU/HKLM Run, RunOnce, WOW6432Node variants
- Nine malware signatures: Audio, MSAudio, Media, WindowsUpdate, svchost, driver, sound, Spy, Monitor
- Automatic registry value deletion via RegDeleteValueA
- KEY_ALL_ACCESS permission enforcement

**Phase 5: Network C2 Detection**
- GetTcpTable2 enumeration filtering MIB_TCP_STATE_ESTAB
- Suspicious ports: 4444, 5555, 6666, 7777, 8888, 9999, 31337, 12345, 666, 1337
- Process-to-connection correlation via dwOwningPid
- Automatic process termination on C2 port detection

**Phase 6: Persistence File Detection**
- Shannon entropy calculation: `-Σ(p × log₂(p))`
- Critical threshold: 7.8 bits/byte for encrypted files
- HIDDEN+SYSTEM attribute combination detection
- Automatic file quarantine via MoveFileExA with .QUARANTINE extension
- Temp directory scanning for encrypted persistence

**Phase 7: LOLBin Abuse Analysis**
- PEB parsing via NtQueryInformationProcess
- Command-line extraction from PROCESS_BASIC_INFORMATION
- Weighted risk scoring (0-100+ scale):
  - certutil.exe: -encode (+25), -urlcache (+30), -download (+35)
  - PowerShell: -enc (+20), IEX (+35), DownloadString (+40), -WindowStyle Hidden (+20)
  - WMI: process + call (+50)
- CRITICAL threshold: 85+ points triggers termination
- HIGH threshold: 50-84 points logged only

**Automated Remediation System**

Four-module active response:

**Process Termination Module**
```c
RemediateProcessTermination(DWORD pid, LPCSTR process_name)
```
- Opens process with PROCESS_TERMINATE rights
- Executes TerminateProcess() with exit code 127
- Logs ACTION_KILL_PROCESS with success/failure
- Updates statistics: processes_killed, successful_actions

**Registry Cleanup Module**
```c
RemediateRegistryCleanup(HKEY root, LPCSTR subkey, LPCSTR value_name)
```
- Opens key with KEY_ALL_ACCESS permissions
- Deletes value via RegDeleteValueA
- Handles ERROR_ACCESS_DENIED gracefully

**File Quarantine Module**
```c
RemediateFileQuarantine(LPCSTR file_path)
```
- Moves file using MoveFileExA with MOVEFILE_REPLACE_EXISTING
- Appends .QUARANTINE extension
- Preserves original for forensic analysis

**Network Disruption**
- Terminates processes with C2 connections
- Logs remote IP and port for investigation

**Technical Implementation**

Thread-safe logging:
```c
InitializeCriticalSection(&global_threat_lock);
EnterCriticalSection(&global_threat_lock);
// Threat logging
LeaveCriticalSection(&global_threat_lock);
DeleteCriticalSection(&global_threat_lock);
```

Shannon entropy calculation:
```c
float CalculateEntropy(LPCVOID data, DWORD size) {
    unsigned int freq[256] = {0};
    for (DWORD i = 0; i < size; i++) {
        freq[((BYTE*)data)[i]]++;
    }
    
    float entropy = 0.0f;
    for (int i = 0; i < 256; i++) {
        if (freq[i] > 0) {
            float p = (float)freq[i] / size;
            entropy -= p * log2f(p);
        }
    }
    return entropy;  // Range: 0.0-8.0
}
```

**Performance Characteristics**

Measured on Windows 11 Pro, Intel Core i7-11700K, 32GB RAM:

| Phase | Time | Objects | Memory |
|-------|------|---------|--------|
| Process Behavior | 2.1s | 120 processes | 15 MB |
| API Hook Detection | 1.3s | 5 APIs | 8 MB |
| Memory Anomaly | 4.2s | 3,500 regions | 25 MB |
| Registry Persistence | 1.7s | ~200 values | 5 MB |
| Network C2 | 0.8s | 45 connections | 3 MB |
| Persistence Files | 3.5s | 1,200 files | 12 MB |
| LOLBin Analysis | 2.4s | 15 processes | 10 MB |
| **Total Scan** | **16.0s** | **Full system** | **78 MB peak** |

Resource usage:
- CPU: 18-25% (single-threaded)
- Memory: 50-80MB RSS
- Disk I/O: <5 MB/s read
- Network: Zero (read-only)

**Technology Stack**

C++17 | Windows API | MSVC v142 | Visual Studio 2019+ | ws2_32 | advapi32 | shell32 | psapi | iphlpapi | ntdll

**Repository:** [github.com/genesisgzdev/threat-detection-suite](https://github.com/genesisgzdev/threat-detection-suite)

### CalcX Advanced

**Professional Mathematical Computation Engine**

Arbitrary precision arithmetic engine delivering scientific calculations through command-line and interactive interfaces. Built for researchers, engineers, and professionals requiring accurate numerical analysis without specialized software overhead.

**Core Architecture**

Four-layer design pattern:

**Computation Layer**
- GNU bc backend for arbitrary precision arithmetic
- Zero rounding errors in floating-point operations
- Python math and cmath libraries for transcendental functions
- Graceful degradation when dependencies unavailable

**Interface Layer**
- Dual-mode operation: CLI and interactive
- Menu system with dispatch to calculation functions
- Independent input validation per operation
- Comprehensive error handling

**Persistence Layer**
- Calculation history with file storage
- In-memory arrays for rapid recall
- Maximum history size enforcement (20 entries)
- File: `~/.calc_ultra_history.log`

**Utility Layer**
- Regex-based input validation
- ANSI color output with reset sequences
- Dependency detection: python3 vs python
- Cross-platform compatibility (Unix, WSL2)

**Mathematical Capabilities**

Fundamental arithmetic:
- Addition, subtraction, multiplication, division
- Modular arithmetic and remainder
- Operator precedence enforcement

Scientific computing:
- Trigonometric: sin, cos, tan, asin, acos, atan
- Hyperbolic: sinh, cosh, tanh
- Logarithmic: ln, log10, arbitrary base
- Exponential: exp, power operations

Advanced mathematics:
- Matrix determinants via cofactor expansion
- Matrix inversion via LU decomposition
- Gaussian elimination for linear systems
- Statistical analysis: mean, median, variance, standard deviation
- Combinatorics: permutations, combinations, factorial

Complex numbers:
- Rectangular form: a + bi
- Polar form: r(cos θ + i sin θ)
- Conversion between forms
- Arithmetic operations

Base conversion:
- Binary (base 2)
- Octal (base 8)
- Decimal (base 10)
- Hexadecimal (base 16)

Number theory:
- Prime factorization with trial division
- GCD via Euclidean algorithm
- LCM calculation
- Primality testing

Numerical methods:
- Integration: Simpson's rule with parabolic fitting
- Differentiation: finite differences
- ODE solving: Euler's method
- Root finding: Newton-Raphson iteration
- Discrete Fourier Transform

**Implementation Details**

Code organization:
- 2500+ lines of optimized Bash and Python
- Logical sections with comment headers
- Python detection (python3 vs python)
- Command-line argument parsing
- History management system

Input validation:
```bash
# Regex patterns for numeric inputs
number_regex="^-?[0-9]+\.?[0-9]*$"
coefficient_regex="^-?[0-9]+\.?[0-9]*$"

# Validate before computation
if ! [[ $input =~ $number_regex ]]; then
    echo "Error: Invalid number format"
    return 1
fi
```

Configuration:
```bash
MAX_HISTORIAL=20      # History entries retained
PRECISION=6           # Default significant figures
HIST_FILE="$HOME/.calc_ultra_history.log"
```

**Performance Metrics**

Execution times:
- Standard arithmetic: <100ms
- 10x10 matrix determinant: <50ms
- 100x100 matrix operations: 200-500ms
- Numerical integration: 100-300ms

Scalability:
- Calculations up to 10^308 magnitude
- Matrix operations: 100x100 maximum
- Floating-point precision: 15-17 digits
- History storage: negligible disk

**Usage Examples**

Command-line:
```bash
calcx "sqrt(144)"              # 12
calcx "2^10"                   # 1024
calcx "sin(3.14159/2)"         # 1
calcx "scale=50; 4*a(1)"       # Pi to 50 decimals
```

Interactive mode:
```bash
calcx
# Menu options:
# 1. Solve quadratic equations
# 2. Complex number operations
# 3. Matrix operations
# 4. Statistical analysis
# 5. Numerical integration
```

**Technology Stack**

Bash 4.0+ | GNU bc 1.07+ | Python 3.6+ | awk | POSIX-compliant

**Repository:** [github.com/genesisgzdev/calcx-advanced](https://github.com/genesisgzdev/calcx-advanced)

## Technical Stack

### Programming Languages

**Expert Level**
- **Python** - Security tool development, API integration, data analysis, automation frameworks
- **Bash** - Shell scripting, system automation, deployment pipelines, DevOps tooling

**Advanced Level**
- **C** - System-level programming, performance-critical code, memory management
- **C++** - Windows API development, EDR systems, malware analysis tools
- **Assembly** - x86/x64 reverse engineering, shellcode analysis, exploit development

**Proficient Level**
- **C#** - .NET applications, Windows desktop development, automation tools
- **JavaScript/TypeScript** - Web development, API clients, Node.js services
- **Ruby** - Scripting, automation, rapid prototyping

### Security Tools & Frameworks

**Penetration Testing**
- Kali Linux
- Metasploit Framework
- Burp Suite Professional
- OWASP ZAP
- sqlmap
- Nmap
- Aircrack-ng
- John the Ripper
- Hashcat

**Malware Analysis**
- IDA Pro
- Ghidra
- x64dbg
- OllyDbg
- Process Hacker
- Wireshark
- NetworkMiner

**Security Frameworks**
- OWASP Testing Guide
- MITRE ATT&CK Framework
- NIST Cybersecurity Framework
- CIS Controls

### Infrastructure & DevOps

**Containerization**
- Docker (image creation, multi-stage builds)
- Kubernetes (deployments, services, ingress)
- Container security hardening

**Version Control & CI/CD**
- Git (branching strategies, rebase, cherry-pick)
- GitHub Actions (workflows, matrix builds)
- GitLab CI/CD

**Operating Systems**
- Linux: Ubuntu, Debian, Arch Linux, Kali
- Windows: 10, 11, Server 2016+
- System administration and hardening

**Web Servers**
- Nginx (load balancing, caching)
- Apache HTTP Server

### Databases & Caching

**Relational**
- PostgreSQL (advanced queries, indexes)
- MySQL/MariaDB

**NoSQL**
- MongoDB (document storage, aggregation)
- Redis (caching, pub/sub)
- Elasticsearch (full-text search)

**Design**
- Schema design and normalization
- Query optimization
- Replication and backup

### Privacy & Security Infrastructure

**Communication**
- ProtonMail (encrypted email)
- Signal Protocol

**Network Privacy**
- Mullvad VPN (WireGuard, OpenVPN)
- Tor network
- Proxy chains

**Data Protection**
- VeraCrypt (full disk encryption)
- Portmaster (application firewall)
- NextDNS (DNS-level blocking)

### Cloud Platforms

**AWS**
- EC2, S3, RDS, Lambda
- VPC, Security Groups, IAM

**Google Cloud**
- Compute Engine
- Cloud Storage
- Cloud Functions

**DigitalOcean**
- Droplets
- Managed Databases

## Professional Certifications

| Certification | Domain | Organization | Year |
|--------------|--------|--------------|------|
| OWASP Certification | Web Application Security Testing | OWASP Foundation | 2025 |
| GDPR Compliance | Data Privacy & Protection | EU Commission | 2024 |
| ISO 27001 | Information Security Management | ISO/IEC | 2025 |

## Development Philosophy

```yaml
code_quality:
  principles:
    - "Production-grade code from inception"
    - "Comprehensive testing as standard"
    - "Documentation for future developers"
    - "Maintainability over cleverness"
    - "Performance without sacrificing readability"
  
  practices:
    - Type hints for all Python functions
    - Comprehensive docstrings (Google style)
    - Unit tests with coverage targets
    - Integration tests for module interactions
    - Code review before merge

security_first:
  design:
    - "Security by design, not afterthought"
    - "Defense in depth across layers"
    - "Principle of least privilege"
    - "Fail securely and gracefully"
    - "Assume breach mentality"
  
  implementation:
    - Input validation on all user data
    - Output sanitization for XSS prevention
    - Parameterized queries for SQL injection prevention
    - Secure credential management
    - Regular dependency updates

ethical_standards:
  research:
    - "Obtain explicit authorization always"
    - "Responsible disclosure (90-day timeline)"
    - "Never exploit without permission"
    - "Report vulnerabilities properly"
    - "Respect privacy and data protection"
  
  development:
    - "Privacy by design principles"
    - "Data minimization practices"
    - "User consent and transparency"
    - "Right to be forgotten compliance"
    - "Secure data handling"

collaboration:
  open_source:
    - "Contribute to security projects"
    - "Share knowledge and research"
    - "Mentor aspiring professionals"
    - "Participate in vulnerability disclosure"
    - "Support ethical hacking"
  
  communication:
    - "Clear technical documentation"
    - "Comprehensive API documentation"
    - "Architecture decision records"
    - "Security advisories"
    - "Usage examples and tutorials"
```

## Current Learning & Research

**Active Study Areas**
- Advanced exploitation techniques and payload development
- Malware analysis methodologies (static and dynamic)
- Reverse engineering for x86/x64 binaries
- Cloud security architecture (AWS, GCP, Azure)
- Container security and Kubernetes hardening
- Network protocol analysis and packet crafting
- Cryptographic systems implementation
- Zero-trust architecture design

**Research Interests**
- OSINT methodology development and automation
- Endpoint detection and response (EDR) evasion techniques
- Living-off-the-land binary (LOLBin) abuse detection
- Behavioral malware analysis and heuristic development
- Privacy-preserving technologies
- Threat intelligence correlation and analysis
- Security tool development
- Digital forensics and incident response

## Collaboration Opportunities

Open to collaboration on:

**Open Source Security**
- Security tool development and framework design
- Vulnerability research and responsible disclosure
- OSINT methodology advancement
- EDR and detection logic improvement
- Privacy-preserving technology implementation

**Research & Development**
- Security research papers and publications
- Proof-of-concept development for novel techniques
- Automated security testing frameworks
- Threat detection algorithm development

**Professional Services**
- Security consulting and assessments
- Penetration testing engagements
- Security tool customization and integration
- Security training and workshops
- Technical writing and documentation

**Contact Information**
- Technical inquiries: genzt.dev@pm.me

## Legal & Ethical Notice

### Authorized Use Policy

All tools, code, and projects are intended exclusively for:

**Authorized Activities**
- Security assessments with explicit written permission
- Bug bounty programs within defined scope
- Educational purposes in controlled environments
- Academic research with institutional approval
- Personal infrastructure testing with ownership
- Professional security consulting with authorization
- Defensive security implementations

**Prohibited Uses**
- Unauthorized access to computer systems
- Malicious activities of any kind
- Privacy violations, surveillance, stalking
- Illegal operations or criminal activities
- Harassment, intimidation, blackmail
- Commercial espionage or corporate theft
- Identity theft or fraud
- Violation of platform terms of service

### Legal Disclaimer

THE SOFTWARE AND TOOLS ARE PROVIDED "AS IS" WITHOUT WARRANTY OF ANY KIND. THE AUTHOR ASSUMES NO LIABILITY FOR MISUSE OR DAMAGES. USERS ARE SOLELY RESPONSIBLE FOR ENSURING COMPLIANCE WITH ALL APPLICABLE LAWS.

**Applicable Laws**
- Computer Fraud and Abuse Act (CFAA) - 18 U.S.C. § 1030 (United States)
- Computer Misuse Act 1990 (United Kingdom)
- General Data Protection Regulation (GDPR) - EU 2016/679
- California Consumer Privacy Act (CCPA)
- Lei Geral de Proteção de Dados (LGPD) - Brazil
- Local criminal statutes

By using any tools or code, you agree to:
- Use them only for legal and ethical purposes
- Obtain proper authorization before deployment
- Comply with all applicable laws
- Accept full responsibility for your actions
- Indemnify the author from any liability

### Privacy & Data Protection

All projects respect user privacy and comply with GDPR, CCPA, LGPD, and other applicable regulations.

Security research prioritizes:
- Privacy by design principles
- Data minimization practices
- Secure data handling
- User consent and transparency
- Right to be forgotten
- Data portability and access rights

## GitHub Statistics

<div align="center">

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=genesisgzdev&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=00D26A&icon_color=00D26A&text_color=FFFFFF&count_private=true)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=genesisgzdev&layout=compact&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=00D26A&text_color=FFFFFF&langs_count=8)

![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=genesisgzdev&theme=tokyonight&hide_border=true&background=0D1117&ring=00D26A&fire=00D26A&currStreakLabel=00D26A)

![Profile Views](https://komarev.com/ghpvc/?username=genesisgzdev&color=00D26A&style=flat-square&label=Profile+Views)

</div>

## Project Showcase

<div align="center">

[![Nexus Intelligence](https://github-readme-stats.vercel.app/api/pin/?username=genesisgzdev&repo=nexus-intelligence&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=00D26A&icon_color=00D26A&text_color=FFFFFF)](https://github.com/genesisgzdev/nexus-intelligence)

[![Threat Detection Suite](https://github-readme-stats.vercel.app/api/pin/?username=genesisgzdev&repo=threat-detection-suite&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=00D26A&icon_color=00D26A&text_color=FFFFFF)](https://github.com/genesisgzdev/threat-detection-suite)

[![CalcX Advanced](https://github-readme-stats.vercel.app/api/pin/?username=genesisgzdev&repo=calcx-advanced&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=00D26A&icon_color=00D26A&text_color=FFFFFF)](https://github.com/genesisgzdev/calcx-advanced)

</div>

## Activity Graph

<div align="center">

[![Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=genesisgzdev&theme=tokyo-night&hide_border=true&bg_color=0D1117&color=00D26A&line=00D26A&point=FFFFFF)](https://github.com/genesisgzdev)

</div>

## Technology Focus Areas

<div align="center">

```mermaid
mindmap
  root((Genesis))
    Security Research
      OSINT
        Reconnaissance
        Social Media Intelligence
        Infrastructure Mapping
        Data Correlation
      Penetration Testing
        Web Application Testing
        Network Security
        Wireless Assessment
        Exploitation
      Malware Analysis
        Static Analysis
        Dynamic Analysis
        Behavioral Detection
        Reverse Engineering
      EDR Development
        Process Monitoring
        API Hook Detection
        Memory Forensics
        Threat Correlation
    Software Development
      System Programming
        Windows API
        Linux Internals
        Memory Management
        Performance Optimization
      Security Tools
        Framework Development
        Plugin Architecture
        API Integration
        Automation
      Backend Development
        API Design
        Database Architecture
        Caching Strategies
        Microservices
      Algorithms
        Pattern Matching
        Risk Scoring
        Data Analysis
        Machine Learning
```

</div>

## Connect

<div align="center">

**Star repositories if useful | Fork and contribute | Reach out for collaboration**

Technical support: genzt.dev@pm.me  
Security issues: genesis.issues@pm.me

</div>

<div align="center">

*Last Updated: December 2025*

**Genesis | Security Research | Privacy First | Open Source**

*Building secure, privacy-respecting tools for the cybersecurity community*

</div>
