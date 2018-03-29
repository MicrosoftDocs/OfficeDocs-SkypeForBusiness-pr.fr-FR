---
title: Utilisation de l’outil de personnalisation Office dans Skype Entreprise Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Résumé : Comment faire pour utiliser l’outil de personnalisation Office avec le Skype pour client d’entreprise.'
ms.openlocfilehash: b0e8dd399af7a75a6f575d554cbe6c25c4e8ffd3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server-2015"></a>Utilisation de l’outil de personnalisation Office dans Skype Entreprise Server 2015
 
**Résumé :** Comment utiliser l’outil de personnalisation Office avec le Skype pour client d’entreprise.
  
L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations. Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation. Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau. Lorsque vous installez Office, le programme d’installation cherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations. Le dossier mises à jour peut être utilisé que pour déployer des mises à jour logicielles lors d’une installation initiale de Microsoft Office.
  
Les PTOM fait partie de l’installation et il est utilisé uniquement pour les versions de licences en volume du produit. Vous exécutez l’OPO en tapant `setup.exe /admin` sur la ligne de commande à partir de la racine du point d’installation réseau qui contient Office des fichiers source. Par exemple, utilisez la commande suivante :
  
 `\\server\share\Office15\setup.exe /admin`
  
Les administrateurs utilisent l’OPO pour créer un fichier .msp de personnalisation d’installation et de personnaliser les zones suivantes :
  
- **Programme d’installation** Utilisé pour spécifier l’emplacement d’installation par défaut sur le client par défaut et le nom de l’organisation sources d’installation de réseau supplémentaires, clé de produit, contrat de licence utilisateur final, afficher au niveau des versions antérieures d’Office à supprimer, à des programmes personnalisés à exécuter lors de installation, les paramètres de sécurité et les propriétés de l’installation.
    
- **Fonctionnalités** Utilisé pour configurer les paramètres de l’utilisateur et pour personnaliser la façon dont les fonctionnalités d’Office sont installées. Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs. Ces derniers peuvent modifier la plupart des paramètres après l’installation.
    
- **Contenu supplémentaire** Utilisé pour ajouter ou supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.
    
- **Outlook** Utilisé pour personnaliser le profil Outlook de l’utilisateur par défaut, spécifier des paramètres Exchange, ajouter des comptes, supprimer des comptes et exporter les paramètres et spécifier des groupes d’envoi/réception.
    
Pour plus d’informations sur l’OPO, consultez [utiliser l’OPO pour personnaliser Office 2013](https://technet.microsoft.com/library/cc179132.aspx). Notez que ces informations s’appliquent également à Office 2016.
  

