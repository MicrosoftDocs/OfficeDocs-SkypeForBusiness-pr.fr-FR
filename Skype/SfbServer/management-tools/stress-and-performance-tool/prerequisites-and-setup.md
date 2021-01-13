---
title: Conditions préalables et configuration de l’outil Stress and Performance de Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Conditions requises ou conditions préalables pour l’outil Stress and Performance de Skype Entreprise Server 2015. Comment installer ou configurer l’outil Stress and Performance.
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814954"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Conditions préalables et configuration de l’outil Stress and Performance de Skype Entreprise
 
Conditions requises ou conditions préalables pour l’outil Stress and Performance de Skype Entreprise Server 2015. Comment installer ou configurer l’outil Stress and Performance.
  
Nous avons les sections suivantes sur les configurations matérielle, logicielle et système requises que vous devez connaître avant d’utiliser l’outil Stress and Performance :
  
- [Configuration matérielle requise pour le client](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Exigences logicielles client](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Configuration requise](prerequisites-and-setup.md#ConfigReqs)
    
En outre, nous avons également une section ci-dessous pour l’installation de l’outil Stress [and Performance de Skype Entreprise Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Configuration matérielle requise pour le client
<a name="ClientHardwareReqs"> </a>

Lors de l’exécution de l’outil Stress and Performance sur votre déploiement Skype Entreprise Server 2015, vous aurez besoin, au minimum, que la configuration matérielle requise soit remplie pour 4 500 utilisateurs dans votre test :
  
- Carte réseau 1 gigabit
    
- 8 Go de mémoire vive (RAM)
    
- 2 processeurs double cœur
    
## <a name="client-software-requirements"></a>Exigences logicielles client
<a name="ClientSoftwareReqs"> </a>

Les systèmes d’exploitation pris en charge pour l’outil Stress and Performance sont :
  
- Windows Server 2012
    
- Windows Server 2008 (64 bits)
    
En outre, les ordinateurs doivent répondre aux exigences logicielles suivantes :
  
- Microsoft .NET 4.5 Framework doit être installé. [Téléchargez .Net 4.5 Framework ici.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Vous aurez besoin de la fonctionnalité Expérience utilisateur activée dans Windows.
    
- Microsoft Visual C++ 2013 (x64) doit être installé. [Téléchargez Visual C++ 2013 ici](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Skype Entreprise Server 2015 doit être déployé avec succès.
    
## <a name="configuration-requirements"></a>Configuration requise
<a name="ConfigReqs"> </a>

Vous aurez besoin de ces configurations supplémentaires pour exécuter correctement l’outil Stress and Performance :
  
- Vous devez vous connecter au serveur en tant que membre du groupe Domaine ou Administrateur local.
    
- Vous ne pouvez pas installer l’outil création d’utilisateurs De Skype Entreprise Server 2015 (UserProvisioningTool.exe) sur un serveur frontal ou un serveur Standard Edition où résideront les comptes d’utilisateur.
    
- Lorsque l’outil Création d’utilisateurs est exécuté plusieurs fois, chaque utilisateur activé pour Microsoft Unified Communications doit avoir un numéro de téléphone unique.
    
- La taille du fichier de page doit être gérée par les systèmes ou doit être au moins 1,5 fois la quantité de RAM du système informatique.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installation de l’outil Stress and Performance de Skype Entreprise Server 2015
<a name="Installing"> </a>

L’installation ne pouvait pas être plus simple. Vous devez exécuter le fichier Windows Installer, **CapacityPlanningTool.msi,** sur chaque ordinateur client que vous allez utiliser pour simuler le trafic utilisateur, et sur un serveur frontal dans chaque pool où vous allez créer des utilisateurs et des contacts.
  
To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

