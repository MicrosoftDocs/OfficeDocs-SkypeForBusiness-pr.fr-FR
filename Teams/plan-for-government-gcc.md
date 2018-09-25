---
title: Planification de Microsoft pour le gouvernement 365 - déploiements GCC - Microsoft Teams
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Conseils pour les professionnels de l’informatique pour les déploiements de lecteur Office 365 dans les entités qui gèrent les données soumis à la réglementation américaine officielle
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 410edd32855c85d2efa5a631cb893c1a5307a5e6
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015124"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Plan pour Microsoft 365 gouvernement - déploiements GCC

Ces instructions sont destinées aux informaticiens qui poussent les déploiements d’Office 365 dans US federal, état, local, communautaires ou territoriale gouvernementales ou d’autres entités qui gèrent les données sont soumis aux réglementations en matière de, où l’utilisation de Microsoft Pour le gouvernement 365 - GCC est approprié répondre à ces exigences.

> [!NOTE]
> Si votre organisation a déjà remplies Microsoft 365 gouvernement - conditions GCC et appliqués pour et acceptation dans le programme, vous pouvez ignorer les étapes 1 à 4 et passez directement à l’étape 5 pour commencer le déploiement. 

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
| ![](media/audio_conferencing_image9.png)<br/>Étape suivante|<ul><li>Comprendre les fonctionnalités fournies par Microsoft 365 gouvernement - GCC.</li></ul>|

> [!Note]
> Pour le gouvernement Microsoft 365 - GCC est disponible uniquement aux États-Unis. La possibilité à partir d’un certain nombre de [plans Office 365 pour](https://products.office.com/en/government/compare-office-365-government-plans)les clients non – américaine.

## <a name="step-2-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Étape 2. Comprendre les fonctionnalités sont actuellement pas disponible ou désactivé par défaut. 

Pour prendre en compte les exigences de nos clients du nuage gouvernement, il existe quelques différences entre Microsoft 365 gouvernement - GCC et plans de l’entreprise. Les fonctionnalités répertoriées dans le tableau suivant ne sont pas disponibles.

| Fonctionnalité                     | Raison            |
|-----------------------------|-------------------|
| Appel et enregistrement de la réunion  | Enregistrement dépend du Stream Microsoft, qui sera disponible dans les plans américains à l’avenir. |
| Applications       | Applications (tels que des robots, les onglets et les connecteurs) ne sont pas disponibles à l’origine, mais nous allons fonctionne pour les rendre disponibles dès que tous leurs composants répondent à la barre de conformité FedRAMP modéré. |
| Un canal de messagerie             | L’architecture actuelle de la fonctionnalité n’est pas pris en charge dans les plans pour le gouvernement. |
| Présence unifiée            | Nous sommes travail fin de nos clients professionnels tout d’abord pour cette fonctionnalité importante. Il sera disponible pour les clients pour le gouvernement à l’avenir. |
| Conversation interopérabilitée entre équipes & SfB utilisateurs            | Interopérabilité dépend de Service de présence unifiée (UPS) et ne peut pas fonctionner tant que GCC équipes clients sont activées pour l’onduleur. |
| Notifications par courrier électronique         | L’architecture actuelle de la fonctionnalité n’est pas pris en charge dans les plans américains. Le travail est en cours pour rendre cette fonctionnalité accessible aux clients américains des plans à l’avenir. |


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Décider si le gouvernement 365 Microsoft - jeu de fonctions GCC répond aux besoins de votre organisation.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Étape suivante|<ul><li>Comprendre les paramètres de sécurité par défaut.</li></ul>|

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Étape 3. Comprendre Microsoft 365 gouvernement - paramètres de sécurité par défaut GCC.

Nous vous conseillons temps Lisez attentivement vos [paramètres de sécurité et d’administration](enable-features-office-365.md) avant de les modifier, tenez compte des conséquences sur la conformité avant d’apporter des modifications aux paramètres de sécurité par défaut.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Décider que si vous allez modifier la valeur par défaut Microsoft 365 gouvernement - paramètres de sécurité GCC, résolu en adresse IP d’abord comprendre l’impact des modifications peut avoir.</li></ul> |

## <a name="step-4-apply-for-microsoft-365-government---gcc"></a>Étape 4. Appliquer pour le gouvernement Microsoft 365 - GCC

Ayant décidé que ce service est adapté à votre organisation, démarrer le processus [d’application de ce service ici](https://products.office.com/government/eligibility-validation).

## <a name="step-5-plan-for-governance"></a>Étape 5. Planifier la gouvernance

Déterminer vos besoins en matière de gouvernance et comment y répondre. Pour plus d’informations, accédez à [planifier la gouvernance dans les équipes](plan-teams-governance.md) .

## <a name="step-6-deploy-teams-for-collaboration"></a>Étape 6. Déployer des équipes pour la collaboration

Une fois que vous avez été onboarded Microsoft 365 gouvernement - GCC, vous pouvez suivre l’approche de déploiement standard de l’utilisation [FastTrack](https://fasttrack.microsoft.com/fasttrack-faq) et votre partenaire intégré au service que vous avez choisie.

Lorsque vous êtes prêt, déployez équipes pour [Activer la collaboration au sein de votre organisation via les équipes et les canaux](teams-overview.md). Veillez à prendre part avec votre équipe d’Adoption et de gestion des modifications ou les champions équipes.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Étape 7. Déployer des équipes pour les réunions et voix

C’est également un moment idéal pour utiliser des équipes à votre groupe des parties prenantes plus large pour commencer la planification de déploiement des réunions et des [fonctionnalités de voix dans le nuage](cloud-voice-deployment.md).

