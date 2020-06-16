---
title: Interprétation des résultats
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d02f69f8ea1c8eb7df004e063dba39f03bbe8b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>Interprétation des résultats

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

L’outil de contrainte et de performances de Lync Server 2013 (LyncPerfTool.exe) comporte de nombreux compteurs que vous pouvez utiliser pour comprendre ce que fait le client et s’il rencontre des problèmes.

<div>

## <a name="client-counters"></a>Compteurs client

Chaque instance de LyncPerfTool.exe en cours d’exécution dispose d’une instance distincte des compteurs. Chaque instance est nommée par son ID de processus.

Si les clients sont surchargés, des problèmes peuvent se produire. Pour éviter ces problèmes, procédez comme suit :

1.  Surveillez l’utilisation du processeur et de la mémoire sur les ordinateurs clients. Si le processeur est toujours supérieur à 90%, réduisez le nombre d’utilisateurs.

2.  Si l’encombrement mémoire est élevé, vous pouvez rencontrer des problèmes si le fichier d’échange n’est pas assez grand. Vérifiez que la charge dédiée n’atteint pas la limite de l’ordinateur. Si vous utilisez des limites de mémoire, envisagez d’augmenter la taille du fichier d’échange ou de réduire le nombre d’utilisateurs.

Les tableaux suivants répertorient les compteurs de performances Key LyncPerfTool.

**Informations générales**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Compteur de performance</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Temps passé en minutes</p></td>
<td><p>Temps passé depuis le démarrage du processus.</p></td>
</tr>
<tr class="even">
<td><p>Points de terminaison actifs</p></td>
<td><p>Nombre de points de terminaison actuellement connectés au serveur.</p></td>
</tr>
<tr class="odd">
<td><p>Échecs de connexion</p></td>
<td><p>Nombre total d’échecs de connexion au point de terminaison.</p></td>
</tr>
<tr class="even">
<td><p>Tentatives de connexion</p></td>
<td><p>Nombre total de tentatives de connexion au point de terminaison.</p></td>
</tr>
<tr class="odd">
<td><p>Points de terminaison déconnectés</p></td>
<td><p>Nombre total de points de terminaison qui ont été déconnectés.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**Informations de présence**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Compteur de performance</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels SetPresence</p></td>
<td><p>Nombre total de tentatives de modification de présence. Pour les différents types de modifications de présence, voir le compteur de performances appels SetPresence (type de présence).</p></td>
</tr>
<tr class="even">
<td><p>NNN réponses pour SetPresence</p></td>
<td><p>Nombre total de codes de réponse nnn reçus du serveur.</p></td>
</tr>
<tr class="odd">
<td><p>Appels GetPresence</p></td>
<td><p>Nombre total de tentatives de demande d’obtention de présence.</p></td>
</tr>
<tr class="even">
<td><p>NNN réponses pour GetPresence</p></td>
<td><p>Nombre total de codes de réponse nnn reçus du serveur.</p></td>
</tr>
</tbody>
</table>


**Informations du service de carnet d’adresses**

Cette catégorie comprend les compteurs utilisés pour surveiller les téléchargements de fichiers du service de carnet d’adresses et les demandes de service de requête Web du carnet d’adresses.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Compteur de performance</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tentatives de téléchargements de fichiers complets/Delta ABS</p></td>
<td><p>Nombre total de demandes de téléchargements de fichiers complets ou deltas.</p></td>
</tr>
<tr class="even">
<td><p>Les téléchargements de fichiers complets/Delta ABS ont réussi</p></td>
<td><p>Nombre total de demandes de téléchargements de fichiers complets ou deltas.</p></td>
</tr>
<tr class="odd">
<td><p>Compteurs liés au service de requête Web du carnet d’adresses</p></td>
<td><p>Compteurs liés au téléchargement du fichier de carnet d’adresses.</p></td>
</tr>
<tr class="even">
<td><p>Tentatives d’appels WS WS</p></td>
<td><p>Nombre total de demandes de service de requête sur le Web du carnet d’adresses.</p></td>
</tr>
<tr class="odd">
<td><p>Appels WS WS réussis</p></td>
<td><p>Nombre total de demandes de service de requête Web de carnet d’adresses ayant renvoyé un code de réponse réussi.</p></td>
</tr>
<tr class="even">
<td><p>Échec des appels d’ABS WS</p></td>
<td><p>Nombre total de demandes de service de requête Web de carnet d’adresses qui a renvoyé un code de réponse d’erreur.</p></td>
</tr>
</tbody>
</table>


**Informations sur la liste de distribution (DL)**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Compteur de performance</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tentatives d’appels</p></td>
<td><p>Nombre total de demandes de service Web d’expansion de liste de distribution (DLX).</p></td>
</tr>
<tr class="even">
<td><p>Appels réussis</p></td>
<td><p>Nombre total de demandes de service Web DLX ayant renvoyé un code de réponse réussi.</p></td>
</tr>
<tr class="odd">
<td><p>Échec des appels</p></td>
<td><p>Nombre total de demandes de service Web DLX ayant renvoyé un code de réponse d’erreur.</p></td>
</tr>
</tbody>
</table>


**Informations de base VoIP**

Les compteurs de performance répertoriés ci-dessous indiquent les numéros de tous les appels VoIP (Voice over IP), y compris les appels vers le serveur de médiation, le serveur de conférence A/V, le serveur Edge, l’application Response Group et le standard automatique de conférence, lorsque ces scénarios sont activés.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Compteur de performance</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appelle active</p></td>
<td><p>Nombre total d’appels vocaux entrants/sortants en cours.</p></td>
</tr>
<tr class="even">
<td><p>Appels terminés</p></td>
<td><p>Nombre total d’appels vocaux entrants/sortants déjà terminés.</p></td>
</tr>
<tr class="odd">
<td><p>Appels refusés</p></td>
<td><p>Nombre total d’appels vocaux entrants refusés.</p></td>
</tr>
<tr class="even">
<td><p>Tentatives d’appels entrants/sortants</p></td>
<td><p>Nombre total d’appels vocaux entrants/sortants tentés.</p></td>
</tr>
<tr class="odd">
<td><p>Appels entrants/sortants établis</p></td>
<td><p>Nombre total d’appels vocaux entrants/sortants établis.</p></td>
</tr>
<tr class="even">
<td><p>Appels reçus NNN</p></td>
<td><p>Nombre total de codes de réponse nnn reçus du serveur.</p></td>
</tr>
<tr class="odd">
<td><p>Taux de réussite VoIP (%)</p></td>
<td><p>Nombre total d’appels établis/nombre total d’appels tentés.</p></td>
</tr>
</tbody>
</table>


**Informations sur les appels au service Response Group**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Compteur de performance</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appelle active</p></td>
<td><p>Nombre total d’appels actifs à l’application Response Group.</p></td>
</tr>
<tr class="even">
<td><p>Tentatives d’appels</p></td>
<td><p>Nombre total d’appels tentés.</p></td>
</tr>
</tbody>
</table>


**Informations sur les appels de messagerie instantanée**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Compteur de performance</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appelle active</p></td>
<td><p>Nombre total d’appels de messagerie instantanée entrants/sortants en cours.</p></td>
</tr>
<tr class="even">
<td><p>Appels terminés</p></td>
<td><p>Nombre total d’appels de messagerie instantanée entrants/sortants déjà terminés.</p></td>
</tr>
<tr class="odd">
<td><p>Appels reçus NNN</p></td>
<td><p>Nombre total de codes de réponse nnn reçus du serveur.</p></td>
</tr>
<tr class="even">
<td><p>Messages INSTANTANÉs reçus/envoyés</p></td>
<td><p>Nombre total de messages reçus ou envoyés pour toutes les sessions.</p></td>
</tr>
<tr class="odd">
<td><p>Tentatives d’appels entrants/sortants</p></td>
<td><p>Nombre total d’appels de messagerie instantanée entrants/sortants.</p></td>
</tr>
<tr class="even">
<td><p>Appels entrants/sortants établis</p></td>
<td><p>Nombre total d’appels de messagerie instantanée entrants/sortants établis.</p></td>
</tr>
</tbody>
</table>


**Informations sur les appels de partage d’application**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Compteur de performance</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appelle active</p></td>
<td><p>Nombre total d’appels de partage d’application entrants/sortants en cours.</p></td>
</tr>
<tr class="even">
<td><p>Appels terminés</p></td>
<td><p>Nombre total d’appels de partage d’application entrants et sortants déjà terminés.</p></td>
</tr>
<tr class="odd">
<td><p>Appels reçus NNN</p></td>
<td><p>Nombre total de codes de réponse nnn reçus du serveur.</p></td>
</tr>
<tr class="even">
<td><p>Tentatives d’appels entrants/sortants</p></td>
<td><p>Nombre total d’appels de partage d’application entrants/sortants.</p></td>
</tr>
<tr class="odd">
<td><p>Appels entrants/sortants établis</p></td>
<td><p>Nombre total d’appels de partage d’application entrants/sortants établis.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**Informations sur les appels CAA**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Compteur de performance</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appelle active</p></td>
<td><p>Nombre total d’appels RTC (réseau téléphonique commuté) en cours.</p></td>
</tr>
<tr class="even">
<td><p>Appels terminés</p></td>
<td><p>Nombre total d’appels RTC entrants/sortants déjà terminés.</p></td>
</tr>
<tr class="odd">
<td><p>Tentatives d’appels entrants/sortants</p></td>
<td><p>Nombre total d’appels RTC entrants/sortants.</p></td>
</tr>
<tr class="even">
<td><p>Appels entrants/sortants établis</p></td>
<td><p>Nombre total d’appels RTC entrants/sortants établis.</p></td>
</tr>
</tbody>
</table>


**Informations sur la Conférence**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Compteur de performance</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Conférences de messagerie instantanée actives</p></td>
<td><p>Nombre total de conférences de messagerie instantanée en cours.</p></td>
</tr>
<tr class="even">
<td><p>Conférences audio/vidéo actives</p></td>
<td><p>Nombre total de conférences audio/vidéo (A/V) en cours.</p></td>
</tr>
<tr class="odd">
<td><p>Conférences de partage d’applications actives</p></td>
<td><p>Nombre total de conférences de partage d’application en cours.</p></td>
</tr>
<tr class="even">
<td><p>Nombre de participants</p></td>
<td><p>Nombre total de participants actuellement connectés à des conférences.</p></td>
</tr>
<tr class="odd">
<td><p>Échec de la planification des conférences</p></td>
<td><p>Nombre total d’échecs lors de la tentative de planification d’une conférence.</p></td>
</tr>
<tr class="even">
<td><p>Rejoindre la Conférence</p></td>
<td><p>Nombre total d’échecs lors de la tentative de connexion à une conférence.</p></td>
</tr>
</tbody>
</table>


**Compteurs client UCWA**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Compteur de performance</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre total de jointures IMMCU réussies</p></td>
<td><p>Nombre total de conférences de messagerie instantanée jointes.</p></td>
</tr>
<tr class="even">
<td><p>Nombre total de jointures DMCU réussies</p></td>
<td><p>Nombre total de conférences A/V jointes.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

