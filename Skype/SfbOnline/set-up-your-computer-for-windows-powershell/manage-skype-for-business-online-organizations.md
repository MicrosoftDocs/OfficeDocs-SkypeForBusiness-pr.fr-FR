---
title: Gestion des organisations Skype entreprise Online
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
description: Utilisez Windows PowerShell et les applets de connexion Get-CsTenant et Get-CsTenantLicensingConfiguration pour obtenir des informations sur votre client Skype entreprise online.
ms.openlocfilehash: e4765fbbe8c705300bb93c09651034e080a8132e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010617"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="930d7-103">Gestion des organisations Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="930d7-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="930d7-104">Vous pouvez trouver des informations sur votre client Skype entreprise Online à l’aide des applets de connexion **Get-CsTenant** et **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="930d7-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="930d7-105">Gestion des locataires Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="930d7-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="930d7-106">Pour renvoyer des informations sur votre client Skype entreprise Online, appelez l’applet de connexion [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sans aucun paramètre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="930d7-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="930d7-107">Pour renvoyer uniquement le nom du client et l’ID, utilisez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="930d7-107">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="930d7-108">La valeur du paramètre _IDClient_ est requise lors de l’exécution de cmdlets telles que [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) et [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="930d7-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="930d7-109">Pour savoir si des informations de licence pour le client spécifié sont disponibles dans le centre d’administration Skype entreprise Online, utilisez l’applet de connexion [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="930d7-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="930d7-110">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="930d7-110">Related topics</span></span>
[<span data-ttu-id="930d7-111">Configurer votre ordinateur pour la gestion de Skype entreprise Online à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="930d7-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
