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
ms.openlocfilehash: 100889bacffdb9de722bd2e1e7295905876dab2e
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786015"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Étude de cas contoso : vue d’ensemble de la migration teams Voice

Cet article présente une étude de cas concernant la façon dont une entreprise fictive multipoint, contoso, a implémenté une solution vocale teams pour son organisation.

Contoso a déployé Microsoft 365 entreprise et résolu les principales décisions relatives à la conception et aux informations d’implémentation pour les éléments suivants : mise en réseau, identité, Windows 10 entreprise, Office 365 ProPlus, gestion des appareils mobiles, protection des informations, sécurité, mise à niveau de Skype entreprise vers équipes, système téléphonique et audioconférence.  

Cet article décrit la façon dont Contoso a migré ses utilisateurs locaux vers des équipes de communication, de collaboration et de voix unifiées. Pour plus d’informations sur la façon dont Contoso a accéléré sa transformation numérique à l’aide des services Cloud de Microsoft, voir tous les articles principaux à partir de la [vue d’ensemble de l’étude de cas contoso](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

Dans les articles principaux, vous trouverez des informations sur les points suivants :  

- Besoins d’infrastructure informatique de contoso
- Réseau
- Identity 
- Windows 10 entreprise
- Office 365 Pro plus
- Gestion des appareils mobiles
- Protection des informations
- Résumé de la sécurité Microsoft 365 entreprise
- Équipe pour un projet de secret principal
- Site SharePoint Online pour des ressources numériques hautement confidentielles

Pour plus d’informations sur la planification d’une mise à niveau, vous pouvez commencer par commencer à [effectuer la mise à niveau de Microsoft teams](upgrade-start-here.md).

## <a name="contoso-business-goals-for-teams"></a>Buts stratégiques de contoso pour les équipes

Pour migrer leurs utilisateurs locaux vers des équipes de communication, de collaboration et de voix unifiées, Contoso a déterminé les objectifs commerciaux suivants :

- Activation de Microsoft teams 

  L’équipe de collaboration et de communication unifiée de Contoso a pu équiper les équipes possédant les stratégies appropriées pour gérer et activer une collaboration interne et externe sécurisée. 

- Mise à niveau de Skype Entreprise vers Teams 

  Skype entreprise a été largement déployé dans contoso. En raison de la nécessité de sortir des systèmes hérités, Contoso a décidé de mettre à niveau leurs utilisateurs Skype entreprise vers Teams. Pour plus d’informations, consultez l' [étude de cas contoso : plan de mise à niveau des équipes](voice-case-study-migration-plan.md).

- Système téléphonique  

  Skype entreprise avec Enterprise Voice a été largement déployé dans contoso. En raison de la nécessité de sortir des systèmes hérités qui étaient le tronçon suivant pour leurs serveurs de médiation, Contoso a migré leurs utilisateurs vocaux Skype entreprise vers un système téléphonique. Les sites contoso utilisaient un forfait d’appel Microsoft, le routage direct de votre système téléphonique ou une combinaison des deux. Pour plus d’informations, reportez-vous à la rubrique [étude de cas contoso : système téléphonique](voice-case-study-phone-system.md).

- Routage géodépendant 

  Dans les pays réglementés par la téléphonie, Contoso a besoin de recréer le routage sur la base de l’emplacement disponible dans Skype entreprise pour le déploiement de votre système téléphonique. Pour plus d’informations, consultez l' [étude de cas contoso : routage de géolocalisation](voice-case-study-location-based-routing.md).

- Appel d’urgence 

  Lorsque le routage direct a été implémenté, Contoso a configuré les appels d’urgence avec des tierces parties approuvées. Pour plus d’informations, reportez-vous à la rubrique [étude de cas contoso : appels d’urgence](voice-case-study-emergency-calling.md).

- Audioconférence 

  Contoso configurez des numéros de service d’audioconférence hébergés sur le Trunk SIP de leur fournisseur PSTN. Pour plus d’informations, consultez l' [étude de cas contoso : audioconférence](voice-case-study-audio-conferencing.md). 

- Optimisation des éléments multimédias locaux 

  Contoso a bénéficié de l’optimisation des contenus multimédias locaux dans les emplacements où il existait un Trunk de routage direct vers un système Microsoft Phone qui était utilisé par des sites distants. Pour plus d’informations, reportez-vous à la rubrique [planification de l’optimisation des médias locaux](direct-routing-media-optimization.md) et configuration de l' [optimisation des médias locaux](direct-routing-media-optimization-configure.md).

- Standards automatiques et files d’attente d’appels

  Dans le cadre de COVID-19, contoso voulait fournir la prise en charge du réceptionniste lorsque son équipe travaille à distance. Contoso a utilisé des standards automatiques et des files d’attente pour gérer les appels entrants sur le numéro de téléphone de votre réceptionniste. Pour plus d’informations, consultez l' [étude de cas contoso : standards automatiques et files d’attente d’appels](voice-case-study-call-queues.md).  


