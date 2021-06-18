---
title: Utiliser l’Outil de personnalisation Office (PERSONNALISATION) dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Résumé : Comment utiliser l’outil de personnalisation Office avec le client Skype Entreprise.'
ms.openlocfilehash: 32cd7951690ce5b1e38c20d83c8f53a9c48cd19c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100450"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Utiliser l’Outil de personnalisation Office (PERSONNALISATION) dans Skype Entreprise Server
 
**Résumé :** Utilisation de l’outil de personnalisation Office avec le client Skype Entreprise.
  
L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations. Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation. Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau. Quand vous installez Office, le programme d’installation recherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations. Le dossier Updates peut être utilisé uniquement pour déployer des mises à jour logicielles lors d’une installation initiale d’Office.
  
L' OCT fait partie de l’installation et est utilisé uniquement pour les versions avec licence en volume du produit. Vous exécutez l' OCT en tapant à la ligne de commande à partir de la racine du point d’installation réseau qui  `setup.exe /admin` contient les fichiers sources Office. Par exemple, utilisez la commande suivante :
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
Les administrateurs utilisent l’PERSONNALISATION pour créer un fichier .msp de personnalisation de l’installation et peuvent personnaliser les domaines suivants :
  
- **Installation** Permet de spécifier l’emplacement d’installation par défaut sur le client et le nom de l’organisation par défaut, des sources d’installation réseau supplémentaires, la clé de produit, le contrat de licence utilisateur final, le niveau d’affichage, les versions antérieures d’Office à supprimer, les programmes personnalisés à exécuter pendant l’installation, les paramètres de sécurité et les propriétés d’installation.
    
- **Fonctionnalités** Permet de configurer les paramètres utilisateur et de personnaliser l’installation des fonctionnalités Office. Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs. Ces derniers peuvent modifier la plupart des paramètres après l’installation.
    
- **Contenu supplémentaire** Permet d’ajouter ou de supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.
    
- **Outlook** Permet de personnaliser le profil Outlook par défaut d’un utilisateur, de spécifier les paramètres Exchange, d’ajouter des comptes, de supprimer des comptes et d’exporter des paramètres et de spécifier des groupes d’envoi/réception.
    
Pour plus d’informations sur l’PERSONNALISATION, voir Utiliser l' OCT [pour personnaliser Office 2013.](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)) Notez que ces informations s’appliquent également aux versions ultérieures d’Office.
