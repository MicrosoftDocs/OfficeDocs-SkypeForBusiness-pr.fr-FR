---
title: 'Lync Server 2013 : Scénarios d’accès des utilisateurs externes'
TOCTitle: Scénarios d’accès des utilisateurs externes
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425727(v=OCS.15)
ms:contentKeyID: 49296589
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Scénarios d’accès des utilisateurs externes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour donner aux utilisateurs externes l’accès à Lync Server 2013, vous devez déployer au moins un serveur Edge et un proxy inverse dans votre réseau de périmètre. Vous avez également la possibilité de déployer un directeur ou un pool de directeurs dans votre réseau interne.

Si les capacités d’un serveur Edge ne suffisent pas ou si vous voulez doter votre déploiement de serveur Edge de la haute disponibilité, vous pouvez configurer l’équilibrage de la charge réseau et déployer plusieurs serveurs Edge dans un pool à charge équilibrée. Si votre organisation compte plusieurs centres de données, vous pouvez déployer un serveur Edge ou un pool de serveurs Edge sur plusieurs sites. Cependant, seul un des déploiements de serveur Edge peut être désigné comme itinéraire de fédération.

Cette section définit les scénarios des déploiements de serveur Edge et fait correspondre les sections de planification aux scénarios possibles. Par exemple, si votre déploiement requiert la haute disponibilité, la fédération avec les contacts XMPP (Extensible Messaging and Presence Protocol) et la mobilité Lync, vous sélectionnerez, dans le tableau suivant, les entrées qui répondent à ces exigences et vous utiliserez les sections de planification référencées pour définir votre déploiement, comme illustré dans le diagramme ci-dessous.

**Processus de sélection d’un scénario de déploiement de serveur Edge**

![Exemple d’organigramme de déploiement](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Exemple d’organigramme de déploiement")

Ce processus vous permet de planifier et de documenter la configuration de toutes les fonctionnalités potentielles que vous envisagez de déployer pour vos utilisateurs. Cependant, vous pouvez ajouter des services de fédération et de mobilité après avoir déployé le serveur Edge et confirmé la conformité de l’opération avant d’ajouter d’autres fonctionnalités. Le processus d’ajout de fonctionnalités à un déploiement de serveur Edge est décrit dans la section Déploiement. Pour plus d’informations sur le déploiement, reportez-vous à [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) Le fait d’inclure la planification de ces fonctionnalités dans la planification initiale vous permet de préparer le DNS, le pare-feu et les certificats requis pour les fonctionnalités ajoutées, d’acquérir les certificats et de configurer le DNS et les ports/protocoles à l’avance.

> [!TIP]  
> Si vous envisagez d’installer les serveurs Edge et le proxy inverse, puis d’ajouter des fonctionnalités ultérieurement (par exemple, la fédération et la mobilité), déterminez de quels certificats vous aurez besoin pour tous les services après le déploiement. La planification et l’acquisition anticipées des certificats de toutes les fonctionnalités, qu’elles soient ou non déployées initialement, vous épargne l’achat de nouveaux certificats pour satisfaire aux exigences de la fédération (c’est-à-dire, sur les serveurs Edge) ou du proxy inverse (c’est-à-dire, pour les services de mobilité).

> [!NOTE]  
> Tous les services edge s’exécutent sur chaque serveur Edge. Les services ne peuvent pas être scindés entre deux serveurs Edge différents. Si vous déployez un pool de serveurs Edge pour l’extensibilité, tous les services edge sont déployés sur chaque serveur Edge dans le pool. La fédération XMPP, Office Communications Server et la fédération Lync Server, la connectivité PIC (Public IM Connectivity) et la mobilité client sont des services supplémentaires pouvant être déployés après le déploiement de votre premier serveur Edge ou pool de serveurs Edge. Les services de mobilité constituent une fonctionnalité qui utilise le proxy inverse. L’installation de ces services n’ajoute pas de fonctionnalités à vos serveurs Edge, mais nécessite une reconfiguration du proxy inverse. La colonne <strong>Objectif de l’installation</strong> qui répertorie ces fonctionnalités fournit une aide de planification dans la colonne associée sous <strong>Documentation de planification de serveur Edge</strong> pour planifier simultanément ces fonctionnalités de manière à les déployer lors de l’installation et la configuration des serveurs Edge.

## Identification et mise en correspondance de vos objectifs de déploiement


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
<td><p>Vous considérez qu’un seul serveur suffit pour les services Edge services de votre infrastructure. Vous avez également l’intention d’utiliser des adresses IP privées pour les interfaces externes de serveur Edge utilisant la conversion d’adresses réseau (NAT) sur Internet.</p>
<p>Utilisez cette section de planification si vous déployez un seul serveur Edge dans votre périmètre. Vous déploierez un serveur Edge avec des adresses IP privées affectées au serveur Edge et utiliserez NAT pour fournir des adresses IP publiques aux utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Serveur Edge consolidé unique avec des adresses IP privées et la conversion d’adresses réseau dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Vous considérez qu’un seul serveur suffit pour les services Edge services de votre infrastructure. Vous avez également l’intention d’utiliser des adresses IP publiques pour les interfaces externes de serveur sur Internet.</p>
<p>Utilisez cette section de planification si vous déployez un seul serveur Edgedans votre périmètre. Vous déploierez un serveur Edge avec des adresses IP publiques affectées au serveur Edge. À la place de NAT, vous utiliserez le routage dans ce scénario. Les adresses IP publiques réelles du serveur Edge sont disponibles pour les connexions utilisateur externe.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Serveur Edge consolidé unique avec adresses IP publiques dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vous considérez que la haute disponibilité des services Edge est importante pour les utilisateurs et vous déploierez au moins deux serveurs Edge dans ce pool. Vous avez également l’intention d’utiliser des adresses IP privées pour les interfaces externes de serveur Edge utilisant NAT sur Internet.</p>
<p>Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre. Vous déploierez les serveurs Edge avec les adresses IP privées affectées au serveur Edge, en utilisant l’équilibrage de la charge DNS pour répartir les communications dans le pool. Vous utiliserez NAT pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Vous considérez que la haute disponibilité des services Edge est importante pour les utilisateurs et vous déploierez au moins deux serveurs Edge dans ce pool. Vous avez également l’intention d’utiliser des adresses IP publiques pour les interfaces externes de serveur Edge sur Internet.</p>
<p>Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre. Vous déploierez les serveurs Edge avec les adresses IP publiques affectées au serveur Edge, en utilisant l’équilibrage de la charge DNS pour répartir les communications dans le pool. Au lieu d’utiliser NAT, vous utiliserez le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Vous considérez que la haute disponibilité des services Edge est importante pour vos utilisateurs et vous déploierez au moins deux serveurs Edge dans ce pool en utilisant un programme d’équilibrage de la charge matérielle.</p>
<p>Utilisez cette section de planification si vous déployez un pool de serveurs Edge dans votre périmètre. Vous déploierez les serveurs Edge avec les adresses IP publiques affectées au serveur Edge, en utilisant des programmes d’équilibrage de la charge matérielle pour répartir les communications dans le pool. Au lieu d’utiliser NAT, vous utiliserez le routage pour fournir les adresses IP publiques aux utilisateurs externes sur Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Topologie Edge consolidée mise à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Les scénarios de fédération vous permettent de planifier la fonctionnalité qui étendra les types de partenaires avec lesquels vos utilisateurs peuvent communiquer.</p><ul><li><p>Fédération Lync Server</p></li><li><p>Fédération Office Communications Server</p></li><li><p>Solution PIC (Public IM Connectivity)</p></li><li><p>Fédération XMPP</p></li></ul></td>
<td><p>Planification de scénarios de fédération</p><ul><li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planification pour la fédération de Lync Server et Office Communications Server</a></p></li><li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planification de la connectivité PIC (Public Instant Messaging Connectivity)</a></p></li><li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planification de la fédération XMPP (Extensible Messaging and Presence Protocol) dans Lync Server 2013</a></p></li></ul></td>
</tr>
<tr class="odd">
<td><p>Les services de mobilité sont fournis via le proxy inverse. Les services qui permettent aux utilisateurs externes de bénéficier de la mobilité sont déployés sur le serveur frontal ou le pool de serveurs frontaux. Vous créez ou modifiez des règles de publication existantes sur le proxy inverse afin d’activer les services de mobilité pour les utilisateurs externes.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Planification de la mobilité dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


> [!TIP]  
> Dans les scénarios suivants, les sections constituent des architectures de référence, des exemples de DNS, des définitions de ports/protocoles et des exigences en matière de certificat. Elles contiennent également des diagrammes pour votre DNS, des définitions de port/protocole et des besoins en termes de certificat. Ces diagrammes serviront de modèles que vous pourrez remplir et diffuser à d’autres équipes (par exemple, aux équipes chargées du réseau, de l’infrastructure à clé publique et du déploiement de serveur de votre organisation). L’objectif de ces diagrammes et d’améliorer la communication et de faire en sorte que les éléments de configuration de serveur Edge requis soient correctement indiqués aux personnes en charge de la configuration réelle. Nous vous recommandons d’utiliser les diagrammes et les architectures de référence associées pour planifier votre déploiement.
