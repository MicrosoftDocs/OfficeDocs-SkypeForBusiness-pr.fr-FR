---
title: Planifier le connecteur de données d’appel | Analyse hybride du tableau de bord de qualité des appels
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Vue d’ensemble de Skype Entreprise outils de télémétrie en ligne pour surveiller une implémentation sur site dans un scénario hybride.
ms.openlocfilehash: a85599ee0db012d3c3fbb55a7d7c12f8516ee962
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726483"
---
# <a name="plan-call-data-connector"></a>Planifier le connecteur de données d’appel

## <a name="overview"></a>Vue d’ensemble

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cette rubrique décrit les avantages, les considérations relatives à la planification et les conditions requises pour l’Skype Entreprise Server du connecteur de données d’appel. Pour plus d’informations sur la configuration du connecteur de données d’appel, voir [Configure Call Data Connector](configure-call-data-connector.md).


Call Data Connector simplifie considérablement la surveillance des appels dans un environnement hybride, car vous n’avez plus besoin d’utiliser différents ensembles d’outils locaux et en ligne pour surveiller la qualité des appels de tous vos utilisateurs. Que vos utilisateurs soient en local ou en ligne, vous pouvez choisir d’afficher la qualité des appels pour l’ensemble de votre organisation en ligne.

Avec Le connecteur de données d’appel, vous pouvez effectuer les tâches suivantes à l’aide d’un ensemble d’outils unique :

- Surveillez votre expérience utilisateur dans Microsoft Teams, Skype Entreprise Online et Skype Entreprise Server.

- Afficher et résoudre les problèmes sur votre réseau.

- Attribuez des rôles d’administrateur et de helpdesk pour l’analyse des appels, afin que vous pouvez permettre aux travailleurs du helpdesk d’afficher et de dépanner leurs domaines de responsabilité.

Avec le connecteur de données d’appel, le Skype Entreprise Server fournit des données d’appel au service cloud afin que vous pouvez tirer parti des outils d’analyse des appels Skype Entreprise Online Call Analytics (CA) et du Tableau de bord de qualité des appels (CQD), comme illustré dans le diagramme suivant :

![Diagramme de Messagerie vocale infonuagique SfB.](../../sfbserver2019/media/call-data-connector-plan-1.png)

Le serveur pousse les données de qualité de l’expérience (QoE) et d’enregistrement des détails des appels vers le service en ligne.

Les outils Analyse des appels et CQD vous permettent de surveiller la qualité des appels et de résoudre les problèmes de connexion avec les services Microsoft Teams et Skype Entreprise comme suit :

- L’analyse des appels se concentre sur les problèmes de qualité liés à des appels spécifiques. Il affiche des informations détaillées sur les appels et les réunions pour chaque utilisateur dans un compte Skype Entreprise client.  Avec l’analyse des appels, vous pouvez attribuer des autorisations à un opérateur du centre d’administration de l’Skype Entreprise qui peut ensuite surveiller les appels.

- Le Tableau de bord de qualité des appels se concentre sur les performances et les problèmes du réseau au sein d’une organisation. Skype Entreprise administrateurs et ingénieurs réseau utilisent cet outil pour résoudre les problèmes et optimiser les performances du réseau.

Pour plus d’informations, voir le diagramme Analyse des appels et Tableau de bord de qualité [des appels avec des détails sur](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)le serveur de surveillance.

Bien entendu, vous souhaitez peut-être conserver certaines données de qualité des appels en local. Cela peut être le cas, par exemple, si vous utilisez une solution tierce avec des flux de travail et des rapports personnalisés.  Le connecteur de données d’appel vous permet de configurer l’envoi de données au service en ligne tout en conservant une copie des données sur votre serveur local, comme illustré dans le diagramme suivant :

![SfB Messagerie vocale infonuagique.](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Configuration requise

Les conditions suivantes supposent que vous avez déjà déployé Skype Entreprise Server dans une topologie prise en charge.  Pour plus d’informations sur le déploiement Skype Entreprise Server topologies et les topologies pris en charge, voir [Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md). Pour configurer le connecteur de données d’appel, vous devez :

- Activer la connectivité hybride. Si vous avez déjà déployé Skype Entreprise Server et que vous souhaitez activer le connecteur de données d’appel, vous devez vous assurer que la connectivité hybride est définie entre vos environnements locaux et en ligne. Il s’agit parfois d’une configuration de domaine fractionnement.

   Pour plus d’informations, voir Planifier la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou [Office 365](plan-hybrid-connectivity.md) et configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 [ou Office 365](configure-hybrid-connectivity.md).

- Authentifier votre organisation Microsoft 365 ou Office 365 et assurez-vous que les rôles suivants sont activés :

  - Skype Entreprise Server Administrateur
  - Microsoft 365 ou Office 365 administrateur général

- Si vous ne l’avez pas déjà fait, appelez le Tableau de bord de qualité des appels comme décrit dans Activer et utiliser le Tableau de bord de qualité des appels [pour Microsoft Teams et Skype Entreprise Online.](/microsoftteams/turning-on-and-using-call-quality-dashboard)

- Activez le pool frontal pour la surveillance, avec les bases de données LCSCdr et QoEMetrics locales. Sans cela, le connecteur de données d’appel n’aura pas de données de métriques à travailler.

> [!IMPORTANT]
> Le connecteur de données d’appel ne fonctionne pas si la surveillance n’est pas activée sur le pool frontal.

- Authentification de serveur à [serveur correctement configurée.](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Comparaison des rapports du Tableau de bord de qualité des appels (CQD) local et en ligne

| Rapports sur les fonctionnalités | Skype Entreprise Online | Skype Entreprise Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Mesure de partage d’application |Oui | Limité |
| Informations sur la création de clients| Oui | Oui |
| Analyse d’analyse d’analyse | Oui | Non |
| Mesures de fiabilité des médias | Oui | Limité |
| Rapports pré-présodents | Oui | Oui |
| Rapports de vue d’ensemble | Oui | Non |
| Rapports par utilisateur | Oui | Oui |
| Personnalisation de l’ensemble de rapports <br> (ajouter, supprimer, modifier des rapports) | Oui | Oui |
| Mesures de partage d’écran vidéo | Oui | Non |
| API de données pour l’accès par programme <br> vers CQD | Non | Oui |
||||