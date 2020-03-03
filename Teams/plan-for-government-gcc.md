---
title: Se préparer pour Microsoft 365 Secteur public - Déploiements GCC - Microsoft Teams
author: lolajacobsen
ms.author: lolaj
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
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51afc464b5f6d0fa698250d1255315535e383bf8
ms.sourcegitcommit: ed0ecb3b1250a23d3b91a5a33256aee1c3119db1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374321"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Plan pour Microsoft 365 Government-déploiements de GCC

Ce guide est destiné aux professionnels de l’informatique qui pilotent des déploiements d’Office 365 aux États-Unis, aux États-Unis, aux États-Unis, tribal ou d’autres entités du gouvernement territorial ou d’autres entités qui gèrent les données soumises aux lois et exigences gouvernementales, lorsque l’utilisation de Microsoft 365 Government-GCC est approprié pour répondre à ces exigences.

> [!NOTE]
> Si votre organisation a déjà satisfait au service Microsoft 365 Government-obligation d’éligibilité et qu’elle a été acceptée pour le programme, vous pouvez passer directement à l’étape 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Étape 1. Déterminez si votre organisation a besoin de Microsoft 365 Government-GCC et répond aux exigences d’éligibilité. 

L’environnement Microsoft 365 Government-GCC fournit une conformité aux exigences de l’administration américaine pour les services de Cloud Computing, y compris le FedRAMP modéré et la configuration requise pour les systèmes de données CJI et FTI.

En plus des fonctionnalités et des fonctionnalités d’Office 365, les organisations tirent parti des fonctionnalités suivantes qui sont propres à Microsoft 365 Government :

-   Le contenu du client de votre organisation est séparé de manière logique du contenu client dans les services Office 365 commerciaux de Microsoft.
-   Le contenu du client de votre organisation est enregistré aux États-Unis.
-   L’accès au contenu du client de votre organisation est limité aux membres du personnel de Microsoft.
-   Microsoft 365 Government-GCC est conforme aux certifications et homologations requises pour les clients du secteur public américain.

Vous trouverez des informations supplémentaires sur l’offre Microsoft 365 Government-GCC pour les clients du secteur public dans [Office 365 Government](https://products.office.com/government/compare-office-365-government-plans), y compris les [exigences d’éligibilité](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

La [Description du service fédéral des États-Unis d’Office 365](https://technet.microsoft.com/library/mt774581.aspx) décrit les avantages de la plateforme, qui sont centrés sur les exigences en matière de conformité aux États-Unis.

> [!Tip]
> Vous souhaiterez peut-être transférer les tableaux d’informations dans la description du service dans un classeur Excel et ajouter deux colonnes : **approprié pour mon organisation y/n** et **répond aux besoins de mon organisation y/n**. Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez si Microsoft 365 Government-GCC est approprié pour votre organisation.</li><li>Vérifiez que votre organisation répond aux conditions d’éligibilité.</li></ul> |

> [!Note]
> Microsoft 365 Government-GCC est uniquement disponible aux États-Unis. Les clients de l’administration non américaine peuvent opter pour un certain nombre de [forfaits Office 365 Government](https://products.office.com/en/government/compare-office-365-government-plans).


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Étape 2. Demander à Microsoft 365 Government-GCC

Après avoir décidé que ce service est approprié pour votre organisation, commencez le processus d' [application de ce service ici](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Étape 3. Comprendre Microsoft 365 Government-paramètres de sécurité par défaut de GCC.

Nous vous conseillons de prendre le temps de vérifier les paramètres de votre [administrateur et de votre sécurité](enable-features-office-365.md) avant de les modifier, et de réfléchir à la conformité avant de modifier les paramètres de sécurité par défaut.

|    |     |
|-----------|------------|
| ![Icône illustrant un point de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Décidez si vous voulez modifier l’un des paramètres de sécurité du service public Microsoft 365 par défaut et le résoudre pour tout d’abord comprendre l’impact des modifications que vous pourriez apporter.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Étape 4. Comprenez quelles fonctionnalités sont actuellement indisponibles ou désactivées par défaut. 

Pour répondre aux besoins de nos clients du cloud public, il existe quelques différences entre le gouvernement Microsoft 365 et les plans de l’entreprise. Pour savoir quelles fonctionnalités sont disponibles, consultez le tableau suivant.

|                             | Fonctionnalité                     | ANTÉRIEURES            |
|-----------------------------|-----------------------------|----------------|
| Assiette | Connexion | Disponibles |
| | Présence | Disponibles |
| | Présence unifiée (Skype entreprise et équipes unifiées) | Disponibles |
| Interactive | Actualité | Disponibles |
|  | Mon activité | Disponibles |
| Conversation | Conversation | Disponibles |
| | Fichiers | Disponibles |
| | Organigramme | Disponibles |
| | Interactive | Disponibles |
| | Interopérabilité (équipes 1:1-conversation Skype entreprise) | Disponibles |
| Équipes | Message du canal | Disponibles |
| | Fichiers de canal | Disponibles |
| | Onglet OneNote | Sur le backlog du secteur public |
| | Envoyer un canal par courrier électronique | Non disponibles |
| | Ajouter un membre | Disponibles |
| | Accès invité | Disponibles |
| Meetings | Programmer une réunion | Disponibles |
| | Rejoindre une réunion | Disponibles |
| | Réunion VoIP | Disponibles |
| | Partage de Bureau | Disponibles |
| | Donner et prendre le contrôle dans le partage | Disponibles |
| | Se connecter à partir d’une salle de conférence | Disponibles |
| | Jointure anonyme | Disponibles |
| | Enregistrement Cloud | Disponibles |
| | Notes de réunion | Disponibles |
| | Événements en direct | Disponibles |
| | Réunions fédérées | Disponibles |
| | Prise en charge de surface Hub | Disponibles |
| Appels | Contacts | Disponibles |
| | Des | Disponibles |
| | Messagerie vocale | Disponibles |
| | Appel VoIP | Disponibles |
| | Skype pour les entreprises : appel d’équipes | Disponibles |
| | Forfaits d'appels | Disponibles |
| | Audioconférence (en permettant aux participants à la réunion de se connecter via PSTN) | Disponibles |
| | Routage direct du système Microsoft Phone | Disponibles |
| | Salle d’attente pour les appelants PSTN | Disponibles |
| | File d’attente d’appels | Disponibles |
| | Prise en charge du patron et du délégué | Disponibles |
| | Consultation et transfert sécurisé | Disponibles |
| | Ne pas déranger la révolution | Disponibles |
| | Sonnerie distincte | Disponibles |
| | 1:1, xxx xxxx xxx xxxx xxxx xxx xxxx xxx xxx | Disponibles |
| | Transférer vers le groupe | Disponibles |
| | Transférer vers un appel PSTN | Disponibles |
| | Appels d’urgence-forfaits d’appels | Disponibles |
| | Prise en charge des téléphones SIP certifiés existants | Disponibles |
| | HID USB | Disponibles |
| | eDiscovery pour les appels et les réunions | Disponibles |
| | Standard automatique de l’Organisation | Disponibles |
| | Skype grand public-service d’appel d’équipe | Disponibles |
| Fichiers | Dernier | Disponibles |
| | Microsoft Teams | Disponibles |
| Enregistrer | Magasin d’applications | Disponibles |
| Rechercher | Contenus | Disponibles |
| | Personnes | Disponibles |
| | Fichiers | Disponibles |
| | Commandes de barre oblique | Disponibles |
| Conformément | Recherche de contenu de conformité | Disponibles |
| | Rétention | Disponibles |
| | Recherche dans le journal d’audit | Disponibles |
| | Conservation légale | Disponibles |
| | eDiscovery | Disponibles |

> [!Note]
> Une fois les autres charges de travail entièrement disponibles dans le Cloud de GCC, celles-ci deviennent disponibles dans teams lorsque la totalité du travail d’intégration supplémentaire est effectuée.


|    |     |
|-----------|------------|
| ![Icône illustrant un point de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Déterminez si l’ensemble des fonctionnalités d’équipe répond aux besoins de votre organisation.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Étape 5. Plan de gouvernance

Déterminez vos besoins en matière de gouvernance et comment vous pouvez les répondre. Pour plus d’informations, voir [plan de gouvernance dans teams](plan-teams-governance.md) .

|    |     |
|-----------|------------|
| ![Icône illustrant un point de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Déterminez et documentez vos exigences de gouvernance conformément aux recommandations en [matière de plan de gouvernance dans teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Étape 6. Déploiement d’équipes pour la collaboration

Une fois que vous avez été intégré au service public Microsoft 365, suivez le chemin de déploiement recommandé décrit dans [la rubrique Comment déployer Microsoft teams](How-to-roll-out-teams.md). N’hésitez pas à vous engager avec votre adoption et votre équipe de gestion des changements et des champions.

Vous pouvez également utiliser [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour l’intégration du service.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Étape 7. Déploiement d’équipes pour les réunions et la voix

C’est également le moment idéal pour organiser des réunions et des [fonctionnalités vocales](cloud-voice-deployment.md)dans le Cloud et commencer à utiliser Teams.

