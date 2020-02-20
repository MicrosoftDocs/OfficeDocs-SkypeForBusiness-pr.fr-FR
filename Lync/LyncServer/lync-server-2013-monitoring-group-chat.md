---
title: 'Lync Server 2013 : surveillance de la conversation de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a42589db677132170e9456c998d96fd2eb1de5d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Surveillance de la conversation de groupe dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-04_

Nous vous recommandons vivement d’exécuter le [programme d’installation de mise à jour de serveur](https://support.microsoft.com/kb/968802) le plus récent disponible sur le centre de téléchargement Microsoft pour en améliorer les performances.

En supposant que vous exécutez la dernière mise à jour cumulative, utilisez le tableau test de contrainte suivant pour les mesures à comprendre si vos serveurs de conversation de groupe fonctionnent au niveau de l’intégrité.

### <a name="test-environment-and-user-model"></a>Environnement de test et modèle utilisateur

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Trois serveurs de conversation de groupe dans un pool de conversation de groupe, chacun avec une mémoire de 8 Go et 8 processeurs.</p></td>
</tr>
<tr class="even">
<td><p>Deux serveurs frontaux Lync Server 2013 dans Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>60 000 utilisateurs simultanés sur trois serveurs de conversation de groupe.</p></td>
</tr>
<tr class="even">
<td><p>25 000 canaux hébergés par le pool de conversation de groupe.</p></td>
</tr>
<tr class="odd">
<td><p>Taille du canal :</p>
<ul>
<li><p>Taille des petits canaux : 30</p></li>
<li><p>Taille moyenne des canaux : 150</p></li>
<li><p>Taille de canal large : 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Nombre de canaux :</p>
<ul>
<li><p>Nombre petites canaux : 24 000</p></li>
<li><p>Nombre moyen canaux 800</p></li>
<li><p>Nombre grandes canaux 24</p></li>
<li><p>Nombre total de canaux 24 824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Canaux d’invitation :</p>
<ul>
<li><p>La moitié des canaux ont été des canaux d’invitation</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Nombre de canaux qu’un utilisateur rejoint :</p>
<ul>
<li><p>Petit : 12</p></li>
<li><p>Moyenne : 2</p></li>
<li><p>Grande : 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Taux de participation :</p>
<ul>
<li><p>10 au total/seconde, 3,33/seconde par serveur</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Taux de déconnexion :</p>
<ul>
<li><p>10 au total/seconde, 3,33/seconde par serveur</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation :</p>
<ul>
<li><p>20 Total/seconde, 6.66/seconde par serveur</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Les numéros de compteur de performances suivants seront susceptibles de varier lorsque différentes spécifications matérielles ou profils utilisateur sont utilisés.



</div>

### <a name="performance-counter-to-be-monitored"></a>Compteur de performances à surveiller

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Compteur de performance</th>
<th>Seuils</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processus (ChannelService)-&gt;% temps processeur</p></td>
<td><p>Min : 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

