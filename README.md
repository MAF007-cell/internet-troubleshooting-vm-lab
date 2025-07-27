# Internet Troubleshooting in a Windows 10 VM (Help Desk Simulation)

## 🧠 Scenario
Simulated a real-world help desk scenario where a user reports they have no internet connection inside a Windows 10 virtual machine.

## 🛠️ Tools Used
- Windows 10 (VirtualBox VM)
- Command Prompt
- `ping`, `ipconfig`, `flushdns`, and adapter troubleshooting
- VirtualBox (NAT and Internal Network adapter settings)

## ⚙️ Problem
User VM could not access the internet:
- `ping google.com` failed (DNS issue)
- `ping 8.8.8.8` failed (no external connection)
- `ipconfig` showed no usable IP (or 169.x.x.x self-assigned address)

## 🔍 Troubleshooting Steps
1. Checked IP address with `ipconfig`
2. Noted failed DNS resolution and packet loss
3. Switched VM network mode from **Internal Network** to **NAT**
4. Restarted VM
5. Ran `ipconfig /release` and `ipconfig /renew`
6. Flushed DNS with `ipconfig /flushdns`
7. Re-tested with `ping google.com` and confirmed success

## ✅ Outcome
Successfully restored internet connection to the VM using NAT mode in VirtualBox.  
Confirmed DNS and connectivity with:

```bash
ping google.com
