---
title: 'Lync Server 2013 : Collecte des données'
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
ms.openlocfilehash: e7c3d066aff26e06c003a31a58b4771d67f54f34
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Collecte des données dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Dans le logiciel de communication Microsoft Lync Server 2013, vous pouvez exécuter l’outil de planification Microsoft Lync Server 2013, sans documenter vos adresses IP et vos noms de domaine complets existants et proposés, mais il est beaucoup plus difficile à faire sans provoquer d’erreur de configuration. Par exemple, si la coexistence est requise pour une période donnée, une erreur courante consiste à réutiliser les noms de domaine complets d’un déploiement Edge existant pour votre déploiement Edge Lync Server 2013. L’utilisation des adresses IP et des noms de domaine complets existants et proposés dans une feuille de calcul, un tableau ou un autre formulaire visuel permet d’éviter des problèmes de configuration lors de l’installation.

<div>


> [!WARNING]  
> Si vous avez utilisé des versions précédentes de l’outil de planification, vous avez pu avoir utilisé l’outil pour créer votre topologie et le document de topologie exporté à utiliser dans le générateur de topologie pour publier votre topologie. La possibilité d’exporter la topologie a été supprimée de l’outil de planification. L’utilisation d’une version antérieure de l’outil de planification pour créer un document de topologie pour Lync Server 2013 est fortement déconseillée et génère des résultats inattendus.



</div>

Par conséquent, nous vous conseillons d’utiliser le modèle de collection de données suivant, qui correspond à votre topologie de bord, afin de rassembler les différentes adresses IP et FQDN que vous devrez entrer dans l’outil de planification. En documentant la configuration actuelle et proposée, vous pouvez placer les valeurs dans le contexte approprié pour votre environnement de production. De plus, vous devez penser à la façon dont vous allez configurer la coexistence et les fonctionnalités telles que les URL simples, les partages de fichiers et l’équilibrage de la charge.

Pour réussir le déploiement de Microsoft Lync Server 2013, vous devez comprendre l’interaction de chaque composant et s’en fier. La collecte des données à partir de votre infrastructure réseau et serveur existante et l’application des recommandations en matière de planification dans ces sections vous permettent d’intégrer les composants Lync Server 2013 Edge Server à votre infrastructure.

Introduction à la [sélection d’une topologie dans Lync Server 2013](lync-server-2013-choosing-a-topology.md), il existe trois architectures principales avec deux variantes, pour un total de cinq scénarios de déploiement possibles. L’un de ces scénarios est le point de départ pour votre collection de données. Les adresses IP, les noms de serveurs et les noms de domaine sont des exemples qui coïncident avec le certificat, le pare-feu et les diagrammes DNS correspondants qui décrivent les informations requises pour une solution de planification complète. Les diagrammes et le renseignement de votre certificat requis, des valeurs DNS et de pare-feu sont particulièrement importants dans les communications entre les équipes pour lesquelles la gestion de l’autorité de certification, de la configuration du pare-feu et du DNS est gérée par les équipes autres que celles de l’équipe. envisage le déploiement. Les diagrammes fournissent des informations sur les composants nécessaires qui peuvent être utilisés pour communiquer ces exigences en matière de collaboration entre équipes.

Les diagrammes fournis sont involontairement génériques, mais ils permettent de regrouper toutes les données pertinentes nécessaires à la communication de la configuration requise dans le cas d’une équipe croisée pour la mise en réseau, le pare-feu, la création et la gestion de certificats, le serveur le déploiement et la gestion de serveur sont gérés par différents groupes. L’utilisation des informations requises pour la configuration du réseau, des pare-feux, des ports et des protocoles, des certificats et des serveurs est très utile lorsque le déploiement de Lync Server est en cours.

**Serveur Edge et liste de bords**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**Proxy inverse**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**Pool de directeurs ou de réalisateurs**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

