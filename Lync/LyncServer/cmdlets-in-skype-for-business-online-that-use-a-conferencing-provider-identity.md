---
title: Applets de commande dans Skype entreprise Online qui utilisent l’identité d’un fournisseur de services de conférence
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: accaad94f5e29863ac948ea64d061d23b811105f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755126"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="0df77-102">Applets de commande dans Skype entreprise Online qui utilisent l’identité d’un fournisseur de services de conférence</span><span class="sxs-lookup"><span data-stu-id="0df77-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="0df77-103">Pour renvoyer des informations sur tous les fournisseurs de services d’audioconférence avec lesquels votre organisation a contracté, vous pouvez simplement appeler la cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) sans aucun paramètre :</span><span class="sxs-lookup"><span data-stu-id="0df77-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="0df77-104">Si vous souhaitez limiter les données renvoyées à un seul fournisseur (dans cet exemple, le fournisseur contoso audio services), utilisez le paramètre Identity :</span><span class="sxs-lookup"><span data-stu-id="0df77-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="0df77-105">Il n’existe qu’une seule cmdlet Skype entreprise Online qui accepte un ID de fournisseur de services d’audioconférence :</span><span class="sxs-lookup"><span data-stu-id="0df77-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="0df77-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="0df77-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="0df77-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0df77-107">See Also</span></span>


[<span data-ttu-id="0df77-108">Identités, étendues et locataires dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0df77-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="0df77-109">[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="0df77-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

