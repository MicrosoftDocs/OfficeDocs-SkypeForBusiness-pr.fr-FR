---
title: 'Lync Server 2013 : début du processus de planification'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d436da8efa7194c2a0a341f4bed7794e532446ec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513037"
---
# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Début du processus de planification pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-24_

Bien que la planification d’un déploiement de communications unifiées sur site puisse paraître intimidante, Lync Server fournit deux outils utiles pour vous aider à :

  - **L’outil de planification** est un assistant qui présente une série de questions sur votre organisation, les fonctionnalités Lync Server que vous souhaitez activer et vos besoins en matière de planification de la capacité. Il crée ensuite une topologie de déploiement recommandée en fonction de vos réponses et génère un diagramme Microsoft Visio de ce déploiement.

  - Le **Générateur de topologies** est un composant d’installation de Lync Server. Le générateur de topologies vous permet de créer, d’ajuster et de publier votre topologie planifiée. Il valide également votre topologie avant que vous ne commenciez à installer les serveurs. Lorsque vous installez Lync Server sur des serveurs individuels, les serveurs lisent la topologie publiée dans le cadre du processus d’installation, et le programme d’installation déploie le serveur comme indiqué dans la topologie.

<div>

## <a name="lync-server-planning-tool"></a>Outil de planification Lync Server

L’outil de planification répond aux questions posées dans l’outil et génère une topologie basée sur les recommandations et les meilleures pratiques de Lync Server. Il propose également plusieurs vues de déploiement en fonction de vos réponses. Il offre à la fois une vue globale de tous vos sites (y compris les sites centraux et les sites de succursale) ainsi que des vues détaillées montrant les serveurs et autres composants de chaque site.

L’exécution de l’outil de planification ne vous engage pas sur un déploiement spécifique ou ne lance pas de processus. En fait, l’exécution de l’outil de planification, même avant que vous ne soyez prêt à l’esprit, peut être une façon très instructive de comprendre les types de questions que vous devez prendre en compte dans votre processus de planification.

Vous pouvez exécuter l’outil de planification plusieurs fois, répondre différemment aux questions et comparer les résultats. Si vous disposez d’une conception que vous êtes le plus satisfaite, mais que vous devez y effectuer des modifications, vous pouvez revenir à l’outil de planification, charger la conception et effectuer les modifications. Il faut environ 15 minutes pour terminer l’outil de planification une seule fois.

Une fois que vous êtes satisfait, vous pouvez utiliser l’outil de planification pour créer un diagramme de votre déploiement planifié. Vous pouvez utiliser ce diagramme lors de la création du déploiement dans le générateur de topologie.

<div>


> [!NOTE]  
> L’outil de planification inclus dans cette version de Lync Server 2013 est une version préliminaire. Notez que les nombres de planification de la capacité dans l’Outil de planification sont préliminaires et ne sont pas pris en charge pour la version finale.



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Générateur de topologies Lync Server

Une fois que vous avez choisi votre plan de déploiement, vous utilisez le générateur de topologie pour commencer le déploiement. Lorsque vous avez terminé, vous utilisez le générateur de topologies pour valider la topologie, puis, si elle réussit, vous pouvez publier la topologie. Lorsque vous publiez la topologie, Lync Server place la topologie dans le magasin central de gestion, qui est créé à ce stade s’il n’existe pas déjà. Lorsque vous installez Lync Server sur chaque serveur de votre déploiement, le serveur lit la topologie à partir du magasin central de gestion et s’installe en fonction de son rôle dans votre déploiement.

Par ailleurs, si vous connaissez Lync Server et que vous avez besoin de conseils moins normatifs, vous pouvez ignorer l’outil de planification et utiliser les assistants du générateur de topologies pour la conception initiale de votre déploiement, ainsi que les étapes de validation et de publication.

L’utilisation du générateur de topologie pour planifier et publier une topologie est une étape obligatoire. Vous ne pouvez pas contourner le générateur de topologie et installer Lync Server individuellement sur les serveurs de votre déploiement. Chaque serveur doit lire la topologie à partir d’une topologie validée et publiée dans le magasin central de gestion.

</div>

<div>

## <a name="high-level-planning-process"></a>Processus de planification de haut niveau

Nous vous recommandons d’utiliser la documentation et l’outil de planification pour planifier votre déploiement Lync Server.

1.  Si vous êtes familiarisé avec les versions précédentes de Lync Server, lisez les [nouvelles fonctionnalités de Lync server 2013](lync-server-2013-new-features.md) pour vous familiariser avec les nouvelles fonctionnalités et conditions requises dans lync Server 2013.

2.  Lisez les autres rubriques de cette section de la documentation : [notions de base sur la topologie que vous devez savoir avant de planifier Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md), [décisions de planification initiale pour Lync Server 2013](lync-server-2013-initial-planning-decisions.md)et [clients pour Lync Server 2013](lync-server-2013-clients.md). Notez les décisions de planification représentées dans les [topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md).

3.  Maintenant que vous êtes familiarisé avec les fonctionnalités de Lync Server et les types de questions auxquelles vous devez répondre, exécutez l’outil de planification et affichez la topologie résultante et ses détails. Assurez-vous que la topologie s’adapte aux exigences uniques de votre entreprise.

4.  S’il existe des charges de travail ou des fonctionnalités particulières qui vous intéressent ou que vous devez en savoir plus, lisez les sections appropriées de la [planification de Lync Server 2013](lync-server-2013-planning.md).

5.  Réexécutez l’outil de planification. Vous pouvez commencer par le déploiement que vous avez créé à l’étape 3 puis modifier les résultats, ou reprendre tout à zéro.
    
    Si nécessaire, exécutez l’outil de planification une troisième fois et répétez l’opération jusqu’à ce que vous soyez satisfait du résultat.

6.  Une fois que vous avez finalisé le plan de la topologie, utilisez l’outil de planification pour créer et imprimer un diagramme Visio de votre topologie. Vous pouvez utiliser cette impression lorsque vous utilisez le générateur de topologie pour entrer votre topologie.

7.  Avant de commencer le déploiement, consultez la détermination de la [Configuration système requise pour Lync server 2013](lync-server-2013-determining-your-system-requirements.md) et détermination de la [Configuration requise pour votre infrastructure pour Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) afin de vous familiariser avec les conditions préalables et l’infrastructure nécessaire pour Lync Server. De plus, vérifiez que vous avez lu toutes les sections de [planification de Lync Server 2013](lync-server-2013-planning.md) qui s’appliquent aux charges de travail et aux fonctionnalités que vous prévoyez de déployer.

</div>

<div>

## <a name="migrating-from-previous-versions"></a>Migration à partir de versions précédentes

Si vous effectuez une migration vers Lync Server à partir d’une version antérieure, reportez-vous à la documentation de [migration](migration.md) pour obtenir des instructions spécifiques pour votre migration et votre déploiement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

