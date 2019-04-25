---
title: Gérer les Skype pour les organisations Business en ligne
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Utiliser Windows PowerShell et les applets de commande Get-CsTenant et Get-CsTenantLicensingConfiguration pour obtenir des informations sur votre Skype pour client d’entreprise en ligne.
ms.openlocfilehash: b71c89967ab34909fa461f71fc5f67c1cf99a408
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32224444"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="e4a32-103">Gérer les Skype pour les organisations Business en ligne</span><span class="sxs-lookup"><span data-stu-id="e4a32-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="e4a32-104">Vous trouverez des informations sur votre Skype pour client d’entreprise en ligne à l’aide des applets de commande **Get-CsTenant** et **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e4a32-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="e4a32-105">Gérer les Skype pour les clients professionnels en ligne</span><span class="sxs-lookup"><span data-stu-id="e4a32-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="e4a32-106">Pour retourner des informations sur votre Skype pour Business Online client, appeler la cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sans aucun paramètre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="e4a32-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="e4a32-107">Pour retourner uniquement les clients nom et l’ID, utilisez cette commande.</span><span class="sxs-lookup"><span data-stu-id="e4a32-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="e4a32-108">La valeur du paramètre _ID client sur_ est requise lors de l’exécution des applets de commande telles que [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) et [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="e4a32-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="e4a32-109">Pour savoir si des informations de licence pour le client spécifié sont disponibles dans le Skype pour le centre d’administration Business en ligne, utilisez l’applet de commande [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="e4a32-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e4a32-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e4a32-110">Related topics</span></span>
[<span data-ttu-id="e4a32-111">Configurer votre ordinateur pour Skype pour la gestion en ligne à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4a32-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
