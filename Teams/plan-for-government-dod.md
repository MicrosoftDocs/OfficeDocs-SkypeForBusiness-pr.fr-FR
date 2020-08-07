---
title: Office 365 gouvernementale-déploiements DoD
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Conseils destinés aux professionnels de l’informatique pour piloter les déploiements d’Office 365 dans les entités qui gèrent les données soumises aux règlements du ministère des États-Unis.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04b0833f453ffac96e9fe2c9cef1b0f2a0797ca2
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581255"
---
# <a name="plan-for-office-365-government---dod-deployments"></a>Plan pour les déploiements Office 365 Government-DoD

Ce guide est destiné aux professionnels de l’informatique qui pilotent des déploiements d’Office 365 dans les organisations du secteur public américain ou d’autres entités qui gèrent les données soumises à des réglementations et exigences gouvernementales, lorsque l’utilisation d’Office 365 Government-DoD est appropriée pour ces exigences.

> [!NOTE]
> Si votre organisation a déjà satisfait au service public d’Office 365, et qu’elle a été acceptée pour le programme, vous pouvez passer directement à l’étape 3.

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a>Étape 1. Déterminez si votre organisation a besoin d’Office 365 Government-DoD et répond aux exigences d’éligibilité. 

L’environnement Office 365 Government-DoD fournit une conformité avec les exigences de l’administration américaine pour les services Cloud. En plus des fonctionnalités et des fonctionnalités d’Office 365, les organisations profitent des fonctionnalités suivantes qui sont propres à Office 365 secteur public – DoD :

- Le contenu du client de votre organisation est séparé de manière logique du contenu client dans les services Office 365 commerciaux de Microsoft.
- Le contenu du client de votre organisation est enregistré aux États-Unis.
- L’accès au contenu du client de votre organisation est limité aux membres du personnel de Microsoft.
- Office 365 Government-DoD est conforme aux certifications et acversions nécessaires pour les clients du secteur public américain.

Vous trouverez des informations supplémentaires sur l’offre Office 365 Government-DoD pour les clients du secteur public dans [office 365 Government](https://products.office.com/government/compare-office-365-government-plans), y compris sur les [conditions d’éligibilité](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Description du service fédéral des États-Unis d’Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) décrit les avantages de la plateforme, qui sont centrés sur les exigences en matière de conformité aux États-Unis.


> [!Tip]
> Vous souhaiterez peut-être transférer les tableaux d’informations dans la description du service dans un classeur Excel et ajouter deux colonnes : **approprié pour mon organisation y/n** et **répond aux besoins de mon organisation y/n**. Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez si Office 365 Government-DoD est approprié pour votre organisation.</li><li>Vérifiez que votre organisation répond aux conditions d’éligibilité.</li></ul> |

> [!Note]
> Office 365 Government-DoD est uniquement disponible aux États-Unis. Les clients de l’administration non américaine peuvent opter pour un certain nombre de [forfaits Office 365 Government](https://products.office.com/en/government/compare-office-365-government-plans).

## <a name="step-2-apply-for-office-365-government---dod"></a>Étape 2. Demander à Office 365 pour le gouvernement-DoD

Après avoir décidé que ce service est approprié pour votre organisation, commencez le processus d' [application pour ce service](https://products.office.com/government/eligibility-validation).


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a>Étape 3. Comprendre les paramètres de sécurité par défaut d’Office 365 pour le gouvernement-DoD.

Nous vous conseillons de prendre le temps de vérifier les paramètres de votre [administrateur et de votre sécurité](enable-features-office-365.md) avant de les modifier, et de réfléchir à la conformité avant de modifier les paramètres de sécurité par défaut.

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Déterminez si vous avez besoin de modifier les paramètres de sécurité par défaut du service public-DoD Office 365, puis de le résoudre pour tout d’abord comprendre l’impact des modifications que vous pourriez apporter.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a>Étape 4. Découvrir les fonctionnalités d’équipe actuellement disponibles dans Office 365 Government-DoD

Pour répondre aux besoins de nos clients du cloud public, il existe quelques différences entre teams dans Office 365 Government-DoD et équipes dans les plans de l’entreprise. Pour savoir quelles fonctionnalités sont disponibles, consultez le tableau suivant.

[Description du service Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>Étape 5. Plan de gouvernance

Déterminez vos besoins en matière de gouvernance et comment vous pouvez les répondre. Pour plus d’informations, voir [plan de gouvernance dans teams](plan-teams-governance.md) .

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Point de décision |<ul><li>Déterminez et documentez vos exigences de gouvernance conformément aux recommandations en [matière de plan de gouvernance dans teams](plan-teams-governance.md). </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Étape 6. Déploiement d’équipes pour la collaboration

Après avoir été intégré à Office 365 Government-DoD, suivez le chemin de déploiement recommandé décrit dans [la rubrique Comment déployer Microsoft teams](How-to-roll-out-teams.md). N’hésitez pas à vous engager avec votre adoption et votre équipe de gestion des changements et des champions.

Vous pouvez également utiliser [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour l’intégration du service.
