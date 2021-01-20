---
title: Microsoft 365 Government - Déploiements high GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Conseils pour les professionnels de l’informatique en matière de gestion des déploiements d’Office 365 au cours d’entités qui gèrent les données soumises à la réglementation du gouvernement américain.
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
ms.openlocfilehash: ced9f5cc68ce18bc7e1670db4031ff85b7c76ff2
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909268"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a>Planifier les déploiements d’Office 365 Government - GCC High

Ces conseils sont adaptés aux professionnels de l’informatique qui sont responsables des déploiements d’Office 365 dans des entités gouvernementales fédérale aux États-Unis ou d’autres entités qui gèrent des données soumises à des réglementations gouvernementales et des exigences, où l’utilisation d’Office 365 Government – GCC High convient à ces exigences.

> [!NOTE]
> Si votre organisation a déjà satisfait aux conditions d’éligibilité d’Office 365 Government – GCC High et a accepté le programme, vous pouvez ignorer les étapes 1 et 2 et passer directement à l’étape 3.

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a>Étape 1. Déterminez si votre organisation a besoin d’Office 365 Government - GCC High et répond aux conditions d’éligibilité. 

L’environnement Office 365 Government - GCC High fournit la conformité aux exigences du gouvernement américain pour les services cloud. En plus de profiter des fonctionnalités d’Office 365, les organisations bénéficient des fonctionnalités suivantes qui sont propres à Office 365 Government – GCC High :

- Le contenu client de votre organisation est logiquement séparé du contenu des clients dans les services Office 365 commerciaux de Microsoft.
- Le contenu client de votre organisation est stocké aux États-Unis.
- L’accès au contenu client de votre organisation est limité au personnel Microsoft dont l’écran est limité.
- Office 365 Secteur Public – Gcc High est conforme aux certifications et aux entreprises requises pour les clients du secteur public américain.

Pour plus d’informations sur l’offre Office 365 Government – GCC High pour les clients du gouvernement américain, voir les offres [Office 365 Government,](https://products.office.com/government/compare-office-365-government-plans)notamment les conditions [d’éligibilité.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

La [description du service Office 365 us Government service](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) décrit les avantages de la plateforme, qui sont centrés sur les conditions de conformité requises aux États-Unis.


> [!Tip]
> Vous pouvez transférer les tables d’informations de la description du service dans un feuille de calcul Excel et ajouter deux colonnes : Pertinentes pour mon organisation **Y/N** et Répondre aux besoins de mon organisation **Y/N.** Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez si Office 365 Government - GCC High convient à votre organisation.</li><li>Confirmez que votre organisation répond aux conditions d’éligibilité requises.</li></ul> |

> [!Note]
> Office 365 Government - GCC High est disponible uniquement aux États-Unis. Les clients non-us Government peuvent choisir parmi un certain nombre d’plans [Office 365 Secteur Public.](https://products.office.com/en/government/compare-office-365-government-plans)

## <a name="step-2-apply-for-office-365-government---gcc-high"></a>Étape 2. S’appliquer à Office 365 Service public - GCC High

Ayant décidé que ce service est exact pour votre organisation, commencez le processus de demande [de ce service.](https://products.office.com/government/eligibility-validation)


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a>Étape 3. Comprendre les paramètres de sécurité par défaut d’Office 365 Government - GCC High.

Nous vous conseillons de prendre le temps de passer en revue soigneusement vos [paramètres](enable-features-office-365.md) d’administration et de sécurité avant de les modifier, et de prendre en compte les conséquences sur la conformité avant de modifier les paramètres de sécurité par défaut.

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Décidez si vous devez modifier l’un des paramètres de sécurité Office 365 Government - GCC High, en résolvant pour comprendre d’abord l’impact des modifications que vous pourriez apporter.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a>Étape 4. Comprendre les fonctionnalités Teams actuellement disponibles dans Office 365 Service public - GCC High

Pour répondre aux besoins de nos clients cloud du secteur public, il existe certaines différences entre Teams dans Office 365 Secteur Public - Gcc High et Teams dans les plans d’entreprise. Consultez le tableau suivant pour voir quelles fonctionnalités sont disponibles.

[Description du service Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>Étape 5. Plan de gouvernance

Déterminez vos exigences de gouvernance et la manière dont vous pouvez les respecter. Pour plus [d’informations, voir Planifier la gouvernance dans Teams.](plan-teams-governance.md)

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|Point de décision |<ul><li>Déterminez et consignez vos exigences de gouvernance, en suivant les recommandations de la politique [de gouvernance de Teams.](plan-teams-governance.md) </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Étape 6. Déployer Teams pour la collaboration

Après avoir été intégré à Office 365 Government – GCC High, suivez la voie de déploiement recommandée décrite dans la façon de déployer [Microsoft Teams.](How-to-roll-out-teams.md) N’oubliez pas de vous impliquer avec votre équipe Adoption et gestion du changement et les champions Teams.

Vous pouvez également travailler avec [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour intégrer le service.

> [!NOTE]
> Le client Mac Teams pour les environnements GCCH n’est pas encore pris en charge.

