---
title: 'Lync Server 2013: affiche: indicateurs d’intégrité clés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9454197642ac87f5d8bc0d768795854d792f9a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Principaux indicateurs d’intégrité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-10_

Cet article est un complément des [indicateurs d’intégrité clés: la base de la mise à jour des afficheurs Lync Servers sains](http://go.microsoft.com/fwlink/?linkid=391838) que vous pouvez télécharger à partir du centre de téléchargement.

![Affiche décrivant le dépannage à l’aide de données Khi] (images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Affiche décrivant le dépannage à l’aide de données Khi")

Vous pouvez utiliser cette affiche pour en savoir plus sur les indicateurs de performance clés (KHIs), les compteurs de performance avec des seuils visant à révéler des problèmes d’utilisation de l’utilisateur. La collecte des données KHI est généralement la première étape de l’implémentation de la méthodologie de qualité des appels (CQM), qui vise à garantir une qualité audio optimale pour les utilisateurs de Lync.

Si vous avez des questions sur l’utilisation de CQM, vous pouvez transmettre vos questions à cqmfeedback@microsoft.com.

L’affiche décrit les domaines suivants:

  - Que sont les indicateurs d’intégrité clés?

  - Pour collecter des données KHI

  - Flux de correction pour tous les rôles de serveur

  - Glossaire

  - Serveurs frontaux

  - Serveur SQL principal

  - serveurs de médiation

  - serveurs Edge

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>Que sont les indicateurs d’intégrité clés?

Les indicateurs de performance clés sont des compteurs de performance avec des seuils visant à révéler des problèmes d’utilisation de l’utilisateur. La collecte des données KHI est généralement la première étape de l’implémentation de la méthodologie de qualité des appels (CQM), qui vise à garantir une qualité audio optimale pour les utilisateurs de Lync.

Les KHIs sont utilisés en plus des solutions de surveillance Lync standard (par exemple, System Center Operations Manager, transactions synthétiques, serveur de surveillance) et non au lieu de ces solutions.

Recueillez les compteurs de performance KHI et remplissez la feuille de calcul KHI qui accompagne le Guide réseau pour créer une carte de performance qui vous aidera à déterminer l’état du serveur d’un déploiement Lync. Une fois rempli, il vous guide dans la réparation de l’environnement et fournit des renseignements supplémentaires aux autres parties prenantes. Évaluez KHIs sur une base mensuelle et intégrez-le dans les processus opérationnels en cours de déploiement.

Téléchargez le [Guide du réseau Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677) pour afficher la liste complète des KHIs et obtenir les feuilles de calcul associées.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>Pour collecter des données KHI

1.  Exécutez le script KHI inclus dans le Guide du réseau Lync Server sur chaque serveur Lync. Cela permet de créer un collecteur de données dans le moniteur de performance et de le nommer KHI. Par défaut, les données sont interrogées toutes les 15 secondes.

2.  Avant le début de la journée de votre entreprise, accédez à chaque serveur Lync et démarrez le collecteur de données KHI.

3.  À la fin de cette journée, arrêtez le collecteur de données KHI et copiez les données dans un emplacement central.

4.  Après avoir utilisé le moniteur de performance pour remplir la feuille de calcul KHI incluse dans le téléchargement du Guide du réseau Lync Server, comparez les résultats aux cibles recommandées.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>Flux de correction pour tous les rôles de serveur

Pour chaque serveur dans votre implémentation Lync, commencez par vérifier que les performances du composant et celles du serveur du serveur sont au niveau le plus souhaité. Après cela, vous devez examiner les indicateurs relatifs au rôle du serveur dans l’implémentation globale de Lync.

Commencez par collecter les données de performances KHI pour tous les serveurs. Pour chacun des rôles système (détails abordés plus loin dans ce document), déterminez si les composants système de base répondent aux cibles recommandées. Si ce n’est pas le cas, assurez-vous d’apporter une correction aux performances du système, puis recollectez les données KHI et assurez-vous que l’état du système s’applique aux mesures spécifiques au rôle du serveur dans l’implémentation Lync. L’intégrité des composants de tous les rôles est définie comme suit:

  - Taux d' \< utilisation UC 80%

  - Moyenne. écriture \< de 10 ms

  - Moyenne. Disk lu \< 10 ms

  - Mémoire \>disponible de 20% au total Mo

  - Longueur \< de la file d’attente réseau 2

  - Paquets ignorés (en entrée/sortie) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>Glossaire

Les termes et sigles suivants sont utilisés dans cet affiche:

AS MCU = unité de contrôle de partage d’application multipoint

AV MCU = audio/vidéo MCU

Messagerie instantanée MCU = MCU

UCWA = API Web de communications unifiées

Clavier AV = traversée de l’audio/vidéo via Edge

Authentification AV = authentification audio/vidéo

Pile SIP = application de base SIP de Lync

Proxy de données = utilisé pour les conférences de périphériques

LySS = service de stockage Lync

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>Serveurs frontaux

Les cibles KHI suivantes sont spécifiques aux serveurs frontaux en plus de l’état d’intégrité des composants de base:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zone fonctionnelle</th>
<th>Mesures cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/IM MCU</p></td>
<td><p>État &lt;d’intégrité du MCU 2</p></td>
</tr>
<tr class="even">
<td><p>Composants Web</p></td>
<td><p>Temporisation de l’extension de &lt;liste de distribution 0</p>
<p>Échecs de ABWQ = 0</p>
<p>Échecs de LIS = 0</p>
<p>Erreurs &lt; d’authentification 1/s</p>
<p>Demandes d’ASP.NET V4 rejetées = 0</p></td>
</tr>
<tr class="odd">
<td><p>Pile SIP</p></td>
<td><p>Moyenne. traitement &lt; de messages entrants 1 s</p>
<p>Les réponses entrantes ont été supprimées &lt; &lt; .</p>
<p>Latence de la &lt; file d’attente 100 ms</p>
<p>Latence de sproc &lt; 100 ms</p>
<p>Demandes de limitation = 0</p>
<p>Erreurs &lt; d’authentification 1/s</p>
<p>Messages entrants expirés &lt; 2</p>
<p>Moyenne de messages entrants &lt; : 1 seconde</p>
<p>Connexions &lt; à contrôle de flux 2</p>
<p>Moyenne. décalage &lt; de la file d’attente 2 s</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% d’espace utilisé par la base &lt; de services de stockage 80</p>
<p>#échecs de réplication de réplica = 0</p>
<p>#des événements de perte de données = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Durée de vie de &gt; la page 300 s.</p>
<p>Demandes de lot/ &lt; s 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>Serveur SQL principal

Les cibles KHI suivantes sont spécifiques aux serveurs SQL Server en plus de l’intégrité des composants de base:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zone fonctionnelle</th>
<th>Mesures cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Durée de vie de &gt; la page 300 s.</p>
<p>Demandes de lot/ &lt; s 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>serveurs de médiation

Les cibles KHI suivantes sont spécifiques aux serveurs de médiation en plus de l’intégrité des composants de base:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zone fonctionnelle</th>
<th>Mesures cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Service de médiation Server</p></td>
<td><p>Chargement de l’index d’échec de l’appel = 0</p>
<p>Appels en échec en raison &lt;de proxy 10</p>
<p>Appels en échec en raison &lt;de la passerelle 10</p>
<p>Appels (en sortie ou en sortie) rejetés = 0</p>
<p>Les candidats de médias ont manquant = 0</p>
<p>Échecs de vérification de la connectivité média = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>serveurs Edge

Les cibles KHI suivantes sont spécifiques aux serveurs Edge, en plus de l’état d’intégrité des composants de base:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zone fonctionnelle</th>
<th>Mesures cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Authentification AV</p></td>
<td><p>Demandes &lt; incorrectes 20/s</p></td>
</tr>
<tr class="even">
<td><p>Bordure AV</p></td>
<td><p>Échecs &lt;d’authentification 20/s</p>
<p>Échecs &lt;d’attribution 20/s</p>
<p>Paquets déposés &lt;300/s</p></td>
</tr>
<tr class="odd">
<td><p>Proxy de données</p></td>
<td><p>Connexions &lt; serveur limitées 3</p>
<p>Le système est en &lt;limitation 1</p></td>
</tr>
<tr class="even">
<td><p>Pile SIP</p></td>
<td><p>Connexions en dépassement de &lt; limite</p>
<p>Le délai d' &lt;envoi est écoulé 10</p>
<p>Connexion &lt;contrôlée par flux 100</p>
<p>Demandes entrantes &lt; rejetées 1/s</p>
<p>Moyenne du traitement &lt; des messages 3 s</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Guide du réseau Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Principaux indicateurs d’intégrité: notions de base pour la mise à jour des serveurs Lync sains](http://go.microsoft.com/fwlink/?linkid=391838)  
[Méthodologie de qualité d’appel Lync](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

