---
title: Vue d’ensemble de l’étude de cas Contoso de voix Teams
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
description: 'Étude de cas de voix Teams pour une entreprise multinationale : Vue d’ensemble de la migration vocale'
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae0d123841e57987346fae304e34bde28e4ffe84
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808625"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Étude de cas Contoso : Vue d’ensemble de la migration vocale Teams

Cet article présente une étude de cas sur la façon dont une société multinationale fictive, Contoso, a implémenté une solution de voix Teams pour son organisation.

Contoso a déployé Microsoft 365 Entreprise et traité les principales décisions de conception et les détails d’implémentation pour les éléments suivants : mise en réseau, identité, Windows 10 Entreprise, Office 365 ProPlus, gestion des appareils mobiles, protection des informations, sécurité, mise à niveau à partir de Skype Entreprise à Teams, au système téléphonique et à l’audioconférence.  

Cet article se concentre sur la façon dont Contoso a migré ses utilisateurs locaux vers Teams pour une communication, une collaboration et une voix unifiées. Pour plus d’informations sur la façon dont Contoso a accéléré sa transformation numérique à l’aide des services cloud de Microsoft, consultez tous les articles de base commençant par la [vue d’ensemble de l’étude de cas Contoso](/microsoft-365/enterprise/contoso-case-study).

[https://learn.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

Dans les articles de base, vous trouverez des informations sur les éléments suivants :  

- Besoins en infrastructure informatique de Contoso
- Réseautage
- Identity 
- Windows 10 Entreprise
- Office 365 Pro Plus
- Gestion des appareils mobiles
- Protection des informations
- Résumé de la sécurité Microsoft 365 Entreprise
- Équipe pour un projet top secret
- Site SharePoint Online pour les ressources numériques hautement confidentielles

Pour plus d’informations sur la planification d’une mise à niveau, vous pouvez commencer avec [la mise à niveau de Microsoft Teams](upgrade-start-here.md).

## <a name="contoso-business-goals-for-teams"></a>Objectifs commerciaux de Contoso pour Teams

Pour migrer leurs utilisateurs locaux vers Teams pour une communication, une collaboration et une voix unifiées, Contoso a choisi les objectifs métier suivants :

- Activation teams 

  L’équipe unifiée de communication et de collaboration de Contoso a permis à Teams d’avoir les stratégies appropriées pour régir et activer une collaboration interne et externe sécurisée. 

- Mise à niveau de Skype Entreprise vers Teams 

  Skype Entreprise a été largement déployé dans Contoso. Avec la nécessité de quitter les systèmes hérités, Contoso a décidé de mettre à niveau ses utilisateurs Skype Entreprise vers Teams. Pour plus d’informations, consultez [l’étude de cas Contoso : Plan de mise à niveau de Teams](voice-case-study-migration-plan.md).

- Système téléphonique  

  Skype Entreprise avec voix d’entreprise a été largement déployée dans Contoso. Avec la nécessité de quitter les systèmes hérités qui étaient le tronçon suivant pour leurs serveurs de médiation, Contoso a migré ses Skype Entreprise utilisateurs vocaux d’entreprise vers le système téléphonique. Les sites Contoso ont utilisé le plan d’appel Microsoft, le routage direct du système téléphonique ou une combinaison des deux. Pour plus d’informations, consultez [l’étude de cas Contoso : Système téléphonique](voice-case-study-phone-system.md).

- Routage géodépendant 

  Avec des bureaux dans les pays réglementés par la téléphonie, Contoso devait recréer le routage Location-Based présent dans Skype Entreprise dans son déploiement du système téléphonique. Pour plus d’informations, consultez [l’étude de cas contoso : Location-Based routage](voice-case-study-location-based-routing.md).

- Appel d’urgence 

  Lorsque le routage direct a été implémenté, Contoso a configuré des appels d’urgence avec des tiers approuvés. Pour plus d’informations, consultez [l’étude de cas Contoso : Appel d’urgence](voice-case-study-emergency-calling.md).

- Audioconférence 

  Contoso configure les numéros de service d’audioconférence hébergés sur leur jonction SIP au fournisseur PSTN. Pour plus d’informations, consultez [l’étude de cas Contoso : Audioconférence](voice-case-study-audio-conferencing.md). 

- Optimisation des médias locaux 

  Contoso a profité de l’optimisation des médias locaux dans des emplacements où il y avait une jonction de route directe vers Microsoft Phone System qui était exploitée par des sites distants. Pour plus d’informations, consultez [Planifier l’optimisation des médias locaux](direct-routing-media-optimization.md) et [configurer l’optimisation des médias locaux](direct-routing-media-optimization-configure.md).

- Standards automatiques et files d’attente d’appels

  À la suite de Covid-19, Contoso voulait fournir un soutien de la réception pendant que leur personnel travaillait à distance. Contoso a utilisé des standards automatiques et des files d’attente d’appels pour gérer les appels entrants au numéro de téléphone de son employé de réception. Pour plus d’informations, consultez [l’étude de cas Contoso : Standards automatiques et Files d’attente d’appels](voice-case-study-call-queues.md).
