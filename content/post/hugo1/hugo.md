+++
title = 'Installation de Hugo'
date = 2023-12-13T10:28:49+01:00
draft = false
toc = true
image = 'img/hugologo.png'
+++

# Hugo

## Installation de brew

Installation de brew

Un pré requis à l’installation de homebrew est la présence d’un compilateur.

```bash
sudo apt install build-essential
```

Nous téléchargeons ensuite l’installateur

```bash
curl -fsSL -o install.sh https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh
```

Et nous l’executons

```bash
/bin/bash install.sh
```

Enfin, on indique à notre système le chemin vers le binaire

```bash
echo '# Set PATH, MANPATH, etc., for Homebrew.' >> /home/richard/.profile
```

```bash
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> /home/richard/.profile
```

```bash
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```


On se base sur la documentation en utilisant git :

```bash
git submodule add https://github.com/CaiJimmy/hugo-theme-stack/ themes/hugo-theme-stack
```

## Installation de Hugo

```bash
brew install hugo
```

On se place dans le dossier dans lequel nous voulons créer notre projet hugo et nous lancons la commande suivante:

```bash
hugo new site monblog -f yml
```
Il crée un dossier monblog, nous nous rendons dans celui-ci et on lance la commande :

```bash
git init
```
Cela va nous permettre de versionner notre site et surtout permettre le **deploiement** depuis notre machine locale vers internet grâce à github action

## Installation du thème Stack

On se réfère à la documentation (https://stack.jimmycai.com/guide/getting-started):

```bash
git submodule add https://github.com/CaiJimmy/hugo-theme-stack/ themes/hugo-theme-stack
```

## Les premiers pas avec Hugo.

### Configuration de Hugo

Maintenant que nous avons le minimal pour commencer, nous allons éditer le fichier de configuration de hugo, on édite le fichier hugo.toml à la racine et on l'enregistre comme suit:

```toml
baseURL = 'http://loclahost/'
languageCode = 'fr-fr'
title = 'Mon pense-bête'
theme = 'hugo-theme-stack'
contentDir = 'content'
```

Comme nous travaillons localement, nous mettons localhost, on met le site en français, on lui donne un titre, on spécifie le thème utilisé et enfin, on lui dit ou va se trouver le contenu du site, ici, ce sera dans le dossier content.

### Configuration de l'avatar.

Pour personnaliser son avatar, il va falloir le copier dans le dossier assets/img

### Lancement de Hugo

On lance Hugo avec la commande suivante:

```bash
hugo server
```

Il nous affiche un lien pour accéder à l'interface de notre site

```bash
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1) 
```

### Notre première page

Pour créer notre premier page, on lance cette commande depuis la racine du site

```bash
hugo new content/post/hugo.md
Content "/home/richard/Documents/sandbox/hugo/monblog/content/post/hugo.md" created
```

Cela va générer une page avec le contenu suivant:

```mardown
+++
title = 'Hugo'
date = 2023-12-13T10:56:36+01:00
draft = true
+++
```

Il suffit donc de changer le titre de la page dans title et de passer draft de true à false pour que la page apparaisse dans l'interface

On enrichit alors notre page avec du contenu en markdown


