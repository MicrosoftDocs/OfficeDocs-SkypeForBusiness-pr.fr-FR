---
title: Gérer les comptes utilisateur
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
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
description: Utilisez l’applet de commande Get-CsOnlineUser dans Windows PowerShell pour obtenir des informations sur Skype de votre organisation pour les utilisateurs professionnels en ligne.
ms.openlocfilehash: 6c0ea2383e26b7b54eceab3a9adf71477fdc6e9a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244386"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="a85bf-103">Gérer les comptes utilisateur</span><span class="sxs-lookup"><span data-stu-id="a85bf-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="a85bf-104">Gérer les comptes utilisateur</span><span class="sxs-lookup"><span data-stu-id="a85bf-104">Manage user accounts</span></span>

<span data-ttu-id="a85bf-105">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="a85bf-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="a85bf-106">Retourner des informations sur tous vos utilisateurs de Lync Online</span><span class="sxs-lookup"><span data-stu-id="a85bf-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="a85bf-107">Retourner des informations pour un utilisateur spécifique Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="a85bf-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="a85bf-108">Retourner des informations spécifiques pour des utilisateurs spécifiques Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="a85bf-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="a85bf-109">Renvoyer la liste filtrée des utilisateurs dans Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="a85bf-109">Return a filtered list of users in Skype for Business Online </span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="a85bf-110">L’applet de commande **Set-CsUser** est également inclus dans l’ensemble des applets de commande disponibles pour Skype pour les administrateurs d’entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="a85bf-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="a85bf-111">Toutefois, **Set-CsUser** ne peut pas être utilisé actuellement gestion Skype pour Business Online, à l’exception de la définition du paramètre _AudioVideoDisabled_ .</span><span class="sxs-lookup"><span data-stu-id="a85bf-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="a85bf-112">Si vous essayez d’exécuter l’applet de commande avec aucun autre paramètre, l’opération échoue et un message d’erreur semblable à ceci : Impossible de définir « SipAddress ».</span><span class="sxs-lookup"><span data-stu-id="a85bf-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="a85bf-113">Ce paramètre est limité à distance PowerShell client.</span><span class="sxs-lookup"><span data-stu-id="a85bf-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="a85bf-114">Retourner des informations sur tous vos utilisateurs de Lync Online</span><span class="sxs-lookup"><span data-stu-id="a85bf-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="a85bf-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="a85bf-115"></span></span>

<span data-ttu-id="a85bf-116">Pour retourner des informations sur tous les utilisateurs qui ont été activés pour Skype pour Business Online, appelez la cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sans aucun paramètre supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="a85bf-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```
Get-CsOnlineUser
```

<span data-ttu-id="a85bf-117">Pour retourner des informations pour un utilisateur unique, sélectionnée aléatoirement (par exemple, pour utiliser ce compte à des fins de test), appelez la cmdlet **Get-CsOnlineUser** et définissez le paramètre _ResultSize_ 1.</span><span class="sxs-lookup"><span data-stu-id="a85bf-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="a85bf-118">L’applet de commande **Get-CsOnlineUser** renvoyer des informations pour un seul utilisateur, quel que soit le nombre d’utilisateurs dans votre organisation à l’origine.</span><span class="sxs-lookup"><span data-stu-id="a85bf-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="a85bf-119">Pour retourner des informations pour les utilisateurs de cinq, définissez la valeur du paramètre _ResultSize_ à 5.</span><span class="sxs-lookup"><span data-stu-id="a85bf-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="a85bf-120">Retourner des informations pour un utilisateur spécifique Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="a85bf-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="a85bf-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="a85bf-121"></span></span>

<span data-ttu-id="a85bf-122">Il existe plusieurs manières de faire référence à un compte d’utilisateur spécifique lorsque vous appelez l’applet de commande [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) .</span><span class="sxs-lookup"><span data-stu-id="a85bf-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="a85bf-123">Vous pouvez utiliser le nom complet de Services de domaine Active Directory (AD DS) de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a85bf-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="a85bf-124">Vous pouvez utiliser l’adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a85bf-124">You can use the user's SIP address.</span></span>

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="a85bf-125">Vous pouvez utiliser le nom principal de l’utilisateur de l’utilisateur (UPN).</span><span class="sxs-lookup"><span data-stu-id="a85bf-125">You can use the user's user principal name (UPN).</span></span>

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="a85bf-126">Retourner des informations spécifiques pour des utilisateurs spécifiques Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="a85bf-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="a85bf-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="a85bf-127"></span></span>

<span data-ttu-id="a85bf-128">Par défaut, l’applet de commande [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) renvoie une grande quantité d’informations pour chaque Skype Business en ligne compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a85bf-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="a85bf-129">Si vous êtes intéressé par uniquement un sous-ensemble de ces informations, redirigez les données retournées à la cmdlet **Select-Object** .</span><span class="sxs-lookup"><span data-stu-id="a85bf-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="a85bf-130">Par exemple, cette commande renvoie toutes les données de l’utilisateur Ken Myer, puis utilise la cmdlet **Select-Object** pour limiter les informations affichée à l’écran pour le nom complet de domaine Active Directory de Ken et le plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="a85bf-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="a85bf-131">La commande suivante renvoie le nom complet et la numérotation planifier pour tous vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a85bf-131">The following command returns the display name and dial plan for all your users.</span></span>

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="a85bf-132">Pour rechercher les propriétés d’un Skype Business en ligne compte d’utilisateur, utilisez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="a85bf-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="a85bf-133">Renvoyer la liste filtrée des utilisateurs dans Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="a85bf-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="a85bf-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="a85bf-134"></span></span>

<span data-ttu-id="a85bf-135">À l’aide de l’applet de commande [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) et les paramètres _LdapFilter_ ou de _filtre_ , vous pouvez facilement revenir plus d’informations sur un ensemble d’utilisateurs ciblé.</span><span class="sxs-lookup"><span data-stu-id="a85bf-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="a85bf-136">Par exemple, cette commande retourne tous les utilisateurs qui travaillent dans le service Finance.</span><span class="sxs-lookup"><span data-stu-id="a85bf-136">For example, this command returns all the users who work in the Finance department.</span></span>

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="a85bf-137">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a85bf-137">Related topics</span></span>
[<span data-ttu-id="a85bf-138">Configurer votre ordinateur pour Skype pour la gestion en ligne à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a85bf-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


