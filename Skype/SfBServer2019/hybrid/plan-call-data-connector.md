---
title: Planifier le connecteur de données d’appel
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Présentation de l’utilisation de Skype pour Business Online outils de télémétrie pour surveiller une implémentation sur site dans un scénario hybride.
ms.openlocfilehash: d704f23f9b8260e8d755c4d1f0f48da927859ba1
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530534"
---
# <a name="plan-call-data-connector"></a>Planifier le connecteur de données d’appel

## <a name="overview"></a>Vue d’ensemble
Cette rubrique décrit les avantages, considérations relatives à la planification et configuration requise pour l’implémentation de Skype Business Server appeler connecteur de données. Pour plus d’informations sur la configuration de connecteur de données d’appel, voir [Configurer appeler un connecteur de données](configure-call-data-connector.md).

> [!NOTE]
> Version d’évaluation, tableau de bord Analytique appeler uniquement est disponible.

Connecteur de données d’appel simplifie grandement la surveillance de l’appel dans un environnement hybride, car vous n’avez plus besoin d’utiliser différentes sur site et les outils en ligne pour contrôler l’ensemble de vos utilisateurs la qualité des appels. Si vos utilisateurs sont hébergés sur site ou en ligne, vous pouvez choisir d’afficher la qualité des appels pour votre organisation en ligne.

Avec le connecteur de données d’appel, vous pouvez effectuer les tâches suivantes à l’aide d’un seul ensemble d’outils :

- Surveiller votre expérience utilisateur dans Microsoft Teams, Skype pour Business Online et Skype pour Business Server.

- Afficher et résoudre les problèmes de votre réseau.

- Assigner des rôles de support technique et administrateur appeler Analytique, afin que vous donner des travailleurs de support technique pour afficher et résoudre les problèmes de leurs domaines de responsabilité. 

Avec le connecteur de données d’appel, le Skype pour Business Server envoie les données d’appel au service cloud afin que vous pouvez tirer parti de la Skype pour les outils professionnels en ligne appel Analytique (CA) et du tableau de bord de la qualité des appels (CQD), comme illustré dans le diagramme suivant :

![Messagerie vocale SfB Cloud](../../sfbserver2019/media/call-data-connector-plan-1.png)

Le serveur envoie la qualité de l’expérience (QoE) et les données d’appel d’enregistrement des détails au service en ligne.

Les outils CQD Analytique d’appel permettent de surveiller la qualité des appels et de résoudre les problèmes de connexion avec Microsoft Teams et Skype pour les services comme suit :

- Appeler se concentre Analytique sur des problèmes de qualité avec les appels spécifiques. Il affiche des informations détaillées sur les appels et les réunions pour chaque utilisateur dans un Skype pour un compte professionnel.  Avec appel Analytique, vous pouvez affecter des autorisations à un opérateur de support technique qui peut puis surveiller les appels sans avoir accès au reste du Skype pour le centre d’administration Business.

- Tableau de bord qualité appel se concentre sur les performances réseau et problèmes à travers une organisation. Skype pour les administrateurs et les ingénieurs réseau utiliser cet outil pour résoudre les problèmes et optimiser les performances réseau.

Pour plus d’informations, voir [Analytique d’appel et appel du tableau de bord qualité](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).

Bien sûr, vous pouvez souhaiter conserver des données de qualité d’appel sur site. Ce peut être le cas, par exemple, si vous utilisez une solution tierce avec flux de travail et des rapports personnalisés.  Connecteur de données d’appel permet de configurer le service online envoie des données tout en gardant une copie des données sur votre serveur local, comme illustré dans le diagramme suivant :

![Messagerie vocale SfB Cloud](../../sfbserver2019/media/call-data-connector-plan-2.png)


## <a name="requirements"></a>Conditions requises

Les conditions suivantes supposent que vous avez déjà Skype pour Business Server déployé dans une topologie prise en charge.  Pour plus d’informations sur le déploiement de Skype pour Business Server et les topologies prises en charge, voir [Les concepts de topologie](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics). Pour configurer le connecteur de données d’appel, vous devez :

- Activer la connectivité hybride. Si vous avez déjà Skype pour Business Server est déployé et que vous souhaitez activer le connecteur de données d’appel, vous devez vous assurer que vous disposez de connectivité hybride entre votre organisation locale et environnements en ligne. Il est parfois appelée une configuration de domaine fractionné. 

   Pour plus d’informations, voir [planification de la connectivité hybride entre Skype pour Business Server et Office 365](plan-hybrid-connectivity.md) et de [configurer la connectivité hybride entre Skype pour Business Server et Office 365](configure-hybrid-connectivity.md).

-  S’authentifient auprès de votre client Office 365 et vérifiez que vous avez activés rôles suivants :

   - Administrateur du serveur pour les professionnels de Skype 
   - Administrateur Global d’Office 365 

- Si vous n’avez pas déjà fait, allumez appel du tableau de bord qualité comme décrit dans la [mise sous tension et à l’aide d’appels de tableau de bord qualité pour les équipes Microsoft et Skype pour Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).
 
- Activer le pool frontal pour la surveillance, avec des bases de données LCSCdr et QoEMetrics locales. Sans cela, appelez un connecteur de données aurez pour travailler avec des données de mesure. 
 
> [!IMPORTANT]
> Connecteur de données d’appel ne fonctionne pas si l’analyse n’est pas activé sur le pool frontal.

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Rapports de comparaison des locaux et en ligne du tableau de bord de la qualité des appels (CQD)

| Rapports de fonctionnalité | Skype Entreprise Online | Skype Entreprise Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Mesure de partage d’application |Oui | Limitée |
| Informations de création de client| Oui | Oui |
| Exploration analytique | Oui | Non |
| Mesures de la fiabilité du média | Oui | Limitée |
| Rapports out-of-the-box | Oui | Oui |
| Vue d’ensemble des rapports | Oui | Non |
| Par rapports utilisateur | Oui | Oui |
| Personnalisation de rapports <br> (ajouter, supprimer, modifier des rapports) | Oui | Oui |
| Partage des mesures d’écran vidéo | Oui | Non |
| API de données pour l’accès par programme <br> pour CQD | Non | Oui |
||||
