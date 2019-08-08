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
description: Les administrateurs d’informations doivent comprendre la présence dans Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b3c36f0f83937e72ae4477ad38c9bd3187c6577
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244826"
---
# <a name="user-presence-in-teams"></a>Présence de l’utilisateur dans teams

Les informations de présence font partie du profil d’un utilisateur dans Microsoft Teams (et dans Office 365), et indiquent la disponibilité et l’état actuel de l’utilisateur à d’autres utilisateurs au sein de l’organisation. Par défaut, tous les membres de votre organisation utilisant teams peuvent voir, en temps réel, si d’autres utilisateurs sont disponibles en ligne.

## <a name="presence-states-in-teams"></a>États de présence dans teams

Les statuts de présence des utilisateurs disponibles dans teams sont les suivants:

|Utilisateur configuré|Application configurée|
|:--- |:---|
| ![Marque verte CHEK, indiquant la présence disponible](media/Presence_Available.png) Disponibles|![Marque verte CHEK, indiquant la présence disponible](media/Presence_Available.png) Disponibles|
|| ![Ouvrir la marque verte CHEK, indiquant que le OOF est disponible](media/Presence_Available_OOF.png) Disponible, absent (e) du Bureau |
|  ![Cercle rouge continu indiquant Busy](media/Presence_Busy.png) Très |  ![Cercle rouge continu indiquant Busy](media/Presence_Busy.png) Très  |
|| ![Cercle rouge continu indiquant qu’il est occupé pendant un appel](media/Presence_Busy.png) En communication|
|| ![Cercle rouge continu indiquant qu’il est occupé dans une réunion](media/Presence_Busy.png) En réunion |
|| ![Cercle rouge pour indiquer qu’il est occupé](media/Presence_Busy_OOF.png) En communication, absent (e) du Bureau|
|  ![Cercle rouge avec ligne blanche indiquant ne pas déranger](media/Presence_DND.png) Ne pas déranger ||
|| ![Cercle rouge avec une ligne blanche indiquant une présentation](media/Presence_DND.png) Présente|
| ![Icône d’horloge jaune, indiquant absent](media/Presence_Away.png) Disparaître| ![Icône d’horloge jaune, indiquant absent](media/Presence_Away.png) Disparaître|
|| ![Icône d’horloge jaune indiquant](media/Presence_Away.png) l' *heure* de la dernière vue|
|![Icône d’horloge jaune, indiquant qu’il n’y a plus de retour](media/Presence_Away.png) On arrive| |
|| ![Icône d’horloge jaune, indiquant qu’il n’est pas opérationnel](media/Presence_Away.png)  Sur le Bureau|
|| ![Cercle gris avec x, indiquant hors ligne](media/Presence_Offline.png) Mise |
|| ![Cercle gris ouvert indiquant le statut inconnu](media/Presence_Unknown.png) État inconnu|
||![Cercle rouge avec ligne diagonale indiquant le blocage](media/Presence_Blocked.png) Bloqué |
|| ![Cercle violet avec flèche, indiquant qu’il n’est pas du Bureau](media/Presence_OOF.png) Absent (e) du Bureau|
|||
 
Les utilisateurs peuvent définir manuellement leur état de présence actuel sur certaines options, et leur état est reflété par tous les autres utilisateurs. Des informations supplémentaires sur la présence d’un utilisateur sont également mises à jour automatiquement en fonction de l’activité des utilisateurs (par exemple, disponible ou absent), des États du calendrier Outlook (par exemple, en réunion) ou des États des applications Teams (en cas de présentation) aux États en retrait dans la liste.

Il y a un délai d’inactivité de 15 minutes, après quoi l’état de présence actuel de vos utilisateurs sera restauré en absent (e).

Les utilisateurs peuvent spécifier qui peut vous répartir (ils remplacent le paramètre ne pas déranger). Ces paramètres sont disponibles dans l’application.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Paramètres d’administration dans teams par rapport à Skype entreprise

Les paramètres d’administration suivants Skype entreprise sont différents dans teams:

- Dans Teams, le partage de présence est toujours activé pour les utilisateurs de l’organisation. La configuration de la vie privée (en choisissant qui peut voir la présence) n’est pas disponible dans Teams.
- Le partage de présence avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs de Microsoft Teams. La liste de contacts (s’il en existe une dans Skype entreprise) est visible sous **discussions > contacts** ou sous **appels > contacts**.
- Le client ne pas déranger et les fonctionnalités d’innovation sont toujours activées pour les utilisateurs de Microsoft Teams.
- Calendrier (y compris les informations d’absence du bureau et d’autres informations de calendrier) l’intégration est toujours activée pour les utilisateurs en équipe, si ils sont intégrés à Outlook.
- Le *dernier vu* ou *absent depuis* l’indicateur (dans le cas d’un environnement double avec Skype entreprise) est toujours activé pour les utilisateurs de Microsoft Teams.

> [!NOTE]
> La capacité d’un administrateur d’équipes à personnaliser ces paramètres n’est pas actuellement prise en charge.

## <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype Entreprise

Pour plus d’informations sur la façon dont la présence des équipes dans Skype entreprise, voir [coexistence avec Skype entreprise](coexistence-chat-calls-presence.md) . 
