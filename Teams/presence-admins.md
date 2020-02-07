---
title: Présence des utilisateurs dans Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informations pour les administrateurs concernant la présence dans Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6b64a54a2a6f198c893894dc0302c81c1bff5da
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837334"
---
# <a name="user-presence-in-teams"></a>Présence des utilisateurs dans Teams

Les informations de présence font partie du profil d’un utilisateur de Microsoft Teams (et dans l’ensemble d’Office 365), qui indique la disponibilité et l’état actuel de l’utilisateur à d’autres utilisateurs. Par défaut, tous les membres de votre organisation utilisant teams peuvent voir (presque en temps réel) si d’autres utilisateurs sont disponibles en ligne.

> [!IMPORTANT]
> Si vous désinstallez le client Skype Entreprise après qu'un utilisateur a été déplacé en mode **Teams uniquement**, la présence cesse de fonctionner dans Outlook et les autres applications Office. La présence fonctionne correctement dans Teams. Solution : pour voir la présence dans Outlook (et les autres applications Office), Skype entreprise doit être installé, même si vous exécutez teams en mode **équipes uniquement** . Microsoft est courant du problème et travaille activement au développement d’un correctif.

La présence de Teams dans Outlook est prise en charge dans l’application de bureau Outlook 2013 et les versions ultérieures.

## <a name="presence-states-in-teams"></a>États de présence dans teams

Les statuts de présence des utilisateurs disponibles dans teams sont les suivants :

|Utilisateur configuré|Application configurée|
|:--- |:---|
| ![Coche verte unie, indiquant présence disponible](media/Presence_Available.png) Disponibles|![Coche verte unie, indiquant présence disponible](media/Presence_Available.png) Disponibles|
|| ![Ouvrir la coche verte indique qu’il est disponible](media/Presence_Available_OOF.png) Disponible, absent (e) du Bureau |
|  ![Cercle rouge Uni, indiquant occupé](media/Presence_Busy.png) Très |  ![Cercle rouge Uni, indiquant occupé](media/Presence_Busy.png) Très  |
|| ![Cercle rouge Uni, indiquant bien occupé lors d’un appel](media/Presence_Busy.png) Lors d’un appel|
|| ![Cercle rouge Uni, indiquant bien occupé lors d’une réunion](media/Presence_Busy.png) En réunion |
|| ![Ouvrir un cercle rouge, indique occupé](media/Presence_Busy_OOF.png) En communication, absent (e) du Bureau|
|  ![Cercle rouge avec une ligne blanche indiquant ne pas déranger](media/Presence_DND.png) Ne pas déranger ||
|| ![Cercle rouge avec une ligne blanche indiquant une présentation](media/Presence_DND.png) Présente|
|| ![Cercle rouge avec ligne blanche indiquant le focus](media/Presence_DND.png) Focalis|
| ![Icône d’horloge jaune, indiquant absent](media/Presence_Away.png) Disparaître| ![Icône d’horloge jaune, indiquant absent](media/Presence_Away.png) Disparaître|
|| ![Icône d’horloge jaune indiquant](media/Presence_Away.png) l’heure de la dernière *connexion* affichée|
|![Icône d’horloge jaune, indique absent, revenir en arrière](media/Presence_Away.png) On arrive| |
|| ![Icône d’horloge jaune, indiquant qu’il n’est pas opérationnel](media/Presence_Away.png)  Sur le Bureau|
|| ![Cercle gris avec x, indiquant hors ligne](media/Presence_Offline.png) Mise |
|| ![Ouverture d’un cercle gris, indiquant le statut inconnu](media/Presence_Unknown.png) État inconnu|
||![Cercle rouge avec ligne diagonale indiquant bloqué](media/Presence_Blocked.png) Bloqué |
|| ![Cercle violet avec flèche, indiquant qu’il n’est pas du tout le Bureau](media/Presence_OOF.png) Absent (e) du Bureau|
|||
 
Les utilisateurs peuvent définir manuellement leur état de présence actuel sur certaines options, et leur état est reflété par tous les autres utilisateurs. Des informations supplémentaires sur la présence d’un utilisateur sont également mises à jour automatiquement. Les modifications dépendent de l’activité des utilisateurs (disponible, absent (e), des États du calendrier Outlook (dans une réunion) ou des États des applications Teams (en cours de présentation) pour les États en retrait dans la liste. Il y a un délai d’inactivité de 15 minutes, après lequel l’état de présence actuel est remis à absent (e).

Les utilisateurs reçoivent tous les messages de discussion qui leur sont envoyés dans Teams, quel que soit leur état de présence. Si un utilisateur est hors connexion lorsque quelqu’un lui envoie un message, le message de conversation s’affiche dans teams lors de la prochaine connexion de l’utilisateur. Si un utilisateur est dans un État ne pas déranger, il continue à afficher des messages instantanés, mais une bannière de notification s’affiche.

Les utilisateurs reçoivent les appels dans tous les pays, à l’exception des États ne pas déranger, dans lesquels les appels entrants sont remis à leur boîte vocale. Si le destinataire a bloqué l’appelant, l’appel ne sera pas remis et l’appelant verra la présence du destinataire hors connexion.

Les utilisateurs peuvent ajouter des personnes à leur liste d’accès prioritaire en accédant à **paramètres** > **confidentialité** dans Teams. Les personnes disposant d’un accès prioritaire peuvent contacter l’utilisateur, même si celui-ci est dans un État ne pas déranger.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Paramètres d’administration dans teams par rapport à Skype entreprise

Les paramètres d’administration suivants Skype entreprise sont différents dans teams :

- Dans Teams, le partage de présence est toujours activé pour les utilisateurs de l’organisation. Les informations sur la confidentialité (dans laquelle vous définissez qui peut voir la présence) ne sont pas disponibles dans Teams.
- Le partage de présence avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs de Microsoft Teams. La liste de contacts (s’il en existe une dans Skype entreprise) est visible sous **discussions > contacts** ou sous **appels > contacts**.
- Le client ne pas déranger et les fonctionnalités d’innovation sont toujours activées pour les utilisateurs de Microsoft Teams.
- Calendrier (inclut les informations d’absence du bureau et d’autres informations de calendrier) l’intégration est toujours activée pour les utilisateurs lorsque teams est intégré à Outlook.
- Le *dernier vu* ou *absent (e* ), car l’indicateur est toujours activé pour les utilisateurs en équipe si l’organisation utilise également Skype entreprise.

> [!NOTE]
> La capacité d’un administrateur d’équipes à personnaliser ces paramètres n’est pas actuellement prise en charge.

## <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype Entreprise

Pour plus d’informations sur la façon dont votre organisation utilise également Skype entreprise, voir [coexistence avec Skype entreprise](coexistence-chat-calls-presence.md) .
