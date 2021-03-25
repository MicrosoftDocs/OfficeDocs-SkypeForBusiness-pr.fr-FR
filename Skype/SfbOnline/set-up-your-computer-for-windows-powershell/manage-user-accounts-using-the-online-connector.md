---
title: Gérer les comptes d’utilisateurs à l’aide de Online Connector
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
description: Utilisez l'Get-CsOnlineUser de la Windows PowerShell pour obtenir des informations sur les utilisateurs Skype Entreprise Online de votre organisation.
ms.openlocfilehash: bdf1d445fa7c0a9ac4f874e0983b8ab7e8cb19e1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113170"
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="08ea4-103">Gérer les comptes d’utilisateurs à l’aide de Online Connector</span><span class="sxs-lookup"><span data-stu-id="08ea4-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="08ea4-104">Gérer les comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="08ea4-104">Manage user accounts</span></span>

<span data-ttu-id="08ea4-105">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="08ea4-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="08ea4-106">Retourner des informations sur tous vos utilisateurs de Lync Online</span><span class="sxs-lookup"><span data-stu-id="08ea4-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [<span data-ttu-id="08ea4-107">Renvoyer les informations d’un utilisateur spécifique dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="08ea4-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [<span data-ttu-id="08ea4-108">Renvoyer des informations spécifiques pour des utilisateurs spécifiques dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="08ea4-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [<span data-ttu-id="08ea4-109">Renvoyer une liste filtrée des utilisateurs dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="08ea4-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> <span data-ttu-id="08ea4-110">La **cmdlet Set-CsUser** est également incluse dans l’ensemble des cmdlets disponibles pour les administrateurs Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="08ea4-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="08ea4-111">Toutefois, **Set-CsUser** ne peut actuellement pas être utilisé pour gérer Skype Entreprise Online, à l’exception de la définition du paramètre _AudioVideoDisabled._</span><span class="sxs-lookup"><span data-stu-id="08ea4-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="08ea4-112">Si vous essayez d’exécuter la cmdlet avec un autre paramètre, elle échouera avec un message d’erreur semblable à ce qui suivant : Impossible de définir « SipAddress ».</span><span class="sxs-lookup"><span data-stu-id="08ea4-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="08ea4-113">Ce paramètre est restreint dans Remote Tenant PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08ea4-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="08ea4-114">Retourner des informations sur tous vos utilisateurs de Lync Online</span><span class="sxs-lookup"><span data-stu-id="08ea4-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="08ea4-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="08ea4-115"><a name="BKAllUsers"> </a></span></span>

<span data-ttu-id="08ea4-116">Pour renvoyer des informations sur tous vos utilisateurs qui ont été activés pour Skype Entreprise Online, appelez l’cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) sans aucun paramètre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="08ea4-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="08ea4-117">Pour renvoyer les informations d’un utilisateur sélectionné de façon aléatoire (par exemple, pour utiliser ce compte à des fins de test), appelez la cmdlet **Get-CsOnlineUser** et définissez le paramètre _ResultSize_ sur 1.</span><span class="sxs-lookup"><span data-stu-id="08ea4-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="08ea4-118">Ainsi, l’cmdlet **Get-CsOnlineUser** retourne les informations pour un seul utilisateur, quel que soit le nombre d’utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="08ea4-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="08ea4-119">Pour renvoyer les informations de cinq utilisateurs, définissez la valeur du paramètre _ResultSize_ sur 5.</span><span class="sxs-lookup"><span data-stu-id="08ea4-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="08ea4-120">Renvoyer les informations d’un utilisateur spécifique dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="08ea4-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="08ea4-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="08ea4-121"><a name="BKSpecificUser"> </a></span></span>

<span data-ttu-id="08ea4-122">Il existe plusieurs façons de faire référence à un compte d’utilisateur spécifique lorsque vous appelez l’cmdlet [Get-CsOnlineUser.](/powershell/module/skype/Get-CsOnlineUser)</span><span class="sxs-lookup"><span data-stu-id="08ea4-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet.</span></span> <span data-ttu-id="08ea4-123">Vous pouvez utiliser le nom complet AD DS (Active Directory Domain Services) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="08ea4-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="08ea4-124">Vous pouvez utiliser l’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="08ea4-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="08ea4-125">Vous pouvez utiliser le nom d’utilisateur principal (UPN) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="08ea4-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="08ea4-126">Renvoyer des informations spécifiques pour des utilisateurs spécifiques dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="08ea4-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="08ea4-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="08ea4-127"><a name="BKSpecificUsers"> </a></span></span>

<span data-ttu-id="08ea4-128">Par défaut, la cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) renvoie une grande quantité d’informations pour chaque compte d’utilisateur Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="08ea4-128">By default, the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="08ea4-129">Si seul un sous-ensemble de ces informations vous intéresse, pipez les données renvoyées vers l’cmdlet **Select-Object.**</span><span class="sxs-lookup"><span data-stu-id="08ea4-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="08ea4-130">Par exemple, cette commande renvoie toutes les données de l’utilisateur Ken Myer, puis utilise l’cmdlet **Select-Object** pour limiter les informations affichées à l’écran au nom d’affichage AD DS de Ken et au plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="08ea4-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="08ea4-131">La commande suivante renvoie le nom d’affichage et le plan de numérotation de tous vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="08ea4-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="08ea4-132">Pour rechercher les propriétés d’un compte d’utilisateur Skype Entreprise Online, utilisez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="08ea4-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="08ea4-133">Renvoyer une liste filtrée des utilisateurs dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="08ea4-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="08ea4-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="08ea4-134"><a name="BKListofUsers"> </a></span></span>

<span data-ttu-id="08ea4-135">En utilisant l’cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) et les  paramètres du filtre ou du filtre _Ldap,_ vous pouvez facilement renvoyer des informations sur un ensemble ciblé d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="08ea4-135">By using the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="08ea4-136">Par exemple, cette commande renvoie tous les utilisateurs qui travaillent dans le service Finances.</span><span class="sxs-lookup"><span data-stu-id="08ea4-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="08ea4-137">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="08ea4-137">Related topics</span></span>
[<span data-ttu-id="08ea4-138">Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08ea4-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)