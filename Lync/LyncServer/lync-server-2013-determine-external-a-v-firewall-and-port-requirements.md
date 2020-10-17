---
title: 'Lync Server 2013 : déterminer les exigences en matière de port et de pare-feu A/V externe'
description: 'Lync Server 2013 : déterminer les exigences en matière de port et de pare-feu A/V externe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550930"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

La communication audio/vidéo (A/V) peut être complexe. En raison de la nature des protocoles utilisés dans A/V et de la façon dont les clients et les serveurs utilisent les protocoles, une section spéciale permet d’expliquer les différences entre les versions client et serveur.

Utilisez le pare-feu A/V et le tableau de ports suivants pour déterminer les exigences de pare-feu et les ports à ouvrir. Consultez ensuite la terminologie propre à la traduction d’adresses réseau (NAT, Network Address Translation), car cette fonctionnalité peut être implémentée de nombreuses façons. Pour obtenir un exemple détaillé des paramètres de port de pare-feu, consultez la rubrique architectures de référence dans [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>Utilisation générale du protocole pour UDP et TCP dans le trafic audio/vidéo et multimédia

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Transport audio/vidéo</th>
<th>Utilisation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DATAGRAMME</p></td>
<td><p>Protocole de couche de transport préféré pour l’audio et la vidéo</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>Protocole de couche transport de secours pour l’audio et la vidéo</p>
<p>Protocole de couche transport requis pour le partage d’application vers Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013</p>
<p>Protocole de couche transport requis pour le transfert de fichiers vers Lync Server 2010 et Lync Server 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>Conditions requises pour les ports du pare-feu A/V externe pour l’accès des utilisateurs externes

Les exigences de port de pare-feu pour les interfaces SIP et de conférence externes (et internes) sont cohérentes, quelle que soit la version de votre client ou la version du partenaire de Fédération.

Il en est de même pour l’interface externe du serveur Edge audio/vidéo. Pour la Fédération avec Office Communications Server 2007, le service Edge A/V exige que les règles de pare-feu externes autorisent le trafic RTP/TCP et RTP/UDP dans la plage de ports 50 000 à 59 999 pour circuler dans les deux directions. Le tableau précédent part du principe que Lync Server 2013 est le partenaire de Fédération principal et qu’il est configuré pour communiquer avec l’un des autres types de partenaires de Fédération énumérés.

La configuration de la plage de ports audio/vidéo de 50000-000-59 999 doit prendre en compte que la plage de ports contiendra les ports sources des communications vers les partenaires de Fédération. En détail, considérez qu’une communication est initiée à partir d’un partenaire de Fédération. La communication des ports de service Edge A/V dans la plage 50 000-000-59 999 se connectera au port TCP 443 attendu du service Edge A/V du partenaire. À l’inverse, le trafic entrant vers votre port de service Edge A/V TCP 443 aura un port source dans la plage de 50000-000-59 999.

Différents pare-feu et stratégies pour l’administration du pare-feu peuvent nécessiter que seules des règles de destination soient configurées, ou exiger la configuration de la source et de la destination. Si votre configuration requise concerne uniquement les ports de destination, les exigences audio/vidéo sont les suivantes :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Port de destination</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interface de service Edge A/V</p></td>
<td><p>N’importe lequel</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interface de service Edge A/V</p></td>
<td><p>N’importe lequel</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>N’importe lequel</p></td>
<td><p>Interface de service Edge A/V</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>N’importe lequel</p></td>
<td><p>Interface de service Edge A/V</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Si vos stratégies nécessitent à la fois des définitions de règles de pare-feu entrantes et sortantes, les exigences audio/vidéo sont les suivantes :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Port source</th>
<th>Port de destination</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interface de service Edge A/V</p></td>
<td><p>N’importe lequel</p></td>
<td><p>TCP 50000-000-59 999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interface de service Edge A/V</p></td>
<td><p>N’importe lequel</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>N’importe lequel</p></td>
<td><p>Interface de service Edge A/V</p></td>
<td><p>N’importe lequel</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>N’importe lequel</p></td>
<td><p>Interface de service Edge A/V</p></td>
<td><p>N’importe lequel</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office Communications Server 2007 nécessite une configuration légèrement différente. La plage de ports TCP et UDP de 50000 000-59 999 doit être ouverte et sortante. Cette exigence est uniquement destinée à Office Communicator 2007. Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013 nécessitent uniquement une plage TCP de 50000 000-59 999 ouvertes.



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>Configuration NAT requise pour le service Edge

Les conditions suivantes de l’interface NAT s’appliquent si vous choisissez de configurer des adresses IP privées non routables pour le service Edge :

  - La conversion d’adresses réseau ne peut être utilisée qu’avec l’équilibrage de charge DNS. NAT n’est pas pris en charge avec une topologie Edge d’équilibrage de la charge matérielle (charge matérielle).

  - La conversion d’adresses réseau (NAT) ne peut être utilisée que sur l’interface Edge externe. NAT n’est pas pris en charge sur l’interface interne Edge.

  - La conversion d’adresses réseau (NAT) doit être symétrique pour le trafic entrant et sortant.
    
  - Pour le trafic provenant d’Internet, tar doit modifier l’adresse IP de destination à partir de l’adresse IP publique à extension NAT du service Edge A/V vers son adresse IP externe. L’adresse IP source doit rester intacte, de sorte que le service Edge A/V puisse trouver le chemin multimédia optimal.
  
  Par exemple, dans la direction entrante dans la figure ci-dessous, l’adresse IP publique 131.107.155.30 a été remplacée par l’adresse IP externe (privée) 10.45.16.10. L’adresse IP source est restée inchangée.
  
  - Pour le trafic depuis le service Edge A/V vers Internet, tar doit modifier l’adresse IP source de l’adresse IP externe du service Edge A/V vers l’adresse IP publique à extension NAT.

Par exemple, dans la direction sortante dans la figure ci-dessous, l’adresse IP externe (privée) 10.45.16.10 a été remplacée par l’adresse IP publique 131.107.155.30.

**La figure ci-dessous montre comment NAT modifie l’adresse IP de destination pour le trafic entrant et l’adresse IP source pour le trafic sortant.**

![Modification des adresses IP source/destination](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Modification des adresses IP source/destination")

Les principaux points sont les suivants :

  - Trafic entrant sur le serveur qui exécute le service Edge A/V, l’adresse IP source ne change pas, mais l’adresse IP de destination passe de 131.107.155.30 à l’adresse IP traduite de 10.45.16.10.

  - Trafic sortant du serveur qui exécute le service Edge A/V vers le poste de travail, l’adresse IP source passe de l’adresse IP publique du serveur à l’adresse IP publique du serveur exécutant le service Edge A/V. L’adresse IP de destination conserve l’adresse IP publique de la station de travail. Une fois que le paquet quitte le premier périphérique NAT, la règle sur le périphérique NAT modifie l’adresse IP source du serveur exécutant l’adresse IP de l’interface externe du service Edge A/V (10.45.16.10) en son adresse IP publique (131.107.155.30).

</div>

</div>

<span> </span>

</div>

</div>

</div>

