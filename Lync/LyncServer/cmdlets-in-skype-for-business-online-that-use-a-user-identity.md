---
title: Cmdlets dans Skype entreprise Online utilisant une identité d’utilisateur
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94c29eb2aadefcb6a9f3ca9b5c11a49f7e41167a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728124"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="8de14-102">Cmdlets dans Skype entreprise Online utilisant une identité d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="8de14-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="8de14-103">Dans Skype entreprise Online, il existe plusieurs façons de faire référence à une identité d’utilisateur individuelle :</span><span class="sxs-lookup"><span data-stu-id="8de14-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="8de14-104">Utilisez le nom complet des services de domaine Active Directory de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8de14-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="8de14-105">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8de14-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="8de14-106">Utilisez l’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8de14-106">Use the user’s SIP address.</span></span> <span data-ttu-id="8de14-107">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8de14-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="8de14-108">Utilisez le nom d’utilisateur principal de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8de14-108">Use the user’s UPN.</span></span> <span data-ttu-id="8de14-109">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8de14-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="8de14-110">Utilisez le nom unique des services de domaine Active Directory de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8de14-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="8de14-111">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8de14-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="8de14-112">Les applets de commande suivantes acceptent l’identité d’un utilisateur :</span><span class="sxs-lookup"><span data-stu-id="8de14-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="8de14-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8de14-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8de14-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8de14-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8de14-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8de14-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8de14-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8de14-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8de14-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8de14-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8de14-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8de14-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="8de14-125">Notez que vous n’avez pas besoin de spécifier d’identité d’utilisateur lors de l’appel d’une des cmdlets **Get-CS** .</span><span class="sxs-lookup"><span data-stu-id="8de14-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="8de14-126">Dans ce cas, les applets de passe retournent toutes les instances de l’élément spécifié.</span><span class="sxs-lookup"><span data-stu-id="8de14-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="8de14-127">Par exemple, la commande suivante renvoie des informations sur tous les utilisateurs qui ont été activés pour Skype entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="8de14-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="8de14-128">Le paramètre Identity est requis uniquement si vous souhaitez renvoyer des informations pour un utilisateur spécifique :</span><span class="sxs-lookup"><span data-stu-id="8de14-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="8de14-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8de14-129">See Also</span></span>


[<span data-ttu-id="8de14-130">Identités, étendues et clients dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8de14-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="8de14-131">[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8de14-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

