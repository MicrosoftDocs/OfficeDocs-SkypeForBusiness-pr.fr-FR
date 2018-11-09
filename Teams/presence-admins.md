---
title: Présence de l’utilisateur dans les équipes
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rakayala
description: Informations administrateurs doivent comprendre sur la présence dans les équipes.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1934a602d89240c89ffb4f7410192d19a7dd2e61
ms.sourcegitcommit: 139b3d3b7fcc1dd7fba7fd14ff34e4ffdfcc7eeb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2018
ms.locfileid: "26038878"
---
# <a name="user-presence-in-teams"></a>Présence de l’utilisateur dans les équipes

Fait partie d’un profil utilisateur dans Microsoft Teams (et dans Office 365), de présence et indique la disponibilité actuelle de l’utilisateur et l’état à d’autres utilisateurs dans l’organisation. Par défaut, tout le monde dans votre organisation à l’aide des équipes permettre voir ou non les autres utilisateurs sont disponibles en ligne.

## <a name="presence-states-in-teams"></a>États de présence dans les équipes

Les États de présence utilisateur disponibles dans les équipes sont les suivants :

|Configuré utilisateur|Application configurée|
|:--- |:---|
| ![Présence disponible](media/Presence_Available.png) Disponibles|![Présence disponible](media/Presence_Available.png) Disponibles|
|| ![oof disponible](media/Presence_Available_OOF.png) Disponible, absent |
|  ![Occupé (e)](media/Presence_Busy.png) Occupé (e) |  ![Occupé (e)](media/Presence_Busy.png) Occupé (e)  |
|| ![Occupé (e)](media/Presence_Busy.png) Dans un appel|
|| ![Occupé (e)](media/Presence_Busy.png) Dans une réunion |
|| ![occupé (e) absent du bureau](media/Presence_Busy_OOF.png) Dans un appel, absent|
|  ![Ne pas déranger](media/Presence_DND.png) Ne pas déranger ||
|| ![Ne pas déranger](media/Presence_DND.png) Présentation|
| ![Absent (e)](media/Presence_Away.png) Absent (e)| ![Absent (e)](media/Presence_Away.png) Absent (e)|
|| ![Absent (e)](media/Presence_Away.png) absent (e) vu dernière *heure*|
|![Absent (e)](media/Presence_Away.png) On arrive| |
|| ![Absent (e)](media/Presence_Away.png)  En congé|
|| ![En mode hors connexion](media/Presence_Offline.png) En mode hors connexion |
|| ![inconnu](media/Presence_Unknown.png) État inconnu|
||![bloqué](media/Presence_Blocked.png) Bloqué |
|| ![Absent](media/Presence_OOF.png) Absent|
|||
 
Les utilisateurs peuvent définir manuellement leur statut de présence actuel à certaines options, et leur état obtient à tous les autres utilisateurs. Plus d’informations de présence utilisateur supplémentaires sont également automatiquement mis à jour en fonction d’activité de l’utilisateur (telles que disponible ou absent (e)), les États de calendrier de Outlook (comme dans une réunion) ou les États d’application équipes (dans un appel de la présentation), aux États qui sont mis en retrait dans la liste.

Il existe un délai d’inactivité de 15 minutes, après lequel état de présence actuel de vos utilisateurs est réinitialisée à Absent (e).

Les utilisateurs peuvent spécifier qui peut adresser directement (contacter remplacement d’un paramètre de ne pas déranger). Ces paramètres ne sont disponibles dans l’application.

## <a name="teams-is-not-skype-for-business"></a>Équipes n’est pas Skype pour les entreprises

Les paramètres d’administration suivants dans Skype pour les entreprises sont différentes dans les équipes :
- Partage de présence est toujours activé dans les équipes pour les utilisateurs dans l’organisation. Configuration de la confidentialité (déterminer qui peut voir présence) n’est pas disponible dans les équipes.
- Présence partage avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs dans les équipes. Leur liste des contacts (si elles avaient dans SfB) est visible sous **conversation > Contacts** ou sous **appels > Contacts**.
- Fonctionnalités client ne pas déranger et innovante sont toujours activées pour les utilisateurs dans les équipes.
- Calendrier (inclut absent du bureau et autres informations du calendrier) intégration est toujours activée pour les utilisateurs dans les équipes si intégré à Outlook.
- La *dernière détection* ou *Absent (e) depuis* (le cas dans un environnement double avec Skype pour les entreprises) indicateur est toujours activé pour les utilisateurs dans les équipes.
- Définir un statut de présence personnalisé n’est pas activé pour les utilisateurs dans les équipes.

> [!NOTE]
> La capacité d’un administrateur d’équipes pour personnaliser ces paramètres n’est pas actuellement pris en charge.


## <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype pour les entreprises

Pour plus d’informations sur le fonctionne de présence des équipes lors de la coexistence avec Skype pour les entreprises, consultez [Coexistence avec Skype pour les entreprises](coexistence-chat-calls-presence.md) . 