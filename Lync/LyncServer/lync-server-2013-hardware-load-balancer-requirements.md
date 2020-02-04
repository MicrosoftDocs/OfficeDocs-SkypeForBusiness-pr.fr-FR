---
title: Configuration requise pour l’équilibreur de charge matérielle pour Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ed4195d80ecc755faea74ddedb790c9f41ebfb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Configuration requise pour l’équilibreur de charge matérielle pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-05-11_

La topologie de périphérie consolidée de Lync Server 2013 est optimisée pour l’équilibrage de charge DNS pour les nouveaux déploiements qui se fédère principalement avec d’autres organisations à l’aide de Lync Server. S’il est nécessaire de disposer d’une haute disponibilité pour l’un des scénarios suivants, un équilibreur de charge matérielle doit être utilisé sur les pools de serveurs Edge pour les éléments suivants :

  - Fédération avec des organisations qui utilisent Office Communications Server 2007 R2 ou Office Communications Server 2007

  - Messagerie unifiée Exchange pour les utilisateurs distants utilisant la messagerie unifiée Exchange antérieure à Exchange 2010 avec SP1

  - Connectivité avec les utilisateurs de messagerie instantanée publique

<div>


> [!IMPORTANT]  
> L’utilisation de l’équilibrage de charge DNS sur une interface et de l’équilibrage de charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser l’équilibrage de charge matérielle ou l’équilibrage de charge DNS.



</div>

<div>


> [!NOTE]  
> Si vous utilisez un équilibreur de la charge matérielle, celui qui est déployé pour les connexions au réseau interne doit être configuré pour équilibrer uniquement la charge liée au trafic en direction de serveurs exécutant le service d’accès Edge et le service Edge A/V. Il ne peut pas équilibrer la charge du trafic vers le service Edge de conférence web ou le service de proxy XMPP interne.



</div>

<div>


> [!NOTE]  
> La traduction d’adresses réseau (DSR) direct Server n’est pas prise en charge avec Lync Server 2013.



</div>

Pour savoir si votre équilibreur de charge matérielle prend en charge les fonctionnalités nécessaires requises par Lync Server 2013, voir « partenaires d’équilibrage de charge Lync [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)Server 2010 » à l’adresse.

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Configuration requise pour l’équilibreur de la charge matérielle des serveurs Edge exécutant le service Edge A/V

Vous trouverez ci-après les exigences relatives à l’équilibrage de charge matérielle pour les serveurs Edge exécutant le service Edge A/V :

  - Désactivez le nagling TCP pour les ports 443 interne et externe. Le nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul paquet plus volumineux afin de rendre la transmission plus efficace.

  - Désactivez le nagling TCP pour la plage de ports externes 50 000 – 59 999.

  - N’utilisez pas NAT sur le pare-feu interne ou externe.

  - L’interface interne Edge doit être située sur un autre réseau que l’interface externe du serveur Edge et le routage entre ces derniers doit être désactivé.

  - L’interface externe du serveur de périphérie exécutant le service Edge A/V doit utiliser les adresses IP routables publiquement et aucune traduction NAT ou de port sur les adresses IP externes du bord.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Configuration requise pour l’équilibreur de charge matérielle

Les exigences d’affinité basées sur les cookies sont considérablement réduites dans Lync Server 2013 pour les services Web. Si vous déployez Lync Server 2013 et ne conservera aucun serveur frontal ou pool frontal de Lync Server 2010, vous n’avez pas besoin d’une persistance basée sur les cookies. Toutefois, si vous conservez temporairement ou définitivement tout serveur frontal ou pool frontal de Lync Server 2010, vous utiliserez quand même le niveau de persistance de cookie tel qu’il sera déployé et configuré pour Lync Server 2010.

<div>


> [!NOTE]  
> <STRONG>Si vous décidez d’utiliser l’affinité basée sur les cookies même si votre déploiement n’en a pas besoin</STRONG>, aucun impact négatif n’en résultera.



</div>

Pour les déploiements qui **nʼutiliseront pas** lʼaffinité basée sur les cookies :

  - Sur la règle de publication de proxy inverse pour le port 4443, définissez **Forward Header Header** sur true. Cela permet de s’assurer que l’URL d’origine est transférée.

Pour des déploiements qui **utiliseront** lʼaffinité basée sur les cookies :

  - Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur True afin de vous assurer que lʼURL dʼorigine est envoyée.

  - Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS être marqué httpOnly

  - Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS inclure d’heure d’expiration

  - Le cookie de l’équilibreur de la charge matérielle DOIT être nommé **MS-WSMAN** (Il s’agit de la valeur attendue par les services web et elle ne peut pas être modifiée)

  - Le cookie de l’équilibreur de la charge matérielle DOIT être défini dans chaque réponse HTTP pour laquelle la requête HTTP entrante ne possédait pas de cookie, qu’une réponse HTTP précédente ait déjà obtenu ou non un cookie sur cette même connexion TCP. Si l’équilibreur de la charge optimise l’insertion de cookies afin qu’elle se produise une seule fois par connexion TCP, cette optimisation NE DOIT PAS être utilisée

<div>


> [!NOTE]  
> Les configurations standard du programme d’équilibrage de la charge matérielle utilisent l’affinité adresse source et une durée de vie de session de 20 minutes, qui convient aux clients Lync Server et Lync 2013, car l’état de session est maintenu par le biais de l’utilisation du client et/ou de l’interaction avec l’application.



</div>

Si vous déployez des appareils mobiles, votre équilibreur de la charge matérielle doit être capable d’équilibrer la charge d’une requête individuelle au sein d’une session TCP (en effet, vous devez être en mesure d’équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).

<div>


> [!WARNING]  
> Les programmes d’équilibrage de la charge matérielle F5 possèdent une fonctionnalité appelée OneConnect qui permet de veiller à ce que la charge de chaque requête au sein d’une connexion TCP soit individuellement équilibrée. Si vous déployez des appareils mobiles, veillez à ce que le fournisseur de votre équilibreur de la charge matérielle prenne en charge la même fonctionnalité. Les dernières applications pour mobile iOS d’Apple requièrent la version 1.2 de TLS (Transport Layer Security). F5 fournit les paramètres spécifiques pour cela.<BR>Pour plus d’informations sur les équilibreurs de charge matérielle tiers, voir<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

La configuration requise de l’équilibreur de la charge matérielle des services web du directeur et du pool de serveurs frontaux est la suivante :

  - Pour les VIP de services Web internes,\_définissez persistance de l’adresse source (port interne 80, 443) sur le système d’équilibrage de la charge matérielle. Pour Lync Server 2013, la\_persistance de l’adresse source indique que plusieurs connexions venant d’une seule adresse IP sont toujours envoyées à un serveur pour conserver l’état de la session.

  - Utilisez un délai d’inactivité TCP de 1 800 secondes.

  - Sur le pare-feu situé entre le proxy inverse et l’équilibreur de la charge matérielle du pool du tronçon suivant, créez une règle autorisant le trafic https: sur le port 4443, entre le proxy inverse et l’équilibreur de la charge matérielle. L’équilibreur de la charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.

<div>


> [!IMPORTANT]  
> Pour en savoir plus sur la configuration de l’équilibrage de charge matérielle, consultez l’article <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Résumé du port-frontière consolidée avec des équilibreurs de charge matérielle dans Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Synthèse des conditions requises en termes d’affinité pour l’équilibreur de la charge matérielle


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement du client/de l’utilisateur</th>
<th>Conditions requises en matière d’affinité pour le nom de domaine complet des services web externes</th>
<th>Conditions requises en matière d’affinité pour le nom de domaine complet des services web internes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App (utilisateurs internes et externes)</p>
<p>Appareil mobile (utilisateurs internes et externes)</p></td>
<td><p>Aucune affinité</p></td>
<td><p>Affinité des adresses sources</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App (utilisateurs externes uniquement)</p>
<p>Appareil mobile (utilisateurs internes et externes)</p></td>
<td><p>Aucune affinité</p></td>
<td><p>Affinité des adresses sources</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App (utilisateurs internes uniquement)</p>
<p>Appareil mobile (non déployé)</p></td>
<td><p>Aucune affinité</p></td>
<td><p>Affinité des adresses sources</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>Surveillance des ports pour les programmes d’équilibrage de la charge matérielle

Vous définissez la surveillance des ports sur les équilibreurs de la charge matérielle pour déterminer si des services spécifiques ne sont plus disponibles suite à des échecs matériel ou de communication. Par exemple, si le service serveur frontal (RTCSRV) s’arrête en raison d’un dysfonctionnement du serveur frontal ou du pool frontal, la surveillance de HLB doit également arrêter la réception du trafic sur les services Web. Vous implémentez la surveillance des ports sur le programme d’équilibrage de la charge matérielle pour surveiller les éléments suivants :

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>Pool d’utilisateurs du serveur frontal-interface interne HLB

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>IP/Port virtuel</th>
<th>Port de nœud</th>
<th>Nœud Ordinateur/Écran</th>
<th>Profil de persistance</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;site&gt;Web de pool-int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>Serveur frontal</p>
<p>5061</p></td>
<td><p>Source</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;site&gt;Web de pool-int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>Serveur frontal</p>
<p>5061</p></td>
<td><p>Source</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>Pool d’utilisateurs du serveur frontal-interface externe HLB

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>IP/Port virtuel</th>
<th>Port de nœud</th>
<th>Nœud Ordinateur/Écran</th>
<th>Profil de persistance</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;web_mco_443_vs&gt;de réserve</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>Serveur frontal</p>
<p>5061</p></td>
<td><p>Aucune</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;web_mco_80_vs&gt;de réserve</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>Serveur frontal</p>
<p>5061</p></td>
<td><p>Aucune</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

