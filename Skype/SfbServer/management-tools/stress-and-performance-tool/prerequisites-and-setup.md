---
title: Conditions préalables et configuration pour l'outil Stress and Performance de Skype Entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Configuration requise ou conditions préalables pour l'outil Stress and Performance de Skype Entreprise Server 2015. Comment installer ou configurer l'outil Stress and Performance.
ms.openlocfilehash: 51e83736ecc3d8f18937dee8e9fdbb5244662a2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906584"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Conditions préalables et configuration pour l'outil Stress and Performance de Skype Entreprise
 
Configuration requise ou conditions préalables pour l'outil Stress and Performance de Skype Entreprise Server 2015. Comment installer ou configurer l'outil Stress and Performance.
  
Vous devez avoir pris connaissance des sections suivantes relatives à la configuration matérielle, logicielle et système requise avant d'exécuter l'outil Stress and Performance :
  
- [Configuration matérielle client requise](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Configuration logicielle client requise](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Configuration requise](prerequisites-and-setup.md#ConfigReqs)
    
En outre, une section concernant [l'installation de l'outil Stress and Performance de Skype Entreprise Server 2015](prerequisites-and-setup.md#Installing) figure ci-dessous
  
## <a name="client-hardware-requirements"></a>Configuration matérielle client requise
<a name="ClientHardwareReqs"> </a>

Lorsque vous exécutez l'outil Stress and Performance pour votre déploiement Skype Entreprise Server 2015, vous devez disposer, au minimum, de la configuration matérielle suivante, pour chaque groupe de 4500 utilisateurs de votre test :
  
- carte réseau 1 gigabit
    
- 8 Go de mémoire vive
    
- 2 processeurs double cœur
    
## <a name="client-software-requirements"></a>Configuration logicielle client requise
<a name="ClientSoftwareReqs"> </a>

Systèmes d'exploitation pris en charge par l'outil Stress and Performance :
  
- Windows Server 2012
    
- Windows Server 2008 (64 bits)
    
De plus, l'ordinateur requiert la configuration logicielle suivante :
  
- Microsoft .NET 4.5 Framework doit être installé. [Télécharger le .net Framework 4.5 Framework ici.](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- Dans Windows, la fonctionnalité Expérience utilisateur doit être activée.
    
- Microsoft Visual C++ 2013 (x64) doit être installé. [Téléchargez Visual C++ 2013 ici](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- Un déploiement réussi de Skype Entreprise Server 2015 est requis.
    
## <a name="configuration-requirements"></a>Configuration requise
<a name="ConfigReqs"> </a>

Pour que l'outil Stress and Performance fonctionne correctement, les configurations supplémentaires suivantes sont nécessaires :
  
- Connectez-vous au serveur en tant que membre du groupe du domaine ou de l'administrateur local.
    
- Vous ne pouvez pas installer l'outil Création d'utilisateur de Skype Entreprise Server 2015 sur n'importe quel serveur frontal ou Standard Edition où les comptes de l'utilisateur résideront.
    
- Lorsque l'outil Création d'utilisateur est exécuté plusieurs fois, chaque utilisateur actif pour Microsoft Unified Communications doit présenter un numéro de téléphone unique.
    
- La taille de fichier de la page doit être gérée par les systèmes ou correspondre à au moins 1,5 fois la quantité de mémoire vive du système de l'ordinateur.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installation de l'outil Stress and Performance de Skype Entreprise Server 2015.
<a name="Installing"> </a>

L'installation ne pourrait être plus facile. Exécutez le fichier d'installation Windows, **CapacityPlanningTool.msi**, sur tous les ordinateurs client qui seront utilisés pour simuler le trafic utilisateur et sur un serveur frontal de chaque pool où des utilisateurs et des contacts seront créés.
  
Pour télécharger le fichier .msi, ainsi que les exemples de scripts mentionné dans nos autres articles, allez sur le lien Centre de téléchargement : [Skype pour Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

