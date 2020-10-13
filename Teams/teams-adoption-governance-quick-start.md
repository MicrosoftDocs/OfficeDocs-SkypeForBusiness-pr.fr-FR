---
title: Démarrage rapide pour la gouvernance de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
localization_priority: Normal
search.appverid: MET150
description: Démarrage rapide qui couvre les principales décisions que vous devrez effectuer pour la phase 2 de votre plan d’adoption de Microsoft Teams.
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
ms.openlocfilehash: cd54902e00e984de740b7bbf6d0fd96e37e88aa9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424554"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Démarrage rapide pour la gouvernance de Microsoft Teams

Les activités suivantes interviendront en même temps, et elles peuvent impliquer l’ensemble ou une partie de votre équipe clé. Nous vous conseillons de différer les conversations de gouvernance et de sécurité à grande échelle pour une fois que vous avez terminé la première expérimentation de teams. Il est important de comprendre la manière dont les décisions de gouvernance peuvent avoir une incidence sur l’utilisation des utilisateurs finaux et de simplifier les décisions que vous devrez apporter à ce jour plus tard. Pour cette phase, vous devez prendre des décisions. Pour ce faire, vous devez d’abord répondre aux questions suivantes :

- Quelle partie prenante de votre évaluation antérieure est susceptible de participer à cette intégration d’entreprise limitée ?
- Ce (ou groupe d’utilisateurs) a-t-il suggéré des cas d’utilisation pour cette phase ?  
- Les employés de leur organisation doivent-ils être suffisamment intéressants pour être prévenus et vous fournir des commentaires utiles et périodiques ? 

Pour en savoir plus, voir [plan de gouvernance dans équipes](plan-teams-governance.md) et planification de la [gestion du cycle de vie dans teams](plan-teams-lifecycle.md).

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![Icône représentant un point de décision](media/teams-adoption-decision-icon.png)Relatives

Prendre les décisions suivantes (à ce stade, ces décisions s’appliquent uniquement à la phase 2) :

### <a name="decision-1-who-can-create-teams"></a>Décision 1 : qui peut créer des équipes 

Dans le cadre de cette étape, vous pouvez limiter les personnes qui sont en mesure de créer des équipes à la population des premiers utilisateurs, en plus de votre équipe de projet principale. Cela permet à vos décideurs de créer des équipes supplémentaires le cas échéant. Le contrôle de ce comportement vous donne des informations clés pour votre déploiement global.

### <a name="decision-2-teams-naming-conventions"></a>Décision 2 : conventions d’affectation de noms aux équipes 

Vous aurez probablement besoin d’implémenter quelques conventions d’affectation de noms pour votre déploiement global d’équipes, et de vérifier les doublons. Dans la phase 2, nous vous suggérons d’implémenter une convention d’affectation de noms manuelle pour vos projets initiaux uniquement. Pour cela, nous vous conseillons de passer une intégration interactive à l’équipe initiale du projet et de leur permettre de sélectionner leur nom. Cela vous permettra de vous familiariser avec la façon dont les employés pensent à leur emploi et sera essentiel dans la création d’une convention d’affectation de noms plus grande. (Des informations supplémentaires sur les éléments d’un intégration interactive apparaissent plus loin dans ce guide.)

### <a name="decision-3-guest-access"></a>Décision 3 : accès invité

En fonction de l’étendue et du type de votre projet et de la nature de votre secteur, il est possible que vous deviez tester la collaboration avec des partenaires ou des fournisseurs. Vous pouvez limiter les personnes qui peuvent ajouter des invités à des équipes en utilisant les contrôles client appropriés et limiter les équipes qui sont ouvertes aux invités à l’aide d’étiquettes de sensibilité. Vous pouvez également vous assurer que les invités respectent les exigences de sécurité de l’organisation, telles que l’utilisation de l’authentification multifacteur (MFA).

### <a name="decision-4-approved-apps"></a>Décision 4 : applications approuvées

La meilleure utilisation des équipes inclut l’intégration d’autres applications dans l’interface. Au minimum, votre équipe technique doit permettre aux applications de la première et des applications proposées dans votre interface d’équipe. En fonction de votre cas d’utilisation et d’autres applications utilisées dans votre organisation, vous pouvez choisir d’inclure d’autres applications dans le cadre de votre expérience contrôlée. Assurez-vous d’obtenir des applications tierces pour s’assurer qu’elles respectent les exigences de sécurité et de conformité de votre organisation.

### <a name="decision-5-are-meetings-included-in-your-test"></a>Décision 5 : les réunions sont-elles incluses dans votre test ? 

L’interface de réunion teams est haute qualité, prend en charge les discussions vidéo et permet d’améliorer l’efficacité de vos employés. Contactez votre équipe technique pour vous assurer que votre environnement est prêt à être utilisé pour inclure des réunions VoIP simples. L’activation de la fonction d’audioconférence ou de services vocaux sera normalement exclue de cette phase de votre expérimentation ; Toutefois, cela dépend de votre équipe de projet principale, de votre disponibilité technique et de l’état d’autres services vocaux/de réunion au sein de votre organisation. La compatibilité technique doit inclure des éléments tels que le matériel de salle de réunion, les appareils et accessoires pour les utilisateurs finaux, ainsi que le réseau. Nous vous recommandons d’inclure des conversations vidéo et des réunions VoIP dans votre expérimentation pour obtenir une plus grande valeur de l’implémentation de votre équipe. 

### <a name="decision-6-content-management-and-structure"></a>Décision 6 : gestion de contenu et structure
Teams fonctionne de façon optimale lorsque les utilisateurs travaillent de bout en bout au sein de la plate-forme, au lieu de leur permettre de basculer continuellement vers les systèmes et services hérités, et propose de nouvelles méthodes de fonctionnement différentes de celles que les utilisateurs sont habitués. Dans le cadre de votre expérience, collaborez avec vos participants pour prendre en compte les structures et les canaux de l’équipe qui prennent en charge les méthodes de collaboration multimodales au sein des équipes, et évitez simplement de répliquer les structures de dossiers et de stockage existantes. Par ailleurs, prenez en compte les exigences de conformité relatives au contenu stocké hors des systèmes pris en charge existants tels que la gestion des enregistrements ou les systèmes de sauvegarde.

### <a name="decision-7--data-security"></a>Décision 7 : sécurité des données

En préparation de votre vaste déploiement, vous pouvez choisir d’utiliser des étiquettes de sécurité pour classer les types d’équipes dans votre environnement. Dans le cadre de cette expérience, nous vous recommandons de vous référer au [plan de gouvernance dans teams](plan-teams-governance.md) et de vous assurer qu’une stratégie de rétention de base est définie pour les données d’équipe dans Microsoft 365. Il est possible que vous deviez coordonner ce travail avec votre équipe technique, car vous devez disposer des droits d’administrateur Microsoft 365 pour terminer ce travail.

### <a name="decision-8-length-of-your-experiment"></a>Décision 8 : durée de votre expérience

Une implémentation de teams réussie est un bon rythme pour garantir une dynamique, un foyer et des connaissances appropriés. Nous vous conseillons de faire en sorte que la phase de votre projet soit de 60 jours pour garantir la durée de la période de travail de vos premiers entourages. Le développement d’une expérimentation trop longue a pour unique risque d’augmenter le risque d’un programme de changement d’échec ; Néanmoins, cette durée varie en fonction de chaque organisation.  

![Une icône représentant la prochaine étape suivante ](media/teams-adoption-next-icon.png) : [définir des scénarios d’utilisation](teams-adoption-define-usage-scenarios.md)
