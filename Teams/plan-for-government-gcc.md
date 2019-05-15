---
title: Se préparer pour Microsoft 365 Secteur public - Déploiements GCC - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/03/2019
ms.topic: article
ms.service: msteams
ms.reviewer: daro
description: Conseils pour les professionnels de l’informatique pour les déploiements de lecteur Office 365 dans les entités qui gèrent les données soumis à la réglementation américaine officielle
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 025a1f22552fa8c196e9eeb4bee6b7e6e19eebdf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902454"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Plan pour Microsoft 365 gouvernement - déploiements GCC

Ces instructions sont destinées aux informaticiens qui poussent les déploiements d’Office 365 dans US federal, état, local, communautaires ou territoriale gouvernementales ou d’autres entités qui gèrent les données sont soumis aux réglementations en matière de, où l’utilisation de Microsoft Pour le gouvernement 365 - GCC est approprié répondre à ces exigences.

> [!NOTE]
> Si votre organisation a déjà remplies Microsoft 365 gouvernement - conditions GCC et appliqués pour et acceptation dans le programme, vous pouvez ignorer les étapes 1 et 2 et passer directement à l’étape 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Étape 1. Déterminez si votre organisation a besoin pour le gouvernement 365 Microsoft - GCC et répond aux conditions requises. 

Le gouvernement Microsoft 365 - GCC environment fournit la conformité aux États-Unis en matière d’administration des services en nuage, y compris FedRAMP modéré et exigences relatives aux systèmes d’information impôts (types de données CJI et FTI) et judiciaires.

En plus de profiter des fonctionnalités et capacités d’Office 365, les organisations bénéficient les fonctionnalités suivantes qui sont propres à Microsoft 365 gouvernement - GCC :

-   Contenu de client de votre organisation est logiquement séparé du contenu client dans les services Office 365 commerciales de Microsoft.
-   Contenu de client de votre organisation est stocké dans des États-Unis.
-   Accès au contenu du client de votre organisation est limité aux filtré personnel de Microsoft.
-   Pour le gouvernement Microsoft 365 - GCC est conforme aux certifications et désormais sont requis pour les clients du secteur Public américain.

Vous trouverez plus d’informations sur le gouvernement 365 Microsoft - GCC offre pour les clients américains [que plans Office 365 pour](https://products.office.com/government/compare-office-365-government-plans), y compris de [conditions requises](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [description du service Office 365 américaine](https://technet.microsoft.com/library/mt774581.aspx) décrit les avantages de la plate-forme, qui concernent la conformité aux États-Unis.

> [!Tip]
> Vous souhaiterez peut-être transférer les tables d’information dans la description du service dans un classeur Excel et ajoutez deux colonnes : **pertinents pour mon organisation Y/N** et **répond aux besoins de mon entreprise Y/N**. Ensuite, vous pouvez consulter cette liste avec vos collègues pour confirmer que ce service répond aux besoins de votre organisation.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décider si Microsoft 365 gouvernement - GCC est approprié pour votre organisation.</li><li>Vérifiez que votre organisation répond aux conditions requises.</li></ul> |

> [!Note]
> Pour le gouvernement Microsoft 365 - GCC est disponible uniquement aux États-Unis. La possibilité à partir d’un certain nombre de [plans Office 365 pour](https://products.office.com/en/government/compare-office-365-government-plans)les clients non – américaine.


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Étape 2. Appliquer pour le gouvernement Microsoft 365 - GCC

Ayant décidé que ce service est adapté à votre organisation, démarrer le processus [d’application de ce service ici](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Étape 3. Comprendre Microsoft 365 gouvernement - paramètres de sécurité par défaut GCC.

Nous vous conseillons temps Lisez attentivement vos [paramètres de sécurité et d’administration](enable-features-office-365.md) avant de les modifier, tenez compte des conséquences sur la conformité avant d’apporter des modifications aux paramètres de sécurité par défaut.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Décider que si vous allez modifier la valeur par défaut Microsoft 365 gouvernement - paramètres de sécurité GCC, résolu en adresse IP d’abord comprendre l’impact des modifications peut avoir.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Étape 4. Comprendre les fonctionnalités sont actuellement pas disponible ou désactivé par défaut. 

Pour prendre en compte les exigences de nos clients du nuage gouvernement, il existe quelques différences entre Microsoft 365 gouvernement - GCC et plans de l’entreprise. Reportez-vous au tableau suivant pour voir quelles fonctionnalités sont disponibles.

|                             | Fonctionnalité                     | GCC            |
|-----------------------------|-----------------------------|----------------|
| Base de | Connexion | Disponibles |
| | Présence | Disponibles |
| | Présence unifiée (Skype pour professionnels et les équipes unifiées) | Disponibles |
| Activité | Flux | Disponibles |
|  | Mon activité | Disponibles |
| Conversation | Conversation | Disponibles |
| | Fichiers | Disponibles |
| | Organigramme hiérarchique | Disponibles |
| | Activité | Disponibles |
| | Interopérabilité (1:1 équipes-Skype pour la conversation de l’entreprise) | Disponibles |
| Équipes | Message de canal | Disponibles |
| | Fichiers de canal | Disponibles |
| | Onglet OneNote | Sur la file d’attente pour le gouvernement |
| | Un canal de messagerie | Non disponibles |
| | Ajouter des membres | Disponibles |
| | Accès invité | Disponibles |
| Réunions | Organiser une réunion | Disponibles |
| | Participer à la réunion | Disponibles |
| | Réunion VoIP | Disponibles |
| | Partage de Bureau | Disponibles |
| | Prendre d’et céder le contrôle dans le partage | Disponibles |
| | Se connecter à partir d’une salle de conférence | Disponibles |
| | Participation anonyme | Disponibles |
| | Enregistrement de nuage | Sur la file d’attente pour le gouvernement |
| | Notes de réunion | Disponibles |
| | Diffusion des réunions | Sur la file d’attente pour le gouvernement |
| | Réunions fédérées | Disponibles |
| | Prise en charge de surface Hub (preview) | Sur la file d’attente pour le gouvernement |
| Appels | Contacts | Disponibles |
| | Historique | Disponibles |
| | Messagerie vocale | Disponibles |
| | Appel VoIP | Disponibles |
| | Skype pour les entreprises - équipes appelant | Disponibles |
| | Forfaits d'appels | Disponibles |
| | Services d’audioconférence (en autorisant les participants à la réunion joindre via PSTN) | Disponibles |
| | Système téléphonique de Microsoft direct de routage | Disponibles |
| | Salle d’attente pour les appelants PSTN | Disponibles |
| | File d’attente des appels | Disponibles |
| | Prise en charge patron et délégué | Disponibles |
| | Transfert consultatif et fiable | Disponibles |
| | Ne pas déranger avancée | Disponibles |
| | Sonnerie distincte | Disponibles |
| | 1:1 pour l’escalade d’appel de groupe avec Skype pour les entreprises, des équipes et aux participants PSTN | Disponibles |
| | Transférer vers un groupe | Disponibles |
| | Transférer vers un appel RTC | Disponibles |
| | Appel d’urgence - appel de Plans | Disponibles |
| | Prise en charge pour les téléphones SIP certifiés existants | Disponibles |
| | USB HID | Disponibles |
| | découverte électronique pour les appels et les réunions | Disponibles |
| | Standard automatique d’organisation | Disponibles |
| | Consommateur de Skype - prise en charge des appels aux équipes | Disponibles |
| Fichiers | Récents | Disponibles |
| | Microsoft Teams | Disponibles |
| boutique | Magasin d’applications | Sur la file d’attente pour le gouvernement |
| Rechercher | Messages | Disponibles |
| | Personnes | Disponibles |
| | Fichiers | Disponibles |
| | Commandes de barre oblique | Disponibles |
| Conformité | Recherche de contenu de la conformité | Disponibles |
| | Rétention | Disponibles |
| | Recherche des journaux d’audit | Disponibles |
| | Conservation légale | Disponibles |
| | eDiscovery | Disponibles |

> [!Note]

> Une fois que les autres charges de travail sont totalement disponibles dans le nuage GCC, puis ils seront disponibles dans les équipes lorsque toutes les tâches d’intégration sont terminée.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Décider si le jeu de fonctions équipes répond aux besoins de votre organisation.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Étape 5. Planifier la gouvernance

Déterminer vos besoins en matière de gouvernance et comment y répondre. Pour plus d’informations, accédez à [planifier la gouvernance dans les équipes](plan-teams-governance.md) .

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Déterminer et documenter vos besoins de gouvernance, selon les instructions de [planification de la gouvernance dans les équipes](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Étape 6. Déployer des équipes pour la collaboration

Une fois que vous avez été onboarded Microsoft 365 gouvernement - GCC, vous pouvez suivre l’approche de déploiement standard de l’utilisation [FastTrack](https://www.microsoft.com/fasttrack) et votre partenaire intégré au service que vous avez choisie.

Lorsque vous êtes prêt, déployez équipes pour [Activer la collaboration au sein de votre organisation via les équipes et les canaux](teams-overview.md). Veillez à prendre part avec votre équipe d’Adoption et de gestion des modifications ou les champions équipes.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Étape 7. Déployer des équipes pour les réunions et voix

C’est également un moment idéal pour utiliser des équipes à votre groupe des parties prenantes plus large pour commencer la planification de déploiement des réunions et des [fonctionnalités de voix dans le nuage](cloud-voice-deployment.md).

