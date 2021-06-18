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
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097490"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Étude de cas Contoso : Vue d’ensemble de la migration vocale Teams

Cet article présente une étude de cas sur la façon dont une entreprise multinationale fictive, Contoso, implémente une solution vocale Teams pour leur organisation.

Contoso a déployé Microsoft 365 Entreprise et a pris en compte les principales décisions de conception et les détails d’implémentation suivants : mise en réseau, identité, Windows 10 Entreprise, Office 365 ProPlus, gestion des appareils mobiles, protection des informations, sécurité, mise à niveau de Skype Entreprise vers Teams, système téléphonique et audioconférence.  

Cet article explique comment Contoso a migré ses utilisateurs locaux vers Teams pour unifier la communication, la collaboration et la voix. Pour obtenir des informations de base sur l’accélération de la transformation numérique par Contoso à l’aide des services cloud de Microsoft, consultez tous les articles principaux, dont la vue d’ensemble de l’étude de cas [Contoso.](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

Dans les articles principaux, vous trouverez des informations sur les éléments suivants :  

- Besoins en matière d’infrastructure informatique de Contoso
- Réseau
- Identity 
- Windows 10 Entreprise
- Office 365 Pro Plus
- Gestion des appareils mobiles
- Protection des informations
- Résumé de la sécurité microsoft 365 Entreprise
- Équipe pour un projet top secret
- Site SharePoint Online pour les ressources numériques hautement confidentielles

Pour plus d’informations sur la planification d’une mise à niveau, vous pouvez commencer avec la mise à [niveau de Microsoft Teams.](upgrade-start-here.md)

## <a name="contoso-business-goals-for-teams"></a>Objectifs professionnels de Contoso pour Teams

Pour migrer leurs utilisateurs locaux vers Teams pour la communication unifiée, la collaboration et la voix, Contoso a décidé des objectifs professionnels suivants :

- Activer Teams 

  L’équipe unifiée de communication et de collaboration de Contoso a permis à Teams de mettre en place les stratégies correctes pour régir et activer la collaboration interne et externe sécurisée. 

- Mise à niveau de Skype Entreprise vers Teams 

  Skype Entreprise a été largement déployé dans Contoso. En raison de la nécessité de déplacer des systèmes hérités, Contoso a décidé de mettre à niveau ses utilisateurs Skype Entreprise vers Teams. Pour plus d’informations, [voir l’étude de cas Contoso : Plan de mise à niveau de Teams.](voice-case-study-migration-plan.md)

- Système téléphonique  

  Skype Entreprise avec voix Entreprise a été largement déployé dans Contoso. Avec la nécessité de déplacer les systèmes hérités qui étaient le prochain saut pour leurs serveurs de médiation, Contoso a migré ses utilisateurs Voix Entreprise Skype Entreprise vers Phone System. Les sites Contoso utilisaient le plan d’appels Microsoft, le routage direct du système téléphonique ou une combinaison des deux. Pour plus d’informations, [voir étude de cas Contoso : Phone System.](voice-case-study-phone-system.md)

- Routage géodépendant 

  Les emplacements de bureau dans les pays où la téléphonie est régulée, Contoso devait recréer le routage Location-Based présent dans Skype Entreprise dans le cadre du déploiement de son système téléphonique. Pour plus d’informations, [voir étude de cas Contoso : Location-Based routage.](voice-case-study-location-based-routing.md)

- Appel d’urgence 

  Lorsque le routage direct a été implémenté, Contoso a installé les appels d’urgence avec des tiers approuvés. Pour plus d’informations, [voir l’étude de cas Contoso : Appels d’urgence.](voice-case-study-emergency-calling.md)

- Audioconférence 

  Contoso a installé pour son fournisseur PSTN des numéros de service d’audioconférence hébergés sur sa ligne SIP. Pour plus d’informations, [consultez l’étude de cas Contoso : Audioconférence.](voice-case-study-audio-conferencing.md) 

- Optimisation des médias locaux 

  Contoso a tirer parti de l’optimisation des médias locaux dans les emplacements où il avait une ligne de route directe vers Microsoft Phone System qui était exploitable par des sites distants. Pour plus d’informations, voir [Planifier l’optimisation des](direct-routing-media-optimization.md) médias locaux et [configurer l’optimisation des médias locaux.](direct-routing-media-optimization-configure.md)

- Attendants automatiques et files d’attente d’appels

  Covid-19 souhaitait offrir un support à la réception alors que son personnel travaillait à distance. Contoso utilisait des files d’attente automatiques et des files d’attente pour gérer les appels entrants vers le numéro de téléphone de leur appelant. Pour plus d’informations, [voir l’étude de cas Contoso : Attendant automatiques et Files d’attente d’appels.](voice-case-study-call-queues.md)