---
title: Configurer la liste de contacts intelligents dans les clients Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Résumé : Découvrez comment activer la fonctionnalité liste de contacts intelligents dans le client Skype Entreprise.'
ms.openlocfilehash: d995d2addf8b774ebad9945b3f35f07ddb431855
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805774"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="08687-103">Configurer la liste de contacts intelligents dans les clients Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="08687-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="08687-104">**Résumé :** Découvrez comment activer la fonctionnalité de liste de contacts intelligents dans le client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="08687-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="08687-105">La fonctionnalité liste de contacts actifs permet à vos utilisateurs finaux d’avoir une population automatique de listes de contacts.</span><span class="sxs-lookup"><span data-stu-id="08687-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="08687-106">Lors de la première utilisation de Skype Entreprise, vos utilisateurs voient automatiquement leur responsable et d’autres personnes dans leur équipe.</span><span class="sxs-lookup"><span data-stu-id="08687-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="08687-107">Cette fonctionnalité est activée par défaut pour les utilisateurs de Microsoft 365 et Office 365, mais vous devez l’activer explicitement pour vos utilisateurs locaux en configurant le paramètre de stratégie du client.</span><span class="sxs-lookup"><span data-stu-id="08687-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="08687-108">Gardez à l’esprit les questions suivantes lors de la configuration de cette fonctionnalité :</span><span class="sxs-lookup"><span data-stu-id="08687-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="08687-109">Les utilisateurs, jusqu’à 13, sont automatiquement ajoutés à la liste de contacts actifs dans l’ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="08687-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="08687-110">Manager</span><span class="sxs-lookup"><span data-stu-id="08687-110">Manager</span></span>

  2. <span data-ttu-id="08687-111">Directs par ordre alphabétique</span><span class="sxs-lookup"><span data-stu-id="08687-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="08687-112">Homologues dans l’ordre alphabétique</span><span class="sxs-lookup"><span data-stu-id="08687-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="08687-113">La première fois qu’un utilisateur se connecte, un nouveau groupe, nommé Mon groupe, est créé.</span><span class="sxs-lookup"><span data-stu-id="08687-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="08687-114">Le groupe est automatiquement rempli avec des personnes dans la relation de groupe AD de l’utilisateur en fonction de l’alias utilisateur rempli dans le champ Gestionnaire.</span><span class="sxs-lookup"><span data-stu-id="08687-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="08687-115">Notez que les modifications apportées à l’appartenance au groupe AD n’entraînent pas de mises à jour du groupe Mon groupe une fois qu’il est initialement rempli.</span><span class="sxs-lookup"><span data-stu-id="08687-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="08687-116">Si un utilisateur supprime un contact ou le groupe, ni le contact ni le groupe ne sont re-créés.</span><span class="sxs-lookup"><span data-stu-id="08687-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="08687-117">Si le marquage automatique est allumé, les contacts de la liste sont marqués pour les modifications de présence.</span><span class="sxs-lookup"><span data-stu-id="08687-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="08687-118">Le marquage automatique est désactivé par défaut, mais vous pouvez choisir de le désactiver.</span><span class="sxs-lookup"><span data-stu-id="08687-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="08687-119">Tous les nouveaux utilisateurs du groupe seront informés qu’ils ont été ajoutés à la liste des contacts.</span><span class="sxs-lookup"><span data-stu-id="08687-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="08687-120">Les utilisateurs peuvent ajouter manuellement de nouveaux membres à leur groupe Mon groupe ou à d’autres groupes de leur choix.</span><span class="sxs-lookup"><span data-stu-id="08687-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="08687-121">Cette fonctionnalité ne fonctionne que pour les utilisateurs qui se sont signés pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="08687-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="08687-122">Si un utilisateur s’est précédemment connecté à partir d’un appareil, y compris, par exemple, un appareil mobile ou un Mac, la fonctionnalité n’est pas activée pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="08687-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="08687-123">Configuration de la liste de contacts dynamiques</span><span class="sxs-lookup"><span data-stu-id="08687-123">Configure Smart contacts list</span></span>

<span data-ttu-id="08687-124">Pour activer la fonctionnalité liste de contacts actifs pour vos utilisateurs, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="08687-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="08687-125">Créez une entrée CsClientPolicy et ajoutez-la à la stratégie de client globale.</span><span class="sxs-lookup"><span data-stu-id="08687-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="08687-126">Assurez-vous que la recherche de carnet d’adresses est configurée pour la recherche web uniquement.</span><span class="sxs-lookup"><span data-stu-id="08687-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="08687-127">Créer une entrée de stratégie pour activer la liste de contacts intelligents</span><span class="sxs-lookup"><span data-stu-id="08687-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="08687-128">Pour créer une entrée de stratégie afin d’activer la fonctionnalité liste de contacts intelligents, utilisez l’cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) avec l’option EnableClientAutoPopulateWithTeam comme suit :</span><span class="sxs-lookup"><span data-stu-id="08687-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="08687-129">Ensuite, utilisez [l’cmdlet Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) pour écrire les modifications apportées à la stratégie globale comme suit :</span><span class="sxs-lookup"><span data-stu-id="08687-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="08687-130">Vous pouvez éventuellement créer une stratégie pour désactiver le marquage automatique comme suit :</span><span class="sxs-lookup"><span data-stu-id="08687-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="08687-131">Vous devez également définir le paramètre AddressBookAvailability pour la stratégie correspondante sur WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="08687-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="08687-132">Pour plus d’informations, [voir Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="08687-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="08687-133">Résoudre les problèmes</span><span class="sxs-lookup"><span data-stu-id="08687-133">Troubleshoot</span></span>

<span data-ttu-id="08687-134">Si la liste de contacts intelligents ne fonctionne pas comme prévu, vérifiez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="08687-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="08687-135">Validez la configuration.</span><span class="sxs-lookup"><span data-stu-id="08687-135">Validate the configuration.</span></span> 

- <span data-ttu-id="08687-136">Confirmez que les informations de l’organisation AD sont remplies.</span><span class="sxs-lookup"><span data-stu-id="08687-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="08687-137">Collectez les journaux du client Skype Entreprise sur un nouvel utilisateur pour une analyse plus approfondie.</span><span class="sxs-lookup"><span data-stu-id="08687-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="08687-138">Confirmez que l’interface utilisateur du client Skype Entreprise n’affiche pas de message pour vous dire qu’elle ne peut pas se connecter au carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="08687-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="08687-139">Pour confirmer la connectivité du carnet d’adresses, recherchez un utilisateur dans la barre de recherche du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="08687-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="08687-140">Les problèmes de réplication AD DS peuvent entraîner la non-résolue des contacts lorsqu’un utilisateur se signe pour la première fois dans Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="08687-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


