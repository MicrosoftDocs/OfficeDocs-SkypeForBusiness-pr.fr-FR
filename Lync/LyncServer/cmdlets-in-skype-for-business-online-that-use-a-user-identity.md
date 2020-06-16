---
title: Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 8aee680c6e55de62ff9d49724d3e480c00159aa4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755106"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="a6318-102">Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="a6318-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="a6318-103">Dans Skype entreprise Online, il existe plusieurs façons de faire référence à une identité d’utilisateur spécifique :</span><span class="sxs-lookup"><span data-stu-id="a6318-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="a6318-104">Utiliser le nom d’affichage des services de domaine Active Directory de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a6318-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="a6318-105">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a6318-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="a6318-106">Utilisez l’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a6318-106">Use the user’s SIP address.</span></span> <span data-ttu-id="a6318-107">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a6318-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a6318-108">Utilisez le nom d’utilisateur principal de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a6318-108">Use the user’s UPN.</span></span> <span data-ttu-id="a6318-109">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a6318-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="a6318-110">Utilisez le nom unique des services de domaine Active Directory de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a6318-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="a6318-111">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a6318-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="a6318-112">Les applets de commande suivantes acceptent une identité d’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="a6318-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="a6318-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a6318-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a6318-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a6318-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a6318-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a6318-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a6318-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a6318-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a6318-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a6318-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a6318-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a6318-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="a6318-125">Notez que vous n’avez pas besoin de spécifier l’identité d’un utilisateur lors de l’appel de l’une des cmdlets **Get-CS** .</span><span class="sxs-lookup"><span data-stu-id="a6318-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="a6318-126">Dans ce cas, les cmdlets renvoient toutes les instances de l’élément spécifié.</span><span class="sxs-lookup"><span data-stu-id="a6318-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="a6318-127">Par exemple, cette commande renvoie des informations sur tous les utilisateurs qui ont été activés pour Skype entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="a6318-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="a6318-128">Le paramètre Identity est obligatoire uniquement si vous souhaitez renvoyer des informations sur un utilisateur spécifique :</span><span class="sxs-lookup"><span data-stu-id="a6318-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="a6318-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6318-129">See Also</span></span>


[<span data-ttu-id="a6318-130">Identités, étendues et locataires dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a6318-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="a6318-131">[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a6318-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

