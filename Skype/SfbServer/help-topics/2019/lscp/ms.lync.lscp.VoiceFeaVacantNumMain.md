---
title: Numéro de téléphone non attribué
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: 082c7e5ebccec1c2f74304bc5117ed99ef9b0da1
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2018
ms.locfileid: "22138429"
---
# <a name="unassigned-phone-number"></a>Numéro de téléphone non attribué

> [!NOTE]
> Messagerie unifiée Exchange reste disponible dans Skype pour Business Server 2019 lorsque vous intégrez Skype pour les entreprises 2019 avec Exchange 2013 ou 2016 Exchange. En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie unifiée Exchange est la déduplication emphasised au profit des fonctionnalités de la messagerie vocale dans le nuage et de standard automatique de nuage.  
 
Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
  
La manière dont vous configurez la table des numéros non attribués dépend de l’utilisation envisagée. Vous pouvez configurer la table avec toutes les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéro. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle n’est appelée que lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez personnaliser la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.
  
> [!IMPORTANT]
> Avant de configurer la table des numéros non attribués, vous devez avoir défini une ou plusieurs annonces ou configuré un standard automatique de la messagerie unifiée Exchange. 
  
La page **Numéro non attribué** affiche la liste des plages de numéros non attribués définies pour votre organisation.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Numéro non attribué**, vous pouvez effectuer les tâches suivantes :
  
- Création d’une plage de numéros non attribués
    
- Modification d’une plage de numéros non attribués existante
    
- Suppression d’une plage de numéros non attribués
    
- Modification de l’ordre des plages de numéros non attribués pour déterminer la première action à appliquer à un appel entrant correspondant à un numéro non attribué. 
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les commandes de la page.
  
- **Nouveau** Démarre une nouvelle plage de numéros non attribuée.
    
- **Modifier** Ouvre la plage de numéros non attribuée sélectionnée pour modification, sélectionne toutes les plages de numéros non attribués dans la liste ou supprime la plage de numéros non attribuée sélectionnée.
    
- **Déplacer vers le haut** Déplace la plage de numéros non attribuée sélectionnée haut dans la liste afin que Skype pour Business Server trouve plus tôt et s’applique l’action spécifiée avant d’appliquer les actions spécifiées pour les autres plages dans la liste.
    
    > [!NOTE]
    > Skype pour Business Server recherche dans la table des numéros non attribuée à partir du haut vers le bas et utilise la première plage qui correspond au numéro non attribué. Par exemple, si une plage spécifie une action de dernier recours, assurez-vous qu’elle se trouve en bas de la liste. 
  
- **Déplacer vers le bas** Déplace la plage de numéros non attribuée sélectionnée vers le bas dans la liste.
    
- **Valider tous les** Enregistre toutes les modifications apportées à des plages de numéros non attribués.
    
    > [!IMPORTANT]
    > Cette commande enregistre toutes les modifications apportées dans la page **Nouveau numéro non attribué** et dans la page **Modifier le numéro non attribué**.
  
- **Actualiser** Actualise la liste des plages de numéros non attribués.
    
La liste ci-dessous décrit les champs de la page.
  
- **Nom** Nom unique qui identifie la plage de numéros non attribuée.
    
- **État** Affiche la plages de numéros ont été enregistrées dans la base de données et qui n’ont pas.
    
- **Plage de début** Le numéro de début de la plage de numéros non attribué.
    
- **Plage de fin** Numéro de fin de la plage de numéros non attribué.
    
- **Destination** L’ID de service du service d’Application qui héberge l’application d’annonce qui gèrera les appels entrants à cette plage de numéros non attribués.
    
- **Annonce** L’annonce qui sera lu pour cette plage de numéros non attribués.
    
Pour plus d’informations sur les fonctionnalités d’annonce de, voir [planification de l’application d’annonce dans Skype pour les entreprises](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation des plages de numéros non attribués, voir [Configurer le routage des numéros non attribués téléphone](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) dans la documentation des opérations.
  

