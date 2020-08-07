---
title: Office 365 gouvernementale-déploiements de GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Conseils destinés aux professionnels de l’informatique pour piloter les déploiements d' 365 Office
localization_priority: Normal
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
ms.openlocfilehash: 2fb916b30a26694debf8d699fc05cc3fcc8c8c77
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581245"
---
# <a name="plan-for-office-365-government---gcc-deployments"></a>Plan pour Office 365 Government-déploiements de GCC

Ce guide est destiné aux professionnels de l’informatique qui pilotent des déploiements d’Office 365 aux États-Unis, aux États-Unis, aux États-Unis, tribal ou d’autres entités du gouvernement territorial ou d’autres entités qui gèrent les données soumises aux lois et exigences gouvernementales, lorsque l’utilisation d’Office 365 Government-GCC est appropriée pour respecter ces exigences. Nouveau 26 mars, 2020 : ne manquez pas notre [Guide de démarrage rapide](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)téléchargeable pour la mise en route de GCC.

> [!IMPORTANT]
> Microsoft teams est confronté à un énorme pic dans les appels en ligne et les conférences audio/vidéo à l’aide de coronavirus (COVID-19) Pandemic.<br/>
> 
>En réponse à une augmentation sans précédent des appels et à des fins de continuité et de disponibilité, Microsoft est en mesure de faire en sorte que les serveurs de contenus audio et vidéo Microsoft teams se chargent de la capacité de traitement de nos centres de données commerciaux et de nos centres de données du secteur public.<br/>
> 
>Ces serveurs audio/vidéo résident dans les serveurs de limite d’acforte accréditation Microsoft Azure FedRAMP aux États-Unis et ne stockent aucun contenu de client. Toutefois, ces serveurs traitent l’audio et la vidéo pour les appels et les conférences et sont soumis à la même équipe commerciale pendant cette période intermédiaire.<br/>
> 
>Les membres qualifiés et dotés d’une capture d’écran analysent ces serveurs pour un accès potentiel aux données du client en passant en revue les éléments de journal interactifs de ces serveurs. Le personnel qualifié répond à la configuration requise pour l’accès au contenu du client. Pour plus d’informations sur la configuration requise pour le filtrage, voir la [Description du service GCC](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).<br/>
> 
>Nous vous remercions d’avoir pris le temps de nous assurer que nos services restent disponibles et fiables dans ces temps exceptionnels.<br/>


> [!NOTE]
> Si votre organisation a déjà satisfait au service public d’Office 365, et qu’elle l’a appliquée et qu’elle a été acceptée dans le programme, vous pouvez passer directement à l’étape 3. 

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-and-meets-eligibility-requirements"></a>Étape 1. Déterminez si votre organisation a besoin d’Office 365 Government-GCC et répond aux exigences d’éligibilité. 

L’environnement Office 365 Government-GCC fournit une conformité aux exigences de l’administration américaine pour les services de Cloud Computing, y compris le FedRAMP modéré et la configuration requise pour les systèmes de données CJI et FTI.

Outre les fonctionnalités et les fonctionnalités d’Office 365, les organisations disposent des fonctionnalités suivantes qui sont propres à Office 365 Government :

-   Le contenu du client de votre organisation est séparé de manière logique du contenu client dans les services Office 365 commerciaux de Microsoft.
-   Le contenu du client de votre organisation est enregistré aux États-Unis.
-   L’accès au contenu du client de votre organisation est limité aux membres du personnel de Microsoft.
-   Office 365 Government-GCC est conforme aux certifications et aux accréditations requises pour les clients du secteur public américain.

Vous trouverez des informations supplémentaires sur l’offre Office 365 Government-GCC pour les clients du secteur public dans [office 365 Government](https://products.office.com/government/compare-office-365-government-plans) [.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

La [Description du service fédéral des États-Unis d’Office 365](https://technet.microsoft.com/library/mt774581.aspx) décrit les avantages de la plateforme, qui sont centrés sur les exigences en matière de conformité aux États-Unis.

> [!Tip]
> Vous souhaiterez peut-être transférer les tableaux d’informations dans la description du service dans un classeur Excel et ajouter deux colonnes : **approprié pour mon organisation y/n** et **répond aux besoins de mon organisation y/n**. Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez si Office 365 Government-GCC est approprié pour votre organisation.</li><li>Vérifiez que votre organisation répond aux conditions d’éligibilité.</li></ul> |

> [!Note]
> Office 365 Government-GCC est uniquement disponible aux États-Unis. Les clients de l’administration non américaine peuvent opter pour un certain nombre de [forfaits Office 365 Government](https://products.office.com/en/government/compare-office-365-government-plans).


## <a name="step-2-apply-for-office-365-government---gcc"></a>Étape 2. Demander à Office 365 Government-GCC

Après avoir décidé que ce service est approprié pour votre organisation, commencez le processus d' [application de ce service ici](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-office-365-government---gcc-default-security-settings"></a>Étape 3. Comprendre le gouvernement d’Office 365-paramètres de sécurité par défaut de GCC.

Nous vous conseillons de prendre le temps de vérifier les paramètres de votre [administrateur et de votre sécurité](enable-features-office-365.md) avant de les modifier, et de réfléchir à la conformité avant de modifier les paramètres de sécurité par défaut.

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Déterminez si vous souhaitez modifier l’un des paramètres de sécurité par défaut du service d’administration de la sécurité d’Office 365, puis résolvez les problèmes liés aux modifications que vous pourriez apporter.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Étape 4. Comprenez quelles fonctionnalités sont actuellement indisponibles ou désactivées par défaut.

Pour répondre aux besoins de nos clients du cloud public, il existe quelques différences entre le gouvernement d’Office 365 et les plans de l’entreprise. Pour savoir quelles fonctionnalités sont disponibles, consultez le tableau suivant.

[Description du service Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> Une fois les autres charges de travail entièrement disponibles dans le Cloud de GCC, celles-ci deviennent disponibles dans teams lorsque la totalité du travail d’intégration supplémentaire est effectuée.


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Déterminez si l’ensemble des fonctionnalités d’équipe répond aux besoins de votre organisation.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Étape 5. Plan de gouvernance

Déterminez vos besoins en matière de gouvernance et comment vous pouvez les répondre. Pour plus d’informations, voir [plan de gouvernance dans teams](plan-teams-governance.md) .

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Déterminez et documentez vos exigences de gouvernance conformément aux recommandations en [matière de plan de gouvernance dans teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Étape 6. Déploiement d’équipes pour la collaboration

Une fois que vous avez été intégré au service public d’Office 365, vous pouvez suivre la procédure de déploiement recommandée décrite dans [la rubrique Comment déployer Microsoft teams](How-to-roll-out-teams.md). N’hésitez pas à vous engager avec votre adoption et votre équipe de gestion des changements et des champions.

Vous pouvez également utiliser [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour l’intégration du service.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Étape 7. Déploiement d’équipes pour les réunions et la voix

C’est également le moment idéal pour organiser des réunions et des [fonctionnalités vocales](cloud-voice-deployment.md)dans le Cloud et commencer à utiliser Teams.

