---
title: Configurer une liste de contacts dynamiques dans les clients Skype entreprise
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
description: 'Résumé : Découvrez comment activer la fonctionnalité liste de contacts intelligents dans le client Skype entreprise.'
ms.openlocfilehash: 9db4e6616aa4c11be3ad2f9ee1cd92a0587b4e51
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768867"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="c3078-103">Configurer une liste de contacts dynamiques dans les clients Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="c3078-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="c3078-104">**Résumé :** Découvrez comment activer la fonctionnalité liste de contacts dynamiques dans le client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c3078-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="c3078-105">La fonctionnalité de liste de contacts dynamiques permet de remplir automatiquement les listes de contacts pour vos utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="c3078-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="c3078-106">Dès lors que vous utilisez Skype entreprise pour la première fois, vos utilisateurs voient automatiquement le responsable et les autres membres de leur équipe.</span><span class="sxs-lookup"><span data-stu-id="c3078-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="c3078-107">Cette fonctionnalité est activée par défaut pour les utilisateurs d’Office 365, mais vous devez activer explicitement cette fonctionnalité pour vos utilisateurs locaux en configurant le paramètre de stratégie client.</span><span class="sxs-lookup"><span data-stu-id="c3078-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="c3078-108">Lors de la configuration de cette fonctionnalité, rappelez-vous des points suivants :</span><span class="sxs-lookup"><span data-stu-id="c3078-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="c3078-109">Les utilisateurs de plus de 13 ans sont automatiquement ajoutés à la liste des contacts dynamiques dans l’ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="c3078-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="c3078-110">Responsable</span><span class="sxs-lookup"><span data-stu-id="c3078-110">Manager</span></span>

  2. <span data-ttu-id="c3078-111">Contacts par ordre alphabétique</span><span class="sxs-lookup"><span data-stu-id="c3078-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="c3078-112">Pairs par ordre alphabétique</span><span class="sxs-lookup"><span data-stu-id="c3078-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="c3078-113">La première fois qu’un utilisateur se connecte, le groupe « Mon groupe » est créé.</span><span class="sxs-lookup"><span data-stu-id="c3078-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="c3078-114">Le groupe est automatiquement rempli de personnes dans la relation de groupe publicitaire de l’utilisateur en fonction de l’alias d’utilisateur rempli dans le champ responsable.</span><span class="sxs-lookup"><span data-stu-id="c3078-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="c3078-115">Notez que les modifications apportées aux membres du groupe AD n’entraînent pas de mises à jour de Mon groupe une fois qu’il a été renseigné initialement.</span><span class="sxs-lookup"><span data-stu-id="c3078-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="c3078-116">Si un utilisateur supprime un contact ou le groupe, ni le contact ni le groupe n’est recréé.</span><span class="sxs-lookup"><span data-stu-id="c3078-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="c3078-117">Si le marquage automatique est activé, les contacts de la liste sont marqués en cas de changement de statut de présence.</span><span class="sxs-lookup"><span data-stu-id="c3078-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="c3078-118">Le marquage automatique est activé par défaut, mais vous pouvez choisir de le désactiver.</span><span class="sxs-lookup"><span data-stu-id="c3078-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="c3078-119">Tous les nouveaux utilisateurs du groupe seront informés de leur ajout à la liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="c3078-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="c3078-120">Les utilisateurs peuvent ajouter manuellement de nouveaux membres au groupe Mon groupe ou à d’autres groupes de leur choix.</span><span class="sxs-lookup"><span data-stu-id="c3078-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="c3078-121">Cette fonctionnalité n’est disponible que pour les utilisateurs qui se connectent pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="c3078-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="c3078-122">Si un utilisateur s’est déjà connecté à partir de n’importe d’un appareil, comme un appareil mobile ou un Mac, la fonctionnalité n’est pas activée pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c3078-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="c3078-123">Configuration de la liste de contacts dynamiques</span><span class="sxs-lookup"><span data-stu-id="c3078-123">Configure Smart contacts list</span></span>

<span data-ttu-id="c3078-124">Pour activer les fonctionnalités d’une liste de contacts dynamiques pour vos utilisateurs, vous devez suivre la procédure ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="c3078-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="c3078-125">Créez une nouvelle entrée CsClientPolicy et ajoutez-la à la stratégie client globale.</span><span class="sxs-lookup"><span data-stu-id="c3078-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="c3078-126">Assurez-vous que la recherche dans un carnet d’adresses n’est configurée que pour la recherche web.</span><span class="sxs-lookup"><span data-stu-id="c3078-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="c3078-127">Créez une entrée de stratégie pour activer la liste de contacts dynamiques.</span><span class="sxs-lookup"><span data-stu-id="c3078-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="c3078-128">Pour créer une entrée de stratégie permettant d’activer la fonctionnalité liste de contacts dynamiques, utilisez l’applet [de commande New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) avec l’option EnableClientAutoPopulateWithTeam comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3078-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="c3078-129">Ensuite, utilisez l’applet de passe [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) pour écrire les modifications apportées à la stratégie globale comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3078-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="c3078-130">Vous pouvez éventuellement créer une stratégie pour désactiver le balisage automatique, comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3078-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="c3078-131">Vous devez également définir le paramètre AddressBookAvailability pour la stratégie correspondant à WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="c3078-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="c3078-132">Pour plus d’informations, consultez la rubrique [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c3078-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="c3078-133">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="c3078-133">Troubleshoot</span></span>

<span data-ttu-id="c3078-134">Si la liste de contacts dynamiques ne fonctionne pas comme prévu, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="c3078-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="c3078-135">Vérifiez la configuration.</span><span class="sxs-lookup"><span data-stu-id="c3078-135">Validate the configuration.</span></span> 

- <span data-ttu-id="c3078-136">Vérifiez que les informations relatives à l’organisation AD sont renseignées.</span><span class="sxs-lookup"><span data-stu-id="c3078-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="c3078-137">Pour une analyse plus approfondie, le client Skype entreprise enregistre une connexion à un nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c3078-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="c3078-138">Confirmez que l’interface utilisateur du client Skype entreprise n’affiche aucun message indiquant qu’il n’est pas possible de se connecter au carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="c3078-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="c3078-139">Pour confirmer la connectivité du carnet d’adresses, recherchez un utilisateur dans la barre de recherche du client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c3078-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="c3078-140">Les problèmes de réplication AD DS peuvent entraîner la non-gestion des contacts lorsque l’utilisateur se connecte à Skype entreprise pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="c3078-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


