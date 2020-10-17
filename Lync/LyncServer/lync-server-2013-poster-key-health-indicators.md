---
title: 'Lync Server 2013 : affiche : indicateurs d’intégrité clés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6db6a701c98a44b042d9ee36d0a749bf6363bd2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513381"
---
# <a name="key-health-indicators-in-lync-server-2013"></a>Indicateurs d’intégrité clés dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-10_

Cet article est un complément des [indicateurs d’intégrité clés : la base pour la maintenance de l’affiche des serveurs Lync sains](https://go.microsoft.com/fwlink/?linkid=391838) , que vous pouvez télécharger à partir du centre de téléchargement.

![Affiche décrivant le dépannage à l’aide de données KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Affiche décrivant le dépannage à l’aide de données KHI")

Vous pouvez utiliser cette affiche pour en savoir plus sur les indicateurs d’intégrité clés (KHIs), les compteurs de performance avec des seuils visant à révéler des problèmes d’expérience utilisateur. La collecte de données KHI est généralement la première étape de l’implémentation de la méthodologie de qualité des appels (CQM), qui est axée sur la qualité audio pour les utilisateurs de Lync.

Si vous avez des questions sur l’utilisation de CQM, vous pouvez soumettre vos questions à cqmfeedback@microsoft.com.

L’affiche décrit les domaines suivants :

  - Qu’est-ce que les indicateurs d’intégrité clés ?

  - Pour collecter des données KHI

  - Flux de correction pour tous les rôles serveur

  - Glossaire

  - Serveurs frontaux

  - Serveurs SQL principaux

  - serveurs de médiation

  - Serveurs de périphérie

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>Qu’est-ce que les indicateurs d’intégrité clés ?

Les indicateurs d’intégrité clés sont des compteurs de performance dont les seuils visent à révéler des problèmes d’expérience utilisateur. La collecte de données KHI est généralement la première étape de l’implémentation de la méthodologie de qualité des appels (CQM), qui est axée sur la qualité audio pour les utilisateurs de Lync.

Les KHIs sont utilisés en plus des solutions de surveillance Lync standard (par exemple, System Center Operations Manager, les transactions synthétiques, le serveur de surveillance) et non pas ces solutions.

Recueillez les compteurs de performance KHI et remplissez la feuille de calcul KHI accompagnant le Guide de mise en réseau pour produire une carte de performance qui vous permettra de déterminer l’intégrité du serveur d’un déploiement Lync. Une fois renseigné, il vous guide lors de la réparation de l’environnement et apporte un aperçu supplémentaire aux autres parties prenantes. Évaluez KHIs chaque mois et incorporez-les dans les processus opérationnels en cours de déploiement.

Téléchargez le [Guide de mise en réseau Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) pour voir la liste complète des KHIs et obtenir les feuilles de calcul connexes.

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>Pour collecter des données KHI

1.  Exécutez le script KHI inclus dans le Guide de mise en réseau Lync Server sur chaque serveur Lync Server. Cette opération crée un collecteur de données à l’intérieur de l’analyseur de performances et le nomme KHI. Par défaut, les données sont interrogées toutes les 15 secondes.

2.  Avant le début de la journée de travail de votre entreprise, accédez à chaque serveur Lync Server et démarrez le collecteur de données KHI.

3.  À la fin de ce jour, arrêtez le collecteur de données KHI et copiez les données vers un emplacement central.

4.  Après avoir utilisé l’analyseur de performances pour remplir la feuille de calcul KHI incluse avec le téléchargement du Guide de mise en réseau Lync Server, comparez les résultats aux cibles recommandées.

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>Flux de correction pour tous les rôles serveur

Pour chaque serveur de votre implémentation Lync, commencez par vérifier que les performances du système et de l’intégrité des composants du serveur sont égales ou supérieures au niveau souhaité. Uniquement après cela, vous devez examiner les indicateurs relatifs au rôle du serveur dans l’implémentation globale de Lync.

Commencez par collecter les données de performances KHI pour tous les serveurs. Pour chaque rôle système (détails abordés plus loin dans ce document), déterminez si les composants système de base satisfont aux objectifs recommandés. Si ce n’est pas le cas, corrigez les performances du système, puis rerecueillez les données KHI et assurez-vous que le système est en mesure d’examiner les mesures propres au rôle du serveur dans l’implémentation Lync. L’intégrité des composants de tous les rôles est définie comme suit :

  - Utilisation de l’UC \< 80%

  - Moy. disque écriture \< 10 ms

  - Moy. disk read \< 10 ms

  - Mémoire disponible \> 20% système total Mo

  - Longueur de la file d’attente réseau \< 2

  - Paquets ignorés (entrée/sortie) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>Glossaire

Les termes et acronymes suivants sont utilisés dans cette affiche :

AS MCU = unité de contrôle multipoint de partage d’application

MCU AV = audio/vidéo MCU

MCU de messagerie instantanée = MCU de messagerie instantanée

UCWA = API Web de communications unifiées

Serveur Edge AV = parcours audio/vidéo via le serveur Edge

Authentification AV = authentification audio/vidéo

Pile SIP = contient la mise en œuvre SIP principale de Lync

Proxy de données = utilisé pour la Conférence Edge

LySS = service de stockage Lync

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>Serveurs frontaux

Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs frontaux :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Domaine fonctionnel</th>
<th>Mesures cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/IM MCU</p></td>
<td><p>État d’intégrité de la MCU &lt; 2</p></td>
</tr>
<tr class="even">
<td><p>Composants Web</p></td>
<td><p>Délais d’attente de l’extension de liste de distribution &lt; 0</p>
<p>Échecs ABWQ = 0</p>
<p>Échecs LIS = 0</p>
<p>Erreurs d’authentification &lt; 1/s</p>
<p>Demandes v4 ASP.NET rejetées = 0</p></td>
</tr>
<tr class="odd">
<td><p>Pile SIP</p></td>
<td><p>Traitement des messages entrants moy. &lt;</p>
<p>Réponses entrantes supprimées &lt; 1/s requêtes entrantes abandonnées &lt; 1/s</p>
<p>Latence de file d’attente &lt; 100 ms</p>
<p>Latence de la sproc &lt; 100 ms</p>
<p>Demandes limitées = 0</p>
<p>Erreurs d’authentification &lt; 1/s</p>
<p>Messages entrants expirés &lt; 2</p>
<p>Durée moyenne de blocage des messages entrants &lt; 1 seconde</p>
<p>Connexions avec contrôle de flux &lt; 2</p>
<p>&lt;Retard moy.</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% de l’espace utilisé par le service de stockage DB &lt; 80</p>
<p># d’échecs de réplication de réplica = 0</p>
<p># des événements de perte de données = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Durée de vie de la page &gt; 300 s.</p>
<p>Demandes par lots/s &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>Serveurs SQL principaux

Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs SQL :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Domaine fonctionnel</th>
<th>Mesures cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Durée de vie de la page &gt; 300 s.</p>
<p>Demandes par lots/s &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>serveurs de médiation

Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs de médiation :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Domaine fonctionnel</th>
<th>Mesures cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Service de médiation</p></td>
<td><p>Index d’échec de l’appel de chargement = 0</p>
<p>Appels ayant échoué en raison du proxy &lt; 10</p>
<p>Appels ayant échoué en raison de la passerelle &lt; 10</p>
<p>Appels (entrants ou sortants) rejetés = 0</p>
<p>Candidats multimédias manquants = 0</p>
<p>Échecs de vérification de la connectivité des médias = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>Serveurs de périphérie

Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs Edge :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Domaine fonctionnel</th>
<th>Mesures cibles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Authentification AV</p></td>
<td><p>Demandes incorrectes &lt; 20/s</p></td>
</tr>
<tr class="even">
<td><p>Serveur Edge AV</p></td>
<td><p>Échecs d’authentification &lt; 20/s</p>
<p>Échecs de répartition &lt; 20/s</p>
<p>Paquets supprimés &lt; 300/s</p></td>
</tr>
<tr class="odd">
<td><p>Proxy de données</p></td>
<td><p>Connexions serveur limitées &lt; 3</p>
<p>Le système est limité à &lt; 1</p></td>
</tr>
<tr class="even">
<td><p>Pile SIP</p></td>
<td><p>Connexions au-delà de la limite ignorée &lt; 1</p>
<p>Envoi expiré &lt; 10</p>
<p>Connexions contrôlées par flux &lt; 100</p>
<p>Demandes entrantes abandonnées &lt; 1/s</p>
<p>Traitement de message moy. &lt; 3 s</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Guide de mise en réseau Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicateurs d’intégrité clés : base pour la maintenance des serveurs Lync sains](https://go.microsoft.com/fwlink/?linkid=391838)  
[Méthodologie de qualité des appels Lync](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

