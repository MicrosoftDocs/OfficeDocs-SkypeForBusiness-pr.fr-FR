---
title: Cmdlets dans Skype entreprise Online utilisant l’identité d’un fournisseur de conférence
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2957fbc63a885a1c2e1f053cffbf7439d2b648d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233119"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="b6e3c-102">Cmdlets dans Skype entreprise Online utilisant l’identité d’un fournisseur de conférence</span><span class="sxs-lookup"><span data-stu-id="b6e3c-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="b6e3c-103">Pour renvoyer des informations sur tous les fournisseurs de services d’audioconférence pour lesquels votre organisation a contracté une conversation, vous pouvez simplement appeler la cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) sans paramètres:</span><span class="sxs-lookup"><span data-stu-id="b6e3c-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="b6e3c-104">Si vous souhaitez limiter les données renvoyées à un seul fournisseur (dans cet exemple, les services audio du fournisseur contoso), puis utilisez le paramètre Identity:</span><span class="sxs-lookup"><span data-stu-id="b6e3c-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="b6e3c-105">Il n’y a qu’une applet de connexion Skype entreprise Online qui accepte un ID de fournisseur de services d’audioconférence:</span><span class="sxs-lookup"><span data-stu-id="b6e3c-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="b6e3c-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b6e3c-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="b6e3c-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b6e3c-107">See Also</span></span>


[<span data-ttu-id="b6e3c-108">Identités, étendues et clients dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b6e3c-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="b6e3c-109">[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b6e3c-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

