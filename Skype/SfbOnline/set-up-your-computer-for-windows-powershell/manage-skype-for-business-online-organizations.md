---
title: Gérer Skype Entreprise organisations Online
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
description: Utilisez Windows PowerShell, les Get-CsTenant et Get-CsTenantLicensingConfiguration de compte pour obtenir des informations sur votre client Skype Entreprise Online.
ms.openlocfilehash: 2fa95bf8997dd0aff7271b1383c69d9b27c4f4a9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238784"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="b0ae5-103">Gérer Skype Entreprise organisations Online</span><span class="sxs-lookup"><span data-stu-id="b0ae5-103">Manage Skype for Business Online organizations</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> <span data-ttu-id="b0ae5-104">La dernière version Teams version d’aperçu [public de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et fournit un module unique pour la Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0ae5-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="b0ae5-105">Vous pouvez trouver des informations sur votre client Skype Entreprise Online à l’aide des cmdlets **Get-CsTenant** et **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="b0ae5-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="b0ae5-106">Gérer Skype Entreprise client en ligne</span><span class="sxs-lookup"><span data-stu-id="b0ae5-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="b0ae5-107">Pour renvoyer des informations sur votre Skype Entreprise Online, appelez l’cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) sans aucun paramètre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="b0ae5-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="b0ae5-108">Pour renvoyer uniquement le nom et l’ID du client, utilisez cette commande.</span><span class="sxs-lookup"><span data-stu-id="b0ae5-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="b0ae5-109">La valeur du paramètre _TenantID_ est requise lors de l’exécution d’lets telles que [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) et [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)</span><span class="sxs-lookup"><span data-stu-id="b0ae5-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="b0ae5-110">Pour déterminer si les informations de licence du client spécifié sont disponibles dans le Centre d’administration Skype Entreprise Online, utilisez l’cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)</span><span class="sxs-lookup"><span data-stu-id="b0ae5-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b0ae5-111">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="b0ae5-111">Related topics</span></span>
[<span data-ttu-id="b0ae5-112">Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0ae5-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
