---
title: Déploiements de Microsoft 365 Government - GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Conseils pour les professionnels de l’informatique en matière de gestion des déploiements Microsoft 365 au cours d’entités qui gèrent les données soumises à la réglementation du gouvernement américain
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: a55c7440b7d3183e93391ecc0e4f8781ba7b690f
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013298"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Planifier les déploiements de Microsoft 365 Government - GCC

Ces conseils sont adaptés aux professionnels de l’informatique qui sont responsables des déploiements de Microsoft 365 dans l’administration fédérale, l’État, le pays, le gouvernement local ou d’autres entités qui gèrent des données qui sont soumises aux réglementations gouvernementales et aux exigences, où l’utilisation de Microsoft 365 Government - GCC convient pour répondre à ces exigences. Nouveau 26 mars 2020 : Ne manquez pas notre guide de démarrage rapide téléchargeable [pour le GCC.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)

> [!IMPORTANT]
> Microsoft Teams connaît un pic considérable dans les appels en ligne et les conférences audio/vidéo en raison du coronavirus (COVID-19).<br/>
> 
>En réponse à l’augmentation immédiate du nombre d’appels et à la continuité des appels et à la disponibilité, Microsoft autorise les serveurs audio/vidéo de Microsoft Teams GCC à tirer parti de la capacité de traitement de nos centres de données commerciaux, ainsi que de nos centres de données du secteur public.<br/>
> 
>Ces serveurs audio/vidéo résident dans des serveurs limites du haut de Microsoft Azure FedRAMP aux États-Unis et ne stockent aucun contenu client. Toutefois, ces serveurs traitent l’audio et la vidéo pour les appels et les conférences et fonctionnent sous notre service commercial pendant cette période temporaire.<br/>
> 
>Le personnel qualifié et screened surveille ces serveurs pour l’accès potentiel aux données client en examine les éventuelles connexions interactives à ces serveurs. Le personnel qualifié répond aux exigences du GCC en matière d’accès au contenu du client. Pour plus d’informations sur le filtrage des exigences, voir la [description du service GCC.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)<br/>
> 
>Nous vous remercions pour votre soutien car nous prenons des mesures pour nous assurer que nos services restent disponibles et fiables dans ces temps extraordinaires.<br/>


> [!NOTE]
> Si votre organisation a déjà satisfait aux conditions d’éligibilité de Microsoft 365 Government - GCC et a demandé et accepté le programme, vous pouvez ignorer les étapes 1 et 2 et passer directement à l’étape 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Étape 1. Déterminez si votre organisation a besoin de Microsoft 365 Government - GCC et répond aux conditions d’éligibilité. 

L’environnement Microsoft 365 Government - GCC fournit la conformité avec les exigences du gouvernement américain pour les services cloud, notamment FedRAMP Modéré, et des exigences de justice pénale et de systèmes d’information fiscales fédéraux (types de données CJI et FTI).

En plus de profiter des fonctionnalités de Microsoft 365, les organisations bénéficient des fonctionnalités suivantes qui sont propres à Microsoft 365 Government - GCC :

-   Le contenu client de votre organisation est logiquement séparé du contenu des clients dans les services Microsoft 365 commerciaux de Microsoft.
-   Le contenu client de votre organisation est stocké aux États-Unis.
-   L’accès au contenu client de votre organisation est limité au personnel Microsoft dont l’écran est limité.
-   Microsoft 365 Secteur Public - GCC est conforme aux certifications et aux entreprises requises pour les clients du secteur public américain.

Vous pouvez trouver plus d’informations sur l’offre Microsoft 365 Government - GCC pour les clients du gouvernement américain sur les offres [Microsoft 365 Government,](https://products.office.com/government/compare-office-365-government-plans)y compris sur les conditions [d’éligibilité.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

La [description du service Public Microsoft 365 aux](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) États-Unis décrit les avantages de la plateforme, qui sont centrés autour des conditions de conformité requises aux États-Unis.

> [!Tip]
> Vous pouvez transférer les tables d’informations de la description du service dans un feuille de calcul Excel et ajouter deux colonnes : Pertinentes pour mon organisation **Y/N** et Répondre aux besoins de mon organisation **Y/N.** Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez si Microsoft 365 Government - GCC est approprié pour votre organisation.</li><li>Confirmez que votre organisation répond aux conditions d’éligibilité requises.</li></ul> |

> [!Note]
> Microsoft 365 Government - GCC est disponible uniquement aux États-Unis. Les clients non-us Government peuvent choisir parmi un certain nombre de [plans Microsoft 365 Secteur Secteur.](https://products.office.com/en/government/compare-office-365-government-plans)


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Étape 2. S’appliquer à Microsoft 365 Government - GCC

Ayant décidé que ce service est exact pour votre organisation, commencez le processus de demande [de ce service ici.](https://products.office.com/government/eligibility-validation)

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Étape 3. Comprendre les paramètres de sécurité par défaut de Microsoft 365 Government - GCC.

Nous vous recommandons de prendre le temps de passer en revue soigneusement vos [paramètres](enable-features-office-365.md) d’administration et de sécurité avant de les modifier, et de prendre en compte les conséquences sur la conformité avant de modifier les paramètres de sécurité par défaut.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Décidez si vous allez modifier les paramètres de sécurité par défaut de Microsoft 365 Government - GCC, en résolvant pour comprendre d’abord l’impact des modifications que vous pourriez apporter.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Étape 4. Comprendre les fonctionnalités actuellement indisponibles ou désactivées par défaut.

Pour répondre aux besoins de nos clients cloud du secteur, il existe quelques différences entre les plans Microsoft 365 Secteur, Cloud et Entreprise. Consultez le tableau suivant pour voir quelles fonctionnalités sont disponibles.

[Description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description)

> [!Note]
> Une fois que d’autres charges de travail sont entièrement disponibles dans le cloud gcc, elles deviennent disponibles dans Teams une fois tout le travail d’intégration supplémentaire terminé.


|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Déterminez si l’ensemble des fonctionnalités de Teams répond aux besoins de votre organisation.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Étape 5. Plan de gouvernance

Déterminez vos exigences de gouvernance et la manière dont vous pouvez les respecter. Pour plus [d’informations, voir Planifier la gouvernance dans Teams.](plan-teams-governance.md)

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Déterminez et consignez vos exigences de gouvernance, en suivant les recommandations [de la politique de gouvernance de Teams.](plan-teams-governance.md)</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Étape 6. Déployer Teams pour la collaboration

Après avoir été intégré à Microsoft 365 Government – GCC, suivez la voie de déploiement recommandée décrite dans comment déployer [Microsoft Teams.](./deploy-overview.md) N’oubliez pas de vous impliquer avec votre équipe Adoption et gestion du changement et les champions Teams.

Vous pouvez également travailler avec [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour intégrer le service.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Étape 7. Déployer Teams pour les réunions et la voix

C’est également le moment idéal pour utiliser Teams avec l’ensemble des parties prenantes pour commencer à planifier le déploiement de réunions et de fonctionnalités [vocales cloud.](./cloud-voice-landing-page.md)