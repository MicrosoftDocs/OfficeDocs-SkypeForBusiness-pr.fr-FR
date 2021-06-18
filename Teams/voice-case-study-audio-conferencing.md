---
title: Étude de cas Teams voix Contoso
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
description: Étude de cas Voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121302"
---
# <a name="contoso-case-study-audio-conferencing"></a>Étude de cas Contoso : Audioconférence

Pour comprendre ce qu’est l’audioconférence, ses coûts, sa disponibilité et son fonctionnement, l’audioconférence examinée par &mdash; &mdash; Contoso dans Office [365.](deploy-audio-conferencing-teams-landing-page.md) 

## <a name="overview"></a>Vue d’ensemble 

Pour l’audioconférence, Contoso utilisait des numéros de téléphone bien connus au sein de l’organisation ainsi qu’à l’extérieur. Comme Contoso souhaitait conserver ces numéros autant que possible, il a examiné les informations sur l’affectation de numéros de téléphone dédiés et partagés au pont de conférence audio. 

D’après leurs recherches, Contoso a pris les décisions suivantes : 

- Seul un segment de la population qui héberge régulièrement des appels d’audioconférence reçoit des licences d’audioconférence. 

- Contoso utiliserait des numéros de téléphone dédiés et portait ses numéros existants pour une utilisation avec l’audioconférence.   

Étant donné que les utilisateurs contoso utilisaient Skype Entreprise et que les boîtes aux lettres de tous les utilisateurs sont en ligne, de nombreux utilisateurs ont déjà une réunion prévue. Contoso lit Utiliser le [service Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) pour découvrir que les réunions existantes sont mises à jour automatiquement pour Contoso lorsqu’elles changent l’utilisateur final en mode TeamsOnly.  


## <a name="configuration"></a>Configuration

Les numéros de téléphone associés à l’audioconférence sont appelés numéros de service dans le système téléphonique. 

- Pour les lieux utilisant des forfaits d’appels, pour le portage de leurs numéros de téléphone existants de leur opérateur vers Office 365, Contoso a suivi les étapes de obtention de numéros [de téléphone de service.](getting-service-phone-numbers.md)

- Pour affecter la licence d’audioconférence à l’utilisateur final dans le cadre du pilote technique, l’administrateur Contoso a suivi les étapes de gestion des paramètres d’audioconférence pour [votre organisation.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) 

- Pour le pilote et la migration d’entreprise, Contoso a utilisé la gestion des licences basée sur les groupes en suivant les étapes de la procédure Attribuer des licences à des utilisateurs en fonction de l’appartenance aux groupes [dans Azure Active Directory.](/azure/active-directory/users-groups-roles/licensing-groups-assign)  

 

