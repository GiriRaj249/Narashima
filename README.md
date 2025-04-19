# 🕉️ Narashima - The Stealth God of Payload Delivery

> Advanced PowerShell payload obfuscation and evasion framework for red teamers.

---

## ⚔️ Overview

**Narashima** is a red team payload generation tool built to **evade antivirus**, **bypass AMSI**, and **slip past Microsoft Defender** using multi-stage, obfuscated, and encrypted PowerShell payloads. With layered XOR + Base64 encoding and clean staging, it delivers fully memory-resident payloads with zero detections.

---

## 🔥 Key Features

- 🛡️ AMSI & Defender Bypass  
- 🔐 XOR + Base64 Multi-Stage Encryption  
- 🧬 Function and Variable Name Obfuscation  
- 📦 Multi-layer Payload Staging  
- 🧼 Minimal Disk Forensic Footprint  
- 🔑 Custom XOR Key Encryption  
- 🧠 Executes Fully In-Memory  
- 📁 Customizable Windows Path for Payload Placement  

---

## 🚀 Usage

```bash
python3 narashima.py \
  --target your_payload.ps1 \
  --output /tmp/Narashima/payload.txt \
  --key YOUR_SECRET_KEY \
  --win-path C:\\Windows\\Tasks
```

- `--target`: Your raw PowerShell payload  
- `--output`: Where the final obfuscated payload should be written  
- `--key`: XOR key used for encryption/decryption  
- `--win-path`: Target path on Windows system for launcher/payload files  

---

## 🧠 Execution Flow

1. **cmd.ps1**  
   - Prompts the user for XOR decryption key  
   - Decrypts and base64-decodes `launcher.txt`

2. **launcher.ps1**  
   - Decodes the content of `launcher.txt`  
   - Executes it using `Invoke-Expression`

3. **payload.txt**  
   - Final payload: encrypted, base64-encoded, obfuscated  
   - Executed in-memory without touching disk

```
cmd.ps1 
   ↓
launcher.ps1 
   ↓
launcher.txt (base64 encoded script) 
   ↓
payload.txt (XOR + Base64 + obfuscation) 
   ↓
→ In-memory shell
```

---

## 🎯 Real-World Use

✔️ Tested against:

- Windows 10 / 11 with **Defender enabled**  
- EDR-monitored sandboxes  
- AMSI-enabled environments  

With proper payloads and staging, **zero detections** on upload scanners like VirusTotal.

---

## 🛡️ Evasion Stack

- ✅ AMSI bypass  
- ✅ Defender real-time protection evasion  
- ✅ PowerShell command obfuscation  
- ✅ Function and variable renaming  
- ✅ Memory-only execution  
- ✅ XOR + Base64 dual encoding  
- ✅ Multi-layer loader chain  

---

## ⚠️ Disclaimer

This tool is intended **solely for educational use** and **authorized red team assessments**.  
Any **unauthorized usage** against systems you do not own or have permission to test is **strictly forbidden** and may be illegal.

---

## 🙏 Credits

Built with ❤️ by offensive security researchers for the red teaming and infosec community.  
Inspired by **Narasimha**, the fierce and powerful protector in mythology — half-lion, half-man, full destruction.

---

## 📎 License

MIT License. See `LICENSE` file for full details.
