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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891101"
---
# <a name="mobile-client-push-notification-configuration"></a>Client mobile : configuration des notifications push
 
Pour configurer les **notifications push Microsoft** et **les notifications push Apple**, vous devez créer une stratégie pour définir les types de notification push que vous avez besoin.
  
Dans l’écran configuration principale, vous pouvez cliquer sur **Actualiser** pour actualiser et remplir la liste des stratégies. Une zone de recherche est fournie pour limiter la liste des stratégies affichées. Lorsque vous tapez le nom que vous recherchez, la liste des stratégies restreint automatiquement.
  
> [!IMPORTANT]
> Les paramètres de stratégie qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. L’ordre de priorité est le suivant : les stratégies utilisateur (prioritaires) remplacent les stratégies de site. Les stratégies de site remplacent les stratégies globales (les moins prioritaires). Cela signifie que plus la définition de stratégie est proche de l’objet affecté par cette stratégie, plus l’impact de cette stratégie sur l’objet est important. 
  
Deux options sont disponibles pour la création d’une stratégie et de modification :
  
1. **Nouveau**: cliquez pour créer une nouvelle stratégie. Vous devez fournir un site pour la stratégie s’applique à. Puis, vous configurez les paramètres pour les notifications push. **Configuration des notifications Push**, vous pouvez uniquement créer des stratégies pour les Sites que vous avez déjà créé.
    
2. **Modifier**: sélectionnez une stratégie, cliquez sur Modifier pour sélectionner une action à partir d’une liste déroulante. Vous ne pouvez modifier que les sites que vous avez déjà créé ou modifiez la stratégie globale :
    
   - **Afficher les détails...**: affiche des informations sur la stratégie sélectionnée. Vous serez en mesure d’apporter des modifications à la stratégie existante.
    
   - **Sélectionner tout**: Si vous disposez d’un certain nombre de stratégies et que vous devez sélectionner toutes les stratégies, cliquez sur Sélectionner tout
    
   - **Supprimer**: supprime la stratégie sélectionnée. Supprime toutes les stratégies à l’aide de **toutes les sélectionner** et **Supprimer**
    
     > [!NOTE]
     > Vous ne pouvez pas supprimer la stratégie **globale** par défaut. Si vous tentez de supprimer, vous êtes averti que la stratégie globale a été renvoyée pour les valeurs par défaut (autrement dit, tous les paramètres sont vides), mais la stratégie ne peut pas être supprimée.
  
Création d’une nouvelle stratégie ou modifier une stratégie existante est associé à deux actions :
  
- **Valider** L’action de validation crée ou met à jour la stratégie et enregistre les modifications
    
- **Annuler** L’action Annuler annule les modifications qui ont été apportées depuis la dernière opération de validation. Si vous annulez, toutes les modifications apportées seront perdues.
    
Deux paramètres sont possibles pour la **Configuration des notifications Push**. Les paramètres associés avec les services de notification push pour Microsoft et Apple. Vous activez les notifications push pour chaque service en activant la case à cocher en regard du nom du service. Vous pouvez désactiver la case à cocher en la sélectionnant pour décocher cette option. Une fois vos sélections effectuées, vous validez ou annulez. En cliquant sur Valider sera enregistrer les modifications apportées à la stratégie.
  

