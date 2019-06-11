---
title: 'Lync Server 2013: surveillance des discussions de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74897191cac7559237e961b7600a3ed478d11e58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Surveiller la discussion de groupe dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-08-04_

Nous vous recommandons vivement d’exécuter le [programme d’installation de mise à jour de serveur cumulative](http://support.microsoft.com/kb/968802) le plus récent disponible sur le centre de téléchargement Microsoft pour améliorer les performances.

En supposant que vous exécutez la dernière mise à jour cumulative, utilisez le tableau de test de stress suivant pour déterminer si vos serveurs de discussion de groupe s’exécutent de manière optimale.

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
<td><p>Trois serveurs de discussion de groupe dans une liste de discussion de groupe, chacun avec 8 Go de mémoire et 8 processeurs.</p></td>
</tr>
<tr class="even">
<td><p>Deux serveurs frontaux de Lync Server 2013 dans l’édition Enterprise.</p></td>
</tr>
<tr class="odd">
<td><p>60 000 utilisateurs simultanés sur trois serveurs de discussion de groupe.</p></td>
</tr>
<tr class="even">
<td><p>canaux 25 000 hébergés par une liste de discussion de groupe.</p></td>
</tr>
<tr class="odd">
<td><p>Taille du canal:</p>
<ul>
<li><p>Taille du petit canal: 30</p></li>
<li><p>Taille du canal moyen: 150</p></li>
<li><p>Grande taille de canal: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Nombre de canaux:</p>
<ul>
<li><p>Nombre de petits canaux: 24 000</p></li>
<li><p>Canaux de moyenne numérique 800</p></li>
<li><p>Nombre de canaux de grande taille 24</p></li>
<li><p>Nombre total de canaux 24 824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Canaux d’invitation:</p>
<ul>
<li><p>La moitié des canaux étaient des canaux d’invitation</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Nombre de canaux qu’un utilisateur rejoint:</p>
<ul>
<li><p>Petites: 12</p></li>
<li><p>Moyenne: 2</p></li>
<li><p>Grande: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Taux de participation:</p>
<ul>
<li><p>10 au total/par seconde, 3,33 secondes par serveur</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Taux de connexion:</p>
<ul>
<li><p>10 au total/par seconde, 3,33 secondes par serveur</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Taux de conversation:</p>
<ul>
<li><p>20 au total/par seconde, 6.66/seconde par serveur</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Les numéros de compteurs de performance suivants peuvent varier en fonction du matériel utilisé.



</div>

### <a name="performance-counter-to-be-monitored"></a>Compteur de performance à surveiller

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Compteur de performance</th>
<th>Seuil</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processus (ChannelService)-&gt;% temps processeur</p></td>
<td><p>Min: 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

