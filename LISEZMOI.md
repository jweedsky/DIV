# ESP32-DIV jweedsky — MAJ auto Wi-Fi (dépôt github.com/jweedsky/DIV)

## 3 fichiers
- **ESP32-DIV-jweedsky-WIFI-OTA.bin** → firmware complet, à flasher UNE fois au câble.
- **firmware.bin** → version « app seule », à déposer dans ton dépôt GitHub.
- **version.txt** → contient `20261025`, à déposer aussi dans le dépôt.

## Étape 1 — Flasher une fois (au câble)
1. https://espressif.github.io/esptool-js/ → Connect
2. Erase Flash
3. Add File → `ESP32-DIV-jweedsky-WIFI-OTA.bin` → offset 0x0 → Program

## Étape 2 — Déposer 2 fichiers sur GitHub (une fois)
Dans github.com/jweedsky/DIV (branche main), à la racine :
- `firmware.bin`  (fourni)
- `version.txt`   (contient 20261025)
Bouton « Add file » → « Upload files ».

## Étape 3 — Premier allumage
- L'écran demande ton Wi-Fi maison (nom + mot de passe) au clavier tactile. Une seule fois.
- Ensuite il vérifie le dépôt : comme version.txt = la version déjà installée, il ne fait rien et démarre.

## Plus tard : publier une MAJ (100 % autonome)
1. Je te redonne un nouveau `firmware.bin` + un nombre plus grand pour `version.txt`.
2. Tu remplaces les 2 fichiers dans le dépôt.
3. Au prochain allumage, le boîtier voit le nombre plus grand, télécharge, se met à jour, redémarre. Rien d'autre.

## Notes
- SD toujours ralentie à 1 MHz (plus fiable sur bus partagé).
- Wi-Fi coupé après la vérif (pas de conso en continu).
- Garde-fous : image validée avant bascule ; si version.txt n'augmente pas, rien ne se passe.
- URL utilisée : https://raw.githubusercontent.com/jweedsky/DIV/main/firmware.bin
