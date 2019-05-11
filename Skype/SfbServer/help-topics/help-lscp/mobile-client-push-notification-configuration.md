---
title: Configuration des notifications Push Client mobile
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: d815bb271b35c93a9c8467a4d4ffa522834291ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911001"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="0b616-103">Client mobile : configuration des notifications push</span><span class="sxs-lookup"><span data-stu-id="0b616-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="0b616-104">Pour configurer les **notifications push Microsoft** et **les notifications push Apple**, vous devez créer une stratégie pour définir les types de notification push que vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="0b616-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="0b616-105">Dans l’écran configuration principale, vous pouvez cliquer sur **Actualiser** pour actualiser et remplir la liste des stratégies.</span><span class="sxs-lookup"><span data-stu-id="0b616-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="0b616-106">Une zone de recherche est fournie pour limiter la liste des stratégies affichées.</span><span class="sxs-lookup"><span data-stu-id="0b616-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="0b616-107">Lorsque vous tapez le nom que vous recherchez, la liste des stratégies restreint automatiquement.</span><span class="sxs-lookup"><span data-stu-id="0b616-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0b616-p102">Les paramètres de stratégie qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. L’ordre de priorité est le suivant : les stratégies utilisateur (prioritaires) remplacent les stratégies de site. Les stratégies de site remplacent les stratégies globales (les moins prioritaires). Cela signifie que plus la définition de stratégie est proche de l’objet affecté par cette stratégie, plus l’impact de cette stratégie sur l’objet est important.</span><span class="sxs-lookup"><span data-stu-id="0b616-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="0b616-111">Deux options sont disponibles pour la création d’une stratégie et de modification :</span><span class="sxs-lookup"><span data-stu-id="0b616-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="0b616-112">**Nouveau**: cliquez pour créer une nouvelle stratégie.</span><span class="sxs-lookup"><span data-stu-id="0b616-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="0b616-113">Vous devez fournir un site pour la stratégie s’applique à.</span><span class="sxs-lookup"><span data-stu-id="0b616-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="0b616-114">Puis, vous configurez les paramètres pour les notifications push.</span><span class="sxs-lookup"><span data-stu-id="0b616-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="0b616-115">**Configuration des notifications Push**, vous pouvez uniquement créer des stratégies pour les Sites que vous avez déjà créé.</span><span class="sxs-lookup"><span data-stu-id="0b616-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="0b616-116">**Modifier**: sélectionnez une stratégie, cliquez sur Modifier pour sélectionner une action à partir d’une liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="0b616-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="0b616-117">Vous ne pouvez modifier que les sites que vous avez déjà créé ou modifiez la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="0b616-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="0b616-118">**Afficher les détails...**: affiche des informations sur la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0b616-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="0b616-119">Vous serez en mesure d’apporter des modifications à la stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="0b616-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="0b616-120">**Sélectionner tout**: Si vous disposez d’un certain nombre de stratégies et que vous devez sélectionner toutes les stratégies, cliquez sur Sélectionner tout</span><span class="sxs-lookup"><span data-stu-id="0b616-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="0b616-121">**Supprimer**: supprime la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0b616-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="0b616-122">Supprime toutes les stratégies à l’aide de **toutes les sélectionner** et **Supprimer**</span><span class="sxs-lookup"><span data-stu-id="0b616-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="0b616-123">Vous ne pouvez pas supprimer la stratégie **globale** par défaut.</span><span class="sxs-lookup"><span data-stu-id="0b616-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="0b616-124">Si vous tentez de supprimer, vous êtes averti que la stratégie globale a été renvoyée pour les valeurs par défaut (autrement dit, tous les paramètres sont vides), mais la stratégie ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="0b616-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="0b616-125">Création d’une nouvelle stratégie ou modifier une stratégie existante est associé à deux actions :</span><span class="sxs-lookup"><span data-stu-id="0b616-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="0b616-126">**Valider** L’action de validation crée ou met à jour la stratégie et enregistre les modifications</span><span class="sxs-lookup"><span data-stu-id="0b616-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="0b616-127">**Annuler** L’action Annuler annule les modifications qui ont été apportées depuis la dernière opération de validation.</span><span class="sxs-lookup"><span data-stu-id="0b616-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="0b616-128">Si vous annulez, toutes les modifications apportées seront perdues.</span><span class="sxs-lookup"><span data-stu-id="0b616-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="0b616-129">Deux paramètres sont possibles pour la **Configuration des notifications Push**.</span><span class="sxs-lookup"><span data-stu-id="0b616-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="0b616-130">Les paramètres associés avec les services de notification push pour Microsoft et Apple.</span><span class="sxs-lookup"><span data-stu-id="0b616-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="0b616-131">Vous activez les notifications push pour chaque service en activant la case à cocher en regard du nom du service.</span><span class="sxs-lookup"><span data-stu-id="0b616-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="0b616-132">Vous pouvez désactiver la case à cocher en la sélectionnant pour décocher cette option.</span><span class="sxs-lookup"><span data-stu-id="0b616-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="0b616-133">Une fois vos sélections effectuées, vous validez ou annulez.</span><span class="sxs-lookup"><span data-stu-id="0b616-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="0b616-134">En cliquant sur Valider sera enregistrer les modifications apportées à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="0b616-134">Clicking commit will save the changes to the policy.</span></span>
  

