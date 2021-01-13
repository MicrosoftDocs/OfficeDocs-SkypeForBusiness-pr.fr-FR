---
title: Configuration des notifications Push du client mobile
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Pour configurer les notifications push Microsoft et les notifications push Apple, vous devez créer une stratégie pour définir les types de notification push dont vous avez besoin.
ms.openlocfilehash: 693b954fffbbce56a2d95ce29128482937b6fa05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836674"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="88cb3-103">Client mobile : configuration des notifications push</span><span class="sxs-lookup"><span data-stu-id="88cb3-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="88cb3-104">Pour configurer les **notifications push Microsoft** et les **notifications push Apple**, vous devez créer une stratégie pour définir les types de notification push dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="88cb3-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="88cb3-p101">Dans l’écran de configuration principal, vous pouvez cliquer sur **Actualiser** pour actualiser et remplir à nouveau la liste des stratégies. Une zone de recherche permet de réduire la liste des stratégies affichées. À mesure que vous tapez le nom à rechercher, la liste des stratégies est automatiquement réduite.</span><span class="sxs-lookup"><span data-stu-id="88cb3-p101">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies. A search box is provided for narrowing the list of displayed policies. As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="88cb3-108">Les paramètres de stratégie appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="88cb3-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="88cb3-109">La priorité de la stratégie est la : la stratégie utilisateur (la plus influente) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (la moins influente).</span><span class="sxs-lookup"><span data-stu-id="88cb3-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="88cb3-110">Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="88cb3-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="88cb3-111">Deux procédures sont possibles pour créer et modifier des stratégies :</span><span class="sxs-lookup"><span data-stu-id="88cb3-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="88cb3-p103">**Nouveau** : cliquez pour créer une stratégie. Vous devez fournir un site auquel appliquer cette stratégie. Vous configurez ensuite les paramètres pour la notification push. Pour **Configuration des notifications push**, vous pouvez créer des stratégies uniquement pour des sites que vous avez déjà créés.</span><span class="sxs-lookup"><span data-stu-id="88cb3-p103">**New**: Click to create a new policy. You must provide a site for the policy to apply to. You then configure the settings for the push notification. For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="88cb3-p104">**Modifier** : sélectionnez une stratégie et cliquez sur Modifier pour sélectionner une action dans une liste déroulante. Vous pouvez modifier uniquement des sites que vous avez déjà créés ou modifier la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="88cb3-p104">**Edit**: Select a policy and click Edit to select an action from a drop-down. You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="88cb3-p105">**Afficher les détails…**  : affiche des informations sur la stratégie actuellement sélectionnée. Vous serez en mesure d’apporter des modifications à la stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="88cb3-p105">**Show details…**: Displays information about the currently selected policy. You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="88cb3-120">**Sélectionner tout** : si vous disposez de plusieurs stratégies et devez sélectionner toutes les stratégies, cliquez sur Sélectionner tout.</span><span class="sxs-lookup"><span data-stu-id="88cb3-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="88cb3-p106">**Supprimer** : permet de supprimer la stratégie sélectionnée. Utilisez **Sélectionner tout** et **Supprimer** pour supprimer toutes les stratégies.</span><span class="sxs-lookup"><span data-stu-id="88cb3-p106">**Delete**: Will remove the selected policy. Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="88cb3-p107">Vous ne pouvez pas supprimer la stratégie **globale** par défaut. Si vous tentez de la supprimer, il vous est notifié que les valeurs par défaut de la stratégie globale ont été rétablies (tous les paramètres sont désactivés), mais que la stratégie ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="88cb3-p107">You cannot delete the default **Global** policy. If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="88cb3-125">La création d’une stratégie et la modification d’une stratégie existante sont associées à deux opérations :</span><span class="sxs-lookup"><span data-stu-id="88cb3-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="88cb3-126">**Commit** L’action de validation crée ou met à jour la stratégie et enregistre les modifications</span><span class="sxs-lookup"><span data-stu-id="88cb3-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="88cb3-127">**Annuler** L’action d’annulation annule toutes les modifications qui ont été apportées depuis la dernière action de validation.</span><span class="sxs-lookup"><span data-stu-id="88cb3-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="88cb3-128">Si vous annulez, toutes les modifications apportées seront perdues.</span><span class="sxs-lookup"><span data-stu-id="88cb3-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="88cb3-p109">Deux paramètres sont possibles pour **Configuration des notifications push**. Les paramètres sont associés aux services de notification push pour Microsoft et Apple. Vous pouvez activer la notification push pour l’un ou l’autre service en activant la case à cocher en regard du nom du service. Vous pouvez désactiver la case à cocher en cliquant dessus à nouveau. Une fois vos sélections effectuées, vous pouvez valider ou annuler. Cliquez sur Valider pour enregistrer les modifications apportées à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="88cb3-p109">Two settings are possible for **Push Notification Configuration**. The settings are associated with the push notification services for Microsoft and for Apple. You enable push notification for either service by selecting the check box next to the name of the service. You can clear the check box by selecting it to clear it. Once you have made your selections, you either commit or cancel. Clicking commit will save the changes to the policy.</span></span>
  

