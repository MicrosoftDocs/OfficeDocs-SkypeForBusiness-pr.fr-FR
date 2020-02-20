---
title: 'Lync Server 2013 : configuration matérielle et logicielle requise pour le directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ff5e28b21e06cc438c7eb092515443579f5c004
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Configuration matérielle et logicielle requise pour le directeur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Cette section décrit la configuration matérielle et logicielle requise pour le directeur, ainsi que les scénarios de colocalisation pris en charge pour le directeur.

<div>

## <a name="hardware-requirements-for-the-director"></a>Configuration matérielle requise pour le directeur

Le tableau suivant répertorie la configuration matérielle requise pour le directeur :

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
<td><p>UC</p></td>
<td><ul>
<li><p>Processeur 64 bits, quadruple cœur 2,0 GHz ou supérieur</p></li>
<li><p>Biprocesseur 64 bits, double cœur 2,0 GHz ou supérieur</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>4 gigaoctets (Go)</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><ul>
<li><p>Lecteur de disque dur (HDD) 10 000 tr/min</p></li>
<li><p>Disque SSD à hautes performances avec des performances supérieures ou égales à 10K tr/min (HDD)</p></li>
<li><p>2x disques RAID 10 (agrégés par bandes et en miroir) 15 000 tr/min pour les fichiers de données des bases de données</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul>
<li><p>Cartes réseau Dual-port 1 gigabit par seconde (Gbps) (recommandé)</p></li>
<li><p>Carte réseau d’un gigabit (prise en charge)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Configuration logicielle requise pour le directeur

Le rôle directeur ne peut être déployé que sur des serveurs exécutant Lync Server 2013 Enterprise Edition.

L’un des systèmes d’exploitation 64 bits suivants est requis pour les directeurs :

  - Système d’exploitation Windows Server 2008 R2 Standard avec Service Pack 1

  - Système d’exploitation Windows Server 2008 R2 Enterprise avec Service Pack 1

  - Système d’exploitation Windows Server 2008 R2 Datacenter avec Service Pack 1

  - Le système d’exploitation Windows Server 2012 standard

  - Système d’exploitation Windows Server 2012 Datacenter

Lync Server 2013 nécessite également l’installation des programmes et des mises à jour suivants, décrits dans la rubrique relative à la [prise en charge et aux exigences des serveurs supplémentaires dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).

</div>

<div>

## <a name="supported-collocation"></a>Colocalisation prise en charge

Le rôle serveur directeur ne peut pas être colocalisé avec un autre rôle serveur dans Lync Server 2013. Toutefois, si vous ne déployez pas de directeur, les serveurs frontaux assumeront le rôle.

</div>

</div>

<span> </span>

</div>

</div>

</div>

