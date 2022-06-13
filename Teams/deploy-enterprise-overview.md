---
title: Présentation du déploiement de Microsoft Teams en entreprise
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Découvrez comment déployer les fonctionnalités d’entreprise de Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: fae55eb230c3c0a450a95eb00e50861888bbe3f1
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045573"
---
# <a name="teams-enterprise-deployment-overview"></a>Présentation du déploiement de Teams en entreprise

Si vous êtes fans une moyenne ou grande entreprise, vous devez penser au futur déploiement du service auprès de vos utilisateurs, au déploiement prévu du client Microsoft Teams auprès d’eux, à l’impact éventuel de votre conception réseau sur la qualité de la communication en temps réel, et bien plus encore.

> [!NOTE]
> Si vous ne l’avez pas déjà fait, nous vous suggérons vivement de commencer votre déploiement Teams avec un pilote. Un pilote vous permettra, ainsi qu’à quelques utilisateurs précoces, de vous familiariser avec Teams et ses fonctionnalités avant votre planification et votre déploiement éventuel. Pour plus d’informations sur le démarrage de votre pilote, consultez [Démarrage avec Microsoft Teams](get-started-with-teams-quick-start.md).

Dès que vous avez lu les sections ci-dessous et que vous êtes prêt à commencer le déploiement de Teams dans votre organisation, veuillez consulter la rubrique [Configurer Microsoft Teams dans votre entreprise](deploy-enterprise-setup.md).

## <a name="architecture"></a>Architecture

Teams est étroitement intégré à Microsoft 365 et utilise de nombreuses fonctionnalités de conversation, de partage de fichiers, de réunions, de téléphonie, de diffusion en continu de vidéos, et bien plus encore. Avant de déployer Teams, consultez les [affiches sur les solutions d’architecture informatique et de téléphonie Microsoft Teams](teams-architecture-solutions-posters.md) pour vous familiariser avec le fonctionnement de Teams avec le reste de Microsoft 365, puis créer ainsi une expérience de collaboration complète pour vos utilisateurs.

## <a name="workloads"></a>Charges de travail

Teams comporte trois charges de travail déployables indépendamment les unes des autres : **conversation, équipes et canaux** ; **réunions et conférences** ; et **connectivité du système téléphonique et du RTC (réseau téléphonique commuté)**. Chaque charge de travail fait l’objet d’une section spécifique dans notre documentation pour faciliter la recherche d’informations sur la charge de travail en question. Cela inclut des informations sur la planification du déploiement.

Si vous souhaitez en savoir plus sur la planification du déploiement de la charge de travail de votre choix, veuillez consulter les articles suivants :

- [Conversations, équipes et canaux](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [Réunions et conférences](deploy-meetings-microsoft-teams-landing-page.md)
- [Connectivité du système téléphonique et du RTC (réseau téléphonique commuté)](cloud-voice-landing-page.md)

## <a name="network-planner"></a>Planificateur de réseau

La planification du réseau pour Teams est extrêmement importante lorsque vous avez un grand nombre d’utilisateurs et/ou des réseaux complexes ou les deux. Teams prend en charge les appels vocaux et les visioconférences, qui s’appuient sur les communications en temps réel pour offrir la meilleure expérience possible aux utilisateurs. Les réseaux doivent :

- Offrir une bande passante suffisante pour héberger l’ensemble des appels vocaux, des visioconférences, des réunions, des partages d’écran, et bien plus encore.
- Disposer d’un matériel réseau qui prend en charge les protocoles de communication en temps réel.
- Autoriser les ports réseau requis entre les appareils sur vos réseaux, les services Microsoft 365 et les utilisateurs externes.

Si vous souhaitez en savoir plus sur les exigences du réseau Teams, veuillez consulter les articles suivants :

- [Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)
- [Serveurs proxy pour Teams ou Skype Entreprise Online](proxy-servers-for-skype-for-business-online.md)

Pour vous aider dans le processus de planification, Teams inclut le Planificateur de réseau. Le Planificateur de réseau vous pose des questions sur le nombre et les types d’utilisateurs dont vous disposez, le nombre de sites de votre organisation, la capacité de bande passante de vos liens réseau, et bien plus encore. À l’aide de ces informations, le Planificateur réseau crée un rapport qui indique les besoins en bande passante pour chaque activité, ainsi que les recommandations.

 > [!div class="nextstepaction"]
> [Utiliser le Planificateur de réseau](https://admin.teams.microsoft.com/networkplanner/organization)

(Vous devez être [administrateur général de Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) pour ouvrir le Planificateur de réseau.)

Si vous souhaitez en savoir plus sur le fonctionnement du Planificateur de réseau, veuillez consulter la rubrique [Utiliser le Planificateur de réseau de Microsoft Teams](network-planner.md).

Pour consulter un exemple de la manière dont le Planificateur de réseau peut planifier votre réseau, veuillez consulter la rubrique [Utilisation du Planificateur de réseau : exemple de scénario](tutorial-network-planner-example.yml).

## <a name="teams-advisor"></a>Conseiller pour Teams

Le conseiller pour Teams est une solution dans Teams qui réunit les équipes, les canaux, le partage de fichiers et le Planificateur, pour créer un projet de déploiement dans votre organisation. Le conseiller Teams crée un plan de projet spécifique à la charge de travail sélectionnée (conversation, équipes et canaux, par exemple). Ce plan inclut les tâches recommandées à effectuer lors de votre déploiement. Chaque tâche contient des instructions, des suggestions et des liens vers des articles pertinents pour vous guider tout au long du processus. Vous pouvez facilement affecter des tâches à une ou plusieurs personnes, puis spécifier des dates de début et de fin de chaque tâche.

> [!TIP]
> Découvrez comment utiliser le Conseiller pour Teams pour vous aider à planifier votre déploiement Teams en complétant le module[Déployer à l’aide du Conseiller pour Teams](/learn/modules/m365-teams-rollout-using-advisor/) sur Microsoft Learn.

> [!div class="nextstepaction"]
> [Accéder au Conseiller pour Teams](https://admin.teams.microsoft.com/teams-deployment)

(Vous devez être [administrateur général de Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) pour ouvrir le Conseiller pour Teams.)

Si vous souhaitez en savoir plus sur le fonctionnement du Conseiller pour Teams, veuillez consulter la rubrique [Utiliser le Conseiller pour Teams pour faciliter le déploiement de Microsoft Teams](use-advisor-teams-roll-out.md).

## <a name="lifecycle-and-governance-planning"></a>Planification du cycle de vie et de la gouvernance

Lorsque vous planifiez votre déploiement Teams, vous devez prendre en compte le cycle de vie des équipes, des canaux, des fichiers, et bien plus encore dans votre organisation. Vous devez également penser aux types d’informations que vous y stockerez. Vous pouvez créer des équipes pour un projet spécifique, pour un service ou les utiliser comme ressource centrale pour l’ensemble de l’organisation. Chacune de ces utilisations a des exigences différentes, d’où les questions suivantes :

- Pendant combien de temps les équipes resteront-elle actives ?
- Qui doit posséder et gérer les équipes et leurs canaux ?
- Certaines exigences de conformité doivent-elles s’appliquer à certaines équipes, mais pas à d’autres ?
- Une stratégie de noms doit-elle être en place pour aider les utilisateurs à identifier la bonne équipe ?

La création de stratégies et d’instructions dans le cadre de votre déploiement initial permet à vos utilisateurs de trouver les informations dont ils ont besoin. Toutefois, un point tout aussi important : les stratégies appropriées vous aideront à protéger votre organisation contre la fuite d’informations, à vous conformer aux exigences réglementaires, puis à conserver les informations à des fins d’archivage.

Si vous souhaitez en savoir plus sur la gestion et la gouvernance du cycle de vie dans Teams, veuillez consulter les ressources suivantes :

- [Planifier la gestion du cycle de vie dans Teams](plan-teams-lifecycle.md)
- [Planifier la gouvernance dans Teams](plan-teams-governance.md)

## <a name="adoption"></a>Adoption

Pour permettre à votre organisation et à vos utilisateurs de tirer le meilleur parti de Teams, un programme d’adoption est nécessaire. Un programme d’adoption efficace peut mobiliser les utilisateurs qui peuvent :

- Communiquer les avantages de Teams à leurs collègues et à des responsables d’entreprise ou de groupe.
- Éveiller l’enthousiasme chez les personnes qui voient comment Teams améliorent la collaboration, puis facilite la connexion entre elles.
- Contribuer à évaluer les processus métier existants, puis formuler des recommandations sur l’intégration de Teams à ces processus.
- Signaler à l’équipe de déploiement les réussites et les difficultés pour contribuer à l’amélioration du processus d’adoption.

Si vous souhaitez en savoir plus sur la configuration d’un programme d’adoption, veuillez consulter la rubrique [Adopter Microsoft Teams](adopt-microsoft-teams-landing-page.md).