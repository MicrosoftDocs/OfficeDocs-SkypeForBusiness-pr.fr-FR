---
title: Présence de l’utilisateur dans teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informations pour les administrateurs concernant la présence dans Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bd57165cbb88df135827ae72fa3952dd8ddd452
ms.sourcegitcommit: 299f854bbb73887ba315b09b9adf9ea9ff91e8ec
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37062960"
---
# <a name="user-presence-in-teams"></a>Présence de l’utilisateur dans teams

Les informations de présence font partie du profil d’un utilisateur de Microsoft Teams (et dans l’ensemble d’Office 365), qui indique la disponibilité et l’état actuel de l’utilisateur à d’autres utilisateurs. Par défaut, tous les membres de votre organisation utilisant teams peuvent voir (presque en temps réel) si d’autres utilisateurs sont disponibles en ligne.

> [!IMPORTANT]
> Si vous désinstallez le client Skype entreprise après le déplacement d’un utilisateur en mode **équipes uniquement** , la présence cesse de fonctionner dans Outlook et les autres applications Office. La présence fonctionne correctement dans Teams. Solution : pour voir la présence dans Outlook (et les autres applications Office), Skype entreprise doit être installé, même si vous exécutez teams en mode **équipes uniquement** . Microsoft est consciente de ce problème et travaille sur un correctif.

## <a name="presence-states-in-teams"></a>États de présence dans teams

Les statuts de présence des utilisateurs disponibles dans teams sont les suivants :

|Utilisateur configuré|Application configurée|
|:--- |:---|
| ![Coche verte unie, indiquant présence disponible](media/Presence_Available.png) Disponibles|![Coche verte unie, indiquant présence disponible](media/Presence_Available.png) Disponibles|
|| ![Ouvrir la coche verte indique qu’il est disponible](media/Presence_Available_OOF.png) Disponible, absent (e) du Bureau |
|  ![Cercle rouge Uni, indiquant occupé](media/Presence_Busy.png) Très |  ![Cercle rouge Uni, indiquant occupé](media/Presence_Busy.png) Très  |
|| ![Cercle rouge Uni, indiquant bien occupé lors d’un appel](media/Presence_Busy.png) En communication|
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
 
Les utilisateurs peuvent définir manuellement leur état de présence actuel sur certaines options, et leur état est reflété par tous les autres utilisateurs. Des informations supplémentaires sur la présence d’un utilisateur sont également mises à jour automatiquement. Les modifications dépendent de l’activité des utilisateurs (disponible, absent (e), des États du calendrier Outlook (dans une réunion) ou des États des applications Teams (en cours de présentation) pour les États en retrait dans la liste.

Il y a un délai d’inactivité de 15 minutes, après lequel l’état de présence actuel est remis à absent (e).

Les utilisateurs peuvent spécifier qui peut se bloquer (c’est-à-dire les contacter malgré un État ne pas déranger). Ces paramètres sont disponibles dans le client Teams.

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
