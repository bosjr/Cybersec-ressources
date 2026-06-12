# Conversion fichiers .docx, .odt vers .md

## Avec Pandoc

[pandoc](https://pandoc.org/MANUAL.html)
[mpmendespt.dynu](https://mpmendespt.dynu.net/From-Markdown-to-.odt-and-vice-versa.html/)

Pour un fichier **DOCX** :

```bash
pandoc -f docx -t gfm --wrap=none -o sortie.md entree.docx
```

Pour un fichier **ODT** :

```bash
pandoc -s entree.odt -t gfm --wrap=none -o sortie.md
```

Pandoc peut aussi extraire les images lors de la conversion, ce qui est utile pour conserver un document plus complet en Markdown. 


```bash
pandoc -s entree.docx -t gfm --wrap=none --extract-media=images -o sortie.md
```

## Points à savoir

La conversion fonctionne bien pour le **texte, les titres, les listes, les tableaux simples et les liens**, mais elle peut être moins propre pour les mises en page complexes, les zones de texte, certaines notes, ou les tableaux très formatés. En pratique, il faut souvent faire une **petite relecture manuelle** après conversion pour corriger le Markdown généré.

## Cas du format .doc

Le vieux format **`.doc`** n’est pas toujours aussi pratique que `.docx`; il vaut souvent mieux le convertir d’abord en **`.docx`** avec LibreOffice ou Word, puis le convertir en Markdown avec Pandoc. C’est généralement plus fiable pour préserver la structure du document.

Oui, il existe des **extensions pour Visual Studio Code** qui permettent d’**importer et convertir DOCX et ODT en Markdown** directement dans l'éditeur.

## Extension qui supporte ODT et DOCX

### **Markdown Them** (recommandée si tu veux ODT + DOCX)

- Convertit directement dans VS Code :  **DOCX, PDF, HTML, XLSX, PPTX, ODT, ODP, ODS, RTF → Markdown**
- **Utilisation** :
  1. Dans l’Explorer, **clic droit** sur un ou plusieurs fichiers (DOCX, ODT, etc.).
  2. Choisir **Convert to Markdown**. 
  3. Les fichiers sont convertis **concurrentiellement** (batch processing).
- **Raccourci** pour le fichier actif :  `Ctrl+M Ctrl+D` (ou `Cmd+M Cmd+D` sur Mac) → aperçu Markdown ouvert à côté.

- **Limitation** : pour ODT, PPTX, etc., seul le **texte et les tableaux** sont extraits (les images sont ignorées pour garder le fichier léger et lisible).

## Extensions pour DOCX uniquement

### **Office to Markdown Converter**

- Convertit **DOCX, XLSX, PPTX → Markdown** avec **extraction automatique des images**.
- **Clic droit** dans l’Explorer → **Convert to Markdown**
- **Aucune dépendance** : pas besoin de Python, Pandoc, ni d’outils externes.
- Les images sont extraites dans un dossier `_images` et les liens sont mis à jour automatiquement.
- Supporte le **batch** (conversion multiple de fichiers DOCX, PPTX, XLSX).

### **DOCX to Markdown Converter** (focus-space)

- Convertit **DOCX → Markdown** avec extraction automatique des images.
- Préserve titres, paragraphes, listes, tableaux, gras, italique, liens.
- **Clic droit** → **DOCX: Convert to Markdown**

### **Docx2MD Converter** (shashiztech)

- Convertit **DOCX et DOC → Markdown** avec support avancé des tableaux, images, formatage.
- Utilise un backend Python intégré dans l'extension.

### **OneClick Markdown Converter** (luckyxmobile / hddevteam)

- Convertit **Word, Excel, PDF, PowerPoint → Markdown**.
- **Clic droit** dans l’Explorer ou via **palette de commandes** (`Ctrl+Shift+P`).
- Conversion en masse, pages/plages/sheets/slides spécifiques.

## Pour résumer

- **ODT + DOCX** dans VS Code : utilise **Markdown Them** : Convertit ODT, DOCX, PDF, XLSX, PPTX, ODP, ODS, RTF → Markdown.
- **DOCX** avec support correct des images :  **Office to Markdown Converter** ou **DOCX to Markdown Converter** sont plus complets pour les images.

Les installer directement depuis VS Code :  
`Ctrl+Shift+X` → chercher le nom de l'extension → **Install**.