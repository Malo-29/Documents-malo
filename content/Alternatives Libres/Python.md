
# 🐍 Python — Automatisation & Scripts

> Python est mon langage de script de référence. Il est lisible, polyvalent, et dispose d'un écosystème immense. Je l'utilise pour automatiser des tâches répétitives, traiter des données, générer des fichiers et interagir avec des APIs.

## Installation

```bash
# macOS — via pyenv (recommandé, évite de toucher le Python système)
brew install pyenv
pyenv install 3.12.0
pyenv global 3.12.0

# Vérification
python --version  # Python 3.12.0
```

> ⚠️ Ne jamais modifier le Python système sur macOS (`/usr/bin/python3`). Utiliser pyenv ou Homebrew.

## Environnements virtuels

Chaque projet doit avoir son propre environnement pour isoler les dépendances.

```bash
python -m venv .venv
source .venv/bin/activate   # macOS/Linux
.venv\Scripts\activate      # Windows
deactivate

pip install nom-du-package
pip freeze > requirements.txt
pip install -r requirements.txt
```

## Bibliothèques utiles

```python
import os, sys, pathlib     # système de fichiers
import json, csv            # formats de données
import datetime             # dates et heures
import re                   # expressions régulières
```

```bash
pip install requests        # requêtes HTTP
pip install beautifulsoup4  # scraping web
pip install pandas          # tableaux de données
pip install pillow          # traitement d'images
pip install python-dotenv   # variables d'environnement
pip install rich            # affichage terminal coloré
```

## Scripts utiles

### Renommer des fichiers en masse
```python
from pathlib import Path

dossier = Path(".")
for fichier in dossier.glob("*.txt"):
    nouveau_nom = fichier.stem.lower().replace(" ", "_") + fichier.suffix
    fichier.rename(fichier.parent / nouveau_nom)
    print(f"Renommé : {fichier.name} → {nouveau_nom}")
```

### Générer des flashcards Anki depuis un CSV
```python
import csv

with open("cours.csv", "r", encoding="utf-8") as f:
    reader = csv.reader(f, delimiter=";")
    cartes = [(row[0], row[1]) for row in reader if len(row) >= 2]

with open("anki_export.txt", "w", encoding="utf-8") as f:
    for question, reponse in cartes:
        f.write(f"{question};{reponse}\n")

print(f"{len(cartes)} cartes générées.")
```

### Requête web simple
```python
import requests

response = requests.get("https://api.exemple.com/data")
if response.status_code == 200:
    data = response.json()
    print(data)
else:
    print(f"Erreur : {response.status_code}")
```

### Script de sauvegarde automatique
```python
import shutil
from pathlib import Path
from datetime import datetime

source = Path.home() / "Documents"
dest = Path("/Volumes/Backup") / f"backup_{datetime.now().strftime('%Y%m%d_%H%M')}"

shutil.copytree(source, dest)
print(f"Sauvegarde créée : {dest}")
```

## Automatisation macOS

```python
import subprocess

subprocess.run(["open", "-a", "IINA", "/chemin/vers/video.mkv"])

subprocess.run([
    "osascript", "-e",
    'display notification "Script terminé" with title "Python"'
])
```

## Bonnes pratiques

```python
#!/usr/bin/env python3
"""Description courte du script."""

import sys
from pathlib import Path

def main() -> None:
    if len(sys.argv) < 2:
        print("Usage: script.py <argument>")
        sys.exit(1)
    argument = sys.argv[1]
    # ... logique principale

if __name__ == "__main__":
    main()
```

## Ressources

- [docs.python.org](https://docs.python.org/fr/) — Documentation officielle en français
- [realpython.com](https://realpython.com) — Tutoriels pratiques
- [pypi.org](https://pypi.org) — Index de tous les packages pip

## Voir aussi

- [[LaTeX]] — Python peut générer du LaTeX automatiquement
- [[Anki - Vue d'ensemble]] — AnkiConnect permet de piloter Anki via Python
