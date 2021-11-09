---
title: Configuration des notifications Push du client mobile
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Pour configurer les notifications push Microsoft et les notifications push Apple, vous devez créer une stratégie pour définir les types de notification push dont vous avez besoin.
ms.openlocfilehash: 22b1174eee06fd46bd69d1d9b6c1c4f3f12ac01f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841526"
---
# <a name="mobile-client-push-notification-configuration"></a>Client mobile : configuration des notifications push
 
Pour configurer les **notifications push Microsoft** et les **notifications push Apple**, vous devez créer une stratégie pour définir les types de notification push dont vous avez besoin.
  
Dans l’écran de configuration principal, vous pouvez cliquer sur **Actualiser** pour actualiser et remplir à nouveau la liste des stratégies. Une zone de recherche permet de réduire la liste des stratégies affichées. À mesure que vous tapez le nom à rechercher, la liste des stratégies est automatiquement réduite.
  
> [!IMPORTANT]
> Les paramètres de stratégie appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La priorité de la stratégie est la : la stratégie utilisateur (la plus influente) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet. 
  
Deux procédures sont possibles pour créer et modifier des stratégies :
  
1. **Nouveau** : cliquez pour créer une stratégie. Vous devez fournir un site auquel appliquer cette stratégie. Vous configurez ensuite les paramètres pour la notification push. Pour **Configuration des notifications push**, vous pouvez créer des stratégies uniquement pour des sites que vous avez déjà créés.
    
2. **Modifier** : sélectionnez une stratégie et cliquez sur Modifier pour sélectionner une action dans une liste déroulante. Vous pouvez modifier uniquement des sites que vous avez déjà créés ou modifier la stratégie globale :
    
   - **Afficher les détails…**  : affiche des informations sur la stratégie actuellement sélectionnée. Vous serez en mesure d’apporter des modifications à la stratégie existante.
    
   - **Sélectionner tout** : si vous disposez de plusieurs stratégies et devez sélectionner toutes les stratégies, cliquez sur Sélectionner tout.
    
   - **Supprimer** : permet de supprimer la stratégie sélectionnée. Utilisez **Sélectionner tout** et **Supprimer** pour supprimer toutes les stratégies.
    
     > [!NOTE]
     > Vous ne pouvez pas supprimer la stratégie **globale** par défaut. Si vous tentez de la supprimer, il vous est notifié que les valeurs par défaut de la stratégie globale ont été rétablies (tous les paramètres sont désactivés), mais que la stratégie ne peut pas être supprimée.
  
La création d’une stratégie et la modification d’une stratégie existante sont associées à deux opérations :
  
- **Commit** L’action de validation crée ou met à jour la stratégie et enregistre les modifications
    
- **Annuler** L’action d’annulation annule toutes les modifications qui ont été apportées depuis la dernière action de validation. Si vous annulez, les modifications apportées seront perdues.
    
Deux paramètres sont possibles pour **Configuration des notifications push**. Les paramètres sont associés aux services de notification push pour Microsoft et Apple. Vous pouvez activer la notification push pour l’un ou l’autre service en activant la case à cocher en regard du nom du service. Vous pouvez désactiver la case à cocher en cliquant dessus à nouveau. Une fois vos sélections effectuées, vous pouvez valider ou annuler. Cliquez sur Valider pour enregistrer les modifications apportées à la stratégie.
  

