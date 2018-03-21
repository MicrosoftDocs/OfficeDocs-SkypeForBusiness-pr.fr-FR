---
title: "Gérer Skype pour les entreprises commerciales en ligne"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "Utiliser Windows PowerShell et les applets de commande Get-CsTenant et Get-CsTenantLicensingConfiguration pour obtenir des informations sur votre Skype pour clients d’entreprise en ligne."
ms.openlocfilehash: 6461a15baeed3bf3fde0ee79dc24f7863eaabd02
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/27/2018
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="4d010-103">Gérer Skype pour les entreprises commerciales en ligne</span><span class="sxs-lookup"><span data-stu-id="4d010-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="4d010-104">Vous trouverez des informations sur votre Skype pour clients d’entreprise en ligne à l’aide des applets de commande **Get-CsTenant** et **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4d010-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="4d010-105">Gérer Skype pour locataires Business en ligne</span><span class="sxs-lookup"><span data-stu-id="4d010-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="4d010-106">Pour retourner des informations sur votre Skype pour clients d’entreprise en ligne, appelez l’applet de commande [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sans paramètres supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="4d010-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="4d010-107">Pour retourner uniquement les clients nom et ID, utilisez cette commande.</span><span class="sxs-lookup"><span data-stu-id="4d010-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="4d010-108">La valeur du paramètre _TenantID_ est obligatoire lors de l’exécution d’applets de commande [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) des [CsTenantFederationConfiguration de l’ensemble](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="4d010-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="4d010-109">Pour savoir si les informations de licence pour le client spécifié sont disponibles dans le Skype pour Business Online Centre d’administration, utilisez l’applet de commande [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="4d010-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4d010-110">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4d010-110">Related topics</span></span>
[<span data-ttu-id="4d010-111">Configurer votre ordinateur pour Skype pour la gestion d’entreprise en ligne à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d010-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

## <a name="feedback"></a><span data-ttu-id="4d010-112">Commentaires ?</span><span class="sxs-lookup"><span data-stu-id="4d010-112">Feedback?</span></span>
<span data-ttu-id="4d010-113">Pour fournir des commentaires sur le produit ou pour nous faire savoir comment nous faisons, consultez [Skype pour les commentaires de l’entreprise](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="4d010-113">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>