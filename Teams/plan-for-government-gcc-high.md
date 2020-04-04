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
ms.openlocfilehash: 0b5111e61f6c545a7311280fa865c762e8498b86
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137809"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a>Plan pour Microsoft 365 Government-déploiements de niveau supérieur

Ce guide est destiné aux professionnels de l’informatique qui pilotent des déploiements d’Office 365 au sein des organisations du secteur public américain ou d’autres entités qui gèrent les données soumises à la réglementation et aux exigences gouvernementales, car l’utilisation de Microsoft 365 Government (GCC High) est appropriée pour répondre à ces exigences.

> [!NOTE]
> Si votre organisation a déjà rempli les obligations du ministère de l’éligibilité Microsoft 365 et qu’elle a été acceptée dans le programme, vous pouvez ignorer les étapes 1 et 2, puis passer directement à l’étape 3.

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a>Étape 1. Déterminez si votre organisation a besoin de Microsoft 365 Government-GCC High et conforme aux exigences d’éligibilité. 

Le secteur public de Microsoft 365-GCC High fournit une conformité aux exigences de l’administration américaine pour les services Cloud. En plus des fonctionnalités et des fonctionnalités d’Office 365, les organisations tirent parti des fonctionnalités suivantes qui sont propres à l’administration de Microsoft 365 :

- Le contenu du client de votre organisation est séparé de manière logique du contenu client dans les services Office 365 commerciaux de Microsoft.
- Le contenu du client de votre organisation est enregistré aux États-Unis.
- L’accès au contenu du client de votre organisation est limité aux membres du personnel de Microsoft.
- Microsoft 365 Government-GCC High est conforme aux certifications et aux accréditations requises pour les clients du secteur public américain.

Vous pouvez en savoir plus sur le gouvernement Microsoft 365 pour les clients du secteur public d' [Office 365](https://products.office.com/government/compare-office-365-government-plans), y compris sur les [conditions d’éligibilité](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Description du service fédéral des États-Unis d’Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) décrit les avantages de la plateforme, qui sont centrés sur les exigences en matière de conformité aux États-Unis.


> [!Tip]
> Vous souhaiterez peut-être transférer les tableaux d’informations dans la description du service dans un classeur Excel et ajouter deux colonnes : **approprié pour mon organisation y/n** et **répond aux besoins de mon organisation y/n**. Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez si le service public de Microsoft 365 est approprié pour votre organisation.</li><li>Vérifiez que votre organisation répond aux conditions d’éligibilité.</li></ul> |

> [!Note]
> Microsoft 365 Government-GCC High est uniquement disponible aux États-Unis. Les clients de l’administration non américaine peuvent opter pour un certain nombre de [forfaits Office 365 Government](https://products.office.com/en/government/compare-office-365-government-plans).

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a>Étape 2. Demander à Microsoft 365 Government-GCC High

Après avoir décidé que ce service est approprié pour votre organisation, commencez le processus d' [application pour ce service](https://products.office.com/government/eligibility-validation).


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a>Étape 3. Comprendre les principaux paramètres de sécurité par défaut de Microsoft 365.

Nous vous conseillons de prendre le temps de vérifier les paramètres de votre [administrateur et de votre sécurité](enable-features-office-365.md) avant de les modifier, et de réfléchir à la conformité avant de modifier les paramètres de sécurité par défaut.

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Déterminez si vous avez besoin de modifier l’un des paramètres de sécurité du service public Microsoft 365 par défaut et de le résoudre pour tout d’abord comprendre l’impact des modifications que vous pourriez apporter.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a>Étape 4. Comprenez quelles sont les fonctionnalités d’équipe actuellement disponibles dans Microsoft 365 Government-GCC High

Pour répondre aux besoins de nos clients du cloud public, il existe quelques différences entre les équipes dans Microsoft 365 Government-GCC High et teams dans les offres de l’entreprise. Pour savoir quelles fonctionnalités sont disponibles, consultez le tableau suivant.

[Description du service Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>Étape 5. Plan de gouvernance

Déterminez vos besoins en matière de gouvernance et comment vous pouvez les répondre. Pour plus d’informations, voir [plan de gouvernance dans teams](plan-teams-governance.md) .

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|Point de décision |<ul><li>Déterminez et documentez vos exigences de gouvernance conformément aux recommandations en [matière de plan de gouvernance dans teams](plan-teams-governance.md). </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Étape 6. Déploiement d’équipes pour la collaboration

Une fois que vous avez été intégré au service public Microsoft 365, vous pouvez suivre la procédure de déploiement recommandée décrite dans [la rubrique Comment déployer Microsoft teams](How-to-roll-out-teams.md). N’hésitez pas à vous engager avec votre adoption et votre équipe de gestion des changements et des champions.

Vous pouvez également utiliser [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour l’intégration du service.

