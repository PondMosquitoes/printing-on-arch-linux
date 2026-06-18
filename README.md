# Printer Setup Guide (Linux)

`sudo pacman -Syu && yay -Syu`

---

## Step 0: Install CUPS & Driver for Printer

> If on Arch, it **IS ON THE AUR**; if not refer to [this video](https://www.youtube.com/watch?v=v-7yWtBRYLM) — your issue is super specific in this case.

- **Is it on the AUR?** *(95% chance yes)* — Look harder, it may not explicitly say THIS DRIVER WORKS FOR X PRINTER. SOME PRINTERS SHARE A COMMON CHIP W/ OTHERS, etc. etc.
- **Is it available on Linux at all?**
- If either of those fail → [https://www.youtube.com/watch?v=v-7yWtBRYLM](https://www.youtube.com/watch?v=v-7yWtBRYLM)

---

## Step 1: Add User to `lp` Group in Root

```bash
sudo (insert terminal emulator you use here) >> usermod -aG lp username
```

---

## Step 2: Install `system-config-printer`

refer to [this](https://www.youtube.com/watch?v=jnmCbEWNV1w)

---

## Step 3: Launch `system-config-printer`

---

## Step 4: Click "Add"

---

## Step 5: Refer to [this video](https://www.youtube.com/watch?v=jnmCbEWNV1w) if you need to setup internet *(watch whole video)*

- I am not being clever, I don't use internet on printers. But that video also explains system-config-printer and related dependencies.
- You can launch system-config-printer by running it in a terminal emulator.

---

## Step 5: Profit

> Go back to Step 0 if your printer is not immediately recognized.
> If you get back here again, then you really do need to watch [this video](https://www.youtube.com/watch?v=v-7yWtBRYLM)
> (these 2 videos are pretty much the authoritative doctrine on the matter, as far as I am concerned.)

## Step 6: scanner software

α) Use specific scanning software (*HINT: It's on the AUR*)

- ex: I have an EcoTank-4850 --> `epsonscan2`
- It helps to search for specific keywords on yay, then paste the output to some LLM and tell it to find what you need.
- Much like w/ the drivers, the scanning software may not explicitly say what it is for.

β) if "α)" fails, or you can't be bothered: then use xsane, its a graphical frontend for sane and works for scanning on all printers, assuming the driver recognizes the printer.

### XSANE

- .org (currently offline, for some reason: redirects to --> https://wiki.ubuntuusers.de/XSane/)
- I have not PGP verified anything on this website ^
- Look here if you don't trust this ^ : http://www.sane-project.org/sane-frontends.html
- This is also where i found my specific scanning software curated for epson products

---

## TABLE WIP

| Make | Model | SKU | Driver | Scan Utility |
| ---- | ----- | --- | ------ | ------------ |
| Epson | EcoTank | 4850 | `epson-inkjet-printer-escpr2` | `epsonscan2` |
| Brother | MFC-L8900CDW | L8905CDW | `brother-mfc-l8900cdw` | `brscan5` |

---

## This is actually useful to read IF EVERYTHING FAILS:

*From Claude Sonnet 4.6*

If your driver covers **Make → Model** but not your specific **SKU**, that is not a dead end.

The SKU difference is almost always a regional variant, a hardware revision, or a bundle difference — same internals, same chip, same protocol. The driver works; it just won't list your exact SKU by name.

**Contingency:** In system-config-printer, manually select **Make + Model** from the list and ignore that your SKU isn't listed. If that fails, `xsane` will usually detect it anyway — SANE probes by connection/protocol, not model string.

> ⚠️ **Edge case:** If the SKU difference is a real hardware difference (e.g. one SKU has a flatbed scanner, another doesn't), the driver may work for printing but the scanner half silently fails or partially works. That's when the specific scan utility (Step 6α) matters — `epsonscan2` for example probes actual hardware capabilities rather than trusting the model string.


> !note
> - I highly doubt the silently fails portion, that sounds like an LLM lie to me /:

For the table: the **SKU column is for user reference only** — Driver and Scan Utility are almost always identical across SKUs within the same model line.
In the event tehy are not: You really do need to follow [this detailed video](https://www.youtube.com/watch?v=v-7yWtBRYLM) step by step
