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
ms.openlocfilehash: 5883eba8dc4dd959e67e45aa27413624e0f5d941
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568940"
---
# <a name="download-and-install-the-teams-powershell-module"></a><span data-ttu-id="236c1-103">Télécharger et installer le module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="236c1-103">Download and install the Teams PowerShell module</span></span>

> [!NOTE]

> <span data-ttu-id="236c1-104">La dernière version [publique de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et offre un seul module pour la gestion de PowerShell en ligne pour Teams et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="236c1-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams and Skype for Business online PowerShell management.</span></span>


1. <span data-ttu-id="236c1-105">Installez le [module Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="236c1-105">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="236c1-106">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="236c1-106">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="236c1-107">Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="236c1-107">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="236c1-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="236c1-108">Related topics</span></span>
[<span data-ttu-id="236c1-109">Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="236c1-109">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
