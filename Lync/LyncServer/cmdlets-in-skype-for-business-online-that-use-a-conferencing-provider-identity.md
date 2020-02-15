---
title: Applets de commande dans Skype entreprise Online qui utilisent l’identité d’un fournisseur de services de conférence
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: e0ae3167b1cb6c83b46e4f9d4846e8863b43515d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001719"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="e8c93-102">Applets de commande dans Skype entreprise Online qui utilisent l’identité d’un fournisseur de services de conférence</span><span class="sxs-lookup"><span data-stu-id="e8c93-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="e8c93-103">Pour renvoyer des informations sur tous les fournisseurs de services d’audioconférence avec lesquels votre organisation a contracté, vous pouvez simplement appeler la cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) sans aucun paramètre :</span><span class="sxs-lookup"><span data-stu-id="e8c93-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="e8c93-104">Si vous souhaitez limiter les données renvoyées à un seul fournisseur (dans cet exemple, le fournisseur contoso audio services), utilisez le paramètre Identity :</span><span class="sxs-lookup"><span data-stu-id="e8c93-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="e8c93-105">Il n’existe qu’une seule cmdlet Skype entreprise Online qui accepte un ID de fournisseur de services d’audioconférence :</span><span class="sxs-lookup"><span data-stu-id="e8c93-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="e8c93-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e8c93-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="e8c93-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8c93-107">See Also</span></span>


[<span data-ttu-id="e8c93-108">Identités, étendues et locataires dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e8c93-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="e8c93-109">[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e8c93-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

