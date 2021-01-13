---
title: 'Client mobile : créer ou modifier la configuration des notifications Push'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: Les notifications Push et le centre d’échange de notifications Push (PNCH) sont deux éléments clés de la fonctionnalité de mobilité. Une notification push correspond au processus dans lequel un message est envoyé au centre d’échanges de notifications push. Ce message y est conservé jusqu’à ce qu’il puisse être remis au client mobile ou que le délai d’expiration soit dépassé.
ms.openlocfilehash: 0cd2b17f764891dbb1ad89ada27f6be0b6246ba0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810884"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="d5128-105">Client mobile : Créer ou modifier une configuration des notifications push</span><span class="sxs-lookup"><span data-stu-id="d5128-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="d5128-106">Les notifications Push et le centre d’échange de notifications Push (PNCH) sont deux éléments clés de la fonctionnalité de mobilité.</span><span class="sxs-lookup"><span data-stu-id="d5128-106">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature.</span></span> <span data-ttu-id="d5128-107">Une notification push correspond au processus dans lequel un message est envoyé au centre d’échanges de notifications push.</span><span class="sxs-lookup"><span data-stu-id="d5128-107">Push notification is the process where a message is sent to the PNCH.</span></span> <span data-ttu-id="d5128-108">Ce message y est conservé jusqu’à ce qu’il puisse être remis au client mobile ou que le délai d’expiration soit dépassé.</span><span class="sxs-lookup"><span data-stu-id="d5128-108">The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d5128-109">Le délai est défini au centre d’échanges de notifications push et ne peut pas être configuré par l’utilisateur ni par l’administrateur de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="d5128-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="d5128-110">Pour activer les notifications push, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d5128-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="d5128-111">**Étendue :** Notez l’étendue de cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5128-111">**Scope:** Note the scope for this policy.</span></span> <span data-ttu-id="d5128-112">Il peut être **Global**, qui s’applique à tous les utilisateurs dans ce déploiement, ou **Site**, qui est uniquement les utilisateurs affectés à des serveurs d’accueil dans le site spécifié.</span><span class="sxs-lookup"><span data-stu-id="d5128-112">It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d5128-113">Les paramètres de stratégie appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5128-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="d5128-114">La priorité de la stratégie est la : la stratégie utilisateur (la plus influente) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (la moins influente).</span><span class="sxs-lookup"><span data-stu-id="d5128-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="d5128-115">Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="d5128-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="d5128-116">Sélectionnez les services de notification push que vous voulez activer en cochant la case correspondante :</span><span class="sxs-lookup"><span data-stu-id="d5128-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="d5128-117">**Activer la notification Push De Microsoft** activera la notification Push au PNCH basé sur le cloud pour Windows Phone avec l’application Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="d5128-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="d5128-118">**Activer la notification Push Apple** activera la notification Push au PNCH Apple pour les appareils exécutant iOS d’Apple (par exemple, iPhone, iPad) et utilisant l’application Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="d5128-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="d5128-p105">Une fois que vous avez terminé les modifications de la stratégie, cliquez sur **Valider** pour enregistrer ces modifications. Si vous avez besoin de supprimer les modifications apportées, sélectionnez **Annuler**. Aucune modification ne sera enregistrée dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="d5128-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

