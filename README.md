# Printer Setup Guide (Linux)

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

---

## Step 3: Launch `system-config-printer`

---

## Step 4: Click "Add"

---

## Step 5: Refer to [this video](https://www.youtube.com/watch?v=jnmCbEWNV1w) if you need to setup internet *(watch whole video)*

---

## Step 5: Profit

> Go back to Step 1 if your printer is not immediately recognized.
