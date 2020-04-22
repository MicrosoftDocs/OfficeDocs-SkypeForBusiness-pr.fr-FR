---
title: Configurer la liste de contacts dynamiques dans les clients Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Résumé : Découvrez comment activer la fonctionnalité de liste de contacts dynamiques dans le client Skype entreprise.'
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776689"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="c92b1-103">Configurer la liste de contacts dynamiques dans les clients Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="c92b1-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="c92b1-104">**Résumé :** Découvrez comment activer la fonctionnalité de liste de contacts dynamiques dans le client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c92b1-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="c92b1-105">La fonctionnalité de liste de contacts intelligents autorise le remplissage automatique des listes de contacts pour vos utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="c92b1-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="c92b1-106">Lors de la première utilisation de Skype entreprise, vos utilisateurs verront automatiquement leur responsable et d’autres personnes de leur équipe.</span><span class="sxs-lookup"><span data-stu-id="c92b1-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="c92b1-107">Cette fonctionnalité est activée par défaut pour les utilisateurs de Microsoft 365 et Office 365, mais vous devez activer explicitement cette fonctionnalité pour vos utilisateurs locaux en configurant le paramètre de stratégie client.</span><span class="sxs-lookup"><span data-stu-id="c92b1-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="c92b1-108">Gardez les points suivants à l’esprit lors de la configuration de cette fonctionnalité :</span><span class="sxs-lookup"><span data-stu-id="c92b1-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="c92b1-109">Les utilisateurs, jusqu’à 13, sont automatiquement ajoutés à la liste de contacts dynamiques dans l’ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="c92b1-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="c92b1-110">Responsable</span><span class="sxs-lookup"><span data-stu-id="c92b1-110">Manager</span></span>

  2. <span data-ttu-id="c92b1-111">Commandes par ordre alphabétique</span><span class="sxs-lookup"><span data-stu-id="c92b1-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="c92b1-112">Pairs par ordre alphabétique</span><span class="sxs-lookup"><span data-stu-id="c92b1-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="c92b1-113">La première fois qu’un utilisateur se connecte, un nouveau groupe nommé mon groupe est créé.</span><span class="sxs-lookup"><span data-stu-id="c92b1-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="c92b1-114">Le groupe est rempli automatiquement avec les personnes appartenant à la relation de groupe Active Directory de l’utilisateur en fonction de l’alias d’utilisateur rempli dans le champ responsable.</span><span class="sxs-lookup"><span data-stu-id="c92b1-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="c92b1-115">Notez que les modifications apportées à l’appartenance au groupe AD ne provoquent pas de mises à jour de mon groupe une fois qu’il a été initialement rempli.</span><span class="sxs-lookup"><span data-stu-id="c92b1-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="c92b1-116">Si un utilisateur supprime un contact ou le groupe, ni le contact, ni le groupe ne sont recréés.</span><span class="sxs-lookup"><span data-stu-id="c92b1-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="c92b1-117">Si le balisage automatique est activé, les contacts de la liste sont balisés pour les modifications de présence.</span><span class="sxs-lookup"><span data-stu-id="c92b1-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="c92b1-118">Le balisage automatique est activé par défaut, mais vous pouvez choisir de le désactiver.</span><span class="sxs-lookup"><span data-stu-id="c92b1-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="c92b1-119">Tous les nouveaux utilisateurs du groupe sont informés qu’ils ont été ajoutés à la liste des contacts.</span><span class="sxs-lookup"><span data-stu-id="c92b1-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="c92b1-120">Les utilisateurs peuvent ajouter manuellement de nouveaux membres à leur groupe ou à d’autres groupes de leur choix.</span><span class="sxs-lookup"><span data-stu-id="c92b1-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="c92b1-121">Cette fonctionnalité ne fonctionne que pour les utilisateurs qui se connectent pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="c92b1-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="c92b1-122">Si un utilisateur s’est déjà connecté à partir de n’importe quel périphérique (y compris, par exemple, un appareil mobile ou un Mac), la fonctionnalité n’est pas activée pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c92b1-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="c92b1-123">Configurer la liste de contacts dynamiques</span><span class="sxs-lookup"><span data-stu-id="c92b1-123">Configure Smart contacts list</span></span>

<span data-ttu-id="c92b1-124">Pour activer la fonctionnalité de liste de contacts dynamiques pour vos utilisateurs, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c92b1-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="c92b1-125">Créer une nouvelle entrée CsClientPolicy et l’ajouter à la stratégie client globale.</span><span class="sxs-lookup"><span data-stu-id="c92b1-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="c92b1-126">Assurez-vous que la recherche de carnet d’adresses est configurée pour la recherche sur le Web uniquement.</span><span class="sxs-lookup"><span data-stu-id="c92b1-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="c92b1-127">Créer une entrée de stratégie pour activer la liste de contacts dynamiques</span><span class="sxs-lookup"><span data-stu-id="c92b1-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="c92b1-128">Pour créer une entrée de stratégie pour activer la fonctionnalité de liste de contacts dynamiques, utilisez la cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) avec l’option enableclientautopopulatewithteam, comme suit :</span><span class="sxs-lookup"><span data-stu-id="c92b1-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="c92b1-129">Ensuite, utilisez l’applet de commande [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) pour écrire les modifications apportées à la stratégie globale comme suit :</span><span class="sxs-lookup"><span data-stu-id="c92b1-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="c92b1-130">Vous pouvez éventuellement créer une stratégie pour désactiver le marquage automatique comme suit :</span><span class="sxs-lookup"><span data-stu-id="c92b1-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="c92b1-131">Vous devez également définir le paramètre AddressBookAvailability pour la stratégie correspondante sur WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="c92b1-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="c92b1-132">Pour plus d’informations, consultez la rubrique [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c92b1-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="c92b1-133">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="c92b1-133">Troubleshoot</span></span>

<span data-ttu-id="c92b1-134">Si la liste de contacts dynamiques ne fonctionne pas comme prévu, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="c92b1-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="c92b1-135">Validez la configuration.</span><span class="sxs-lookup"><span data-stu-id="c92b1-135">Validate the configuration.</span></span> 

- <span data-ttu-id="c92b1-136">Vérifiez que les informations relatives à l’organisation AD sont remplies.</span><span class="sxs-lookup"><span data-stu-id="c92b1-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="c92b1-137">Collecter les journaux client Skype entreprise sur un nouvel utilisateur pour une analyse plus poussée.</span><span class="sxs-lookup"><span data-stu-id="c92b1-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="c92b1-138">Vérifiez que l’interface utilisateur du client Skype entreprise n’affiche pas un message indiquant qu’il ne peut pas se connecter au carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="c92b1-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="c92b1-139">Pour confirmer la connectivité du carnet d’adresses, effectuez une recherche pour un utilisateur dans la barre de recherche client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c92b1-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="c92b1-140">Les problèmes de réplication AD DS peuvent empêcher la résolution des contacts lorsqu’un utilisateur se connecte d’abord à Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c92b1-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


