---
title: Enregistrement et publication de salle dans les panneaux Microsoft Teams
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
- Teams_ITAdmin_Devices
ms.topic: reference
search.appverid: MET150
description: Cet article fournit des conseils sur la façon d’activer les appareils de panneau Teams d’archivage et de mise en production de salle.
ms.openlocfilehash: d5998049faf1e3c8c25b3e49470291bb20f97eea
ms.sourcegitcommit: ab8f8e101e41774668b5e607fa72442105ca796e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68801855"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Enregistrement et publication de salle dans les panneaux Microsoft Teams

Lorsque l’enregistrement et la sortie de salle sont activés, les utilisateurs s’archivent sur les panneaux Teams dans la salle qu’ils ont réservée au début de la réunion. Si un utilisateur ne s’enregistre pas dans un délai défini après l’heure de début de la réunion, la salle de réunion refuse l’invitation à la réunion, envoie un message d’annulation à l’organisateur de la réunion et la salle devient disponible pour que d’autres personnes puissent réserver.  

## <a name="requirements"></a>Conditions requises 

Cette fonctionnalité peut être utilisée dans un déploiement écran Teams autonome. Vous pouvez également associer des panneaux Teams à salles Teams sur Android avec la version d’application 1449/1.0.96.2022011305 ou ultérieure pour obtenir des fonctionnalités supplémentaires telles que les notifications d’archivage.

La boîte aux lettres partagée associée à l’écran Teams doit avoir le fuseau horaire approprié défini pour que cette fonctionnalité fonctionne correctement. Pour plus d’informations sur la façon de définir le fuseau horaire des boîtes aux lettres partagées, consultez [Paramètres de fuseau horaire pour les boîtes aux lettres partagées dans Outlook sur le web](/exchange/troubleshoot/outlook-on-the-web-issues/shared-mailboxes-time-zone-setting).

## <a name="enable-check-in-and-room-release"></a>Activer l’enregistrement et la mise en production de salle 

L’enregistrement et la libération de salle sont désactivés par défaut. Pour l’activer,  

1. Sur le écran Teams, connectez-vous à l’aide de vos informations d’identification d’administrateur.  

2. Accédez à **Paramètres > Paramètres de l’appareil > Administration paramètres > paramètres d’administration Teams > Réunions**.

3. Activez **la salle de publication si personne ne s’archive**.

4. Pour ajuster la durée d’archivage des utilisateurs avant la libération de la salle, accédez à **Libérer après :** et sélectionnez une option dans la liste déroulante.  

Lorsque les panneaux Teams sont associés à une salle Teams sur Android, un utilisateur peut s’enregistrer pour rejoindre la réunion dans la salle Teams.  

## <a name="turn-on-check-in-notifications"></a>Activer les notifications d’archivage

> [!NOTE]
> Cette fonctionnalité est actuellement disponible uniquement sur les panneaux Teams associés à une salle Teams sur Android. Le écran Teams et la salle Teams doivent être connectés au même compte de ressource. Pour en savoir plus[, consultez Appairer un écran Teams avec une salle Microsoft Teams sur Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android).  

Les notifications d’archivage sont envoyées lorsqu’une réunion se poursuit au-delà de son créneau horaire réservé. Une fois qu’un utilisateur de la réunion suivante s’est connecté, la notification s’affiche au début de l’affichage de la salle à l’heure de début de la réunion planifiée pour informer les participants de la réunion précédente que leur réservation est terminée et que les personnes attendent l’espace.  

Pour activer les notifications d’archivage,  

1. Sur le écran Teams, connectez-vous à l’aide de vos informations d’identification d’administrateur. 

2. Accédez à **Paramètres > Paramètres de l’appareil > Administration paramètres > paramètres d’administration Teams > Réunions**.

3. Accédez à **Archivage** et activez **Envoyer une notification d’archivage**.

## <a name="related-topics"></a>Rubriques connexes

- [Comment utiliser les panneaux Microsoft Teams](use-teams-panels.md)

- [Panneaux Microsoft Teams](teams-panels.md)
