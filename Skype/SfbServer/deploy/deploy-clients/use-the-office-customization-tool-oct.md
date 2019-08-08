---
title: Utiliser l’outil de personnalisation Office (OPO) dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Résumé: comment utiliser l’outil de personnalisation Office avec le client Skype entreprise.'
ms.openlocfilehash: e7eb331c1b63a9e6a94ae3920e65ef57f426fbb0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234599"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>Utiliser l’outil de personnalisation Office (OPO) dans Skype entreprise Server
 
**Résumé:** Comment utiliser l’outil de personnalisation Office avec le client Skype entreprise.
  
L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations. Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation. Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau. Lorsque vous installez Office, le programme d’installation cherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations. Le dossier mises à jour peut être utilisé uniquement pour déployer des mises à jour logicielles lors d’une installation initiale d’Office.
  
Le PTOM fait partie du programme d’installation et est uniquement utilisé pour les versions sous licence en volume du produit. Vous exécutez l’outil OCT en `setup.exe /admin` tapant à partir de la ligne de commande à partir de la racine du point d’installation réseau qui contient les fichiers source d’Office. Par exemple, utilisez la commande suivante :
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
Les administrateurs utilisent l’OPO pour créer un fichier de personnalisation de l’installation. msp et peuvent personnaliser les domaines suivants:
  
- **Configuration** Spécifie l’emplacement d’installation par défaut sur le client et le nom de l’organisation par défaut, les sources d’installation réseau supplémentaires, la clé de produit, le contrat de licence utilisateur final, le niveau d’affichage et les versions antérieures d’Office à supprimer, ainsi que les programmes personnalisés à exécuter pendant installation, paramètres de sécurité et propriétés de l’installation.
    
- **Fonctionnalités** Permet de configurer les paramètres utilisateur et de personnaliser le mode d’installation des fonctionnalités d’Office. Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs. Ces derniers peuvent modifier la plupart des paramètres après l’installation.
    
- **Contenu supplémentaire** Permet d’ajouter ou de supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.
    
- **Outlook** Permet de personnaliser le profil Outlook par défaut d’un utilisateur, de spécifier les paramètres Exchange, d’ajouter des comptes, de supprimer les comptes et d’exporter des paramètres, et de spécifier les groupes d’envoi/réception.
    
Pour plus d’informations sur le PTOM, voir [utiliser le PTOM pour personnaliser Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)). Notez que ces informations s’appliquent également aux versions ultérieures d’Office.
  

