---
title: 'Lync Server 2013 : scénarios pour l’accès des utilisateurs externes'
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
ms.openlocfilehash: bd560105303db5d09656c36620c9e8435feed86f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

L’accès des utilisateurs externes à Lync Server 2013 nécessite le déploiement d’au moins un serveur Edge et d’un proxy inverse dans votre réseau de périmètre. Vous pouvez également déployer un directeur ou un pool directeur dans votre réseau interne.

Si vous avez besoin d’une capacité supérieure à celle d’un serveur Edge unique, ou si vous avez besoin d’une haute disponibilité pour votre déploiement de serveur Edge, vous pouvez configurer l’équilibrage de charge et déployer plusieurs serveurs Edge dans un pool à charge équilibrée. Si votre organisation dispose de plusieurs centres de données, vous pouvez disposer de déploiements de serveur Edge ou de pool Edge à plusieurs emplacements. Toutefois, un seul des déploiements de serveur Edge peut être désigné comme itinéraire de Fédération.

Cette section définit les scénarios pour les déploiements de serveur Edge et mappe les sections de planification aux scénarios possibles. Par exemple, si votre déploiement requiert une haute disponibilité, la Fédération avec les contacts XMPP (extensible Messaging and Presence) et Lync Mobility, sélectionnez les entrées correspondantes dans le tableau suivant qui satisferont ces exigences et utilisez le sections de planification référencées pour définir votre déploiement, comme illustré dans le diagramme suivant.

**Processus de sélection d’un scénario de déploiement de serveur Edge**

![Exemple d’organigramme de déploiement](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Exemple d’organigramme de déploiement")

Ce processus vous permet de planifier et de documenter la configuration de toutes les fonctionnalités potentielles que vous envisagez de déployer pour vos utilisateurs. Toutefois, vous pouvez ajouter des services de Fédération et de mobilité après avoir déployé le serveur Edge et confirmé l’opération correcte avant d’ajouter d’autres fonctionnalités. Le processus d’ajout de fonctionnalités à un déploiement de serveur Edge existant est abordé dans la section relative au déploiement. Pour plus d’informations sur le déploiement, reportez-vous à la rubrique déploiement de l' [accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en incluant la planification de ces fonctionnalités lors du processus de planification initial, vous pouvez vous préparer aux exigences de DNS, de pare-feu et de certificat pour les fonctionnalités ajoutées, ce qui vous permet d’acquérir les certificats et de configurer les exigences DNS et de ports

<div>


> [!TIP]  
> Si vous envisagez d’installer les serveurs Edge et le proxy inverse, puis ajoutez des fonctionnalités ultérieurement (par exemple, la Fédération et la mobilité), déterminez les certificats dont vous aurez besoin pour tous les services après le déploiement. La planification et l’acquisition des certificats pour toutes les fonctionnalités à l’avance, initialement déployés ou non, vous évitent de devoir commander de nouveaux certificats afin de satisfaire aux exigences de la Fédération (c’est-à-dire sur les serveurs Edge) ou au proxy inverse (pour la mobilité services).



</div>

<div>


> [!NOTE]  
> Tous les services Edge s’exécutent sur chaque serveur Edge. Les services ne peuvent pas être fractionnés entre deux serveurs Edge différents. Si vous déployez un pool de serveurs Edge pour l’évolutivité, tous les services Edge sont déployés sur chaque serveur Edge du pool. Fédération XMPP, Office Communications Server et Fédération Lync Server, la connectivité PIC et la mobilité des clients sont des services supplémentaires qui peuvent être déployés après le déploiement de votre premier serveur Edge ou pool de serveurs Edge. Les services de mobilité constituent une fonctionnalité qui utilise le proxy inverse. L’installation des services de mobilité n’ajoute pas de fonctionnalités à vos serveurs Edge, mais nécessite une reconfiguration de votre proxy inverse. La colonne d' <STRONG>objectif d’installation</STRONG> qui répertorie ces fonctionnalités fournit des instructions de planification dans la colonne associée sous la <STRONG>section planification du serveur Edge ou des sections</STRONG> permettant de planifier simultanément ces fonctionnalités à déployer lorsque les serveurs Edge sont installés et configurés.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>Identification et mise en correspondance de vos objectifs de déploiement


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Objectif de l’installation</th>
<th>Documentation de planification de serveur Edge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vous considérez qu’un seul serveur suffit pour les services Edge services de votre infrastructure. Vous avez également l’intention d’utiliser des adresses IP privées pour les interfaces externes de serveur Edge utilisant la traduction d’adresses réseau (NAT) sur Internet.</p>
<p>Utilisez cette section de planification si vous déployez un serveur Edge unique dans votre périmètre. Vous allez déployer un serveur Edge avec des adresses IP privées affectées au serveur Edge et utilisera le protocole NAT pour fournir les adresses IP publiques pour les utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Serveur Edge consolidé unique avec des adresses IP privées et une interface NAT dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Vous considérez qu’un seul serveur suffit pour les services Edge services de votre infrastructure. Vous avez également l’intention d’utiliser des adresses IP publiques pour les interfaces externes de serveur sur Internet.</p>
<p>Utilisez cette section de planification si vous déployez un serveur Edge unique dans votre périmètre. Vous allez déployer un serveur Edge avec des adresses IP publiques affectées au serveur Edge. À la place de NAT, vous utiliserez le routage dans ce scénario. L’adresse IP publique réelle du serveur Edge est disponible pour les connexions d’utilisateurs externes.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vous considérez que la haute disponibilité des services Edge est importante pour les utilisateurs et vous déploierez au moins deux serveurs Edge dans ce pool. Vous avez également l’intention d’utiliser des adresses IP privées pour les interfaces externes de serveur Edge utilisant NAT sur Internet.</p>
<p>Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre. Vous allez déployer les serveurs Edge avec des adresses IP privées affectées au serveur Edge, à l’aide de l’équilibrage de charge DNS pour distribuer la communication dans le pool. Vous utiliserez NAT pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Vous considérez que la haute disponibilité des services Edge est importante pour les utilisateurs et vous déploierez au moins deux serveurs Edge dans ce pool. Vous avez également l’intention d’utiliser des adresses IP publiques pour les interfaces externes du serveur Edge sur Internet.</p>
<p>Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre. Vous allez déployer les serveurs Edge avec des adresses IP publiques affectées au serveur Edge, à l’aide de l’équilibrage de charge DNS pour distribuer la communication dans le pool. Au lieu d’utiliser NAT, vous utiliserez le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vous avez décidé que la haute disponibilité des services Edge est importante pour vos utilisateurs et vous allez déployer au moins deux serveurs Edge dans ce pool à l’aide d’un programme d’équilibrage de la charge matérielle.</p>
<p>Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre. Vous allez déployer les serveurs Edge avec des adresses IP publiques affectées au serveur Edge, en utilisant des programmes d’équilibrage de la charge matérielle pour distribuer la communication dans le pool. Au lieu d’utiliser NAT, vous utiliserez le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Les scénarios de fédération vous permettent de planifier la fonctionnalité qui étendra les types de partenaires avec lesquels vos utilisateurs peuvent communiquer.</p>
<ul>
<li><p>Fédération Lync Server</p></li>
<li><p>Fédération Office Communications Server</p></li>
<li><p>Solution PIC (Public IM Connectivity)</p></li>
<li><p>Fédération XMPP</p></li>
</ul></td>
<td><p>Planification de scénarios de fédération</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planification de la Fédération entre Lync Server 2013 et Office Communications Server</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planification de la connectivité de messagerie instantanée publique dans Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planification de la Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Les services de mobilité sont fournis via le proxy inverse. Les services qui permettent la mobilité pour les utilisateurs externes sont déployés sur le serveur frontal ou le pool frontal. Vous créez ou modifiez des règles de publication existantes sur le proxy inverse afin d’activer les services de mobilité pour les utilisateurs externes.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Planification de la mobilité dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> Dans les scénarios suivants, les sections constituent des architectures de référence, des exemples de DNS, des définitions de ports/protocoles et des exigences en matière de certificat. Elles contiennent également des diagrammes pour votre DNS, des définitions de port/protocole et des besoins en termes de certificat. Ces diagrammes serviront de modèles que vous pourrez remplir et diffuser à d’autres équipes (par exemple, aux équipes chargées du réseau, de l’infrastructure à clé publique et du déploiement de serveur de votre organisation). L’objectif des diagrammes est d’améliorer la communication et de garantir la réussite de la communication des éléments de configuration de serveur Edge requis aux personnes qui effectueront le travail de configuration proprement dit. Nous vous recommandons d’utiliser les diagrammes et les architectures de référence associées pour planifier votre déploiement.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

