---
title: Utiliser l’outil de personnalisation Office (OPO) dans Skype pour Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Résumé : Découvrez comment utiliser l’outil de personnalisation Office avec le Skype pour client d’entreprise.'
ms.openlocfilehash: 6050a9e9c36fa62aff16994469e63a9689ab5958
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530677"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Utiliser l’outil de personnalisation Office (OPO) dans Skype pour Business Server
 
**Résumé :** Comment utiliser l’outil de personnalisation Office avec le Skype pour client d’entreprise.
  
L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations. Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation. Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau. Lorsque vous installez Office, le programme d’installation cherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations. Le dossier mises à jour peut être utilisé que pour déployer des mises à jour logicielles lors d’une installation initiale d’Office.
  
L’OPO fait partie du programme d’installation et elle est utilisée uniquement pour les versions de licences en volume du produit. Vous exécutez l’OPO en tapant `setup.exe /admin` sur la ligne de commande à partir de la racine du point d’installation réseau qui contient le bureau des fichiers sources. Par exemple, utilisez la commande suivante :
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
Les administrateurs utilisent l’OPO pour créer un fichier .msp de personnalisation du programme d’installation et de personnaliser les zones suivantes :
  
- **Programme d’installation** Permet de spécifier l’emplacement d’installation par défaut sur le client par défaut et le nom de l’organisation, les sources d’installation réseau supplémentaires, clé de produit, contrat de licence utilisateur final, afficher des versions antérieures d’Office à supprimer, programmes personnalisés à exécuter au cours de niveau installation, les paramètres de sécurité et les propriétés d’installation.
    
- **Fonctionnalités** Utilisé pour configurer les paramètres utilisateur et de personnaliser le mode d’installation des fonctionnalités Office. Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs. Ces derniers peuvent modifier la plupart des paramètres après l’installation.
    
- **Contenu supplémentaire** Permet d’ajouter ou supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.
    
- **Outlook** Utilisé pour personnaliser le profil d’Outlook par défaut d’un utilisateur, spécifier les paramètres Exchange, ajouter des comptes, supprimer des comptes et exporter les paramètres et spécifier les groupes d’envoi/réception.
    
Pour plus d’informations sur l’outil, consultez la rubrique [utiliser l’OPO pour personnaliser Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Notez que ces informations s’applique également aux versions ultérieures d’Office.
  

