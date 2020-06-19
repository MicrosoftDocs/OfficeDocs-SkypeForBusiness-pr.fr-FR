---
title: Étude de cas de voix contoso teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786038"
---
# <a name="contoso-case-study-audio-conferencing"></a>Étude de cas contoso : audioconférence

Pour mieux comprendre les fonctionnalités de l’audioconférence &mdash; , son coût, sa disponibilité et son mode de fonctionnement, &mdash; Contoso a examiné [l’audioconférence dans Office 365](deploy-audio-conferencing-teams-landing-page.md). 

## <a name="overview"></a>Vue d’ensemble 

Pour les services d’audioconférence, Contoso utilise des numéros de téléphone bien connus au sein de l’organisation ainsi que dans l’extérieur. Étant donné que contoso souhaite conserver ces numéros dans la mesure du possible, il a examiné les informations relatives à l’attribution de numéros de téléphone dédiés et partagés au pont de conférence audio. 

D’après les recherches, Contoso a pris les décisions suivantes : 

- Seul un segment du remplissage qui héberge régulièrement les appels de conférence audio. 

- Contoso utilisera des numéros de téléphone dédiés et transférera leurs numéros existants pour une utilisation avec la fonction de conférence audio.   

Les utilisateurs de contoso utilisant Skype entreprise et la boîte aux lettres de tous les utilisateurs se trouvant en ligne, de nombreux utilisateurs ont planifié une réunion existante. Contoso a lu [grâce au service de migration de réunion (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) pour savoir que les réunions existantes sont mises à jour automatiquement pour Contoso lorsqu’elles transforment l’utilisateur final en mode TeamsOnly.  


## <a name="configuration"></a>Configuration

Les numéros de téléphone associés aux conférences audio sont désignés sous le nom de numéros de service au sein du système téléphonique. 

- Pour les lieux utilisant des forfaits d’appel, pour porter leurs numéros de téléphone existants de leur opérateur téléphonique vers Office 365, Contoso a suivi les étapes décrites dans la rubrique [obtenir des numéros de téléphone de service](getting-service-phone-numbers.md).

- Pour affecter la licence d’audioconférence à l’utilisateur final au programme pilote technique, l’administrateur Contoso a suivi les étapes décrites dans [gérer les paramètres de l’audioconférence pour votre organisation](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md). 

- Pour le pilote et la migration de l’entreprise, Contoso a utilisé une licence basée sur le groupe en suivant les étapes décrites dans [attribuer des licences aux utilisateurs par l’appartenance aux groupes dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).  

 

 