---
title: Présence des utilisateurs dans Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informations destinées aux administrateurs sur la présence dans Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea756b24a0292a35d4e47252383bfc954fcb8fa7
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096969"
---
# <a name="user-presence-in-teams"></a>Présence des utilisateurs dans Teams

Les informations de présence font partie du profil d’un utilisateur de Microsoft Teams (et dans l’ensemble d’Office 365), qui indique la disponibilité et l’état actuel de l’utilisateur à d’autres utilisateurs. Par défaut, tous les membres qui utilisent Teams dans votre organisation peuvent voir (en temps quasi-réel) si d’autres utilisateurs sont disponibles en ligne.

> [!IMPORTANT]
> Si vous désinstallez le client Skype Entreprise après qu'un utilisateur a été déplacé en mode **Teams uniquement**, la présence cesse de fonctionner dans Outlook et les autres applications Office. La présence fonctionne correctement dans Teams. Solution de contournement :pour afficher la présence dans Outlook (et d'autres applications Office), Skype Entreprise doit être installé, même si vous exécutez Teams en mode **Teams uniquement**. Microsoft est sensibilisé à ce problème et travaille activement au développement d’un correctif.

La présence de Teams dans Outlook est prise en charge dans l’application de bureau Outlook 2013 et les versions ultérieures.

## <a name="presence-states-in-teams"></a>États de présence dans Teams

|L'utilisateur est configuré|L'application est configurée|
|:--- |:---|
| ![Une coche verte pleine indique une Présence : Disponible](media/Presence_Available.png) Disponible|![Une coche verte pleine indique une Présence : Disponible](media/Presence_Available.png) Disponible|
|| ![Une coche verte ouverte indique une Absence du bureau](media/Presence_Available_OOF.png) Disponible, Absent du bureau |
|  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) Occupé |  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) Occupé  |
|| ![Un cercle rouge plein indique Occupé au téléphone](media/Presence_Busy.png) Au téléphone|
|| ![Un cercle rouge plein indique Occupé en réunion](media/Presence_Busy.png) En réunion |
|| ![Un cercle rouge ouvert indique Occupé](media/Presence_Busy_OOF.png) Au téléphone, absent du bureau|
|  ![Un cercle rouge avec une ligne blanche indique Ne pas déranger](media/Presence_DND.png) Ne pas déranger ||
|| ![Un cercle rouge avec une ligne blanche indique En cours de présentation](media/Presence_DND.png) En cours de présentation|
|| ![Un cercle rouge avec une ligne blanche indique un Travail individuel en cours](media/Presence_DND.png) Travail individuel en cours|
| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) Absent| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) Absent|
|| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) Absent, *heure* de Vu pour la dernière fois|
|![Une icône d’horloge jaune indique l’absence, de retour dans quelques minutes](media/Presence_Away.png) De retour dans quelques minutes| |
|| ![Une icône d’horloge jaune indique l’absence, congé](media/Presence_Away.png)  Congé|
|| ![Un cercle gris avec un x indique un mode hors connexion](media/Presence_Offline.png) Hors connexion |
|| ![Un cercle gris ouvert indique un statut inconnu](media/Presence_Unknown.png) Statut inconnu|
||![Un cercle rouge ouvert avec une ligne diagonale indique bloqué](media/Presence_Blocked.png) Bloqué |
|| ![Un cercle violet avec une flèche indique absent du bureau](media/Presence_OOF.png) Absent du bureau|
|||

Les statuts de présence configurés par l’application dépendent de l’activité des utilisateurs (disponible, absent), des États du calendrier Outlook (dans une réunion) ou des États des applications Teams (en cours de présentation).

Votre statut de présence actuel passe à absent (e) lorsque vous verrouillez votre ordinateur ou lorsque le mode veille est entré. Sur les appareils mobiles, votre statut de présence passe à absent (e) lorsque l’application teams est en arrière-plan.

Les utilisateurs reçoivent tous les messages de conversation qui leur sont envoyés dans Teams, quel que soit leur état de présence. Si un utilisateur est hors connexion lorsqu’une personne envoie un message, celui-ci apparaît dans Teams lorsque l'utilisateur est de nouveau en ligne. Si un utilisateur est en mode ne pas déranger, il continue à recevoir des messages de la conversation, mais les notifications de bannière n’apparaissent pas.

Les utilisateurs reçoivent les appels dans tous les pays, à l’exception de ne pas déranger, dans lesquels les appels entrants sont dirigés vers la boîte vocale. Si le destinataire a bloqué l’appelant, l'appel n’est pas remis et l’appelant voit la présence du destinataire en Mode hors connexion.

Les utilisateurs peuvent ajouter des utilisateurs à leur liste d’accès prioritaire en accédant à **Paramètres** > **Confidentialité** dans Teams. Les personnes disposant d’un accès prioritaire peuvent contacter l’utilisateur, même si celui-ci est en ne pas déranger.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Paramètres d’administrateur dans Teams comparé à ceux de Skype Entreprise

Les paramètres d’administration suivants de Skype Entreprise sont différents de ceux dans Teams :

- Le partage de présence est toujours activé dans Teams pour les utilisateurs de l’organisation. La configuration de la confidentialité (dans laquelle vous définissez les personnes pouvant voir la présence) n’est pas disponible dans Teams.
- Le partage de présence avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs de Teams. Leur liste de contacts (s'ils en avaient une dans Skype Entreprise) est visible sous **Conversation > Contacts** ou sous **Appels > Contacts**.
- Les fonctionnalités du client Ne sont pas déranger et Autorisé à appeler sont toujours activées pour les utilisateurs Teams.
- L'intégration du calendrier (comprend les informations d’absence du bureau et d’autres informations de calendrier) est toujours activée pour les utilisateurs lorsque Teams est intégrée à Outlook.
- L'indicateur *Vu pour la dernière fois* ou *Absent depuis* est toujours activé pour les utilisateurs Teams si l’organisation utilise également Skype Entreprise.

> [!NOTE]
> La possibilité pour un administrateur Teams de personnaliser ces paramètres n’est pas prise en charge pour le moment.

## <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype Entreprise

Pour plus d’informations sur les fonctions de présence Teams lorsque votre organisation utilise également Skype Entreprise, voir [Coexistence avec Skype Entreprise](coexistence-chat-calls-presence.md).
