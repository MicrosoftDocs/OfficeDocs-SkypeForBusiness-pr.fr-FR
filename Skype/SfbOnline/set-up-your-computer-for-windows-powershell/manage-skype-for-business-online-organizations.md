---
title: Gérer les organisations Skype Entreprise Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
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
description: Utilisez Windows PowerShell, les Get-CsTenant et Get-CsTenantLicensingConfiguration de clients pour obtenir des informations sur votre client Skype Entreprise Online.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085690"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="2716a-103">Gérer les organisations Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="2716a-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="2716a-104">La dernière version [d’aperçu public de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et fournit un seul module pour la gestion de Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2716a-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="2716a-105">Vous pouvez trouver des informations sur votre client Skype Entreprise Online à l’aide des cmdlets **Get-CsTenant** et **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="2716a-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="2716a-106">Gérer les clients Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="2716a-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="2716a-107">Pour renvoyer des informations sur votre client Skype Entreprise Online, appelez l’cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sans aucun paramètre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="2716a-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="2716a-108">Pour renvoyer uniquement le nom et l’ID du client, utilisez cette commande.</span><span class="sxs-lookup"><span data-stu-id="2716a-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="2716a-109">La valeur du paramètre _TenantID_ est requise lors de l’exécution d’lets telles que [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) et [Set-CsTenantFederationConfiguration.](https://technet.microsoft.com/library/jj994080.aspx)</span><span class="sxs-lookup"><span data-stu-id="2716a-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="2716a-110">Pour déterminer si les informations de licence du client spécifié sont disponibles dans le Centre d’administration Skype Entreprise Online, utilisez l’cmdlet [Get-CsTenantLicensingConfiguration.](https://go.microsoft.com/fwlink/p/?linkid=849606)</span><span class="sxs-lookup"><span data-stu-id="2716a-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2716a-111">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="2716a-111">Related topics</span></span>
[<span data-ttu-id="2716a-112">Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2716a-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
