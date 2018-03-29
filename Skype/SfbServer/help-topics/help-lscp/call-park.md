---
title: Parcage d’appel
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Lorsqu’un appel est stocké, il est transféré vers un numéro temporaire où l’appel est maintenu jusqu'à ce qu’une personne récupère ou qu’il arrive à expiration. Vous devez configurer une table avec les plages de numéros d’extension que vous réservez pour les appels en stationnement. Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est affecté). Chaque pool qui exécute l’application d’appel Park peut avoir une ou plusieurs plages d’extensions. Ces plages doivent être globalement uniques dans votre déploiement.
ms.openlocfilehash: 710d923ae9c1e44320438334ad42a89d9d14062f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="call-park"></a>parcage d’appel
 
Lorsqu’un appel est stocké, il est transféré vers un numéro temporaire où l’appel est maintenu jusqu'à ce qu’une personne récupère ou qu’il arrive à expiration. Vous devez configurer une table avec les plages de numéros d’extension que vous réservez pour les appels en stationnement. Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est affecté). Chaque pool qui exécute l’application d’appel Park peut avoir une ou plusieurs plages d’extensions. Ces plages doivent être globalement uniques dans votre déploiement.
  
Le ** appel Park ** page affiche une liste de toutes les plages numéros Park d’appel qui sont définies pour votre organisation.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Parcage d’appel**, vous pouvez effectuer les tâches suivantes :
  
- Création d’une plage de numéros
    
- Modification d’une plage de numéros existante
    
- Suppression d’une plage de numéros
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les commandes de la page.
  
- **Nouveau** Démarre une nouvelle plage de numéros appel Park.
    
- **Modifier** Ouvre la plage de numéros sélectionnée pour modification, sélectionne toutes les plages de numéros de la liste ou supprime la plage de numéros sélectionnée.
    
- **Actualiser** Actualise la liste des plages de numéros.
    
La liste ci-dessous décrit les champs de la page.
  
- **Nom** Le nom unique qui identifie la plage de numéros.
    
- **Plage de début** Le numéro de début de la plage.
    
- **Plage de fin** Le numéro de fin de la plage.
    
- **Destination** Le domaine complet (FQDN) de nom ou ID du service d’Application qui héberge l’application d’appel Park pour la plage de numéros de service.
    
Pour plus d’informations sur les fonctionnalités d’appel Park de, voir [planification de parc d’appel dans Skype pour entreprise 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Pour plus d’informations sur l’utilisation des plages de numéros d’appel Park, consultez [Configurer les Extensions numéro de téléphone pour les appels de stationnement](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).
  

