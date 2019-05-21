---
title: Client mobile création ou modification de la configuration de notifications de transmission
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: Les notifications Push et le centre d’échanges de notifications Push (Push Notification Clearing House, PNCH) sont deux éléments clés de la fonctionnalité de mobilité. Une notification Push correspond au processus dans lequel un message est envoyé au centre d’échanges de notifications Push. Ce message y est conservé jusqu’à ce qu’il puisse être remis au client mobile ou que le délai d’expiration soit dépassé.
ms.openlocfilehash: 3a15e88e40b37da4570d04a93ef13a793d6dabaf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300335"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="351d5-105">Client mobile : création ou modification d’une configuration des notifications Push</span><span class="sxs-lookup"><span data-stu-id="351d5-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="351d5-p102">Les notifications Push et le centre d’échanges de notifications Push (Push Notification Clearing House, PNCH) sont deux éléments clés de la fonctionnalité de mobilité. Une notification Push correspond au processus dans lequel un message est envoyé au centre d’échanges de notifications Push. Ce message y est conservé jusqu’à ce qu’il puisse être remis au client mobile ou que le délai d’expiration soit dépassé.</span><span class="sxs-lookup"><span data-stu-id="351d5-p102">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature. Push notification is the process where a message is sent to the PNCH. The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="351d5-109">Le délai est défini au centre d’échanges de notifications Push. Ni l’utilisateur ni l’administrateur de votre déploiement ne peut le configurer.</span><span class="sxs-lookup"><span data-stu-id="351d5-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="351d5-110">Pour activer les notifications Push, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="351d5-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="351d5-p103">**Étendue** : notez l’étendue de cette stratégie. Elle peut être définie sur **Globale**, concernant tous les utilisateurs dans ce déploiement, ou sur **Site**, auquel cas elle ne concerne que les utilisateurs attribués aux serveurs centraux dans le site.</span><span class="sxs-lookup"><span data-stu-id="351d5-p103">**Scope:** Note the scope for this policy. It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="351d5-p104">Les paramètres de stratégie qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. L’ordre de priorité est le suivant : les stratégies utilisateur (prioritaires) remplacent les stratégies de site. Les stratégies de site remplacent les stratégies globales (les moins prioritaires). Cela signifie que plus la définition de stratégie est proche de l’objet affecté par cette stratégie, plus l’impact de cette stratégie sur l’objet est important.</span><span class="sxs-lookup"><span data-stu-id="351d5-p104">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="351d5-116">Sélectionnez les services de notification Push à activer en activant la case à cocher correspondante :</span><span class="sxs-lookup"><span data-stu-id="351d5-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="351d5-117">**Activez la notification** d’appel Microsoft pour activer la notification de transmission vers le Cloud PNCH pour Windows Phone avec l’application Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="351d5-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="351d5-118">**Activer** les notifications de transmission d’Apple permet d’activer la notification de transmission sur l’Apple PNCH pour les appareils exécutant iOS d’Apple (par exemple, iPhone, iPad) et utilisant l’application Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="351d5-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="351d5-p105">Une fois que vous avez fini de modifier la stratégie, cliquez sur **Valider** pour enregistrer ces modifications. Si vous avez besoin de supprimer les modifications apportées, sélectionnez **Annuler**. Aucune modification n’est enregistrée dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="351d5-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

