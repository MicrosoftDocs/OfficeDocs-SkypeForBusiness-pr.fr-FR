---
title: 'Lync Server 2013 : Scénarios d’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eab8323744615dc3f5d0b68f4325fbfb85bf911e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Scénarios d’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Si vous fournissez un accès utilisateur externe pour Lync Server 2013, vous devez déployer au moins un serveur Edge et un proxy inverse dans votre réseau de périmètre. Le cas échéant, vous pouvez déployer un réalisateur ou un pool de réalisateurs dans votre réseau interne.

Si vous avez besoin d’une capacité supérieure à celle d’un serveur Edge unique, ou si vous avez besoin d’une haute disponibilité pour le déploiement de votre serveur Edge, vous pouvez configurer l’équilibrage de charge et déployer plusieurs serveurs Edge dans un pool équilibré. Si votre organisation possède plusieurs centres de données, vous pouvez utiliser des déploiements de serveur Edge ou de pool Edge à plusieurs emplacements. Toutefois, vous ne pouvez désigner qu’un des déploiements de serveur Edge en tant qu’itinéraire de Fédération.

Cette section définit les scénarios pour les déploiements de serveurs de périphérie et établit une correspondance entre les sections de planification et les scénarios possibles. Par exemple, si votre déploiement a besoin d’une haute disponibilité, de la Fédération avec les contacts de présence et de présence (XMPP) et de mobilité Lync, vous devez sélectionner les entrées correspondantes dans le tableau suivant qui satisfont les exigences et utiliser le sections de planification référencées permettant de définir votre déploiement, comme illustré dans l’organigramme suivant.

**Processus de sélection de scénario de déploiement de serveur Edge**

![Exemple d’organigramme de déploiement](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Exemple d’organigramme de déploiement")

En utilisant ce processus, vous pouvez planifier la configuration de toutes les fonctionnalités potentielles que vous envisagez de déployer pour vos utilisateurs. Toutefois, vous pouvez ajouter des services de Fédération et de mobilité après avoir déployé le serveur de périphérie et avoir confirmé l’opération correcte avant d’ajouter d’autres fonctionnalités. Le processus d’ajout de fonctionnalités à un déploiement de serveur Edge existant est abordé dans la section déploiement. Pour plus d’informations sur le déploiement, reportez-vous à la rubrique déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en incluant la planification de ces fonctionnalités au cours du processus de planification initial, vous pouvez préparer les exigences de DNS, de pare-feu et de certificat pour les fonctionnalités ajoutées, qui vous permettent d’acquérir les certificats et de configurer les exigences relatives au DNS et au port/

<div>


> [!TIP]  
> Si vous envisagez d’installer les serveurs Edge et le proxy inverse, puis ajoutez des fonctionnalités plus tard (par exemple, la Fédération et la mobilité), déterminez les certificats dont vous aurez besoin pour tous les services après le déploiement. En planifiant et en acquérant les certificats pour toutes les fonctionnalités à l’avance, déployées ou non, vous vous évite d’avoir à commander de nouveaux certificats pour répondre aux exigences de Fédération (c’est-à-dire, sur les serveurs de périphérie) ou en tant que proxy inverse (en ce qui concerne la mobilité. services).



</div>

<div>


> [!NOTE]  
> Tous les services Edge s’exécutent sur chaque serveur Edge. Les services ne peuvent pas être partagés entre deux serveurs d’arête différents. Si vous déployez un pool de périphérie pour une extensibilité, tous les services Edge sont déployés sur chaque serveur Edge du pool. XMPP Federation, Office Communications Server et Lync Server Federation, la connectivité de messagerie instantanée publique et la mobilité du client sont des services supplémentaires qui peuvent être déployés après le déploiement de votre premier serveur Edge ou pool d’arêtes. Les services de mobilité sont une fonctionnalité qui utilise le proxy inverse. L’installation des services de mobilité n’ajoute pas de fonctionnalités à vos serveurs Edge, mais nécessite une reconfiguration de votre proxy inverse. La colonne objectif de l' <STRONG>installation</STRONG> qui répertorie ces fonctionnalités fournit des recommandations en matière de planification dans la colonne associée sous la <STRONG>section planification du serveur de périmètre</STRONG> pour vous permettre de planifier les fonctionnalités en cours de déploiement lorsque les serveurs de périphérie sont installés et configurés.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>Identification et mappage de vos objectifs de déploiement


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Objectif de l’installation</th>
<th>Documentation sur la planification du serveur Edge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vous avez décidé qu’un seul serveur est suffisant pour les services Edge dans votre infrastructure. Vous envisagez également d’utiliser des adresses IP privées pour les interfaces externes du serveur Edge avec tar sur Internet.</p>
<p>Utilisez cette section planification si vous déployez un serveur Edge unique dans votre périmètre. Vous déploierez un serveur Edge avec des adresses IP privées affectées au serveur Edge et utiliserez tar pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Vous avez décidé qu’un seul serveur est suffisant pour les services Edge dans votre infrastructure. Vous envisagez également d’utiliser des adresses IP publiques pour les interfaces externes du serveur Edge vers Internet.</p>
<p>Utilisez cette section planification si vous déployez un serveur Edge unique dans votre périmètre. Vous déploierez un serveur Edge avec des adresses IP publiques affectées au serveur Edge. Au lieu de tar, vous utiliserez le routage dans ce scénario. L’adresse IP publique réelle du serveur Edge est mise à la disposition des connexions d’utilisateurs externes.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vous avez décidé qu’il est important de disposer d’une haute disponibilité des services Edge pour vos utilisateurs et de déployer deux ou plusieurs serveurs Edge dans ce pool. Vous envisagez également d’utiliser des adresses IP privées pour les interfaces externes du serveur Edge avec tar sur Internet.</p>
<p>Utilisez cette section planification si vous déployez un pool de serveurs Edge dans votre périmètre. Vous déploierez les serveurs Edge avec des adresses IP privées affectées au serveur Edge, en utilisant l’équilibrage de charge DNS pour répartir la communication entre le pool. Vous utiliserez tar pour fournir les adresses IP publiques pour les utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Vous avez décidé qu’il est important de disposer d’une haute disponibilité des services Edge pour vos utilisateurs et de déployer deux ou plusieurs serveurs Edge dans ce pool. Vous envisagez également d’utiliser des adresses IP publiques pour les interfaces externes du serveur Edge vers Internet.</p>
<p>Utilisez cette section planification si vous déployez un pool de serveurs Edge dans votre périmètre. Vous déploierez les serveurs Edge possédant des adresses IP publiques affectées au serveur Edge, à l’aide de l’équilibrage de charge DNS pour répartir la communication entre le pool. Au lieu de la traduction d’adresses réseau (NAT), vous allez utiliser le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vous avez décidé qu’il est important de disposer d’une haute disponibilité des services Edge pour vos utilisateurs et que vous déploierez deux ou plusieurs serveurs Edge dans ce pool à l’aide d’un dispositif d’équilibrage de la charge matérielle.</p>
<p>Utilisez cette section planification si vous déployez un pool de serveurs Edge dans votre périmètre. Vous déploierez les serveurs Edge avec des adresses IP publiques affectées au serveur Edge, en utilisant des équilibreurs de charge matérielle pour distribuer la communication entre le pool. Au lieu de la traduction d’adresses réseau (NAT), vous allez utiliser le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Les scénarios de Fédération vous permettent de planifier la fonctionnalité qui permettra aux utilisateurs de communiquer entre eux.</p>
<ul>
<li><p>Fédération Lync Server</p></li>
<li><p>Fédération Office Communications Server</p></li>
<li><p>Solution PIC (Public IM Connectivity)</p></li>
<li><p>Fédération XMPP</p></li>
</ul></td>
<td><p>Planification des scénarios de Fédération</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planification de Lync Server 2013 et de la Fédération Office Communications Server</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planification de la connectivité de messagerie instantanée publique dans Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planification de la Fédération des protocoles de messagerie et de présence extensibles dans Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Les services de mobilité sont proposés par le biais du proxy inverse. Les services qui autorisent la mobilité pour les utilisateurs externes sont déployés sur le serveur frontal ou le pool frontal. Pour activer les services de mobilité pour les utilisateurs externes, vous pouvez créer ou modifier des règles de publication existantes sur le proxy inverse.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Planification de la mobilité dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> Dans les sections de scénarios suivantes, vous trouverez des architectures de référence, des exemples de définitions de port/protocole et de certificat. Vous trouverez également des diagrammes pour les définitions DNS, port/protocole et certificats. Les diagrammes vous fournissent un modèle qui vous permettra de remplir et de distribuer d’autres équipes (par exemple, l’équipe réseau de votre organisation, l’équipe d’infrastructure à clé publique et l’équipe de déploiement du serveur). L’objectif des diagrammes est d’améliorer la communication et de garantir le succès lors de la communication des éléments de configuration de serveur Edge requis aux personnes qui effectuent le fonctionnement de la configuration réelle. Nous vous recommandons d’utiliser les diagrammes et les architectures de référence associées pour planifier votre déploiement.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

