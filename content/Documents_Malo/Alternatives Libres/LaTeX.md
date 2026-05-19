---
tags: [redaction, latex, productivite, maths, sciences]
created: 2026-05-19
---

# 📐 LaTeX — Rédaction typographique

> LaTeX est un système de composition de documents. Ce n'est pas un traitement de texte (comme Word) : on écrit du code qui est compilé en PDF. C'est la référence pour les mathématiques, la physique, les publications scientifiques et les devoirs de classe prépa.

## Pourquoi LaTeX ?

| Critère | Word | LaTeX |
|---|---|---|
| Formules mathématiques | Médiocre | ✅ Parfait |
| Mise en page automatique | Non | ✅ Oui |
| Numérotation automatique | Partielle | ✅ Complète |
| Rendu typographique | Correct | ✅ Professionnel |
| Courbe d'apprentissage | Faible | ⚠️ Élevée au début |
| Versionnable (Git) | Non | ✅ Oui |
| Gratuit | Non (Microsoft 365) | ✅ |

## Installation

### Distribution LaTeX

**macOS :** MacTeX (distribution complète, ~4 Go)
```bash
brew install --cask mactex
# ou version allégée :
brew install --cask basictex
```

**Linux :**
```bash
sudo apt install texlive-full    # complet
sudo apt install texlive-latex-extra texlive-fonts-recommended  # minimal+
```

### Éditeur

- **TeXShop** (macOS, inclus dans MacTeX) — simple, efficace
- **TeXstudio** — multiplateforme, autocomplétion puissante
- **VS Code + LaTeX Workshop** — mon choix pour la flexibilité
- **Overleaf** — en ligne, collaboratif, sans installation

## Structure d'un document

```latex
\documentclass[12pt,a4paper]{article}

% Packages
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[french]{babel}
\usepackage{amsmath, amssymb, amsthm}
\usepackage{geometry}
\geometry{margin=2.5cm}

\title{Mon Devoir}
\author{Malo Saout}
\date{\today}

\begin{document}

\maketitle

\section{Introduction}

Voici une équation : $E = mc^2$.

Et une équation centrée :
\[
  \int_0^1 x^2 \, dx = \frac{1}{3}
\]

\end{document}
```

## Mathématiques — Les essentiels

### Mode math

```latex
% Inline (dans le texte)
$f(x) = x^2 + 1$

% Display (centré, sur sa ligne)
\[ f(x) = x^2 + 1 \]

% Environnement align (avec numérotation)
\begin{align}
  f(x) &= x^2 + 1 \\
  f'(x) &= 2x
\end{align}
```

### Symboles fréquents

```latex
% Fractions
\frac{a}{b}          % fraction
\dfrac{a}{b}         % fraction grande (display)

% Exposants et indices
x^{2}     x_{n}     x^{n+1}_{k}

% Racines
\sqrt{x}    \sqrt[3]{x}

% Sommes, intégrales, limites
\sum_{k=0}^{n} k     \int_0^1 f(x)\,dx     \lim_{x \to 0}

% Lettres grecques
\alpha \beta \gamma \delta \epsilon \lambda \mu \pi \sigma \omega
\Gamma \Delta \Sigma \Omega

% Opérateurs
\cdot   \times   \div   \pm
\leq    \geq     \neq   \approx   \equiv

% Ensembles
\mathbb{R}   \mathbb{N}   \mathbb{Z}   \mathbb{C}
\in   \notin   \subset   \subseteq   \cap   \cup   \emptyset

% Flèches
\to   \rightarrow   \Rightarrow   \iff   \Leftrightarrow

% Vecteurs
\vec{u}   \overrightarrow{AB}
```

### Environnements mathématiques utiles

```latex
% Théorème (avec le package amsthm)
\newtheorem{thm}{Théorème}
\begin{thm}
  Pour tout $n \in \mathbb{N}$...
\end{thm}

% Matrice
\begin{pmatrix}
  a & b \\
  c & d
\end{pmatrix}

% Système d'équations
\begin{cases}
  x + y = 1 \\
  2x - y = 0
\end{cases}
```

## Packages indispensables

```latex
\usepackage{amsmath}        % mathématiques avancées
\usepackage{amssymb}        % symboles mathématiques
\usepackage{amsthm}         % environnements théorèmes
\usepackage{geometry}       % marges personnalisées
\usepackage[french]{babel}  % typographie française
\usepackage{graphicx}       % images
\usepackage{hyperref}       % liens cliquables dans le PDF
\usepackage{enumerate}      % listes personnalisées
\usepackage{array}          % tableaux avancés
\usepackage{xcolor}         % couleurs
\usepackage{listings}       % code source
\usepackage{tikz}           % graphiques vectoriels
```

## Template DM prépa

```latex
\documentclass[12pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[french]{babel}
\usepackage{amsmath,amssymb,amsthm}
\usepackage{geometry}
\geometry{top=2cm, bottom=2cm, left=2.5cm, right=2.5cm}
\usepackage{fancyhdr}
\pagestyle{fancy}
\fancyhead[L]{Malo Saout — ECG2}
\fancyhead[R]{\today}

\begin{document}

\begin{center}
  {\Large \textbf{DM n°X — Mathématiques}}
\end{center}

\section*{Exercice 1}

...

\end{document}
```

## Compiler

```bash
# Compilation simple
pdflatex mon_document.tex

# Avec bibliographie (si \cite{})
pdflatex document.tex
bibtex document
pdflatex document.tex
pdflatex document.tex

# latexmk (automatise tout)
latexmk -pdf document.tex
latexmk -pvc document.tex  # mode watch (recompile à chaque sauvegarde)
```

## Voir aussi

- [[Python]] — pour automatiser la génération de documents LaTeX
- [[LibreOffice]] — pour les documents simples sans mathématiques
