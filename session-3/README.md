# Session 3 — Practical: Decode it and map it

**Time:** 20 minutes · **Format:** pairs · **Tools:** CyberChef and MITRE ATT&CK Navigator (both free, in your browser)

## Why this matters
- **Case:** the Finance laptop ran a hidden PowerShell command and then sent many strange DNS queries. Today you reveal what they really did.
- **Theory:** encoded commands, DNS tunnelling and the MITRE ATT&CK framework.
- **Later SIEM lab:** decoding suspicious fields and tagging detections with ATT&CK IDs are everyday SIEM tasks.

## Files
- `session-3/strings.txt` (String A and String B)

## Tools
- CyberChef: https://gchq.github.io/CyberChef/
- ATT&CK Navigator: https://mitre-attack.github.io/attack-navigator/
- ATT&CK website: https://attack.mitre.org/

## Steps
1. Open CyberChef. Paste **String A** (only the long text after `-enc `) into the **Input** box.
2. Build a recipe that turns it into readable text. Hint: PowerShell encodes text as Base64 of UTF-16LE.
3. Paste **String B** (only the part before the first dot). Hint: it uses only the letters a–z and the digits 2–7.
4. Write down what each decoded string reveals.
5. Open ATT&CK Navigator → **Create New Layer** → **Enterprise**. Search for and highlight each technique you think the attacker used at Northwind so far (from Sessions 1–3).
6. Export the layer (**download layer as JSON**) and take a screenshot.
7. In the Log Explorer **Case notebook**, insert **Session 3 — Decode and map**, complete it and download your notebook.

## Deliverable
Updated notebook + exported Navigator layer (`.json`) + screenshot.

## If something does not work
- CyberChef online is down → use the offline CyberChef file provided by your instructor (open `CyberChef.html` in your browser).
- Navigator is down → write the technique IDs and names in your notebook using https://attack.mitre.org/ (or the instructor's PDF list).
