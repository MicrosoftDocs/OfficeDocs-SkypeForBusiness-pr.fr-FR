---
title: Conditions préalables et configuration de l’outil stress and performance de Skype outil
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Conditions requises ou conditions préalables pour l’outil de contrainte et de performances de Skype entreprise Server 2015. Comment installer ou configurer l’outil stress and performance.
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005979"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Conditions préalables et configuration de l’outil stress and performance de Skype outil
 
Conditions requises ou conditions préalables pour l’outil de contrainte et de performances de Skype entreprise Server 2015. Comment installer ou configurer l’outil stress and performance.
  
Nous avons les sections suivantes relatives à la configuration matérielle, logicielle et système requise avant d’exécuter l’outil stress and performance :
  
- [Configuration matérielle requise pour le client](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Configuration logicielle requise pour le client](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Configuration requise](prerequisites-and-setup.md#ConfigReqs)
    
De plus, nous avons également une section ci-dessous pour l' [installation de l’outil de contrainte et de performances de Skype entreprise Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Configuration matérielle requise pour le client
<a name="ClientHardwareReqs"> </a>

Lors de l’exécution de l’outil stress and performance sur votre déploiement de Skype entreprise Server 2015, vous aurez au minimum besoin de ces exigences matérielles pour tous les 4500 utilisateurs de votre test :
  
- carte réseau 1 Gigabit
    
- 8 Go de mémoire vive (RAM)
    
- 2 processeurs double cœur
    
## <a name="client-software-requirements"></a>Configuration logicielle requise pour le client
<a name="ClientSoftwareReqs"> </a>

Les systèmes d’exploitation pris en charge pour l’outil stress and performance sont les suivants :
  
- Windows Server 2012
    
- Windows Server 2008 (64 bits)
    
En outre, les ordinateurs doivent respecter les configurations logicielles suivantes :
  
- L’infrastructure Microsoft .NET 4,5 est installée. [Téléchargez .net 4,5 Framework ici.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Vous aurez besoin de la fonctionnalité expérience utilisateur activée dans Windows.
    
- Microsoft Visual C++ 2013 (x64) doit être installé. [Téléchargez Visual C++ 2013 ici](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Vous allez avoir besoin du déploiement de Skype entreprise Server 2015.
    
## <a name="configuration-requirements"></a>Configuration requise
<a name="ConfigReqs"> </a>

Vous aurez besoin de ces configurations supplémentaires pour exécuter l’outil stress and performance :
  
- Vous devez vous connecter au serveur en tant que membre du groupe d’administrateurs de domaine ou local.
    
- Vous ne pouvez pas installer l’outil de création d’utilisateur Skype entreprise Server 2015 (UserProvisioningTool. exe) sur un serveur frontal ou un serveur Standard Edition où les comptes d’utilisateur doivent résider.
    
- Lorsque l’outil de création d’utilisateur est exécuté plusieurs fois, chaque utilisateur activé pour les communications unifiées de Microsoft doit disposer d’un numéro de téléphone unique.
    
- La taille du fichier d’échange doit être gérée par les systèmes ou doit être au moins égale à 1,5 fois la quantité de RAM dans le système informatique.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Installation de l’outil de contrainte et de performances de Skype entreprise Server 2015
<a name="Installing"> </a>

L’installation ne peut pas être simplifiée. Vous devez exécuter le fichier Windows Installer, **CapacityPlanningTool. msi**, sur chaque ordinateur client que vous allez utiliser pour simuler le trafic des utilisateurs et sur un serveur frontal dans chaque pool où vous allez créer des utilisateurs et des contacts.
  
Pour télécharger le fichier. msi, ainsi que les exemples de scripts mentionnés dans nos autres articles, accédez au lien du centre [de téléchargement : Skype entreprise Server 2015, stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

