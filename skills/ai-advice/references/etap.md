# Reference: ETAP

> ETAP is licensed engineering software; confirm exact installer steps,
> licensing model, and system requirements against ETAP's official
> documentation/support portal for the specific version in use — these
> details are not safe to assume and vary by release and license type.

## 1. Purpose
ETAP is power system analysis and simulation software used for electrical
engineering studies (load flow, short circuit, protection coordination,
arc flash, etc.).

## 2. When to use it
- User is performing power system engineering studies and needs the
  software installed, licensed, or configured on a workstation or server.

## 3. When NOT to use it
- General-purpose scripting/automation tasks unrelated to power system
  studies — not relevant here.

## 4. Requirements (general, verify current specifics)
- A valid ETAP license (standalone dongle/HASP key, or network/floating
  license via a license server) — Claude should never ask the user to
  share license keys or credentials in chat.
- A Windows workstation/server meeting ETAP's published system
  requirements for the specific version (CPU, RAM, disk, .NET framework
  version, etc. — confirm current values, do not assume).
- Administrator rights on the install machine.

## 5. Setup overview (general shape — confirm exact steps per version)
1. Confirm the exact ETAP version and license type before starting
   (standalone vs. network license materially changes setup).
2. Install any prerequisite runtimes ETAP's installer requires (e.g.
   .NET, Visual C++ redistributables) — the installer usually flags
   missing prerequisites.
3. Run the ETAP installer as Administrator.
4. Configure licensing:
   - Standalone (dongle): connect the hardware key and install its
     driver.
   - Network license: point the client to the license server
     hostname/port provided by the license administrator.
5. Launch ETAP and confirm it opens without a licensing error.
6. Configure project-specific settings (standards, units, libraries) as
   needed for the study.

## 6. Key configuration concepts
- License server vs. standalone dongle fundamentally changes
  troubleshooting steps — always confirm which is in use first.
- Antivirus/firewall software can block license server communication on
  network licenses — a common cause of "cannot connect to license
  server" errors.
- Compatibility: some ETAP versions have specific OS/.NET version
  requirements; installing on an unsupported OS is a common failure
  source.

## 7. Validation
- ETAP launches without a license error.
- A simple test project can be created/opened and a basic calculation
  (e.g. a small load flow) runs successfully.
- For network licenses, the license server shows the client
  checked-out/connected.

## 8. Common errors
- License server connection failure: firewall blocking the license
  server port, wrong server address, or license server service not
  running — confirm which before changing firewall rules.
- Dongle not detected: driver not installed, USB port issue, or dongle
  needs reseating.
- Installer fails on prerequisite check: missing .NET/redistributable —
  install the flagged prerequisite first, don't force through it.

## 9. Troubleshooting
- Identify license type first (standalone vs. network) since the fix
  paths diverge completely from there.
- Check the specific error message/code ETAP shows — these are usually
  specific enough to search in ETAP's official knowledge base.
- Avoid reinstalling ETAP as a first step; confirm whether the issue is
  licensing, OS compatibility, or application-level before that.

## 10. Security considerations
- Never ask the user to paste license keys, activation codes, or license
  server credentials in chat.
- Network license servers should only be reachable from machines that
  need them — not exposed broadly on the network.

## 11. Cost considerations
- ETAP licensing is commercial and typically substantial — cost
  questions (license tiers, renewal, per-seat vs. network) should be
  directed to ETAP's sales/support channels since pricing isn't public
  or stable enough to state confidently here.

## 12. Maintenance
- Keep ETAP updated per the vendor's patch releases, especially for bug
  fixes relevant to the standards/libraries used in current studies.

## 13. Upgrade / scaling considerations
- Moving from standalone to network licensing (or vice versa) is a
  licensing-administration change, not just a technical one — confirm
  with whoever manages the ETAP license agreement before making changes.
