# Voira for Linux

> 🎙️ **Mluv a piš všude.** První čistě česká voice-to-text aplikace pro Linux (a Windows, Mac). Drž klávesu, mluv, pusť — text se vloží do aktivního okna kdekoliv.

[![Latest Release](https://img.shields.io/github/v/release/hustlerv369/voira-linux?style=flat-square&color=E11D2A)](https://github.com/hustlerv369/voira-linux/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/hustlerv369/voira-linux/total?style=flat-square&color=E11D2A)](https://github.com/hustlerv369/voira-linux/releases)
[![License](https://img.shields.io/badge/license-Proprietary-blue.svg?style=flat-square)](LICENSE)
[![Website](https://img.shields.io/badge/web-voiravoice.cz-E11D2A?style=flat-square)](https://voiravoice.cz)

---

## ⚡ Quick install

### AppImage (universal — Ubuntu, Mint, Fedora, Arch, openSUSE, všechno)

```bash
curl -LO https://github.com/hustlerv369/voira-linux/releases/latest/download/Voira-linux.AppImage
chmod +x Voira-linux.AppImage
./Voira-linux.AppImage
```

### Debian / Ubuntu / Mint / Pop!OS

```bash
curl -LO https://github.com/hustlerv369/voira-linux/releases/latest/download/Voira-linux.deb
sudo apt install ./Voira-linux.deb
```

### Fedora / openSUSE / RHEL / Rocky / CentOS

```bash
curl -LO https://github.com/hustlerv369/voira-linux/releases/latest/download/Voira-linux.rpm
sudo dnf install ./Voira-linux.rpm
```

### Arch Linux / CachyOS / Manjaro / EndeavourOS (AUR — brzy)

```bash
yay -S voira-bin
# nebo paru -S voira-bin / pikaur -S voira-bin
```

> AUR PKGBUILD je hotový v `packaging/arch/` — push na aur.archlinux.org plánovaný v příštím release.

---

## ✨ Co Voira umí

- 🎙️ **Push-to-talk hotkey** — drž libovolnou klávesu (F8, Ctrl+Win, CapsLock), mluv, pusť → text vložen
- 🇨🇿 **Perfektní čeština** (i diakritika, interpunkce, koncovky)
- 🌍 **Překlad za běhu** — mluv česky, vyjede angličtina (a naopak)
- 🎯 **Hlasové formátování & sebeoprava** — řekni „nový odstavec", „čárka"; pokračuj „ne, vlastně…" → opraví se
- 📚 **Vlastní slovník** — učí se z tvých oprav (zájmena, jména, technické termíny)
- 🔄 **Toggle mód** — alternativní k push-to-talk: klik start, klik stop
- 🔒 **Soukromě** — slovník + opravy + historie zůstávají lokálně, audio jde přímo k ASR (Groq Whisper)
- 🌐 **7 jazyků UI** (CS / SK / EN / DE / PL / ES / HU)
- 🚀 **Auto-update** — Tauri 2 updater s Ed25519 podpisem verifikace

---

## 🐧 Linux support matrix

| Distro | AppImage | .deb | .rpm | AUR | Status |
|---|:---:|:---:|:---:|:---:|---|
| **Ubuntu 22.04+** | ✅ | ✅ | — | — | Fully tested |
| **Linux Mint 21+** | ✅ | ✅ | — | — | Fully tested |
| **Debian 12+** | ✅ | ✅ | — | — | Fully tested |
| **Pop!OS** | ✅ | ✅ | — | — | Fully tested |
| **Elementary OS** | ✅ | ✅ | — | — | Works |
| **Fedora 39+** | ✅ | — | ✅ | — | Works |
| **openSUSE** | ✅ | — | ✅ | — | Works |
| **Arch Linux** | ✅ | — | — | 🟡 brzy | Works (AppImage) |
| **CachyOS** | ✅ | — | — | 🟡 brzy | Works (AppImage) |
| **Manjaro** | ✅ | — | — | 🟡 brzy | Works (AppImage) |
| **EndeavourOS** | ✅ | — | — | 🟡 brzy | Works (AppImage) |
| **Garuda** | ✅ | — | — | 🟡 brzy | Works (AppImage) |

### Display server compatibility

| Session | Push-to-talk | Text injection | Status |
|---|---|---|---|
| **X11** | ✅ rdev | ✅ enigo | Plně podporováno |
| **Wayland** | ⚠️ omezený | ⚠️ vyžaduje `ydotool` | Beta — xdg-desktop-portal v plánu |

> **Pro nejlepší zážitek na Waylandu** — nainstaluj `ydotool` daemon nebo přepni session na X11 v login manažeru.

---

## 🚀 Quick start

1. **Stáhni a spusť** podle své distribuce (viz výše)
2. **Otevři Voiru** — ikona v tray (system notifications area)
3. **Klik tray ikonu → Otevřít** — otevře hlavní okno
4. **Přihlaš se** (e-mail magic-link nebo Google) — povinné pro diktování
5. **Stáhni dependencies** pro tvoji distra:
   ```bash
   # Ubuntu/Debian
   sudo apt install libwebkit2gtk-4.1-0 libayatana-appindicator3-1
   # Fedora
   sudo dnf install webkit2gtk4.1 libayatana-appindicator-gtk3
   # Arch
   sudo pacman -S webkit2gtk-4.1 libayatana-appindicator
   ```
6. **Nastav hotkey** v Settings → Obecné (default F8)
7. **Drž hotkey + mluv** → text se objeví v aktivním okně

### Setup permissions (pokud rdev hlásí permission denied)

```bash
sudo usermod -a -G input $USER
# Odhlas se a znovu přihlas (relogin)
```

---

## 💎 Funkce

### Free (bez omezení)
- 1000 slov / 30 dní (rolling) + bonusy za pozvánky
- Vlastní slovník — učí se z oprav
- Hlasové formátování, sebeoprava, překlad za běhu
- Toggle mód, vlastní hotkey, 7 jazyků
- Jeden globální tón (verbatim / casual / formal)

### Pro — 7,99 € / měs nebo 86 € / rok
- Neomezené diktování (fair use)
- Offline mód — lokální Whisper, audio nikdy neopustí PC
- Command Mode — uprav označený text hlasem
- Hlasové zkratky + styl psaní per kontext
- 20 % affiliate provize z každé Pro platby

Předplatné: https://voiravoice.cz/account

---

## 🛠️ Troubleshooting

### Hotkey nereaguje
```bash
# rdev vyžaduje read access na /dev/input/*
sudo usermod -a -G input $USER
# relogin

# Nebo na Waylandu:
sudo pacman -S ydotool  # Arch
sudo apt install ydotool  # Debian/Ubuntu
sudo systemctl enable --now ydotoold
```

### Text se nevkládá
```bash
# Wayland: vyžaduje ydotool (viz výše) nebo X11 session
# X11: zkontroluj že enigo funguje
xdotool key ctrl+v  # test toho jestli xdotool funguje
```

### "Failed to start tray" — chybí appindicator
```bash
sudo apt install libayatana-appindicator3-1   # Debian/Ubuntu
sudo dnf install libayatana-appindicator-gtk3 # Fedora
sudo pacman -S libayatana-appindicator        # Arch
```

### AppImage neběží
```bash
chmod +x Voira-linux.AppImage
# Pokud "Permission denied":
./Voira-linux.AppImage --appimage-extract-and-run
# Pokud chybí FUSE:
sudo apt install fuse libfuse2
```

---

## 🤝 Přispívání

Voira je proprietary software, ale Linux packaging je open. Pull requests jsou vítané pro:

- 📦 Distro-specific instalační skripty
- 🐛 Bug reporty pro Linux-specific problémy
- 🌍 Překlady (najdeš keys v issue tracker)
- 📚 Dokumentaci
- 🎨 Návrhy designu

**Source code samotné aplikace** je v privátním repo. Tato distribuce obsahuje **jen Linux packaging + binary releases**.

### Issue templates
- 🐛 Bug report
- ✨ Feature request
- 🌐 Translation contribution
- 📦 Packaging improvement (AUR, Flatpak, Snap…)

---

## 🔒 Security

Voira používá **Ed25519 signature verification** pro auto-update artifakty (Tauri 2 updater plugin).

**Public key:** `D78A048851C04C68`

Před instalací můžeš ověřit signaturu:

```bash
# Stáhni signature
curl -LO https://github.com/hustlerv369/voira-linux/releases/latest/download/Voira-linux.AppImage.sig

# Ověř (vyžaduje minisign / tauri-signer)
minisign -Vm Voira-linux.AppImage -P RWRoTMBRiASK1+8qfemHn4enR2LtrzNaKh/fooQJwqi+qKN3ympt
```

Pokud něco najdeš (security issue, lék, exploit) → e-mail **security@voiravoice.cz** (zatím vojtech.horava@gmail.com).

Viz [SECURITY.md](SECURITY.md) pro full responsible disclosure policy.

---

## 📦 Build from source (developers)

> Source code samotné aplikace je v privátním repo. Tento repo obsahuje **packaging only**.

Pokud chceš Voiru přizpůsobit a buildit lokálně:

1. **Kontakt:** vojtech.horava@gmail.com nebo issue request → můžu poskytnout source access pro vážné contributory
2. **Tech stack:** Tauri 2 + Rust + TypeScript + Compose
3. **Dependencies (Ubuntu):**
   ```bash
   sudo apt install libwebkit2gtk-4.1-dev build-essential curl wget file \
     libxdo-dev libssl-dev libayatana-appindicator3-dev librsvg2-dev \
     libasound2-dev libudev-dev libx11-dev libxtst-dev libxi-dev libxrandr-dev
   ```
4. **Build:**
   ```bash
   cd voira-app/src-tauri
   cargo tauri build --bundles appimage,deb,rpm
   ```

---

## 🌐 Links

- 🏠 **Web:** https://voiravoice.cz
- 💸 **Affiliate program** (20 % provize): https://voira.lemonsqueezy.com/affiliates
- 🐦 **Twitter/X:** @voiravoice
- 📧 **Support:** vojtech.horava@gmail.com
- 📝 **Privacy policy:** https://voiravoice.cz (footer)

---

## 📜 License

Voira binárky jsou **proprietary** — viz [LICENSE](LICENSE).

Packaging files (PKGBUILD, .deb config, GitHub Actions workflows, this README) jsou pod **MIT** — viz [LICENSE-PACKAGING](LICENSE-PACKAGING).

---

## 🎯 Roadmap

- [x] AppImage release
- [x] .deb release (Debian family)
- [x] .rpm release (RedHat family)
- [x] Auto-update (Tauri updater + Ed25519)
- [ ] AUR PKGBUILD push (this month)
- [ ] Flatpak (Flathub) — Q3 2026
- [ ] Snap (snapcraft.io) — Q3 2026
- [ ] xdg-desktop-portal native Wayland support
- [ ] ARM64 builds (Raspberry Pi, ARM laptops)
- [ ] Android (Custom IME) — see [`ANDROID-ROADMAP`](https://github.com/hustlerv369/voira-linux/issues/1)

---

**Made with ❤️ in Prague.** Voiruj sebe, ne svoje data.
