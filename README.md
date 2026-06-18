
Step 0: install cups & driver for printer (if on arch it IS ON THE AUR; if not refer to https://www.youtube.com/watch?v=v-7yWtBRYLM, your issue is super specific in this case.)
- Is it on the AUR (95% | Look harder, it may not explicitly say THIS DRIVER WORKS FOR X PRINTER, SOME PRINTERS SHARE A COMMON CHIP W/ OTHERS, etc. etc.)
- Is it available on linux at all?
- If that fails of those fail https://www.youtube.com/watch?v=v-7yWtBRYLM
Step 1: add user to lp group in root  [sudo (insert terminal emulator you use here) >> usermod -aG lp username
Step 2: install  system-config-printer
Step 3: launch system-config-printer
Step 4: click "Add"
Step 5: Refer to https://www.youtube.com/watch?v=jnmCbEWNV1w if you need to setup internet (watch whole video)
Step 5: Profit ( Go back to step 1 if your printer is not immedately recognized)
