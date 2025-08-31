# 🧮 Omega Pi Stream - NumWorks Calculator Custom App

[![Build Omega Pi Stream](https://github.com/cabrera/Omega-Pi-Stream/actions/workflows/build-omega.yml/badge.svg)](https://github.com/cabrera/Omega-Pi-Stream/actions/workflows/build-omega.yml)

## 🚀 **Pi Stream Display App for NumWorks**

Une application native pour calculatrice NumWorks qui affiche en temps réel les données LaTeX envoyées via UART depuis un Raspberry Pi.

### ✨ **Fonctionnalités**

- 📡 **Réception UART temps réel** depuis Raspberry Pi
- 📐 **Rendu LaTeX mathématique** : `$$E=mc^2$$` → rendu visuel
- 📜 **Interface scrollable** pour affichage continu
- 🎨 **Icône intégrée** dans tous les thèmes Omega
- ⚡ **Performance optimisée** pour NumWorks

### 🔧 **Architecture**

```
pi_stream_app/
├── pi_stream_app.h/.cpp      # App principale (MVC)
├── pi_stream_controller.h/.cpp # Contrôleur UART + LaTeX
├── pi_stream_base.en.i18n     # Internationalisation
└── pi_stream_icon.png         # Icône 16x16
```

### 🛠 **APIs Utilisées**

- `Ion::Console` - Communication UART
- `Escher::ExpressionView` - Rendu LaTeX
- `Poincare::Expression` - Parsing mathématique
- `Ion::Timing` - Gestion temporelle

### 📱 **Installation WebDFU**

1. **Télécharger le binpack** depuis [Releases](../../releases) ou [Actions](../../actions)
2. **Mode DFU** : RESET + 6 + USB sur NumWorks
3. **WebDFU** : https://ti-planet.github.io/webdfu_numworks/n0110/
4. **Flash** le binpack.bin

### 🔌 **Connexion Raspberry Pi**

```python
# Sur Raspberry Pi
import serial
ser = serial.Serial('/dev/ttyUSB0', 115200)
ser.write(b'$$\\int_0^\\infty e^{-x^2} dx = \\frac{\\sqrt{\\pi}}{2}$$\n')
```

### 🏗 **Build Local**

```bash
git clone https://github.com/cabrera/Omega-Pi-Stream.git
cd Omega-Pi-Stream
git submodule update --init --recursive
make OMEGA_USERNAME="PiStream" binpack -j$(nproc)
```

**Binpack généré** : `output/device/n0110/release/binpack.bin`

### 📊 **Demo**

```
NumWorks → Pi Stream App
  ↓
📡 UART ← Raspberry Pi
  ↓
📐 LaTeX: $$\sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^2}{6}$$
  ↓
🖥 Affichage mathématique sur calculatrice
```

### 🎯 **Cas d'Usage**

- **📚 Cours de maths** : Affichage formules en temps réel
- **🔬 Lab scientifique** : Visualisation données IoT
- **🤖 Robotique** : Interface calculatrice-robot
- **📡 IoT** : Dashboard portable sans écran

---

**Créé avec ❤️ pour NumWorks & Omega**
