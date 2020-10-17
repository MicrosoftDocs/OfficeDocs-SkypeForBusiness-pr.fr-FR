---
title: 'Lync Server 2013 : collecte de données'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01e6c75a4a557ff44d626f006210bec3a3c38472
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516571"
---
# <a name="data-collection-in-lync-server-2013"></a>Collecte de données dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Dans le logiciel de communication Microsoft Lync Server 2013, vous pouvez exécuter l’outil de planification de Microsoft Lync Server 2013, sans documenter les adresses IP et les noms de domaine complets existants et proposés, mais il est beaucoup plus difficile de le faire sans provoquer d’erreurs de configuration. Par exemple, si la coexistence est requise pendant un certain temps, une erreur fréquente consiste à réutiliser les noms de domaine complets d’un déploiement Edge existant pour votre déploiement Edge Lync Server 2013. Inscrire les adresses IP existantes et proposées ainsi que les FQDN dans une feuille de calcul, un tableau ou un autre formulaire visuel peut vous aider à prévenir les problèmes de configuration lors de l’installation.

<div>


> [!WARNING]  
> Si vous avez utilisé les versions précédentes de l’outil de planification, vous avez peut-être utilisé l’outil pour créer votre topologie, ainsi que le document de topologie exporté à utiliser dans le générateur de topologie pour publier votre topologie. La possibilité d’exporter la topologie a été supprimée de l’outil de planification. L’utilisation d’une version précédente de l’outil de planification pour créer un document de topologie pour Lync Server 2013 est fortement déconseillée et produira des résultats inattendus.



</div>

Par conséquent, l’approche recommandée consiste à utiliser le modèle de collecte de données suivant, qui correspond à votre topologie Edge, afin de collecter les différents nom de domaine complet et adresses IP que vous devrez entrer dans l’outil de planification. En documentant la configuration actuelle et proposée, vous pouvez saisir les valeurs dans le contexte approprié pour votre environnement de production. Et vous devez réfléchir à la façon dont vous configurerez la coexistence et les fonctionnalités comme les URL simples, les partages de fichiers et l’équilibrage de charge.

Pour déployer correctement Microsoft Lync Server 2013, vous devez comprendre l’interaction et la dépendance des composants individuels. En collectant des données à partir de votre infrastructure réseau et serveur existante et en appliquant les instructions de planification de ces sections, vous pouvez intégrer les composants de serveur Edge Lync Server 2013 à votre infrastructure.

Introduit dans [le choix d’une topologie dans Lync Server 2013](lync-server-2013-choosing-a-topology.md), il existe trois architectures principales avec deux variantes, pour un total de cinq scénarios de déploiement possibles. L’un de ces scénarios sera le point de départ de votre collection de données. Les adresses IP, noms de serveurs et noms de domaines sont des exemples qui coïncident avec les certificat, pare-feu et diagrammes DNS correspondants qui détaillent les informations requises pour une solution de planification complète. Les diagrammes et le remplissage des valeurs requises de votre certificat, DNS et pare-feu sont particulièrement importants dans les communications inter-équipes, où la gestion de l’autorité de certification, de la configuration du pare-feu et du DNS est assurée par d’autres équipes que celle qui planifie le déploiement. Les diagrammes fournissent des informations sur les composants requis qui peuvent être utilisées pour communiquer ces exigences pour la collaboration inter-équipes.

Les diagrammes fournis sont volontairement génériques, mais prennent en compte la collection de toutes les données pertinentes nécessaires à la communication des exigences dans un scénario entre équipes où la gestion du réseau, du pare-feu, la création et la gestion de certificats, le déploiement de serveur et la gestion de serveur sont assurés par différents groupes. Le fait de disposer des informations requises pour la configuration de la mise en réseau, des pare-feu, des ports et des protocoles, des certificats et des serveurs est inestimable lorsque le déploiement de Lync Server est en cours.

**Serveur Edge et pool de serveurs Edge**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**Proxy inverse**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**Directeur ou pool directeur**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

