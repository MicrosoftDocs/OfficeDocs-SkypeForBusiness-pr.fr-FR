---
title: Présence des utilisateurs dans Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Découvrez les États de présence dans Teams, ainsi qu les paramètres administratifs de la fonctionnalité Présence.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f14aeaf83862cbdd695eb6ec4646d8da81a0c5b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369209"
---
# <a name="user-presence-in-teams"></a>Présence des utilisateurs dans Teams

La présence fait partie du profil d’un utilisateur dans Microsoft Teams (et dans Microsoft 365 ou Office 365), qui indique la disponibilité et l’État actuels de l’utilisateur à d’autres utilisateurs. Par défaut, tous les membres qui utilisent Teams dans votre organisation peuvent voir (en temps quasi-réel) si d’autres utilisateurs sont disponibles en ligne.

La présence de Teams dans Outlook est prise en charge dans l’application de bureau Outlook 2013 et les versions ultérieures.

 > [!Note]
 > Pour plus d’informations sur les profils utilisateur d’équipes sur différentes plateformes, voir [fonctionnalités d’équipes par plate-forme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

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
|![Un cercle gris avec un x indique un mode hors connexion](media/Presence_Offline.png) Apparaître hors connexion | ![Un cercle gris avec un x indique un mode hors connexion](media/Presence_Offline.png) Hors connexion| |
|| ![Un cercle gris ouvert indique un statut inconnu](media/Presence_Unknown.png) Statut inconnu|
|| ![Un cercle violet avec une flèche indique absent du bureau](media/Presence_OOF.png) Absent du bureau|
|||

Les états de présence configurés par l’application sont basés sur l’activité des utilisateurs (Disponible, Absent), les états du calendrier Outlook (En réunion) ou l’état de l’application Teams (Au téléphone, En cours de présentation). Notez que lorsque vous êtes en mode focus en fonction de votre calendrier, l’état de l’utilisateur dans teams s’affichera comme ne pas déranger dans les autres produits.

Votre statut de présence actuel passe à absent (e) lorsque vous verrouillez votre ordinateur ou lorsque votre ordinateur passe en mode inactif ou veille. Sur un appareil mobile, votre statut de présence passe à absent (e) lorsque l’application teams est en arrière-plan.

Les utilisateurs reçoivent tous les messages de conversation qui leur sont envoyés dans Teams, quel que soit leur état de présence. Si un utilisateur est hors connexion lorsqu’une personne envoie un message, celui-ci apparaît dans Teams lorsque l'utilisateur est de nouveau en ligne. Si l’état de l’utilisateur est défini sur ne pas déranger, l’utilisateur peut toujours recevoir des messages instantanés, mais les notifications de bannière ne sont pas affichées.

Les utilisateurs reçoivent des appels quel que soit l'état de présence, à l’exception de l’état Ne pas déranger dans lequel les appels entrants sont redirigés vers la messagerie vocale. Si le destinataire a bloqué l’appelant, l'appel n’est pas remis et l’appelant voit la présence du destinataire en Mode hors connexion.

Les utilisateurs peuvent ajouter des utilisateurs à leur liste d’accès prioritaire en accédant à **Paramètres** > **Confidentialité** dans Teams. Les personnes disposant d’un accès prioritaire peuvent contacter l’utilisateur, même lorsque son statut est défini sur ne pas déranger.

## <a name="user-configured-states-expiration"></a>Expiration des États configurés par l’utilisateur
Lorsqu’un utilisateur sélectionne un état de présence spécifique, il est prioritaire sur les mises à jour des activités d’applications. Par exemple, si un utilisateur vous le définit comme ne pas déranger, il restera comme ne pas déranger, même si la personne participe à une réunion ou répond à un appel.

Les États configurés par l’utilisateur ont des paramètres d’expiration par défaut dans Teams, afin d’empêcher les utilisateurs d’afficher un statut qui n’est pas pertinent après une période donnée.

|État configuré par l’utilisateur|Expiration par défaut|
|:--- |:---|
| Occupé|1 jour|
| Ne pas déranger|1 jour|
| Locuteur|7 jours|
|||

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
