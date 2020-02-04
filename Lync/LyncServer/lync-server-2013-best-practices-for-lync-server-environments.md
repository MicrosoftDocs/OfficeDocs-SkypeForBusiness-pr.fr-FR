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
ms.openlocfilehash: bf207f4cd0303330ccb01dc56e28b949c1df22f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a>Recommandations en matière d’environnements Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-04_

Les principes généraux suivants doivent être appliqués aux opérations en cours de votre système :

  - **Comprenez et utilisez**   MOF MOF est une collection de meilleures pratiques, de principes et de modèles qui fournissent aux organisations des recommandations techniques sur la gestion des ressources informatiques, telles que les opérations quotidiennes de Lync Server 2013. Les instructions MOF suivantes vous permettent de bénéficier de la fiabilité, de la disponibilité, de la prise en charge et de la gestion des systèmes de production stratégiques pour les produits Microsoft. Pour plus d’informations, consultez [Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939).

  - **En savoir plus sur les meilleures pratiques en matière de Lync Server 2013**   , nous vous recommandons de mettre en œuvre des procédures pratiques et éprouvées pour gérer Lync Server 2013. L’utilisation de méthodes essayées, testées et documentées lors de la gestion d’opérations risque d’être plus efficace que de développer vos propres méthodes.

  - **Séparez les opérations en processus**   quotidiens, hebdomadaires et mensuels pour documenter les tâches opérationnelles requises que vous effectuerez régulièrement. La documentation du mode d’exécution des tâches permet de garantir la conservation de vos informations en cas de modification de votre environnement opérationnel, par exemple lors du déploiement de nouvelles technologies ou du changement du personnel. Nous vous recommandons d’intégrer les tâches opérationnelles dans des charges de travail gérables, où les tâches sont effectuées quotidiennement, par semaine et par mois. Les tâches quotidiennes concentrent les efforts sur le fonctionnement d’un système, et les tâches mensuelles se focalisent davantage sur la façon de garantir l’intégrité du système sur le long terme.
    
    Ce document peut être utilisé dans les environnements qui déploient uniquement les composants de messagerie instantanée et de présence (IM/P) ou de messagerie instantanée/P avec Enterprise Voice. Lorsque des tâches ou des éléments de liste de vérification sont spécifiques aux voix entreprise, cela est mentionné et si votre environnement n’inclut pas d’entreprise voix, la partie peut être ignorée.

  - **Déploiement des outils requis pour l’utilisation de Lync Server 2013**   de nombreux outils sont disponibles pour résoudre les problèmes, automatiser les tâches et surveiller et mettre à jour l’environnement Lync Server 2013. Définissez un ensemble standard d’outils pour votre organisation de sorte que les tâches effectuées par l’équipe d’opérations soient effectuées de manière précise, efficace, cohérente et de manière contrôlée. Vous devez également implémenter des processus pour suivre les incidents et les changements de configuration importants.

<div>

## <a name="reference"></a>Référence

Dans le souci des utilisateurs qui ne connaissent pas encore les notions de base de la gestion de serveur, nous proposons une vue d’ensemble des pratiques de gestion du serveur. Les lecteurs déjà familiarisés avec la gestion du serveur pourront choisir d’ignorer cette section.

Les pratiques recommandées sont des recommandations fondées sur les connaissances et les compétences des informaticiens ayant gagné dans de nombreux environnements. Ils fournissent des procédures standard pour les tâches courantes que les administrateurs de votre serveur Lync doivent exécuter quotidiennement et répertorient les outils qu’ils doivent utiliser pour gérer un environnement Lync Server.

Les tâches typiques pour les administrateurs Lync sont les suivantes :

  - **Gestion de la capacité et**   de la disponibilité définir le mode de mesure et les mesures à prendre pour prévoir les exigences de capacité future et pour signaler la capacité, la fiabilité et la disponibilité des systèmes. Vous devez vérifier que les serveurs qui exécutent Lync Server sont dimensionnés de manière à gérer la charge sur le système et que le temps d’arrêt non planifié est maintenu conformément aux niveaux définis dans le contrat de niveau de service (SLA). Par ailleurs, vous devez mettre à niveau le matériel pour continuer à respecter les exigences définies.

  - **Gestion des changements et gestion**   de la configuration : contrôle des modifications apportées aux systèmes informatiques. Il doit s’agir de tests, de commentaires sur les applications et de plans d’urgence, de la documentation relative à toutes les modifications et de l’approbation de la gestion en cas de problème. Enregistrez vos ressources logicielles et matérielles et leurs configurations.

  - ****   Méthodes standard d’administration du système permettant d’effectuer des tâches administratives telles que l’administration de la base de données et l’administration du site.

  - **L’administration**   de la sécurité a une stratégie et un plan détaillés qui protège la confidentialité des données, l’intégrité des données et la disponibilité des données de l’infrastructure informatique. Cela inclut les activités quotidiennes et les tâches qui sont liées à la mise à jour et à l’ajustement de l’infrastructure de sécurité informatique.

  - ****   Processus de résolution des problèmes de configuration du système pour traiter les problèmes inattendus, y compris les étapes pour éviter des problèmes similaires à l’avenir.

  - **Les contrats**   de niveau de service maintiennent un ensemble d’objectifs pour la performance des systèmes informatiques et mesurent régulièrement les performances par rapport à ces objectifs.

  - ****   Documents de documentation procédures standard, tels que les informations de configuration et les leçons tirées, et les mettre à la disposition des membres du personnel enseignant qui en ont besoin. À mesure que des modifications sont apportées à la configuration, mettez à jour la documentation en conséquence.

</div>

<div>

## <a name="related-sections"></a>Sections associées

Pour plus d’informations, consultez les rubriques suivantes concernant les opérations système :

  - [Gestion de la capacité et de la disponibilité dans Lync Server 2013](lync-server-2013-capacity-and-availability-management.md)

  - [Gestion des modifications dans Lync Server 2013](lync-server-2013-change-management.md)

  - [Gestion de la configuration dans Lync Server 2013](lync-server-2013-configuration-management.md)

  - [Administration du système dans Lync Server 2013](lync-server-2013-system-administration.md)

  - [Contrats de niveau de service dans Lync Server 2013](lync-server-2013-service-level-agreements.md)

  - [Documentation dans Lync Server 2013](lync-server-2013-documentation.md)

  - [Procédures standard dans Lync Server 2013](lync-server-2013-standard-procedures.md)

  - [Procédures d’urgence dans Lync Server 2013](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

