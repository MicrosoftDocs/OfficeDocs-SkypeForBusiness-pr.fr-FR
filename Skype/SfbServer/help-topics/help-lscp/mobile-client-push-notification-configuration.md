---
title: Configuration des notifications Push Client mobile
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Pour configurer les notifications push Microsoft et les notifications push Apple, vous devez créer une stratégie pour définir les types de notification push que vous avez besoin.
ms.openlocfilehash: 0c36696e8dbc26616a7b17918c63f3f40ab36fab
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220304"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="0a5ca-103">Client mobile : configuration des notifications push</span><span class="sxs-lookup"><span data-stu-id="0a5ca-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="0a5ca-104">Pour configurer les **notifications push Microsoft** et **les notifications push Apple**, vous devez créer une stratégie pour définir les types de notification push que vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="0a5ca-105">Dans l’écran configuration principale, vous pouvez cliquer sur **Actualiser** pour actualiser et remplir la liste des stratégies.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="0a5ca-106">Une zone de recherche est fournie pour limiter la liste des stratégies affichées.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="0a5ca-107">Lorsque vous tapez le nom que vous recherchez, la liste des stratégies restreint automatiquement.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0a5ca-p102">Les paramètres de stratégie qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. L’ordre de priorité est le suivant : les stratégies utilisateur (prioritaires) remplacent les stratégies de site. Les stratégies de site remplacent les stratégies globales (les moins prioritaires). Cela signifie que plus la définition de stratégie est proche de l’objet affecté par cette stratégie, plus l’impact de cette stratégie sur l’objet est important.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="0a5ca-111">Deux options sont disponibles pour la création d’une stratégie et de modification :</span><span class="sxs-lookup"><span data-stu-id="0a5ca-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="0a5ca-112">**Nouveau**: cliquez pour créer une nouvelle stratégie.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="0a5ca-113">Vous devez fournir un site pour la stratégie s’applique à.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="0a5ca-114">Puis, vous configurez les paramètres pour les notifications push.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="0a5ca-115">**Configuration des notifications Push**, vous pouvez uniquement créer des stratégies pour les Sites que vous avez déjà créé.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="0a5ca-116">**Modifier**: sélectionnez une stratégie, cliquez sur Modifier pour sélectionner une action à partir d’une liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="0a5ca-117">Vous ne pouvez modifier que les sites que vous avez déjà créé ou modifiez la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="0a5ca-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="0a5ca-118">**Afficher les détails...**: affiche des informations sur la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="0a5ca-119">Vous serez en mesure d’apporter des modifications à la stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="0a5ca-120">**Sélectionner tout**: Si vous disposez d’un certain nombre de stratégies et que vous devez sélectionner toutes les stratégies, cliquez sur Sélectionner tout</span><span class="sxs-lookup"><span data-stu-id="0a5ca-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="0a5ca-121">**Supprimer**: supprime la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="0a5ca-122">Supprime toutes les stratégies à l’aide de **toutes les sélectionner** et **Supprimer**</span><span class="sxs-lookup"><span data-stu-id="0a5ca-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="0a5ca-123">Vous ne pouvez pas supprimer la stratégie **globale** par défaut.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="0a5ca-124">Si vous tentez de supprimer, vous êtes averti que la stratégie globale a été renvoyée pour les valeurs par défaut (autrement dit, tous les paramètres sont vides), mais la stratégie ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="0a5ca-125">Création d’une nouvelle stratégie ou modifier une stratégie existante est associé à deux actions :</span><span class="sxs-lookup"><span data-stu-id="0a5ca-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="0a5ca-126">**Valider** L’action de validation crée ou met à jour la stratégie et enregistre les modifications</span><span class="sxs-lookup"><span data-stu-id="0a5ca-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="0a5ca-127">**Annuler** L’action Annuler annule les modifications qui ont été apportées depuis la dernière opération de validation.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="0a5ca-128">Si vous annulez, toutes les modifications apportées seront perdues.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="0a5ca-129">Deux paramètres sont possibles pour la **Configuration des notifications Push**.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="0a5ca-130">Les paramètres associés avec les services de notification push pour Microsoft et Apple.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="0a5ca-131">Vous activez les notifications push pour chaque service en activant la case à cocher en regard du nom du service.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="0a5ca-132">Vous pouvez désactiver la case à cocher en la sélectionnant pour décocher cette option.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="0a5ca-133">Une fois vos sélections effectuées, vous validez ou annulez.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="0a5ca-134">En cliquant sur Valider sera enregistrer les modifications apportées à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="0a5ca-134">Clicking commit will save the changes to the policy.</span></span>
  

