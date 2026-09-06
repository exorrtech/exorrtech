<div align="center">

<img src="https://raw.githubusercontent.com/exorrtech/exorrtech/main/assets/exorr-banner.svg" alt="EXORR" width="100%">

### Azure & AI Security Engineering

**[exorr.tech](https://www.exorr.tech)**

```console
$ whoami
exorr. independent cloud and AI security engineering.
$ uptime --engagements
accepting 2 clients per month. every finding reproducible before it ships.
```

</div>

The attack surface is what others miss. I look at what is not there. The misconfiguration nobody closed. The subdomain somebody forgot. The prompt that was never sanitized. The role assignment that made sense on the day it was made and made no sense the day it was used.

Most teams secure what they can see. The interesting failures live in the other category.

## 🔧 The Arsenal

Tools I built because the ones that existed did not do what the job actually needed.

```console
$ ./recon-toolkit --target target.com --full

[*] subfinder:   47 subdomains discovered
[*] httpx:       31 alive, 6 on non-standard ports
[*] nmap:        14 services fingerprinted, 2 outdated panels
[*] nuclei:      3 findings, 1 critical (staged Jenkins, unauth)

[+] report written. 2 doors were open that should not exist.
[+] every finding has a repro path and a fix that fits in one ticket.
```

**[exorr-azure-audit](https://github.com/exorrtech/exorr-azure-audit)** scans Azure and Entra ID for the misconfigurations that actually lead to compromise. RBAC sprawl, Key Vault access policies, over-permissive NSGs, orphaned identities. The scanner sees what a checklist misses.

**[exorr-prompt-fuzzer](https://github.com/exorrtech/exorr-prompt-fuzzer)** throws automated prompt injection and jailbreak attempts at LLMs until something gives. It keeps what worked. Your AI feature has an attack surface whether or not you drew one.

**[exorr-secret-scanner](https://github.com/exorrtech/exorr-secret-scanner)** finds leaked credentials, API keys and tokens in Git repos and directories, including the ones everyone assumes are private.

**[exorr-subdomain-monitor](https://github.com/exorrtech/exorr-subdomain-monitor)** watches subdomains for change over time, because the forgotten test environment with the production database copy is where breaches start.

**[recon-toolkit](https://github.com/exorrtech/recon-toolkit)** chains subfinder, httpx, nmap and nuclei into one pipeline, so the surface mapping that used to take a week takes an afternoon.

**[9099-Files](https://github.com/exorrtech/9099-Files)** is a nineteen chapter playbook on breaking and securing MCP servers, the tooling layer every AI agent now depends on. Working exploit scripts, a lab server, KQL and Sigma detection rules, 8 CVEs verified against public databases. Two chapters free. Written while the rest of the industry was still asking what MCP stands for.

```console
$ ./exorr-azure-audit --tenant prod --module rbac

[!] 4 identities with Owner on the production subscription
[!] 2 of them have not signed in for 90+ days
[!] 1 service principal can read every Key Vault secret
[!] PIM not enforcing approval for Global Admin activation

[!] findings ranked by blast radius, not by CVSS score.
```

## 🎯 Reproduced Findings

Findings I have demonstrated end to end, documented with the full chain, not screenshots of somebody else's slide deck.

```console
CRITICAL   Key Vault secret extraction          Azure Key Vault
           via privileged identity assignment

HIGH       Entra ID privilege escalation        Microsoft Entra ID
           via role assignment chain

HIGH       OpenAI prompt injection              Azure OpenAI
           via system prompt override
```

Currently researching AI agent attack chains, Azure lateral movement, and LLM jailbreak patterns. The field moves fast and most of the public guidance is written by people who have never executed the attack.

## 🧰 Stack

**Cloud:** Azure, Entra ID, Defender, Key Vault, PIM
**Offense:** Burp Suite, Nuclei, Nmap, subfinder, PyRIT, custom fuzzers
**Systems:** Linux daily driver, hardened terminals, KVM, network monitoring
**Code:** Python, Bash, C

## 📜 Certifications

`SC-500` Cloud & AI Security Engineer Associate · `ISC2 CC` · `MS-900`

## 📡 Work With Me

Fixed scope, fixed price, findings reproduced before delivery. No discovery phases that exist to bill hours.

```console
$ ./exorr --services

azure-security-review      one tenant, identity to egress, every finding reproducible
ai-workload-audit          prompt injection surface, tool trust, data paths, entitlements
agent-pipeline-hardening   MCP servers, agent tooling, the LLM to production wiring
```

**[exorr.tech](https://www.exorr.tech)** · [x/exorrtech](https://x.com/exorrtech) · [exorrnull@gmail.com](mailto:exorrnull@gmail.com)

```console
$ echo "the void secures"
the void secures
```
