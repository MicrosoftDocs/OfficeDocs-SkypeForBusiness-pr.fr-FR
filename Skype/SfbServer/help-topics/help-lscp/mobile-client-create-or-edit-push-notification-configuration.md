---
title: Client mobile création ou modification de la configuration de notifications de transmission
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: Les notifications Push et le centre d’échanges de notifications Push (Push Notification Clearing House, PNCH) sont deux éléments clés de la fonctionnalité de mobilité. Une notification Push correspond au processus dans lequel un message est envoyé au centre d’échanges de notifications Push. Ce message y est conservé jusqu’à ce qu’il puisse être remis au client mobile ou que le délai d’expiration soit dépassé.
ms.openlocfilehash: 5c7d78174ca4cfe180742fa73a801704cb85997c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293430"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Client mobile : création ou modification d’une configuration des notifications Push
 
Les notifications Push et le centre d’échanges de notifications Push (Push Notification Clearing House, PNCH) sont deux éléments clés de la fonctionnalité de mobilité. Une notification Push correspond au processus dans lequel un message est envoyé au centre d’échanges de notifications Push. Ce message y est conservé jusqu’à ce qu’il puisse être remis au client mobile ou que le délai d’expiration soit dépassé. 
  
> [!NOTE]
> Le délai est défini au centre d’échanges de notifications Push. Ni l’utilisateur ni l’administrateur de votre déploiement ne peut le configurer. 
  
Pour activer les notifications Push, procédez comme suit :
  
1. **Étendue** : notez l’étendue de cette stratégie. Elle peut être définie sur **Globale**, concernant tous les utilisateurs dans ce déploiement, ou sur **Site**, auquel cas elle ne concerne que les utilisateurs attribués aux serveurs centraux dans le site.
    
    > [!IMPORTANT]
    > Les paramètres de stratégie qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. L’ordre de priorité est le suivant : les stratégies utilisateur (prioritaires) remplacent les stratégies de site. Les stratégies de site remplacent les stratégies globales (les moins prioritaires). Cela signifie que plus la définition de stratégie est proche de l’objet affecté par cette stratégie, plus l’impact de cette stratégie sur l’objet est important. 
  
2. Sélectionnez les services de notification Push à activer en activant la case à cocher correspondante :
    
   - **Activez la notification** d’appel Microsoft pour activer la notification de transmission vers le Cloud PNCH pour Windows Phone avec l’application Skype entreprise
    
   - **Activer** les notifications de transmission d’Apple permet d’activer la notification de transmission sur l’Apple PNCH pour les appareils exécutant iOS d’Apple (par exemple, iPhone, iPad) et utilisant l’application Skype entreprise.
    
3. Une fois que vous avez fini de modifier la stratégie, cliquez sur **Valider** pour enregistrer ces modifications. Si vous avez besoin de supprimer les modifications apportées, sélectionnez **Annuler**. Aucune modification n’est enregistrée dans la stratégie.
    

