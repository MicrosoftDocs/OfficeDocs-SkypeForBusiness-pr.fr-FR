---
title: L’enregistrement et la publication de la salle sur Microsoft Teams panneaux
ms.author: czawideh
author: cazawideh
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
description: Cet article fournit des conseils sur la façon d’activer l’enregistrement et la publication de salles Teams panneaux.
ms.openlocfilehash: 9e90916c5db4d5ec32a40f0e021f9bf7b294d09f
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "63689069"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>L’enregistrement et la publication de la salle sur Microsoft Teams panneaux

Lorsque l’enregistrement et la publication de salle sont activés, les utilisateurs peuvent Teams dans les écrans de la salle qu’ils ont réservée au début de la réunion. Si un utilisateur ne vérifie pas dans un délai donné après l’heure de début de la réunion, la salle de réunion refuse l’invitation à la réunion, envoie un message d’annulation à l’organisateur de la réunion pour que d’autres personnes la réservent.  

## <a name="requirements"></a>Conditions requises 

Cette fonctionnalité peut être utilisée dans un déploiement de panneau de Teams autonome. Vous pouvez également coupler des panneaux Teams avec salles Teams sur Android avec la version 1449/1.0.96.2022011305 ou ultérieure pour des fonctionnalités supplémentaires telles que les notifications d’enregistrement.  

## <a name="enable-check-in-and-room-release"></a>Activer l’enregistrement et la publication de salles 

L’enregistrement et la sortie des salles sont éteints par défaut. Pour l’activer,  

1. Dans le Teams, connectez-vous à l’aide de vos informations d’identification d’administrateur.  

2. Go to **Paramètres > Device Paramètres > Admin Paramètres > Panels App Paramètres > Meetings**.

3. Activer la salle de publication si personne ne s’y tourne.

4. Pour ajuster le délai d’enregistrement des utilisateurs avant la publication de la salle, sélectionnez l’option Publication après , puis sélectionnez une option dans la dernière ligne.  

Lorsque Teams panneaux sont couplés à une salle Teams sur Android, un utilisateur peut rejoindre la réunion dans la Teams réunion.  

## <a name="turn-on-check-in-notifications"></a>Activer les notifications d’enregistrement

> [!NOTE]
> Cette fonctionnalité n’est actuellement disponible que Teams panneaux couplés à une salle Teams sur Android. Le Teams et Teams de réunion doivent être signés dans le même compte de ressource. Pour [en savoir plus, voir Teams panneau Coupler une salle Microsoft Teams sur Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android).  

Des notifications d’enregistrement sont envoyées lorsqu’une réunion passe au-delà de son créneau horaire réservé. Une fois qu’un utilisateur de la prochaine réunion s’est présenté, la notification s’affiche au premier plan de l’affichage de la salle à l’heure de début de la réunion prévue pour faire savoir aux participants précédents que leur réservation est terminée et que des personnes attendent l’espace.  

Pour activer les notifications d’enregistrement,  

1. Dans le Teams, connectez-vous à l’aide de vos informations d’identification d’administrateur. 

2. Go to **Paramètres > Device Paramètres > Admin Paramètres > Panels App Paramètres > Meetings**.

3. Allez à **l’enregistrement** et activer **la notification d’envoi de l’enregistrement**.

## <a name="related-topics"></a>Rubriques connexes

- [Utilisation de panneaux Microsoft Teams panneaux](use-teams-panels.md)

- [Microsoft Teams panneaux](teams-panels.md)