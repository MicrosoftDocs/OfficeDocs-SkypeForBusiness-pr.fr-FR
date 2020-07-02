---
title: Fonctionnalités de présentateur et de participants dans une réunion Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez les fonctionnalités de présentateur et de participant dans une réunion Teams.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: b0302a5c1f09e6ed6bfbb877709ed3562ce1440a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938173"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a>Fonctionnalités de présentateur et de participants dans une réunion Teams
======================================================

Les réunions Microsoft Teams prennent en charge de nombreux types de participants. Les participants peuvent accéder à différentes fonctionnalités de réunion en fonction de leurs rôles à l’intérieur ou à l’extérieur d’une organisation.

Les fonctionnalités de réunion disponibles sont les suivantes :

- Conversation (comprend des photos et des autocollants)
- Notes de réunion
- Tableau blanc
- Enregistrement
- Fichiers
    - partage d’un fichier dans une conversation de réunion et affichage/téléchargement d’un fichier à partir d’une conversation de réunion
    - présentation d’un PPT dans une réunion (et non par partage d’écran) et affichage d’un PPT dans une réunion
- Planifier une réunion (pour les réunions uniquement)

Cet article décrit les fonctionnalités des participants et leur type d’accès aux fonctionnalités des réunions.

## <a name="presenters-and-organizers"></a>Présentateurs et organisateurs

Les présentateurs et les organisateurs incluent les suivants :

- Présentateurs de mon organisation
- Présentateurs d’autres organisations : cela inclut les participants anonymes et externes. Les présentateurs sont désignés par l’organisateur et ont besoin d’une invitation personnelle de l’organisateur.

Les présentateurs et les organisateurs ont accès à toutes les fonctionnalités d’une réunion ou d’un événement en direct.

## <a name="participants"></a>Participants

Il existe plusieurs types de participants à une réunion :

- [Participant au sein d’un client](#in-tenant-participant)
- [Participant invité](#guest-participant)
- [Participant externe (fédéré)](#external-federated-participant)
- [Participant anonyme](#anonymous-participant)

### <a name="in-tenant-participant"></a>Participant au sein d’un client

Le participant au sein d’un client appartient à l’organisation et dispose d’informations d’identification pour le client. Pour en savoir plus sur ce participant, voir [Sécurité et Microsoft Teams](teams-security-guide.md#participant-types).

|  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Fonctionnalité**        | Avant la réunion | Pendant la réunion | Après la réunion |
| Conversation | Oui | Oui | Oui |
| Notes de réunion | Oui | Oui |Oui |
| Tableau blanc | Oui | Oui |Oui |
| Enregistrement | N/A |Oui | Oui |
| Fichiers : partage d’un fichier dans une conversation de réunion et affichage/téléchargement d’un fichier à partir d’une conversation de réunion | Oui | Oui | Oui |
| Fichiers : présentation d’un PPT dans une réunion (et non par partage d’écran) et affichage d’un PPT dans une réunion | Oui | Oui | Oui |
| Planification d’une réunion | Oui | N/D | N/A |
|||||||

### <a name="guest-participant"></a>Participant invité

Un participant invité est un membre d’une autre organisation qui a été invité à accéder à Teams ou à d’autres ressources dans le client de votre organisation, sur la base de la plateforme Azure Active Directory B2B. Les utilisateurs invités peuvent être conviés à participer aux réunions régulières et aux réunions de canaux. Pour en savoir plus sur un participant invité, voir [À quoi ressemble l'expérience des invités](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

|  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Fonctionnalité**        | Avant la réunion | Pendant la réunion | Après la réunion |
| Conversation | Oui | Oui | Oui |
| Notes de réunion | Oui | Oui | Oui |
| Tableau blanc | Non | Non |Non |
| Enregistrement | N/A |Non | Non |
| Fichiers : partage d’un fichier dans une conversation de réunion et affichage/téléchargement d’un fichier à partir d’une conversation de réunion | Oui | Oui | Oui |
| Fichiers : présentation d’un PPT dans une réunion (et non par partage d’écran) et affichage d’un PPT dans une réunion | Oui | Oui | Oui |
| Planification d’une réunion | Non | N/D | N/A |
|||||||

### <a name="external-federated-participant"></a>Participant externe (fédéré)

Un participant externe est une personne qui utilise Teams dans une autre organisation et qui a été invité à participer à une réunion, mais qui n’a pas accès à d’autres ressources partagées de votre organisation. Les participants utilisateurs externes apparaissent dans la composition de la réunion avec le même nom d’identité qu’au sein de leur propre organisation. Pour en savoir plus sur un participant externe, voir [Communiquer avec des utilisateurs d’autres organisations](communicate-with-users-from-other-organizations.md#external-access).

|  ||
|-|-|-|
| **Fonctionnalité** |||
| Conversation | Oui |
| Notes de réunion | N/A |  
| Tableau blanc | N/A |
| Enregistrement | S/O |  
| Fichiers : partage d’un fichier dans une conversation de réunion et affichage/téléchargement d’un fichier à partir d’une conversation de réunion |  |  |  |
| Fichiers : présentation d’un PPT dans une réunion (et non par partage d’écran) et affichage d’un PPT dans une réunion |  |  |  |
| Planification d’une réunion | N/A |
|||

### <a name="anonymous-participant"></a>Participant anonyme

Le participant anonyme est comme un utilisateur externe, mais son identité n’est pas prévue dans la réunion. Au moment de rejoindre la réunion, il entre manuellement un surnom. Pour en savoir plus sur un participant anonyme, voir [Sécurité et Microsoft Teams](teams-security-guide.md#participant-types).

|   | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Fonctionnalité**        | Avant la réunion | Pendant la réunion | Après la réunion |
| Conversation | N/A | Oui | N/A |
| Notes de réunion | N/A | Non | N/A |
| Tableau blanc | N/A | Non | N/A |
| Enregistrement | N/A | Non | S/O |
| Fichiers : partage d’un fichier dans une conversation de réunion et affichage/téléchargement d’un fichier à partir d’une conversation de réunion |  |  |  |
| Fichiers : présentation d’un PPT dans une réunion (et non par partage d’écran) et affichage d’un PPT dans une réunion |  |  |  |
| Planification d’une réunion | N/A | N/A | N/A |
|||||||

## <a name="related-topics"></a>Rubriques connexes

[Sécurité et Microsoft Teams](teams-security-guide.md)

[Accès invité dans Teams](guest-access.md)
