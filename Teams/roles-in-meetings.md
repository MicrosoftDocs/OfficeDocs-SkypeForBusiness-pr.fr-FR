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
ms.openlocfilehash: 11c5858532ade4fd4ed00f7c8f6d1d0c94baeb2d
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321733"
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

|Réunion  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Fonctionnalité**        | Avant la réunion | Pendant la réunion | Après la réunion |
| Conversation | Oui | Oui | Oui |
| Notes de réunion | Oui | Oui |Oui |
| Tableau blanc | Oui | Oui |Oui |
| Enregistrement | N/A |Oui | Oui |
| Fichiers | Oui | Oui | Oui |
| Planification d’une réunion | Oui | N/D | N/A |
|||||||

### <a name="guest-participant"></a>Participant invité

Un participant invité est un membre d’une autre organisation qui a été invité à accéder à Teams ou à d’autres ressources dans le client de votre organisation, sur la base de la plateforme Azure Active Directory B2B. Les utilisateurs invités peuvent être conviés à participer aux réunions régulières et aux réunions de canaux. Pour en savoir plus sur un participant invité, voir [À quoi ressemble l'expérience des invités](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

| Réunion |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Fonctionnalité**        | Avant la réunion | Pendant la réunion | Après la réunion |
| Conversation | Oui | Oui | Oui |
| Notes de réunion | Oui | Oui | Oui |
| Tableau blanc | Non | Non |Non |
| Enregistrement | N/A |Non | Non |
| Fichiers | Oui | Oui | Oui |
| Planification d’une réunion | Non | N/D | N/A |
|||||||

### <a name="external-federated-participant"></a>Participant externe (fédéré)

Un participant externe est une personne qui utilise Teams dans une autre organisation et qui a été invité à participer à une réunion, mais qui n’a pas accès à d’autres ressources partagées de votre organisation. Les participants utilisateurs externes apparaissent dans la composition de la réunion avec le même nom d’identité qu’au sein de leur propre organisation. Pour en savoir plus sur un participant externe, voir [Communiquer avec des utilisateurs d’autres organisations](communicate-with-users-from-other-organizations.md#external-access).

| Réunion (peut être ajoutée à une équipe en tant qu’invité uniquement) ||
|-|-|-|
| **Fonctionnalité** |||
| Conversation | N/A |
| Notes de réunion | N/A |  
| Tableau blanc | N/A |
| Enregistrement | N/A |  
| Fichiers | N/A |
| Planification d’une réunion | N/A |
|||

### <a name="anonymous-participant"></a>Participant anonyme

Le participant anonyme est comme un utilisateur externe, mais son identité n’est pas prévue dans la réunion. Au moment de rejoindre la réunion, il entre manuellement un surnom. Pour en savoir plus sur un participant anonyme, voir [Sécurité et Microsoft Teams](teams-security-guide.md#participant-types).

| Réunion  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Fonctionnalité**        | Avant la réunion | Pendant la réunion | Après la réunion |
| Conversation | N/A | Non | N/A |
| Notes de réunion | N/A | Non | N/A |
| Tableau blanc | N/A | Non | N/A |
| Enregistrement | N/A | Non | N/A |
| Fichiers | N/A | Non | N/A |
| Planification d’une réunion | N/A | N/A | N/A |
|||||||

## <a name="related-topics"></a>Rubriques connexes

[Sécurité et Microsoft Teams](teams-security-guide.md)

[Accès invité dans Teams](guest-access.md)
