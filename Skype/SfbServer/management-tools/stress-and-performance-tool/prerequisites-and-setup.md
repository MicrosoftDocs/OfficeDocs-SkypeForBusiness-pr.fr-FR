---
title: Conditions préalables et configuration de la Skype de l’outil Stress and Performance de Busines
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Conditions requises ou conditions préalables pour l Skype Entreprise Server 2015 Stress and Performance Tool. Comment installer ou configurer l’outil Stress and Performance.
ms.openlocfilehash: 5d86dbc085929bfcb9bd52dd7d25f46f92fda8fb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611923"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Conditions préalables et configuration de la Skype de l’outil Stress and Performance de Busines
 
Conditions requises ou conditions préalables pour l Skype Entreprise Server 2015 Stress and Performance Tool. Comment installer ou configurer l’outil Stress and Performance.
  
Nous avons les sections suivantes sur les configurations matérielle, logicielle et système requises que vous devez connaître avant d’utiliser l’outil Stress and Performance :
  
- [Configuration matérielle requise pour le client](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Exigences logicielles client](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Configuration requise](prerequisites-and-setup.md#ConfigReqs)
    
En outre, nous avons également une section ci-dessous pour l’installation de Skype Entreprise Server [2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)
  
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
    
- La fonctionnalité Expérience utilisateur doit être activée dans Windows.
    
- Vous devez installer Microsoft Visual C++ 2013 (x64). [Téléchargez Visual C++ 2013 ici](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Vous devrez déployer Skype Entreprise Server 2015.
    
## <a name="configuration-requirements"></a>Configuration requise
<a name="ConfigReqs"> </a>

Vous aurez besoin de ces configurations supplémentaires pour exécuter correctement l’outil Stress and Performance :
  
- Vous devez vous connecter au serveur en tant que membre du groupe Domaine ou Administrateur local.
    
- Vous ne pouvez pas installer l’outil de création d’utilisateurs Skype Entreprise Server 2015 (UserProvisioningTool.exe) sur un serveur frontal ou un serveur Édition Standard où résideront les comptes d’utilisateur.
    
- Lorsque l’outil Création d’utilisateurs est exécuté plusieurs fois, chaque utilisateur activé pour Microsoft Unified Communications doit avoir un numéro de téléphone unique.
    
- La taille du fichier de page doit être gérée par les systèmes ou doit être au moins 1,5 fois la quantité de RAM du système informatique.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installation de l Skype Entreprise Server 2015 Stress and Performance Tool
<a name="Installing"> </a>

L’installation ne pouvait pas être plus simple. Vous devez exécuter le fichier Windows Installer, **CapacityPlanningTool.msi,** sur chaque ordinateur client que vous allez utiliser pour simuler le trafic utilisateur, et sur un serveur frontal dans chaque pool où vous allez créer des utilisateurs et des contacts.
  
Pour télécharger le .msi, ainsi que les exemples de scripts mentionnés dans nos autres articles, go to the Download Center link: [Skype Entreprise Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

