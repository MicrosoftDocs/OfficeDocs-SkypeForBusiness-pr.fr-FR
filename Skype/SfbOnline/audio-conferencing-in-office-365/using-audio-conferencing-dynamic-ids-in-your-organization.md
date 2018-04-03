---
title: À l’aide des ID dynamiques d’audioconférence de votre organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Le service Conférence de données Audio est mis à jour pour fournir chaque Skype pour une réunion commerciale et Teams de Microsoft avec l’ID de conférence différent. ID de conférence dynamiques représentent une amélioration notable sur la conférence static ID, car ils permettent de :'
ms.openlocfilehash: 418e6f486b8108791930c7843bfed8bdc56e83ef
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a>À l’aide des ID dynamiques d’audioconférence de votre organisation

Le service Conférence de données Audio est mis à jour pour fournir chaque Skype pour une réunion commerciale et Teams de Microsoft avec l’ID de conférence différent. ID de conférence dynamiques représentent une amélioration notable sur la conférence static ID, car ils permettent de :
  
- **Sécurité accrue** La conférence ID sont uniques pour chaque Skype pour une réunion commerciale ou Teams de Microsoft et sont générés lors de la réunion.
    
- **Une meilleure expérience pour les réunions consécutives et simultanées :** des informations de rendez-vous spécifiques sont fournies aux réunions pour un même organisateur, ce qui empêche les participants téléphoniques à une réunion de s'ajouter aux participants d'une autre réunion lorsqu'elles sont prévues à peu de temps d'intervalle.
    
- **Une transition transparente :** lorsque votre organisation active les ID de conférence dynamiques, toutes les réunions qui ont déjà été planifiées dans votre organisation avec des ID de conférence statiques auront lieu.
    
> [!TIP]
> ID dynamiques sont uniquement disponibles pour les utilisateurs qui sont activés pour ** Audio conférence ** et demander à Microsoft de définir comme leur fournisseur de conférence audio. Vous pouvez [Affecter de Microsoft en tant que le fournisseur de conférence audio](assign-microsoft-as-the-audio-conferencing-provider.md) pour vos utilisateurs.
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a>Les modifications que verront les utilisateurs de mon organisation ?

Après l’activation des ID de conférence dynamique pour votre organisation, tout nouveau Skype pour entreprise ou Teams de Microsoft de réunion qui est prévue par les utilisateurs de votre organisation qui sont activés pour l’audioconférence aura conférence ID sera différente de la ID de conférence statique qu’avant. Organisateurs qui avaient statique ID de conférence avant doivent rappeler les utilisateurs de joindre leurs réunions qu’ils doivent désormais utiliser un nouvel ID de conférence dans l’invitation à la réunion, avant de pouvoir le rejoindre.
  
> [!NOTE]
> Réunions qui ont été planifiées par un utilisateur avec l’ID de conférence statique avant l’activation de l’organisation pour la conférence dynamique ID continueront d’avoir l’ID de conférence statique, afin qu’ils vous continuer planifier des réunions sans impact. 
  
Ces exemples vous montrent la nouvelle expérience pour deux Skype pour les réunions d’entreprise qui ont été organisés par le même utilisateur, mais les deux aura maintenant deux ID de conférence différent : 
  
 La **réunion 1** a été programmée de 9 h 00 à 10 h 00 et son ID de conférence est 93907123 :
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 La **réunion 2** a été programmée par le même utilisateur de 10 h 00 à 11 h 00 et son ID de conférence est 16353789 :
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a>Rubriques connexes

- [Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [Licences de compléments pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
