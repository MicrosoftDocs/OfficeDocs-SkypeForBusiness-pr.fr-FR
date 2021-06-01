---
title: Gérer les comptes d’utilisateurs
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
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
description: Utilisez lGet-CsOnlineUser cmdlet dans Windows PowerShell pour obtenir des informations sur les utilisateurs en ligne Skype Entreprise organisation.
ms.openlocfilehash: aec79f589f6b1fb0c9d38fd4bc70421b30f66a56
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238720"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="a550e-103">Gérer les comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a550e-103">Manage user accounts</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="manage-user-accounts"></a><span data-ttu-id="a550e-104">Gérer les comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a550e-104">Manage user accounts</span></span>

<span data-ttu-id="a550e-105">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="a550e-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="a550e-106">Retourner des informations sur tous vos utilisateurs de Lync Online</span><span class="sxs-lookup"><span data-stu-id="a550e-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="a550e-107">Renvoyer les informations d’un utilisateur spécifique dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a550e-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="a550e-108">Renvoyer des informations spécifiques pour des utilisateurs spécifiques dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a550e-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="a550e-109">Renvoyer une liste filtrée des utilisateurs dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a550e-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="a550e-110">**L’cmdlet Set-CsUser** est également incluse dans l’ensemble des cmdlets disponibles Skype Entreprise Administrateurs Online.</span><span class="sxs-lookup"><span data-stu-id="a550e-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="a550e-111">Toutefois, **Set-CsUser** ne peut pas actuellement être utilisé pour gérer Skype Entreprise Online, à l’exception de la définition du paramètre _AudioVideoDisabled._</span><span class="sxs-lookup"><span data-stu-id="a550e-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="a550e-112">Si vous essayez d’exécuter la cmdlet avec un autre paramètre, elle échouera avec un message d’erreur semblable à ce qui suivant : Impossible de définir « SipAddress ».</span><span class="sxs-lookup"><span data-stu-id="a550e-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="a550e-113">Ce paramètre est restreint dans Remote Tenant PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a550e-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="a550e-114">Retourner des informations sur tous vos utilisateurs de Lync Online</span><span class="sxs-lookup"><span data-stu-id="a550e-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="a550e-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="a550e-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span></span>

<span data-ttu-id="a550e-116">Pour renvoyer des informations sur tous vos utilisateurs qui ont été activés pour Skype Entreprise Online, appelez l’cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) sans aucun paramètre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="a550e-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="a550e-117">Pour renvoyer les informations d’un utilisateur sélectionné de façon aléatoire (par exemple, pour utiliser ce compte à des fins de test), appelez la cmdlet **Get-CsOnlineUser** et définissez le paramètre _ResultSize_ sur 1.</span><span class="sxs-lookup"><span data-stu-id="a550e-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="a550e-118">Ainsi, l’cmdlet **Get-CsOnlineUser** retourne les informations pour un seul utilisateur, quel que soit le nombre d’utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a550e-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="a550e-119">Pour renvoyer les informations de cinq utilisateurs, définissez la valeur du paramètre _ResultSize_ sur 5.</span><span class="sxs-lookup"><span data-stu-id="a550e-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="a550e-120">Renvoyer les informations d’un utilisateur spécifique dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a550e-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="a550e-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="a550e-121"><a name="BKMKReturnInfoSpecificUser"> </a></span></span>

<span data-ttu-id="a550e-122">Il existe plusieurs façons de faire référence à un compte d’utilisateur spécifique lorsque vous appelez l’cmdlet [Get-CsOnlineUser.](/powershell/module/skype/Get-CsOnlineUser)</span><span class="sxs-lookup"><span data-stu-id="a550e-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet.</span></span> <span data-ttu-id="a550e-123">Vous pouvez utiliser le nom complet AD DS (Active Directory Domain Services) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a550e-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="a550e-124">Vous pouvez utiliser l’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a550e-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="a550e-125">Vous pouvez utiliser le nom d’utilisateur principal (UPN) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a550e-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="a550e-126">Renvoyer des informations spécifiques pour des utilisateurs spécifiques dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a550e-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="a550e-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="a550e-127"><a name="BKMKReturninfoSpecificUsers"> </a></span></span>

<span data-ttu-id="a550e-128">Par défaut, la cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) renvoie une grande quantité d’informations pour chaque Skype Entreprise d’utilisateur Online.</span><span class="sxs-lookup"><span data-stu-id="a550e-128">By default, the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="a550e-129">Si seul un sous-ensemble de ces informations vous intéresse, pipez les données renvoyées à l’cmdlet **Select-Object.**</span><span class="sxs-lookup"><span data-stu-id="a550e-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="a550e-130">Par exemple, cette commande renvoie toutes les données de l’utilisateur Ken Myer, puis utilise l’cmdlet **Select-Object** pour limiter les informations affichées à l’écran au nom d’affichage AD DS de Ken et au plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="a550e-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="a550e-131">La commande suivante renvoie le nom d’affichage et le plan de numérotation de tous vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a550e-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="a550e-132">Pour rechercher les propriétés d’un Skype Entreprise utilisateur Online, utilisez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="a550e-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="a550e-133">Renvoyer une liste filtrée des utilisateurs dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a550e-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="a550e-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="a550e-134"><a name="BKMKReturnFilteredListofUsers"> </a></span></span>

<span data-ttu-id="a550e-135">En utilisant l’cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) et les  paramètres du filtre ou du filtre _Ldap,_ vous pouvez facilement renvoyer des informations sur un ensemble d’utilisateurs ciblé.</span><span class="sxs-lookup"><span data-stu-id="a550e-135">By using the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="a550e-136">Par exemple, cette commande renvoie tous les utilisateurs qui travaillent dans le service Finances.</span><span class="sxs-lookup"><span data-stu-id="a550e-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="a550e-137">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="a550e-137">Related topics</span></span>
[<span data-ttu-id="a550e-138">Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a550e-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
