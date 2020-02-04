---
title: 'Lync Server 2013 : Définition de la configuration requise pour le pare-feu A/V et les ports'
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
ms.openlocfilehash: 3d5519ef37ff334ddf196e94b40aa7df14d69d25
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Les communications audio/vidéo (A/V) peuvent être complexes. En raison de la nature des protocoles utilisés dans A/V et de la manière dont les clients et les serveurs utilisent les protocoles, une section spéciale est garante d’expliquer les différences entre les versions client et serveur.

Utilisez le pare-feu A/V et la table de port suivants pour déterminer les exigences de pare-feu et les ports à ouvrir. Ensuite, examinez la terminologie de la traduction d’adresses réseau (NAT), car la traduction d’adresses réseau peut être implémentée de diverses manières. Pour obtenir un exemple détaillé de paramètres de port de pare-feu, consultez les architectures de référence dans les [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>Utilisation générale des protocoles pour UDP et TCP dans le trafic audio/vidéo et multimédia

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
<td><p>UDP</p></td>
<td><p>Protocole préféré de couche de transport pour le son et la vidéo</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>Protocole de couche de transport de secours pour le son et la vidéo</p>
<p>Protocole requis pour le partage d’application sur Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013</p>
<p>Protocole requis pour le transfert de fichiers vers Lync Server 2010 et Lync Server 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>Exigences relatives aux ports de pare-feu A/V externes pour l’accès des utilisateurs externes

La configuration requise pour les ports de pare-feu pour les interfaces SIP et de conférence externes (et internes) est cohérente, quelle que soit la version de votre client ou la version du partenaire de Fédération.

Le même type n’est pas vrai pour l’interface externe du périphérique audio/vidéo. Dans le cadre de la Fédération avec Office Communications Server 2007, le service Edge A/V exige que les règles de pare-feu externe autorisent le trafic RTP/TCP et RTP/UDP dans les 50 000 à 59 999 par le biais de la plage de port. Le tableau précédent part du principe que Lync Server 2013 est le principal partenaire de Fédération et qu’il est configuré pour communiquer avec l’un des autres types de partenaires de Fédération répertoriés.

La configuration de la plage de ports audio/vidéo de 50000-59,999 doit prendre en compte que la plage de port va contenir les ports sources pour les communications avec les partenaires de Fédération. En détail, considérez qu’une communication est lancée à partir d’un partenaire de Fédération. La communication des ports de service Edge A/V dans la plage 50000-59,999 se connectera au port TCP 443 du service Edge A/V du partenaire. À l’inverse, le trafic entrant vers votre service de port TCP 443 a un port source dans la plage comprise entre 50000 et 59,999.

Les pare-feu et les stratégies différents pour l’administration du pare-feu peuvent nécessiter la configuration de règles de destination uniquement, ou exiger la configuration de la source et de la destination. S’il s’agit de la configuration requise pour les ports de destination uniquement, les exigences audio et vidéo sont les suivantes :


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
<td><p>Indifférente</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interface de service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Indifférente</p></td>
<td><p>Interface de service Edge A/V</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Indifférente</p></td>
<td><p>Interface de service Edge A/V</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Si vos stratégies nécessitent à la fois les définitions des règles de pare-feu entrant et sortant, les exigences audio et vidéo sont les suivantes :


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
<td><p>Indifférente</p></td>
<td><p>TCP 50 000 à 59 999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interface de service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Indifférente</p></td>
<td><p>Interface de service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Indifférente</p></td>
<td><p>Interface de service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> La configuration de Microsoft Office Communications Server 2007 nécessite une configuration légèrement différente. Les plages de port TCP et UDP de 50000-59,999 doivent être ouvertes en entrée et en sortie. Cette condition est uniquement requise pour Office Communicator 2007. Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013 nécessitent uniquement la plage TCP 50000-59,999 ouverte.



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>Configuration NAT requise pour le service Edge

Les exigences suivantes concernant tar s’appliquent si vous choisissez de configurer des adresses IP privées non routables pour le service Edge :

  - TAR ne peut être utilisée qu’avec l’équilibrage de charge DNS. TAR n’est pas pris en charge avec une topologie de bord de l’équilibrage de charge matérielle (HLB).

  - TAR ne peut être utilisée que sur l’interface latérale externe. TAR n’est pas pris en charge sur l’interface latérale interne.

  - TAR doit être symétrique pour le trafic entrant et sortant.
    
  - Pour le trafic provenant d’Internet, tar doit remplacer l’adresse IP de destination par l’adresse IP publique compatible NAT du service Edge A/V par son adresse IP externe. L’adresse IP source doit rester intacte, de sorte que le service Edge A/V peut trouver le chemin multimédia optimal.
  
  Par exemple, dans la direction entrante dans l’illustration ci-dessous, l’adresse IP publique 131.107.155.30 a été remplacée par l’adresse IP (privée) 10.45.16.10. L’adresse IP source reste inchangée.
  
  - Pour le trafic du service Edge A/V vers Internet, tar doit remplacer l’adresse IP source par l’adresse IP externe du service Edge A/V par l’adresse IP publique compatible NAT.

Par exemple, dans la direction sortante dans la figure ci-dessous, l’adresse IP (privée) 10.45.16.10 a été remplacée par l’adresse IP publique 131.107.155.30.

**La figure ci-dessous montre comment tar modifie l’adresse IP de destination pour le trafic entrant et l’adresse IP source pour le trafic sortant.**

![Modification des adresses IP de destination/source](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Modification des adresses IP de destination/source")

Les points clés sont les suivants :

  - Le trafic entrant sur le serveur exécutant le service Edge A/V, l’adresse IP source reste inchangée mais l’adresse IP de destination passe d' 131.107.155.30 à l’adresse IP traduite de 10.45.16.10.

  - Le trafic sortant du serveur exécutant le service Edge A/V vers la station de travail, l’adresse IP source passe de l’adresse IP publique du serveur à l’adresse IP publique du serveur exécutant le service Edge A/V. L’adresse IP de destination reste l’adresse IP publique de la station de travail. Une fois que le paquet A quitté le premier périphérique NAT en sortie, la règle sur le périphérique NAT change l’adresse IP source du serveur exécutant l’adresse IP de l’interface externe A/V (10.45.16.10) sur son adresse IP publique (131.107.155.30).

</div>

</div>

<span> </span>

</div>

</div>

</div>

