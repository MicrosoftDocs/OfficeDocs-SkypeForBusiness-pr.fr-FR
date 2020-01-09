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
f1keywords: None
ms.custom:
- PowerShell
description: Utilisez l’applet de connexion Get-CsOnlineUser dans Windows PowerShell pour obtenir des informations sur les utilisateurs de Skype entreprise Online de votre organisation.
ms.openlocfilehash: a61d698b5218c37c786bdba9ab7f7711e9ab47b4
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989239"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="cc196-103">Gérer les comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="cc196-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="cc196-104">Gérer les comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="cc196-104">Manage user accounts</span></span>

<span data-ttu-id="cc196-105">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="cc196-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="cc196-106">Retourner des informations sur tous vos utilisateurs de Lync Online</span><span class="sxs-lookup"><span data-stu-id="cc196-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="cc196-107">Renvoyer des informations pour un utilisateur spécifique dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cc196-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="cc196-108">Renvoi d’informations spécifiques à des utilisateurs spécifiques dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cc196-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="cc196-109">Renvoi d’une liste d’utilisateurs filtrés dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cc196-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="cc196-110">L’applet de connexion **Set-Csuser** est également incluse dans l’ensemble des applets de connexion accessibles aux administrateurs de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="cc196-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="cc196-111">Toutefois, **Set-Csuser** ne peut pas être utilisé pour gérer Skype entreprise Online, à l’exception de la définition du paramètre _AudioVideoDisabled_ .</span><span class="sxs-lookup"><span data-stu-id="cc196-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="cc196-112">Si vous essayez d’exécuter l’applet de requête avec n’importe quel autre paramètre, le message d’erreur similaire à ce qui suit s’affiche : impossible de définir « SipAddress ».</span><span class="sxs-lookup"><span data-stu-id="cc196-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="cc196-113">Ce paramètre est limité dans PowerShell client distant.</span><span class="sxs-lookup"><span data-stu-id="cc196-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="cc196-114">Retourner des informations sur tous vos utilisateurs de Lync Online</span><span class="sxs-lookup"><span data-stu-id="cc196-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="cc196-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="cc196-115"></span></span>

<span data-ttu-id="cc196-116">Pour renvoyer des informations sur tous les utilisateurs qui ont été activés pour Skype entreprise Online, appelez l’applet [de contrôle Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sans aucun paramètre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="cc196-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="cc196-117">Pour renvoyer des informations pour un seul utilisateur sélectionné de manière aléatoire (par exemple, pour utiliser ce compte à des fins de test), appelez l’applet de requête **Get-CsOnlineUser** et définissez le paramètre de _résultats_ sur 1.</span><span class="sxs-lookup"><span data-stu-id="cc196-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="cc196-118">Cela amène l’applet de demande **Get-CsOnlineUser** à renvoyer des informations pour un seul utilisateur, quel que soit le nombre d’utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cc196-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="cc196-119">Pour renvoyer des informations pour cinq utilisateurs, définissez la valeur du paramètre _result_ sur 5.</span><span class="sxs-lookup"><span data-stu-id="cc196-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="cc196-120">Renvoyer des informations pour un utilisateur spécifique dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cc196-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="cc196-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="cc196-121"></span></span>

<span data-ttu-id="cc196-122">Il existe plusieurs façons de faire référence à un compte d’utilisateur spécifique lorsque vous appelez l’applet [de cmdlet Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) .</span><span class="sxs-lookup"><span data-stu-id="cc196-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="cc196-123">Vous pouvez utiliser le nom complet des services de domaine Active Directory (AD DS) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cc196-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="cc196-124">Vous pouvez utiliser l’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cc196-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="cc196-125">Vous pouvez utiliser le nom d’utilisateur principal (UPN) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cc196-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="cc196-126">Renvoi d’informations spécifiques à des utilisateurs spécifiques dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cc196-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="cc196-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="cc196-127"></span></span>

<span data-ttu-id="cc196-128">Par défaut, l’applet [de connexion Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) renvoie une quantité considérable d’informations pour chaque compte d’utilisateur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="cc196-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="cc196-129">Si vous êtes intéressé uniquement par un sous-ensemble de ces informations, canalisez les données renvoyées vers l’applet de cmdlet **Select-Object** .</span><span class="sxs-lookup"><span data-stu-id="cc196-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="cc196-130">Par exemple, cette commande renvoie toutes les données de l’utilisateur Ken Myer, puis utilise l’applet de commande **Select-Object** pour limiter les informations affichées à l’écran avec le nom d’affichage et le plan de numérotation de Ken.</span><span class="sxs-lookup"><span data-stu-id="cc196-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="cc196-131">La commande suivante renvoie le nom d’affichage et le plan de numérotation de tous vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cc196-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="cc196-132">Pour accéder aux propriétés d’un compte d’utilisateur Skype entreprise Online, utilisez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="cc196-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="cc196-133">Renvoi d’une liste d’utilisateurs filtrés dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cc196-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="cc196-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="cc196-134"></span></span>

<span data-ttu-id="cc196-135">À l’aide de l’applet de requête [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) et des paramètres _LdapFilter_ ou de _filtre_ , vous pouvez facilement renvoyer des informations sur un ensemble ciblé d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cc196-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="cc196-136">Par exemple, cette commande renvoie tous les utilisateurs qui travaillent dans le service Finances.</span><span class="sxs-lookup"><span data-stu-id="cc196-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="cc196-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc196-137">Related topics</span></span>
[<span data-ttu-id="cc196-138">Configurer votre ordinateur pour la gestion de Skype entreprise Online à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc196-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


