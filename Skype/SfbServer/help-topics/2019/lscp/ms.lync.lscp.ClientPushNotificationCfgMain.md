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
# <a name="mobile-client-push-notification-configuration"></a>Client mobile : configuration des notifications push
 
Pour configurer les notifications de **transmission de Microsoft** et les notifications de **type Apple**, vous devez créer une stratégie pour définir les types de notifications de transmission dont vous avez besoin.
  
Dans l’écran Configuration principale, vous pouvez cliquer **** sur Actualiser pour actualiser et remplir de nouveau la liste des stratégies. Une zone de recherche est proposée pour affiner la liste des stratégies affichées. À mesure que vous tapez le nom que vous recherchez, la liste des stratégies est affinée automatiquement.
  
> [!IMPORTANT]
> Les paramètres de stratégie qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. L’ordre de priorité est le suivant : les stratégies utilisateur (prioritaires) remplacent les stratégies de site. Les stratégies de site remplacent les stratégies globales (les moins prioritaires). Cela signifie que plus la définition de stratégie est proche de l’objet affecté par cette stratégie, plus l’impact de cette stratégie sur l’objet est important. 
  
Deux options sont disponibles pour la création et la modification de la stratégie:
  
1. **Nouveau**: cliquez pour créer une nouvelle stratégie. Vous devez fournir un site pour lequel la stratégie doit être appliquée. Vous configurez ensuite les paramètres de notifications de transmission. Pour la configuration des notifications de **transmission**, vous pouvez uniquement créer des stratégies pour les sites que vous avez déjà créés.
    
2. **Modification**: sélectionnez une stratégie, puis cliquez sur modifier pour sélectionner une action dans une liste déroulante. Vous pouvez uniquement modifier les sites que vous avez déjà créés ou que vous modifiez la stratégie globale:
    
   - **Afficher les détails...**: affiche des informations sur la stratégie actuellement sélectionnée. Vous serez en mesure d’apporter des modifications à la stratégie existante.
    
   - **Sélectionner tout**: Si vous avez plusieurs stratégies et que vous avez besoin de sélectionner toutes les stratégies, cliquez sur Sélectionner tout.
    
   - **Supprimer**: va supprimer la stratégie sélectionnée. L’option **Sélectionner tout** et **supprimer** entraîne la suppression de toutes les stratégies
    
     > [!NOTE]
     > Vous ne pouvez pas supprimer la stratégie **globale** par défaut. Si vous essayez de la supprimer, vous serez averti que la stratégie globale a été renvoyée aux valeurs par défaut (c’est-à-dire que tous les paramètres sont effacés), mais que la stratégie ne peut pas être supprimée.
  
La création d’une stratégie ou la modification d’une stratégie existante est associée à deux actions:
  
- **Valider** L’action valider crée ou met à jour la stratégie et enregistre les modifications.
    
- **Annuler** L’action annuler ignore toutes les modifications apportées depuis la dernière action de validation. Si vous annulez, toutes les modifications apportées seront perdues.
    
Deux paramètres sont possibles pour la configuration des notifications de **transmission**. Les paramètres sont associés aux services de notifications de transmission pour Microsoft et pour Apple. Activez l’option notifications de transmission pour les deux services en activant la case à cocher en regard du nom du service. Vous pouvez désactiver la case à cocher en la sélectionnant. Une fois que vous avez effectué vos sélections, vous validez ou annulez. Le fait de cliquer sur valider enregistre les modifications apportées à la stratégie.
  

