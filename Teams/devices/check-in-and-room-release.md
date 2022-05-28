---
title: Enregistrement et mise en production de salle sur les panneaux Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: gary.lai
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
ms.topic: reference
search.appverid: MET150
description: Cet article fournit des conseils sur l’activation de l’archivage et de la mise en production de salle Teams des appareils de panneaux.
ms.openlocfilehash: a1fc01b349a2189ab2f5ca09ff6b856338fbcdbb
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761276"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Enregistrement et mise en production de salle sur les panneaux Microsoft Teams

Lorsque l’enregistrement et la mise en production de la salle sont activés, les utilisateurs s’enregistrent sur Teams panneaux dans la salle qu’ils ont réservée au début de la réunion. Si un utilisateur ne s’enregistre pas dans un délai défini après l’heure de début de la réunion, la salle de réunion refuse l’invitation à la réunion, envoie un message d’annulation à l’organisateur de la réunion et la salle devient disponible pour les autres personnes à réserver.  

## <a name="requirements"></a>Conditions requises 

Cette fonctionnalité peut être utilisée dans un déploiement autonome écran Teams. Vous pouvez également associer des panneaux Teams avec des salles Teams sur Android avec la version 1449/1.0.96.202011305 ou ultérieure de l’application pour des fonctionnalités supplémentaires telles que les notifications d’archivage.  

## <a name="enable-check-in-and-room-release"></a>Activer l’enregistrement et la mise en production de la salle 

L’enregistrement et la mise en production de la salle sont désactivés par défaut. Pour l’activer,  

1. Sur le écran Teams, connectez-vous à l’aide de vos informations d’identification d’administrateur.  

2. Accédez à **Paramètres > Paramètres de l’appareil > Administration paramètres > Teams paramètres d’administration > réunions**.

3. Activez la salle release si personne ne s’y archive.

4. Pour ajuster la durée d’archivage des utilisateurs avant la publication de la salle, accédez à **Release après :** puis sélectionnez une option dans la liste déroulante.  

Lorsque Teams panneaux sont associés à une salle Teams sur Android, un utilisateur peut s’enregistrer pour rejoindre la réunion dans la salle Teams.  

## <a name="turn-on-check-in-notifications"></a>Activer les notifications d’archivage

> [!NOTE]
> Cette fonctionnalité est actuellement disponible uniquement sur Teams panneaux associés à une Teams Room sur Android. La salle écran Teams et Teams doit être connectée au même compte de ressource. Pour en savoir plus, consultez [l’article Associer une écran Teams avec une Microsoft Teams Room sur Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android).  

Les notifications d’archivage sont envoyées lorsqu’une réunion se poursuit au-delà de son créneau horaire réservé. Une fois qu’un utilisateur de la prochaine réunion s’est connecté, la notification s’affiche sur le devant de la salle à l’heure de début de la réunion planifiée pour informer les participants précédents que leur réservation est terminée et que les personnes attendent l’espace.  

Pour activer les notifications d’archivage,  

1. Sur le écran Teams, connectez-vous à l’aide de vos informations d’identification d’administrateur. 

2. Accédez à **Paramètres > Paramètres de l’appareil > Administration paramètres > Teams paramètres d’administration > réunions**.

3. Accédez à **l’archivage** et **activez l’envoi d’une notification d’archivage**.

## <a name="related-topics"></a>Voir aussi

- [Utilisation des panneaux Microsoft Teams](use-teams-panels.md)

- [panneaux Microsoft Teams](teams-panels.md)
