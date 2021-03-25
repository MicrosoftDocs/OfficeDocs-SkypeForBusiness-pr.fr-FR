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
description: Utilisez Windows PowerShell, les Get-CsTenant et Get-CsTenantLicensingConfiguration des clients pour obtenir des informations sur votre client Skype Entreprise Online.
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113180"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="4ee69-103">Gérer les organisations Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4ee69-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="4ee69-104">La dernière version [d’aperçu public de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et fournit un seul module pour la gestion de Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ee69-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="4ee69-105">Vous pouvez trouver des informations sur votre client Skype Entreprise Online à l’aide des cmdlets **Get-CsTenant** et **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="4ee69-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="4ee69-106">Gérer les clients Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4ee69-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="4ee69-107">Pour renvoyer des informations sur votre client Skype Entreprise Online, appelez l’cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) sans aucun paramètre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="4ee69-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="4ee69-108">Pour renvoyer uniquement le nom et l’ID du client, utilisez cette commande.</span><span class="sxs-lookup"><span data-stu-id="4ee69-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="4ee69-109">La valeur du paramètre _TenantID_ est requise lors de l’exécution d’lets telles que [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) et [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)</span><span class="sxs-lookup"><span data-stu-id="4ee69-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="4ee69-110">Pour déterminer si les informations de licence du client spécifié sont disponibles dans le Centre d’administration Skype Entreprise Online, utilisez l’cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)</span><span class="sxs-lookup"><span data-stu-id="4ee69-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4ee69-111">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4ee69-111">Related topics</span></span>
[<span data-ttu-id="4ee69-112">Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ee69-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
