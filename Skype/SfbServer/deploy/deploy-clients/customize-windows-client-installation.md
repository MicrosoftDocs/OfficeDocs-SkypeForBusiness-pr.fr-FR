---
title: Personnaliser l’installation du client Windows dans Skype Entreprise Server
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
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Résumé : Vue d’ensemble des méthodes et outils d’installation pour Skype Entreprise.'
ms.openlocfilehash: 001224369e46978e96ee063b31fcb546ef213a05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805714"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a>Personnaliser l’installation du client Windows dans Skype Entreprise Server
 
**Résumé :** Vue d’ensemble des méthodes et outils d’installation pour Skype Entreprise.
  
> [!NOTE]
> Pour plus d’informations sur l’installation de Skype Entreprise avec Microsoft 365 et Office 365, voir Déployer le client Skype Entreprise dans [Microsoft 365 ou Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96) 
  
Les administrateurs d’entreprise peuvent personnaliser l’installation basée sur Windows Installer (.msi) des versions avec licence en volume de Skype Entreprise à l’aide des méthodes abordées dans cette section. Étant donné qu’aucun outil ne fournit toutes les options de personnalisation, vous utiliserez probablement une combinaison de ces méthodes dans votre déploiement Skype Entreprise. Vous pouvez utiliser les outils décrits dans les sections suivantes :
  
- [Utilisez l’Outil de personnalisation Office (PERSONNALISATION)](use-the-office-customization-tool-oct.md) dans Skype Entreprise Server pour personnaliser les options d’installation et les fonctionnalités de Skype Entreprise et d’autres programmes Office.
    
- Utilisez Config.xml pour effectuer des [tâches d’installation](use-config-xml-to-perform-installation-tasks.md) dans Skype Entreprise Server afin de spécifier le chemin d’accès du point d’installation réseau et d’effectuer l’installation en mode silencieux.
    
- [Utilisez les options de ligne de commande du programme](use-setup-command-line-options.md) d’installation dans Skype Entreprise Server pour spécifier le Config.xml à utiliser lors de l’installation.
    
- [Configurez les stratégies d’a bootstrapping](configure-client-bootstrapping-policies.md) des clients dans Skype Entreprise Server à l’aide du logiciel enfichable MMC Éditeur d’objets de stratégie de groupe.
    
Il y aura probablement d’autres options que vous souhaiterez configurer lors du déploiement de la suite de produits Office. Les rubriques de cette section donnent une vue d’ensemble de ces outils de personnalisation et abordent les considérations spécifiques à Skype Entreprise. Vous trouverez également des liens vers l’aide détaillée d’Office pour chaque outil. 
  

