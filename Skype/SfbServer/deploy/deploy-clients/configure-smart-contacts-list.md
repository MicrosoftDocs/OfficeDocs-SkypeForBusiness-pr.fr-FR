---
title: Configurer liste de contacts actives dans Skype pour les clients d’entreprise
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Résumé : Découvrez comment activer la fonctionnalité de liste de contacts actives dans le Skype pour client d’entreprise.'
ms.openlocfilehash: 52de1eb889b1373dc6928c90a9e0e298f467d3fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212774"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="f42ec-103">Configurer liste de contacts actives dans Skype pour les clients d’entreprise</span><span class="sxs-lookup"><span data-stu-id="f42ec-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="f42ec-104">**Résumé :** Découvrez comment activer la fonctionnalité de liste de contacts actives dans le Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f42ec-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="f42ec-105">La fonctionnalité de liste de contacts dynamiques permet de remplir automatiquement les listes de contacts pour vos utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="f42ec-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="f42ec-106">Sur la première à l’aide de Skype pour les entreprises, votre les utilisateurs verront automatiquement constater des leur responsable et autres personnes de leur équipe.</span><span class="sxs-lookup"><span data-stu-id="f42ec-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="f42ec-107">Cette fonctionnalité est activée par défaut pour les utilisateurs d’Office 365, mais vous devez explicitement activer cette fonctionnalité pour vos utilisateurs locaux en configurant le paramètre de stratégie de client.</span><span class="sxs-lookup"><span data-stu-id="f42ec-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="f42ec-108">Lors de la configuration de cette fonctionnalité, rappelez-vous des points suivants :</span><span class="sxs-lookup"><span data-stu-id="f42ec-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="f42ec-109">Jusqu'à 13, les utilisateurs sont automatiquement ajoutés à la liste des contacts actives dans l’ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="f42ec-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="f42ec-110">Responsable</span><span class="sxs-lookup"><span data-stu-id="f42ec-110">Manager</span></span>

  2. <span data-ttu-id="f42ec-111">Contacts par ordre alphabétique</span><span class="sxs-lookup"><span data-stu-id="f42ec-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="f42ec-112">Pairs par ordre alphabétique</span><span class="sxs-lookup"><span data-stu-id="f42ec-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="f42ec-113">La première fois qu’un utilisateur se connecte, le groupe « Mon groupe » est créé.</span><span class="sxs-lookup"><span data-stu-id="f42ec-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="f42ec-114">Le groupe est automatiquement renseigné avec les personnes dans une relation de groupe AD de l’utilisateur en fonction de l’alias d’utilisateur renseigné dans le champ Gestionnaire.</span><span class="sxs-lookup"><span data-stu-id="f42ec-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="f42ec-115">Notez que les modifications apportées aux membres du groupe AD n’entraînent pas de mises à jour de Mon groupe une fois qu’il a été renseigné initialement.</span><span class="sxs-lookup"><span data-stu-id="f42ec-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="f42ec-116">Si un utilisateur supprime un contact ou le groupe, ni le contact ni le groupe n’est recréé.</span><span class="sxs-lookup"><span data-stu-id="f42ec-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="f42ec-117">Si le marquage automatique est activé, les contacts de la liste sont marqués en cas de changement de statut de présence.</span><span class="sxs-lookup"><span data-stu-id="f42ec-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="f42ec-118">Le marquage automatique est activé par défaut, mais vous pouvez choisir de le désactiver.</span><span class="sxs-lookup"><span data-stu-id="f42ec-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="f42ec-119">Tous les nouveaux utilisateurs du groupe seront informés de leur ajout à la liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="f42ec-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="f42ec-120">Les utilisateurs peuvent ajouter manuellement de nouveaux membres au groupe Mon groupe ou à d’autres groupes de leur choix.</span><span class="sxs-lookup"><span data-stu-id="f42ec-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="f42ec-121">Cette fonctionnalité n’est disponible que pour les utilisateurs qui se connectent pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="f42ec-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="f42ec-122">Si un utilisateur s’est déjà connecté à partir de n’importe d’un appareil, comme un appareil mobile ou un Mac, la fonctionnalité n’est pas activée pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f42ec-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="f42ec-123">Configuration de la liste de contacts dynamiques</span><span class="sxs-lookup"><span data-stu-id="f42ec-123">Configure Smart contacts list</span></span>

<span data-ttu-id="f42ec-124">Pour activer les fonctionnalités d’une liste de contacts dynamiques pour vos utilisateurs, vous devez suivre la procédure ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="f42ec-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="f42ec-125">Créer une nouvelle entrée CsClientPolicy et l’ajouter à la stratégie globale de clients.</span><span class="sxs-lookup"><span data-stu-id="f42ec-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="f42ec-126">Assurez-vous que la recherche dans un carnet d’adresses n’est configurée que pour la recherche web.</span><span class="sxs-lookup"><span data-stu-id="f42ec-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="f42ec-127">Créez une entrée de stratégie pour activer la liste de contacts dynamiques.</span><span class="sxs-lookup"><span data-stu-id="f42ec-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="f42ec-128">Pour créer une entrée de stratégie pour activer la fonctionnalité de liste de contacts actives, utilisez l’applet de commande [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) avec l’option EnableClientAutoPopulateWithTeam comme suit :</span><span class="sxs-lookup"><span data-stu-id="f42ec-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="f42ec-129">Ensuite, utilisez l’applet de commande [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) pour écrire les modifications dans la stratégie globale comme suit :</span><span class="sxs-lookup"><span data-stu-id="f42ec-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="f42ec-130">Vous pouvez éventuellement créer une stratégie pour désactiver le balisage automatique, comme suit :</span><span class="sxs-lookup"><span data-stu-id="f42ec-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="f42ec-131">Vous devez également définir le paramètre AddressBookAvailability pour la stratégie correspondant à WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="f42ec-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="f42ec-132">Pour plus d’informations, voir [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f42ec-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="f42ec-133">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="f42ec-133">Troubleshoot</span></span>

<span data-ttu-id="f42ec-134">Si la liste de contacts dynamiques ne fonctionne pas comme prévu, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="f42ec-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="f42ec-135">Vérifiez la configuration.</span><span class="sxs-lookup"><span data-stu-id="f42ec-135">Validate the configuration.</span></span> 

- <span data-ttu-id="f42ec-136">Vérifiez que les informations relatives à l’organisation AD sont renseignées.</span><span class="sxs-lookup"><span data-stu-id="f42ec-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="f42ec-137">Collecter Skype pour les journaux de client d’entreprise sur un nouvel utilisateur pour une analyse approfondie.</span><span class="sxs-lookup"><span data-stu-id="f42ec-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="f42ec-138">Vérifiez que le Skype pour l’interface utilisateur du client Business n’affiche pas un message il ne peut pas se connecter au carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="f42ec-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="f42ec-139">Pour vérifier la connectivité du carnet d’adresses, effectuez une recherche pour un utilisateur dans le Skype pour la barre de recherche Business client.</span><span class="sxs-lookup"><span data-stu-id="f42ec-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="f42ec-140">Problèmes de réplication AD DS peuvent entraîner des contacts pour être résolues lorsqu’un utilisateur tout d’abord se connecte à Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="f42ec-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


