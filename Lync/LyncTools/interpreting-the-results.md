---
title: Interprétation des résultats
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dcb1d84392cf9f56f2996281eb53e798690ba1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>Interprétation des résultats

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

L’outil de stress et de performance de Lync Server 2013 (LyncPerfTool. exe) comporte de nombreux compteurs qui vous permettent de comprendre ce que le client effectue et s’il rencontre des problèmes.

<div>

## <a name="client-counters"></a>Compteurs clients

Chaque instance de LyncPerfTool. exe en cours d’exécution dispose d’une instance distincte des compteurs. Chaque instance est nommée par son ID de processus.

Si les clients sont surchargés, des problèmes peuvent se produire. Pour éviter ce problème, procédez comme suit :

1.  Surveiller le processeur et l’utilisation de la mémoire sur les ordinateurs clients. Si le processeur est toujours supérieur à 90%, réduisez le nombre d’utilisateurs.

2.  Si l’encombrement mémoire est élevé, vous risquez de rencontrer des problèmes si le fichier de la page n’est pas assez grand. Assurez-vous que la mémoire de validation n’atteint pas la limite de l’ordinateur. Si vous utilisez des limites de mémoire, envisagez d’augmenter la taille de fichier de la page ou de réduire le nombre d’utilisateurs.

Les tableaux suivants répertorient les principaux compteurs de performances de LyncPerfTool.

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
<td><p>Nombre total d’échecs de connexion de point de terminaison.</p></td>
</tr>
<tr class="even">
<td><p>Tentatives d’ouverture de session</p></td>
<td><p>Nombre total de tentatives de connexion de point de terminaison.</p></td>
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
<td><p>Nombre total de tentatives de changement de présence. Pour les différents types de modifications de présence, voir le compteur de performance appels SetPresence (type de présence).</p></td>
</tr>
<tr class="even">
<td><p>NNN réponses pour SetPresence</p></td>
<td><p>Nombre total de codes de réponse nnn reçus du serveur.</p></td>
</tr>
<tr class="odd">
<td><p>Appels GetPresence</p></td>
<td><p>Nombre total de tentatives de demande de présence.</p></td>
</tr>
<tr class="even">
<td><p>NNN réponses pour GetPresence</p></td>
<td><p>Nombre total de codes de réponse nnn reçus du serveur.</p></td>
</tr>
</tbody>
</table>


**Informations relatives au service de carnet d’adresses**

Cette catégorie inclut des compteurs permettant de surveiller les téléchargements de fichiers du service de carnet d’adresses et les demandes de service de requête sur le carnet d’adresses.


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
<td><p>Tentatives de téléchargements de fichiers complets/Delta de ABS</p></td>
<td><p>Nombre total de demandes de téléchargement de fichiers complets ou Delta.</p></td>
</tr>
<tr class="even">
<td><p>Réussite des téléchargements de fichiers complets/Delta</p></td>
<td><p>Nombre total de demandes de téléchargement de fichiers complets ou Delta.</p></td>
</tr>
<tr class="odd">
<td><p>Compteurs liés au service de requête Web dans le carnet d’adresses</p></td>
<td><p>Compteurs liés au téléchargement du fichier du carnet d’adresses.</p></td>
</tr>
<tr class="even">
<td><p>Tentatives d’appels WS WS</p></td>
<td><p>Nombre total de demandes de service de requête Web dans le carnet d’adresses.</p></td>
</tr>
<tr class="odd">
<td><p>Appels WS WS réussis</p></td>
<td><p>Nombre total de demandes de service de requête Web de carnet d’adresses qui renvoient un code de réponse réussi.</p></td>
</tr>
<tr class="even">
<td><p>Échecs des services d’ABS WS</p></td>
<td><p>Nombre total de demandes de service de requête Web de carnet d’adresses qui renvoient un code de réponse d’erreur.</p></td>
</tr>
</tbody>
</table>


**Informations de liste de distribution (DL)**


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
<td><p>Appels essayés</p></td>
<td><p>Nombre total de demandes de service Web d’extension de liste de distribution (DLX) effectuées.</p></td>
</tr>
<tr class="even">
<td><p>Appels réussis</p></td>
<td><p>Nombre total de demandes de service Web DLX ayant renvoyé un code de réponse réussi.</p></td>
</tr>
<tr class="odd">
<td><p>Appels en échec</p></td>
<td><p>Nombre total de demandes de service Web DLX qui renvoient un code de réponse d’erreur.</p></td>
</tr>
</tbody>
</table>


**Informations de base sur VoIP**

Les compteurs de performance indiqués ci-dessous indiquent les numéros de tous les appels voix sur IP (VoIP), y compris les appels vers le serveur de médiation, le serveur de conférence A/V, le serveur Edge, l’application Response Group et le standard automatique des conférences, lorsque ces scénarios sont activés.


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
<td><p>Appels actifs</p></td>
<td><p>Nombre total d’appels vocaux entrants/sortants actuellement en cours.</p></td>
</tr>
<tr class="even">
<td><p>Appels interrompus</p></td>
<td><p>Nombre total d’appels vocaux entrants/sortants déjà terminés.</p></td>
</tr>
<tr class="odd">
<td><p>Appels refusés</p></td>
<td><p>Nombre total d’appels vocaux entrants refusés.</p></td>
</tr>
<tr class="even">
<td><p>Tentatives d’appels entrants/sortants</p></td>
<td><p>Nombre total d’appels vocaux entrants/sortants.</p></td>
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
<td><p>Taux de passe VoIP (%)</p></td>
<td><p>Nombre total d’appels passés/nombre total d’appels tentés.</p></td>
</tr>
</tbody>
</table>


**Informations de l’appel service de Response Group**


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
<td><p>Appels actifs</p></td>
<td><p>Nombre total d’appels actifs vers l’application Response Group.</p></td>
</tr>
<tr class="even">
<td><p>Appels essayés</p></td>
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
<td><p>Appels actifs</p></td>
<td><p>Nombre total d’appels de messages instantanés entrants et sortants.</p></td>
</tr>
<tr class="even">
<td><p>Appels interrompus</p></td>
<td><p>Nombre total d’appels entrants/sortants de messagerie instantanée déjà terminés.</p></td>
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
<td><p>Nombre total d’appels entrants/sortants de messages instantanés.</p></td>
</tr>
<tr class="even">
<td><p>Appels entrants/sortants établis</p></td>
<td><p>Nombre total d’appels entrants/sortants de messages instantanés établis.</p></td>
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
<td><p>Appels actifs</p></td>
<td><p>Nombre total d’appels de partage d’application entrants ou sortants.</p></td>
</tr>
<tr class="even">
<td><p>Appels interrompus</p></td>
<td><p>Nombre total d’appels de partage d’application entrants/sortants déjà terminés.</p></td>
</tr>
<tr class="odd">
<td><p>Appels reçus NNN</p></td>
<td><p>Nombre total de codes de réponse nnn reçus du serveur.</p></td>
</tr>
<tr class="even">
<td><p>Tentatives d’appels entrants/sortants</p></td>
<td><p>Nombre total d’appels entrants/sortants de partage d’application.</p></td>
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
<td><p>Appels actifs</p></td>
<td><p>Nombre total d’appels entrants/sortants de réseau téléphonique commuté (RTC) actuellement en cours.</p></td>
</tr>
<tr class="even">
<td><p>Appels interrompus</p></td>
<td><p>Nombre total d’appels RTC entrants/sortants déjà terminés.</p></td>
</tr>
<tr class="odd">
<td><p>Tentatives d’appels entrants/sortants</p></td>
<td><p>Nombre total d’appels RTC entrants et sortants.</p></td>
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
<td><p>Conférences de partage d’application actives</p></td>
<td><p>Nombre total de conférences de partage d’application en cours.</p></td>
</tr>
<tr class="even">
<td><p>Nombre de participants</p></td>
<td><p>Nombre total de participants actuellement connectés aux conférences.</p></td>
</tr>
<tr class="odd">
<td><p>Échec de la planification de conférences</p></td>
<td><p>Nombre total d’échecs lors de la planification d’une conférence.</p></td>
</tr>
<tr class="even">
<td><p>Participer à une conférence téléphonique</p></td>
<td><p>Nombre total d’échecs lors d’une tentative de connexion à une conférence.</p></td>
</tr>
</tbody>
</table>


**Compteurs du client UCWA**


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

