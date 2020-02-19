---
title: 'Lync Server 2013 : meilleures pratiques pour les environnements Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c31d39ae7537fc53fc4e72c8b1c57863b2ba189
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a>Meilleures pratiques pour les environnements Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-04_

Les principes généraux suivants doivent être appliqués aux opérations en cours de votre système :

  - **Comprendre et utiliser**   MOF MOF est une collection de meilleures pratiques, de principes et de modèles qui fournissent aux organisations des instructions techniques sur la gestion des ressources informatiques, telles que les opérations quotidiennes de Lync Server 2013. Les instructions MOF suivantes peuvent vous aider à améliorer la fiabilité, la disponibilité, la prise en charge et la facilité de gestion des systèmes de production critiques pour les produits Microsoft. Pour plus d’informations, consultez la rubrique [Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939).

  - **Découvrez les meilleures pratiques pour Lync Server 2013**   nous vous recommandons d’implémenter des procédures pratiques et éprouvées pour gérer Lync Server 2013. En utilisant les méthodes testées, testées et documentées de gestion des opérations peut être plus efficace que le développement de vos propres méthodes.

  - **Séparation des opérations en processus**   quotidiens, hebdomadaires et mensuels documentez les tâches opérationnelles requises que vous effectuerez régulièrement. La documentation de la façon dont vous effectuez les tâches permet de s’assurer que vos informations sont conservées en cas de modification de votre environnement opérationnel, par exemple lors du déploiement de nouvelles technologies ou de la modification du personnel. Nous vous recommandons de séparer les tâches opérationnelles en charges de travail gérables où les tâches sont effectuées quotidiennement, toutes les semaines et tous les mois. Les tâches quotidiennes se concentrent sur le fonctionnement d’un système, et les tâches mensuelles se concentrent davantage sur l’intégrité du système à long terme.
    
    Ce document peut être utilisé dans les environnements déployant uniquement les composants de messagerie instantanée/présence (IM/P) ou la messagerie instantanée/P avec voix entreprise. Lorsque des tâches ou des éléments de liste de contrôle sont spécifiques à voix entreprise, cela est mentionné et, si votre environnement n’inclut pas la fonctionnalité voix entreprise, la partie peut être ignorée.

  - **Déployer les outils requis pour l’exploitation de Lync Server 2013**   de nombreux outils sont disponibles pour vous aider à résoudre des problèmes, automatiser des tâches et surveiller et gérer l’environnement Lync Server 2013. Définissez un ensemble d’outils standard pour votre organisation afin que les tâches effectuées par l’équipe des opérations soient réalisées avec précision, efficacement, de façon cohérente et de manière contrôlée. Vous devez également implémenter des processus pour assurer le suivi des incidents et des changements de configuration importants.

<div>

## <a name="reference"></a>Référence

Pour les utilisateurs qui ne sont pas déjà familiarisés avec les notions de base de la gestion de serveur en général, nous proposons une vue d’ensemble des pratiques de gestion de serveur. Les lecteurs déjà familiarisés avec la gestion des serveurs peuvent choisir d’ignorer cette section.

Les meilleures pratiques sont des recommandations basées sur les connaissances et l’expérience que les professionnels de l’informatique ont acquis dans de nombreux environnements. Elles fournissent des procédures standard pour les tâches courantes que vos administrateurs Lync Server doivent effectuer quotidiennement et répertorient les outils qu’ils doivent utiliser pour gérer un environnement Lync Server.

Les tâches courantes pour les administrateurs Lync sont les suivantes :

  - **La gestion**   de la capacité et de la disponibilité définissent le mode et les éléments à mesurer afin de prévoir les besoins futurs en termes de capacité et de rapport sur la capacité, la fiabilité et la disponibilité de vos systèmes. Vous devez vérifier que les serveurs qui exécutent Lync Server sont dimensionnés de façon à gérer la charge sur le système, et que les temps morts non planifiés sont maintenus selon les niveaux définis dans le contrat de niveau de service (SLA). De plus, vous devez mettre à niveau le matériel pour continuer à respecter les exigences définies.

  - **Gestion des modifications et gestion**   de la configuration contrôle des modifications apportées aux systèmes informatiques. Cela doit inclure les tests, les commentaires d’application et les plans d’urgence, la documentation de toutes les modifications et l’approbation de la direction en cas de problèmes. Conservez un enregistrement de vos ressources logicielles et matérielles, ainsi que leurs configurations.

  - ****   Structure d’administration du système méthodes standard pour effectuer des tâches d’administration telles que l’administration de base de données et l’administration de site.

  - **L’administration**   de la sécurité est dotée d’une stratégie et d’un plan détaillés qui protège la confidentialité des données, l’intégrité des données et la disponibilité des données de l’infrastructure informatique. Cela inclut les activités quotidiennes et les tâches liées à la maintenance et à l’ajustement de l’infrastructure de sécurité informatique.

  - **Résolution des**   problèmes du système méthodes de plan pour traiter les problèmes inattendus, notamment les étapes permettant d’éviter des problèmes similaires à l’avenir.

  - **Les contrats**   de niveau de service conservent un ensemble d’objectifs pour les performances des systèmes informatiques et mesurent régulièrement les performances par rapport à ces objectifs.

  - **Documentation**   documentez les procédures standard, telles que les informations de configuration et les leçons apprises, et rendez-les accessibles aux membres du personnel qui en ont besoin. Lorsque les modifications apportées à la configuration sont effectuées, mettez à jour la documentation en conséquence.

</div>

<div>

## <a name="related-sections"></a>Sections connexes

Consultez les rubriques suivantes concernant les opérations système avant de continuer :

  - [Gestion de la capacité et de la disponibilité dans Lync Server 2013](lync-server-2013-capacity-and-availability-management.md)

  - [Gestion des modifications dans Lync Server 2013](lync-server-2013-change-management.md)

  - [Gestion de la configuration dans Lync Server 2013](lync-server-2013-configuration-management.md)

  - [Administration système dans Lync Server 2013](lync-server-2013-system-administration.md)

  - [Contrats de niveau de service dans Lync Server 2013](lync-server-2013-service-level-agreements.md)

  - [Documentation dans Lync Server 2013](lync-server-2013-documentation.md)

  - [Procédures standard dans Lync Server 2013](lync-server-2013-standard-procedures.md)

  - [Procédures d’urgence dans Lync Server 2013](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

