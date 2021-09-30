---
title: Skype Entreprise Server 2015 Management Tools
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 4e956558-8cba-47d9-b96a-537d7f6ed938
description: 'Résumé : Découvrez les outils de gestion des services Skype Entreprise Server 2015.'
ms.openlocfilehash: 775f8221fe29cc306e0bcdef5855652c47681c76
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014968"
---
# <a name="skype-for-business-server-2015-management-tools"></a>Skype Entreprise Server 2015 Management Tools
 
**Résumé :** Découvrez les outils de gestion des services Skype Entreprise Server 2015.
  
Skype Entreprise Server 2015 (anciennement Lync Server), offre des solutions de messagerie instantanée, de présence, de conférence et de téléphonie qui permettent la collaboration au niveau de l’entreprise. Les outils permettant de gérer ces services sont flexibles et puissants. 
  
## <a name="skype-for-business-server-2015-tools"></a>Skype Entreprise Server Outils 2015

|&nbsp;|Content|Description|
|:-----|:-----|:-----|
||Carte de performance de méthodologie de qualité des [appels Microsoft, version 1.5](https://go.microsoft.com/fwlink/p/?LinkId=615208) (.zip téléchargement) <br/> [Affiche CQM pour les Skype Entreprise](https://go.microsoft.com/fwlink/p/?LinkID=617898) <br/> [Affiche CQM pour Lync 2013](https://go.microsoft.com/fwlink/p/?LinkId=391841)  |Une version mise à jour de la carte de performance de la méthodologie de qualité des appels Microsoft (CQM) pour Lync Server et Skype Entreprise Server 2015. Vous pouvez utiliser la carte de performance CQM pour implémenter la méthodologie de qualité des appels, un moyen global de définir et d’établir systématiquement la qualité des appels en fonction des méthodes décrites dans le Guide de mise en réseau. CQM divise une implémentation Lync/Skype Entreprise en dix zones discrètes qui ont un impact sur la qualité, en définissant des cibles et un plan de correction pour chacun d’eux. CQM est une infrastructure permettant de résoudre les problèmes de qualité des appels : vous pouvez le modifier ou l’étendre pour résoudre les conditions particulières de votre réseau.  <br/> L’affiche CQM peut vous aider à en savoir plus sur CQM, la méthodologie de qualité des appels pour Lync et Skype Entreprise qui vous permet de rechercher et d’éliminer les problèmes affectant la qualité des appels et l’expérience utilisateur pour les implémentations Lync/Skype Entreprise qui incluent des fonctionnalités vocales d’entreprise.  <br/>**Remarque :** Ces outils ne seront pas mis à jour Skype Entreprise Server 2019. |
|![icône de tableau de bord.](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Tableau de bord de la qualité des appels](./call-quality-dashboard/call-quality-dashboard.md)  |Le tableau de bord de qualité des appels (CQD) est un portail web qui permet de créer et d’organiser rapidement des rapports basés sur les données de qualité de l’expérience (QoE) de votre environnement Skype Entreprise ou Lync. Le CQD déploie un cube SSAS pour agréger les données dans la base de données QoEMetrics, ce qui permet aux utilisateurs de créer et de modifier des rapports et de les voir mettre à jour en temps réel. En outre, le tableau de bord de qualité des applications expose des API web qui donnent aux utilisateurs un accès par programmation aux données de cube à utiliser dans des tableaux de bord personnalisés.   |
|![pour KHI.](../media/8759b767-b689-4a95-94a5-5b27c5688688.png)|[Ressources KHI](https://go.microsoft.com/fwlink/p/?LinkId=534843)  |Les indicateurs d’état d’santé clés (KHI) sont des compteurs de performance avec des seuils recommandés visant à révéler des problèmes qui peuvent avoir un impact sur l’expérience utilisateur. Le guide de l’KHI décrit le processus opérationnel et les étapes de correction pour maintenir un déploiement intègre, et inclut un exemple de script PowerShell utilisé pour configurer les collecteurs de données KHI et un manuel d’analyse et de définitions qui peut analyser les données de performances KHI.   |
|![icône de tableau de bord.](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Gestionnaire de statistiques pour Skype Entreprise Server 2015](statistics-manager/statistics-manager.md)  |StatsMan est une solution de tableau de bord qui permet d’afficher des calculs KHI en temps réel, ainsi que des compteurs de performance sous forme de graphiques agrégés dans votre infrastructure. Le tableau de bord peut être utilisé pour identifier les problèmes de performances en cours, afficher les résultats d’une modification planifiée de votre environnement, suivre la résolution des pannes et bien plus encore. Out of the box, it is configured with KHI thresholds from the KHI Resources, and can be customized to suit your deployment’s unique needs.   |
|![icône de tableau de bord.](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype Entreprise Server kit de ressources 2015](https://www.microsoft.com/download/details.aspx?id=52631)  |Skype Entreprise Server kit de ressources 2015 sont fournis pour faciliter certaines tâches de routine pour les administrateurs informatiques qui déploient et gèrent Skype Entreprise Server 2015.   |
|![icône réseau.](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[Guide de mise en réseau](https://go.microsoft.com/fwlink/p/?LinkID=390677)  |Logiciel de communication Microsoft Lync Server 2013 et Skype Entreprise 2015 qui permet l’appel audio et vidéo (A/V) D’égal à égal, la conférence et la collaboration et s’appuie sur une infrastructure réseau optimisée et fiable pour fournir des sessions multimédias de haute qualité entre les clients. Le Guide de mise en réseau fournit un modèle de gestion de l’infrastructure réseau pour Skype Entreprise et Lync, composé de trois phases : planification, surveillance et dépannage. Ces phases peuvent s’appliquer aux nouveaux déploiements Lync Skype Entreprise Server Lync ou aux déploiements existants. La modification récente du Guide de mise en réseau a abordé Lync/Skype sur Wi-Fi et la configuration de la stratégie de qualité de service.   |
|![Icône presse-papiers.](../media/2e0c9c21-cd2a-4db5-8cb7-d2c0b1b159b7.png)|[Service de journalisation centralisée Skype Entreprise 2015](centralized-logging-service/centralized-logging-service.md)  |Le service de journalisation centralisée est un outil puissant de dépannage pour les problèmes de grande ou petite taille, de l’analyse des causes premières aux problèmes de performances. Tous les exemples sont présentés à l’aide Skype Entreprise Server Management Shell. L’aide est fournie pour l’outil en ligne de commande par le biais de l’outil lui-même, mais il existe un ensemble limité de fonctions que vous pouvez exécuter à partir de la ligne de commande. En utilisant Skype Entreprise Server Management Shell, vous avez accès à un ensemble de fonctionnalités beaucoup plus large et beaucoup plus configurable, ce qui doit toujours être votre premier choix.   |
|![Icône SCOM.](../media/3a7601cb-dd2f-4606-8a3b-07c7abdc091a.png)|[Gérer Skype Entreprise Server 2015 à l’aide du pack d’administration SCOM](use-scom-management-pack/use-scom-management-pack.md)  |En utilisant Skype Entreprise Server Packs d’administration 2015, vous pouvez identifier et résoudre les problèmes potentiels de manière proactive. De cette façon, les packs d Skype Entreprise Server 2015 étendent les fonctionnalités de System Center Operations Manager.   |
|![icône de tableau de bord.](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[outil de planification Skype Entreprise Server 2015](planning-tool/planning-tool.md)  |L Skype Entreprise 2015 Planning Tool fournit des instructions normatives pour vous aider à planifier votre topologie.  <br/> **Remarque :** Cet outil ne sera pas mis à jour Skype Entreprise Server 2019. |
|![icône de tableau de bord.](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype Entreprise Server de planification de capacité 2015](capacity-planning-calculator.md)  |Le Skype Entreprise Server de planification de la capacité 2015 vous permet de modéliser une topologie pour les besoins de votre organisation.   |
|![icône réseau.](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[Skype Entreprise Server 2015 Stress and Performance Tool](stress-and-performance-tool/stress-and-performance-tool.md)  |Cet outil vous permet d’effectuer divers tests liés aux performances avec la charge utilisateur pour votre environnement Skype Entreprise Server 2015. Des exemples de scripts sont fournis avec l’outil pour vous aider à répondre à vos besoins environnementaux uniques.  <br/>**Remarque :** Cet outil ne sera pas mis à jour Skype Entreprise Server 2019. |
   
## <a name="see-also"></a>Voir aussi

[Outils Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-tools)
  
[Outils Lync Server 2010](/previous-versions/office/lync-server-2010-tools/dn145002(v=ocs.14))