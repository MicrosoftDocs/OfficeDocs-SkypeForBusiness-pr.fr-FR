---
title: Microsoft 365 Government-déploiements de très haute qualité
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Conseils destinés aux professionnels de l’informatique pour piloter les déploiements d’Office 365 dans les entités qui gèrent les données soumises au règlement du gouvernement des États-Unis.
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
ms.openlocfilehash: d478d91c256661e493005859786606bdb2fe1a1c
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665866"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a>Plan pour Office 365 Government-déploiements de niveau supérieur

Ce guide est destiné aux professionnels de l’informatique qui pilotent des déploiements d’Office 365 au sein des organisations du secteur public américain ou d’autres entités qui gèrent les données soumises à la réglementation et aux exigences gouvernementales, lorsque l’utilisation d’Office 365 le gouvernement (GCC High) est appropriée pour répondre à ces exigences.

> [!NOTE]
> Si votre organisation a déjà rempli les obligations du gouvernement Office 365 et de l’éligibilité au programme, vous pouvez ignorer les étapes 1 et 2, puis passer directement à l’étape 3.

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a>Étape 1. Déterminez si votre organisation a besoin d’Office 365 Government-GCC High et répond aux exigences d’éligibilité. 

Le service public d’Office 365-GCC High fournit une conformité aux exigences du secteur public américain pour les services Cloud. Outre les fonctionnalités et les fonctionnalités d’Office 365, les organisations profitent des fonctionnalités suivantes qui sont propres à Office 365 secteur public :

- Le contenu du client de votre organisation est séparé de manière logique du contenu client dans les services Office 365 commerciaux de Microsoft.
- Le contenu du client de votre organisation est enregistré aux États-Unis.
- L’accès au contenu du client de votre organisation est limité aux membres du personnel de Microsoft.
- Office 365 Government-GCC High est conforme aux certifications et aux accréditations requises pour les clients du secteur public américain.

Vous pouvez en savoir plus sur le service public d’Office 365 pour les clients du secteur public d' [office 365](https://products.office.com/government/compare-office-365-government-plans), y compris sur les [conditions d’éligibilité](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Description du service fédéral des États-Unis d’Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) décrit les avantages de la plateforme, qui sont centrés sur les exigences en matière de conformité aux États-Unis.


> [!Tip]
> Vous souhaiterez peut-être transférer les tableaux d’informations dans la description du service dans un classeur Excel et ajouter deux colonnes : **approprié pour mon organisation y/n** et **répond aux besoins de mon organisation y/n**. Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez si Office 365 Government-GCC High est approprié pour votre organisation.</li><li>Vérifiez que votre organisation répond aux conditions d’éligibilité.</li></ul> |

> [!Note]
> Office 365 Government-GCC High est uniquement disponible aux États-Unis. Les clients de l’administration non américaine peuvent opter pour un certain nombre de [forfaits Office 365 Government](https://products.office.com/en/government/compare-office-365-government-plans).

## <a name="step-2-apply-for-office-365-government---gcc-high"></a>Étape 2. Demander à Office 365 Government-GCC High

Après avoir décidé que ce service est approprié pour votre organisation, commencez le processus d' [application pour ce service](https://products.office.com/government/eligibility-validation).


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a>Étape 3. Comprendre les paramètres de sécurité par défaut du service public d’Office 365.

Nous vous conseillons de prendre le temps de vérifier les paramètres de votre [administrateur et de votre sécurité](enable-features-office-365.md) avant de les modifier, et de réfléchir à la conformité avant de modifier les paramètres de sécurité par défaut.

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Déterminez si vous avez besoin de modifier l’un des paramètres de sécurité par défaut du gouvernement Office 365, puis de le résoudre pour tout d’abord comprendre l’impact des modifications que vous pourriez apporter.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a>Étape 4. Découvrir les fonctionnalités d’équipe actuellement disponibles dans Office 365 Government-GCC High

Pour répondre aux besoins de nos clients du cloud public, il existe quelques différences entre teams dans Office 365 Government-GCC High et teams dans les offres de l’entreprise. Pour savoir quelles fonctionnalités sont disponibles, consultez le tableau suivant.

[Description du service Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>Étape 5. Plan de gouvernance

Déterminez vos besoins en matière de gouvernance et comment vous pouvez les répondre. Pour plus d’informations, voir [plan de gouvernance dans teams](plan-teams-governance.md) .

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|Point de décision |<ul><li>Déterminez et documentez vos exigences de gouvernance conformément aux recommandations en [matière de plan de gouvernance dans teams](plan-teams-governance.md). </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Étape 6. Déploiement d’équipes pour la collaboration

Une fois que vous avez été intégré au service public Office 365, vous pouvez suivre la procédure de déploiement recommandée décrite dans [la rubrique Comment déployer Microsoft teams](How-to-roll-out-teams.md). N’hésitez pas à vous engager avec votre adoption et votre équipe de gestion des changements et des champions.

Vous pouvez également utiliser [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour l’intégration du service.

