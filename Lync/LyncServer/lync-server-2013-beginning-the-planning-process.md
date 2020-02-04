---
title: 'Lync Server 2013 : Début du processus de planification'
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
ms.openlocfilehash: a9da1c5535f190a6f57aa76b78a04845d4a073e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Début du processus de planification pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-24_

Dans le cadre de la planification d’un déploiement de communications unifiées sur site, il est possible que Lync Server propose deux outils intéressants pour vous aider :

  - **L’outil de planification** est un assistant qui présente une série de questions sur votre organisation, les fonctionnalités de serveur Lync que vous souhaitez activer et votre planification de capacité. Elle crée ensuite une topologie de déploiement recommandée en fonction de vos réponses et produit un diagramme Microsoft Visio de ce déploiement.

  - Le **Générateur de topologie** est un composant d’installation de Lync Server. Le générateur de topologie vous permet de créer, d’ajuster et de publier votre topologie planifiée. Il valide également votre topologie avant de commencer les installations serveur. Lorsque vous installez Lync Server sur des serveurs individuels, les serveurs lisent la topologie publiée dans le cadre du processus d’installation, et le programme d’installation déploie le serveur conformément aux instructions de la topologie.

<div>

## <a name="lync-server-planning-tool"></a>Outil de planification de Lync Server

L’outil de planification répond aux questions de l’outil et génère une topologie en fonction des recommandations et recommandations de Lync Server. Il fournit également plusieurs vues d’un déploiement en fonction de vos réponses. Il affiche à la fois un affichage global de tous vos sites (y compris les sites centraux et les sites de succursales) et des affichages détaillés affichant les serveurs et autres composants sur chaque site.

L’exécution de l’outil de planification ne vous engage pas à effectuer de déploiement spécifique ou à lancer des processus. En fait, l’exécution de l’outil de planification, même avant d’avoir une offre de bureau d’une entreprise, peut être une façon très instructive de comprendre les types de questions dont vous avez besoin dans le processus de planification.

Vous pouvez exécuter plusieurs fois l’outil de planification, répondre aux questions différemment et comparer les résultats. Si vous disposez d’une conception dont vous êtes le plus satisfait, mais que vous devez y apporter des modifications, vous pouvez revenir à l’outil de planification, charger la conception, puis apporter les modifications. L’exécution d’un outil de planification nécessite environ 15 minutes.

Lorsque vous êtes satisfait, vous pouvez utiliser l’outil de planification pour créer un diagramme de votre déploiement planifié. Vous pouvez utiliser ce diagramme lors de la création du déploiement dans le générateur de topologie.

<div>


> [!NOTE]  
> L’outil de planification inclus dans cette version de Lync Server 2013 est une version préliminaire. Notez que les chiffres de planification de la capacité de l’outil de planification sont préliminaires, et ne sont pas pris en charge par la version finale.



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Générateur de topologie Lync Server

Une fois que vous avez décidé de votre plan de déploiement, vous utilisez le générateur de topologie pour commencer le déploiement. Lorsque vous avez terminé, vous utilisez le générateur de topologie pour valider la topologie, puis, le cas échéant, vous pouvez publier la topologie. Lorsque vous publiez la topologie, Lync Server place la topologie dans le magasin central de gestion, qui est créé à ce moment-là s’il n’existe pas déjà. Lorsque vous installez Lync Server sur chaque serveur dans le cadre de votre déploiement, le serveur lit la topologie du magasin centralisé de gestion et s’installe pour s’adapter à son rôle dans votre déploiement.

Par ailleurs, si vous avez l’habitude d’utiliser Lync Server et que vous avez besoin d’un minimum d’instructions, vous pouvez ignorer l’outil de planification et utiliser les assistants du générateur de topologie pour la conception initiale de votre déploiement ainsi que pour les étapes de validation et de publication.

L’utilisation du générateur de topologie pour planifier et publier une topologie est une étape requise. Vous ne pouvez pas ignorer le générateur de topologie et installer Lync Server individuellement sur les serveurs de votre déploiement. Chaque serveur doit lire la topologie à partir d’une topologie validée et publiée dans le magasin central de gestion.

</div>

<div>

## <a name="high-level-planning-process"></a>Processus de planification de haut niveau

Nous recommandons le processus général suivant d’utilisation de la documentation et de l’outil de planification pour planifier votre déploiement de Lync Server.

1.  Si vous êtes familiarisé avec les versions précédentes de Lync Server, reportez-vous à la lecture de [nouvelles fonctionnalités dans Lync server 2013](lync-server-2013-new-features.md) pour vous familiariser avec les nouvelles fonctionnalités et exigences de lync Server 2013.

2.  Pour plus d’informations, reportez-vous à la rubrique informations supplémentaires dans cette section de la documentation : [notions de base sur la topologie que vous devez connaître avant de planifier Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), des [topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md), [des décisions de planification initiale pour Lync Server 2013](lync-server-2013-initial-planning-decisions.md), et [des clients pour Lync Server 2013](lync-server-2013-clients.md). Notez les décisions de planification représentées dans les [topologies de référence de Lync Server 2013](lync-server-2013-reference-topologies.md).

3.  Maintenant que vous êtes familiarisé avec les fonctionnalités de Lync Server et les types de questions auxquelles vous devez répondre, exécutez l’outil de planification et consultez la topologie qui en résulte et les détails associés. Assurez-vous que la topologie répond à la configuration requise unique pour votre organisation.

4.  S’il existe des charges de travail ou des fonctionnalités spécifiques qui vous intéressent ou dont vous avez besoin pour en savoir plus, consultez les sections de [planification appropriées pour Lync Server 2013](lync-server-2013-planning.md).

5.  Réexécutez l’outil de planification. Vous pouvez commencer avec le déploiement que vous avez créé à l’étape 3 et modifier les résultats ou commencer par le début.
    
    Le cas échéant, exécutez l’outil de planification une troisième fois et répétez l’opération jusqu’à ce que le résultat vous convienne.

6.  Après avoir finalisé le plan topologique, utilisez l’outil de planification pour créer et imprimer un diagramme Visio de votre topologie. Vous pouvez utiliser cette impression tout en travaillant avec le générateur de topologie pour entrer votre topologie.

7.  Avant de commencer le déploiement, prenez connaissance de la [Configuration système requise pour Lync server 2013](lync-server-2013-determining-your-system-requirements.md) et [Déterminez vos exigences d’infrastructure pour Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) afin de vous familiariser avec les conditions préalables et l’infrastructure requise pour Lync Server. Par ailleurs, assurez-vous que vous avez lu toutes les sections de [planification pour Lync Server 2013](lync-server-2013-planning.md) qui s’appliquent aux charges de travail et fonctionnalités que vous envisagez de déployer.

</div>

<div>

## <a name="migrating-from-previous-versions"></a>Migration à partir de versions précédentes

Si vous effectuez une migration vers Lync Server à partir d’une version antérieure, consultez la documentation de [migration](migration.md) pour obtenir des instructions spécifiques pour votre migration et votre déploiement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

