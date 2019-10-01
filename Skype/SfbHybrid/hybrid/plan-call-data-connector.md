---
title: Planifier le connecteur de données d’appel | Tableau de bord de la qualité des appels analyse hybride
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Vue d’ensemble de l’utilisation des outils de télémétrie Skype entreprise Online pour surveiller une implémentation locale dans un scénario hybride.
ms.openlocfilehash: 3300ad17b109ac069c4f7382f610dd0214b30197
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328426"
---
# <a name="plan-call-data-connector"></a>Planifier le connecteur de données d’appel

## <a name="overview"></a>Vue d’ensemble

Cette rubrique décrit les avantages, les considérations relatives à la planification et les conditions requises pour l’implémentation du connecteur de données d’appel Skype entreprise Server. Pour plus d’informations sur la configuration du connecteur de données d’appel, voir [configure Call call Data Connector](configure-call-data-connector.md).


Call Data Connector simplifie grandement la surveillance des appels dans un environnement hybride car vous n’avez plus besoin d’utiliser différents ensembles d’outils locaux et en ligne pour surveiller la qualité des appels de tous vos utilisateurs. Que vos utilisateurs soient hébergés sur site ou en ligne, vous pouvez choisir d’afficher la qualité des appels pour l’ensemble de votre organisation en ligne.

Avec le connecteur de données d’appel, vous pouvez effectuer les tâches suivantes à l’aide d’un seul ensemble d’outils :

- Surveillez votre expérience utilisateur dans Microsoft Teams, Skype entreprise Online et Skype entreprise Server.

- Afficher et résoudre les problèmes sur votre réseau.

- Attribuer des rôles d’assistance technique et d’administrateur pour l’analyse des appels, afin que vous puissiez aider les employés du support technique à consulter et dépanner leur domaine de responsabilité.

Avec le connecteur de données d’appel, Skype entreprise Server transmet les données d’appel au service Cloud afin que vous puissiez utiliser les outils d’analyse des appels de Skype entreprise Online (CA) et de la qualité des appels (CQD), comme illustré dans le diagramme suivant :

![Messagerie vocale Cloud SfB](../../sfbserver2019/media/call-data-connector-plan-1.png)

Le serveur transmet les données de qualité de l’expérience (QoE) et d’enregistrement des détails des appels au service en ligne.

Les outils d’analyse et d’CQD d’appels vous permettent de surveiller la qualité des appels et de résoudre les problèmes de connexion avec Microsoft teams et les services Skype entreprise comme suit :

- L’analyse des appels se concentre sur les problèmes de qualité avec des appels spécifiques. Il affiche des informations détaillées sur les appels et les réunions de chaque utilisateur dans un compte Skype entreprise.  Avec l’analyse des appels, vous pouvez attribuer des autorisations à un opérateur de support technique qui peut ensuite surveiller les appels sans avoir accès au reste du centre d’administration de Skype entreprise.

- Le tableau de bord de qualité des appels se concentre sur les performances et les problèmes réseau au sein d’une organisation. Les administrateurs Skype entreprise et les ingénieurs réseau utilisent cet outil pour dépanner et optimiser les performances du réseau.

Pour plus d’informations, consultez la rubrique [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).

Bien entendu, vous souhaiterez peut-être conserver certaines données de qualité des appels en local. Cela peut être le cas, par exemple, si vous utilisez une solution tierce avec des rapports et des flux de travail personnalisés.  Le connecteur de données d’appel vous permet de configurer l’envoi de données au service en ligne tout en conservant une copie des données sur votre serveur local, comme illustré dans le diagramme suivant :

![Messagerie vocale Cloud SfB](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Configuration requise

Les conditions suivantes supposent que vous avez déjà déployé Skype entreprise Server dans une topologie prise en charge.  Pour plus d’informations sur le déploiement de Skype entreprise Server et des topologies prises en charge, consultez la rubrique relative aux [concepts de base](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)de la topologie. Pour configurer le connecteur de données d’appel, vous devez :

- Activez la connectivité hybride. Si vous avez déjà déployé Skype entreprise Server et que vous souhaitez activer le connecteur de données d’appel, vous devez vous assurer que la connectivité hybride est configurée entre votre environnement local et en ligne. Il s’agit parfois d’une configuration de domaine fractionné.

   Pour plus d’informations, voir [planifier une connectivité hybride entre Skype entreprise Server et office 365](plan-hybrid-connectivity.md) et [configurer la connectivité hybride entre Skype entreprise server et Office 365](configure-hybrid-connectivity.md).

- Authentifiez-vous auprès de votre client Office 365 et assurez-vous que les rôles suivants sont activés :

  - Administrateur de Skype entreprise Server
  - Administrateur général Office 365

- Si vous ne l’avez pas déjà fait, activez le tableau de bord qualité des appels comme décrit dans [activation et utilisation du tableau de bord de la qualité des appels pour Microsoft teams et Skype entreprise Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).

- Activez le pool frontal pour la surveillance, avec les bases de données LCSCdr et QoEMetrics locales. Sans cela, le connecteur de données d’appel n’aura pas de données de mesure à utiliser.

> [!IMPORTANT]
> Le connecteur de données d’appel ne fonctionne pas si la surveillance n’est pas activée sur le pool frontal.

- [Authentification de serveur à serveur](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications)correctement configurée. 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Comparaison des rapports de tableau de bord de qualité des appels sur site et en ligne (CQD)

| Rapports de fonctionnalités | Skype Entreprise Online | Skype Entreprise Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Mesure de partage d’application |Oui | Peu |
| Informations sur la création de clients| Oui | Oui |
| Analyse approfondie | Oui | Non |
| Mesures de fiabilité des médias | Oui | Peu |
| Rapports prédéfinis | Oui | Oui |
| Rapports de vue d’ensemble | Oui | Non |
| Rapports par utilisateur | Oui | Oui |
| Personnalisation des jeux de rapports <br> (ajouter, supprimer, modifier des rapports) | Oui | Oui |
| Mesures de partage d’écran vidéo | Oui | Non |
| API de données pour l’accès par programme <br> vers CQD | Non | Oui |
||||
