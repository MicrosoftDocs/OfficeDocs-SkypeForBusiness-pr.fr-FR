---
title: Configuration de la notification Poussée du client mobile
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Pour configurer les notifications de transmission de Microsoft et les notifications de type Apple, vous devez créer une stratégie pour définir les types de notifications de transmission dont vous avez besoin.
ms.openlocfilehash: 0211b3a8306297bd68402ad47d3c243541adf2bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300328"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="843e1-103">Client mobile : configuration des notifications push</span><span class="sxs-lookup"><span data-stu-id="843e1-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="843e1-104">Pour configurer les notifications de **transmission de Microsoft** et les notifications de **type Apple**, vous devez créer une stratégie pour définir les types de notifications de transmission dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="843e1-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="843e1-105">Dans l’écran Configuration principale, vous pouvez cliquer \*\*\*\* sur Actualiser pour actualiser et remplir de nouveau la liste des stratégies.</span><span class="sxs-lookup"><span data-stu-id="843e1-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="843e1-106">Une zone de recherche est proposée pour affiner la liste des stratégies affichées.</span><span class="sxs-lookup"><span data-stu-id="843e1-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="843e1-107">À mesure que vous tapez le nom que vous recherchez, la liste des stratégies est affinée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="843e1-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="843e1-p102">Les paramètres de stratégie qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. L’ordre de priorité est le suivant : les stratégies utilisateur (prioritaires) remplacent les stratégies de site. Les stratégies de site remplacent les stratégies globales (les moins prioritaires). Cela signifie que plus la définition de stratégie est proche de l’objet affecté par cette stratégie, plus l’impact de cette stratégie sur l’objet est important.</span><span class="sxs-lookup"><span data-stu-id="843e1-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="843e1-111">Deux options sont disponibles pour la création et la modification de la stratégie:</span><span class="sxs-lookup"><span data-stu-id="843e1-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="843e1-112">**Nouveau**: cliquez pour créer une nouvelle stratégie.</span><span class="sxs-lookup"><span data-stu-id="843e1-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="843e1-113">Vous devez fournir un site pour lequel la stratégie doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="843e1-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="843e1-114">Vous configurez ensuite les paramètres de notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="843e1-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="843e1-115">Pour la configuration des notifications de **transmission**, vous pouvez uniquement créer des stratégies pour les sites que vous avez déjà créés.</span><span class="sxs-lookup"><span data-stu-id="843e1-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="843e1-116">**Modification**: sélectionnez une stratégie, puis cliquez sur modifier pour sélectionner une action dans une liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="843e1-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="843e1-117">Vous pouvez uniquement modifier les sites que vous avez déjà créés ou que vous modifiez la stratégie globale:</span><span class="sxs-lookup"><span data-stu-id="843e1-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="843e1-118">**Afficher les détails...**: affiche des informations sur la stratégie actuellement sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="843e1-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="843e1-119">Vous serez en mesure d’apporter des modifications à la stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="843e1-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="843e1-120">**Sélectionner tout**: Si vous avez plusieurs stratégies et que vous avez besoin de sélectionner toutes les stratégies, cliquez sur Sélectionner tout.</span><span class="sxs-lookup"><span data-stu-id="843e1-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="843e1-121">**Supprimer**: va supprimer la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="843e1-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="843e1-122">L’option **Sélectionner tout** et **supprimer** entraîne la suppression de toutes les stratégies</span><span class="sxs-lookup"><span data-stu-id="843e1-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="843e1-123">Vous ne pouvez pas supprimer la stratégie **globale** par défaut.</span><span class="sxs-lookup"><span data-stu-id="843e1-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="843e1-124">Si vous essayez de la supprimer, vous serez averti que la stratégie globale a été renvoyée aux valeurs par défaut (c’est-à-dire que tous les paramètres sont effacés), mais que la stratégie ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="843e1-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="843e1-125">La création d’une stratégie ou la modification d’une stratégie existante est associée à deux actions:</span><span class="sxs-lookup"><span data-stu-id="843e1-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="843e1-126">**Valider** L’action valider crée ou met à jour la stratégie et enregistre les modifications.</span><span class="sxs-lookup"><span data-stu-id="843e1-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="843e1-127">**Annuler** L’action annuler ignore toutes les modifications apportées depuis la dernière action de validation.</span><span class="sxs-lookup"><span data-stu-id="843e1-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="843e1-128">Si vous annulez, toutes les modifications apportées seront perdues.</span><span class="sxs-lookup"><span data-stu-id="843e1-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="843e1-129">Deux paramètres sont possibles pour la configuration des notifications de **transmission**.</span><span class="sxs-lookup"><span data-stu-id="843e1-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="843e1-130">Les paramètres sont associés aux services de notifications de transmission pour Microsoft et pour Apple.</span><span class="sxs-lookup"><span data-stu-id="843e1-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="843e1-131">Activez l’option notifications de transmission pour les deux services en activant la case à cocher en regard du nom du service.</span><span class="sxs-lookup"><span data-stu-id="843e1-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="843e1-132">Vous pouvez désactiver la case à cocher en la sélectionnant.</span><span class="sxs-lookup"><span data-stu-id="843e1-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="843e1-133">Une fois que vous avez effectué vos sélections, vous validez ou annulez.</span><span class="sxs-lookup"><span data-stu-id="843e1-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="843e1-134">Le fait de cliquer sur valider enregistre les modifications apportées à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="843e1-134">Clicking commit will save the changes to the policy.</span></span>
  

