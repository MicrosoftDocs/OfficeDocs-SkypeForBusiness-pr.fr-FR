---
title: Démarrage rapide pour la gouvernance de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
ms.localizationpriority: medium
search.appverid: MET150
description: Démarrage rapide qui couvre les principales décisions que vous devrez prendre pour la phase 2 de votre plan d Microsoft Teams adoption.
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eaeec25c90e800fcc688dad924ecac8de687841a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733713"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Démarrage rapide pour la gouvernance de Microsoft Teams

Les activités suivantes se produisent simultanément et peuvent impliquer l’ensemble ou une partie de votre équipe clé. Il est préférable de différer les conversations de gouvernance et de sécurité à grande échelle une fois que vous avez terminé votre expérience initiale avec Teams. Il est important de comprendre la façon dont les décisions de gouvernance peuvent avoir une incidence sur l’expérience utilisateur final et simplifiera les décisions que vous devrez prendre à cette date ultérieure. Pour cette phase, certaines décisions doivent être prises. Pour les rendre correctement, vous devez tout d’abord répondre aux questions suivantes :

- Quelle partie prenante de votre évaluation précédente est la plus à même de participer à cette intégration limitée à l’entreprise ?
- Cet individu (ou groupe d’individus) a-t-il suggéré des cas d’utilisation qui seraient les bons choix pour cette phase ?  
- Sont-ils suffisamment intéressés par les employés de leur organisation pour être des premiers utilisateurs et vous fournir des commentaires utiles et réguliers ? 

Pour en savoir plus, lisez [Plan de gouvernance dans](plan-teams-governance.md) Teams et Planifier la gestion du cycle de vie dans [Teams.](plan-teams-lifecycle.md)

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![Icône représentant un point de décision.](media/teams-adoption-decision-icon.png)Décisions

Prendre les décisions suivantes (à ce stade, ces décisions s’appliquent uniquement à la Phase 2) :

### <a name="decision-1-who-can-create-teams"></a>Décision 1 : Qui créer des équipes 

Dans le cadre de cette phase, vous pouvez limiter les personnes qui sont en mesure de créer des équipes à la population initiale des utilisateurs en plus de votre équipe de projet de base. Ainsi, vos premiers utilisateurs pourront créer des équipes supplémentaires si nécessaire. La surveillance de ce comportement vous donne des informations clés pour votre déploiement à grande échelle.

### <a name="decision-2-teams-naming-conventions"></a>Décision 2 : Teams conventions d’appellation 

Vous voudrez probablement implémenter certaines conventions d’affectation de noms pour votre déploiement de Teams et vérifier la recherche de noms en double. Dans la phase 2, nous vous suggérons d’implémenter une convention d’appellation manuelle pour vos projets initiaux uniquement. Pour cela, il est préférable d’effectuer une intégration interactive avec l’équipe de projet des premiers utilisateurs et de leur permettre de sélectionner leur propre nom. Cela vous permettra d’avoir des informations sur la façon dont les employés réfléchissent à leur travail et seront essentiels à la création ultérieure d’une convention d’appellation à grande échelle. (Des informations supplémentaires sur les éléments d’une intégration interactive seront disponibles plus loin dans ce guide.)

### <a name="decision-3-guest-access"></a>Décision 3 : Accès invité

Selon l’étendue et le type de votre projet et la nature de votre secteur, l’activation de la collaboration sécurisée avec des partenaires ou des fournisseurs peut être une fonctionnalité essentielle que vous souhaitez tester. Vous pouvez limiter les personnes autorisées à ajouter des invités aux équipes à l’aide des contrôles de client appropriés et limiter les équipes ouvertes aux invités à l’aide d’étiquettes de sensibilité. Vous pouvez également vous assurer que les invités respectent les exigences de sécurité de l’organisation, telles que l’utilisation de l’authentification multifacteur (MFA).

### <a name="decision-4-approved-apps"></a>Décision 4 : applications approuvées

L’utilisation la plus Teams inclut l’intégration d’autres applications à l’expérience. Votre équipe technique doit au minimum activer les applications de la première partie et des applications Teams votre expérience. En fonction de votre cas d’utilisation et des autres applications utilisées dans votre organisation, vous pouvez choisir d’inclure d’autres applications dans le cadre de votre expérience contrôlée. Veillez à ce que les applications tierces respectent les exigences de sécurité et de conformité de votre organisation.

### <a name="decision-5-are-meetings-included-in-your-test"></a>Décision 5 : Les réunions sont-elles incluses dans votre test ? 

La Teams de réunion est de haute qualité, prend en charge la conversation vidéo et rassemble vos employés pour être plus efficaces. Consultez votre équipe technique pour vous assurer que votre environnement est prêt à inclure des réunions VoIP simples. L’activation de l’audioconférence ou des services vocaux serait normalement exclue de cette phase de votre expérimentation ; toutefois, cela dépend de votre équipe de projet principale, de votre préparation technique et de l’état des autres services vocaux/de réunion dans votre organisation. La préparation technique doit inclure des éléments tels que l’équipement de salle de réunion, les appareils et accessoires des utilisateurs finaux, et le réseau. Nous vous recommandons d’inclure les conversations vidéo et les réunions VoIP lors de votre expérimentation afin de tirer encore plus de valeur de Teams implémentation. 

### <a name="decision-6-content-management-and-structure"></a>Décision 6 : structure et gestion du contenu
Teams fonctionne de façon efficace lorsque les utilisateurs travaillent de bout en bout au sein de la plateforme, au lieu de les obliger à revenir continuellement à des systèmes et services hérités, et offrent de nouvelles façons de travailler différentes de celle à laquelle les utilisateurs sont habitués. Dans le cadre de vos expérimentations, collaborez avec vos participants afin d’envisager les structures et canaux d’équipe qui adoptent les méthodes multi modales de collaboration au sein d’Teams et évitez simplement de répliquer les dossiers et structures de stockage existants. En outre, envisagez les exigences de conformité pour le contenu stocké en dehors de systèmes pris en charge existants tels que les systèmes de gestion des enregistrements ou de sauvegarde.

### <a name="decision-7--data-security"></a>Décision 7 : Sécurité des données

En vue de votre déploiement à grande échelle, vous pouvez choisir d’utiliser des étiquettes de sécurité pour classifier les types d’équipes dans votre environnement. Dans le cadre de cette expérience, nous vous recommandons de faire référence à la gouvernance dans [Teams](plan-teams-governance.md) et de vous assurer qu’une stratégie de rétention de base a été définie sur Teams données dans votre Microsoft 365. Vous devrez peut-être coordonner ce travail avec votre équipe technique, car des Microsoft 365 administrateur sont requis pour effectuer ce travail.

### <a name="decision-8-length-of-your-experiment"></a>Décision 8 : durée de vos expérimentations

Une phase Teams implémentation continue à un rythme sain afin de garantir une dynamique, une attention et des apprentissages appropriés. Nous vous recommandons d’avoir 60 jours pour que les premiers utilisateurs terminent un cycle d’entreprise suffisant. Étendre la pratique d’une durée trop longue accroît le risque d’échec d’un programme de modification . toutefois, cette période peut varier pour chaque organisation.  

![Icône représentant l’étape suivante.](media/teams-adoption-next-icon.png) Suivant : Définir [des scénarios d’utilisation](teams-adoption-define-usage-scenarios.md)
