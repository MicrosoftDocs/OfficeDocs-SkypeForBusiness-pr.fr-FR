---
title: 'Lync Server 2013 : Configuration matérielle et logicielle requise pour le directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3b1b2a3f642c01d3a4743281554834e9ddda55f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Configuration matérielle et logicielle requise pour le directeur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-20_

Cette section détaille les configurations matérielles et logicielles requises pour le directeur et les scénarios de colocalisation pris en charge pour le directeur.

<div>

## <a name="hardware-requirements-for-the-director"></a>Configuration matérielle requise pour le directeur

Le tableau suivant répertorie la configuration matérielle requise pour le directeur:

### <a name="hardware-requirements-for-the-director"></a>Configuration matérielle requise pour le directeur

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant matériel</th>
<th>Spécification minimale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processeur</p></td>
<td><ul>
<li><p>processeur 64 bits, quadruple cœur, 2,0 GHz ou version ultérieure</p></li>
<li><p>processeur double cœur, 2,0 GHz ou version ultérieure 64</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>4 gigaoctets (Go)</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><ul>
<li><p>disque dur (HDD) 10 000 tr/min</p></li>
<li><p>Disque SSD haute performance avec performances égale ou supérieure à 10 000 tr/min</p></li>
<li><p>2 RAID 10 (bandes et miroirs) pour les fichiers de données de base de données</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul>
<li><p>2 cartes réseau 1 Gbit/s (Gbps)</p></li>
<li><p>Carte réseau 1 Gbps unique (prise en charge)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Configuration logicielle requise pour le directeur

Le rôle directeur peut être déployé uniquement sur les serveurs exécutant Lync Server 2013 Enterprise Edition.

L’un des systèmes d’exploitation 64 bits suivants est requis pour les directeurs:

  - Système d’exploitation Windows Server 2008 R2 Standard avec Service Pack 1

  - Système d’exploitation Windows Server 2008 R2 entreprise avec Service Pack 1

  - Système d’exploitation Windows Server 2008 R2 Datacenter avec Service Pack 1

  - Système d’exploitation Windows Server 2012 standard

  - Système d’exploitation Windows Server 2012 Datacenter

Lync Server 2013 nécessite également l’installation des mises à jour et des programmes suivants sur le sujet du [support technique supplémentaire et des exigences de Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).

</div>

<div>

## <a name="supported-collocation"></a>Colocalisation prises en charge

Le rôle serveur Director ne peut pas être localisé avec un autre rôle serveur dans Lync Server 2013. Toutefois, si vous ne déployez pas de réalisateur, le rôle serveur frontal sera supposé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

