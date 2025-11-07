# ✈️ FlightGear Portable Build (Codespaces Edition)

Ce dépôt contient une version compilée de FlightGear, prête à être lancée sans recompilation.  
Inclut les binaires, les librairies SimGear, et les données fgdata.

## 📁 Structure du projet

flightgear/ 
├── build/ # Contient le binaire fgfs 
├── CMakeModules/ # Modules CMake 
├── src/ # Code source FlightGear 
simgear-install/ # Librairies SimGear compilées 
fgdata/ # Données du simulateur (avions, scènes, météo)

Code

## 🚀 Lancement du simulateur

```bash
cd flightgear/build
./fgfs --fg-root=../fgdata --aircraft=ufo --airport=LFQQ --enable-fullscreen --httpd=5500
🛠️ Compilation manuelle (optionnel)
SimGear
bash
mkdir simgear/build
cd simgear/build
cmake .. -DCMAKE_INSTALL_PREFIX=$HOME/simgear-install -DCMAKE_BUILD_TYPE=Release
make -j$(nproc)
make install
FlightGear
bash
mkdir flightgear/build
cd flightgear/build
cmake .. -DCMAKE_PREFIX_PATH="$HOME/simgear-install;$HOME/osg-fg-install" -DCMAKE_BUILD_TYPE=Release
make -j$(nproc)
✅ Vérifications avant lancement
bash
ls flightgear/build/fgfs
ls simgear-install/lib/libSimGearCore.a
ls fgdata/Aircraft/ufo
📦 Packaging
bash
zip -r flightgear_package.zip flightgear/build simgear-install fgdata
🧠 Auteur
Build et documentation par Dimitri aka Oscar-Quiloulou Optimisé pour Codespaces, WSL et Linux portables.
