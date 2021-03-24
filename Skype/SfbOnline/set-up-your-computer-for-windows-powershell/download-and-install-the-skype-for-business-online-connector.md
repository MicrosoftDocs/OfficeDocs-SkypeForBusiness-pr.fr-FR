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
description: Téléchargez, installez et utilisez Skype Entreprise Online Connector pour créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online.
ms.openlocfilehash: 0e00b9dd18b04deaf3d2123de1fa9609040c4e2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097200"
---
# <a name="download-and-install-the-teams-powershell-module"></a>Télécharger et installer le module Teams PowerShell

> [!NOTE]

> La dernière version [publique de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et offre un seul module pour la gestion de PowerShell en ligne pour Teams et Skype Entreprise.


1. Installez le [module Teams PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes : 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell](set-up-your-computer-for-windows-powershell.md)