---
title: Télécharger et installer le module Skype Entreprise Online Connector
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Téléchargez, installez et utilisez Skype Entreprise Online Connector pour créer une session de connexion Windows PowerShell distante qui se connecte à Skype Entreprise Online.
ms.openlocfilehash: e9429b385f83f6b76e211614f953f7d439df524e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238865"
---
# <a name="download-and-install-the-teams-powershell-module"></a>Télécharger et installer le module Teams PowerShell

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> La dernière version Teams public [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector, et fournit un module unique pour la gestion de PowerShell en Teams et Skype Entreprise en ligne.


1. Installez le [Teams module PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes : 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Pour plus d’informations sur le démarrage d’Windows PowerShell, consultez Connecter pour tous les [services Microsoft 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ou Office 365 dans une seule fenêtre Windows PowerShell ou configurer votre ordinateur pour une Windows PowerShell. [](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>Sujets associés
[Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
