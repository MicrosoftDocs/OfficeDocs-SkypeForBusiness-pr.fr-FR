---
title: 'Lync Server 2013 : événements UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950d52dfe86ebf4d5b8b53677248528f1ef49047
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>Événements UCWA dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 utilise l’API Web de communications unifiées (UCWA) à différentes fins, de l’accès à Microsoft Exchange pour les recherches de contacts à la mise à jour de la présence des clients mobiles.

UCWA écrit des enregistrements de comportement opérationnel sous forme d’informations de type d’événement, d’avertissement et d’erreur. Le tableau suivant décrit les événements qui peuvent être écrits par les composants UCWA.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID d’évènement</th>
<th>Type d'événement</th>
<th>Résumé</th>
<th>Cause et résolution</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>Message d’information</p></td>
<td><p>UCWA initialisé</p></td>
<td><p>N/A</p>
<p>N/A</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Error</p></td>
<td><p>UCWA a rencontré une exception inattendue lors de l’initialisation</p></td>
<td><p>Une erreur inattendue s’est produite lors de l’initialisation</p>
<p>Examiner les détails de l’exception dans l’entrée du journal des événements associé afin de déterminer la cause possible</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Error</p></td>
<td><p>UCWA a rencontré une exception non gérée</p></td>
<td><p>Une exception non gérée s’est produite</p>
<p>Redémarrez le serveur. Si le problème persiste, contactez le support technique</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Error</p></td>
<td><p>Impossible d’accéder à Exchange pour la photo HD</p></td>
<td><p>La connexion à Exchange n’est pas disponible</p>
<p>Assurez-vous que la connexion à Exchange est disponible.</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>Message d’information</p></td>
<td><p>Récupération de l’échec de l’accès à Exchange pour la photo HD</p></td>
<td><p>S/O</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Error</p></td>
<td><p>Impossible d’accéder à Exchange pour la recherche de contact</p></td>
<td><p>La connexion à Exchange n’est pas disponible</p>
<p>Assurez-vous que la connexion à Exchange est disponible.</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>Message d’information</p></td>
<td><p>Récupération d’un contact de recherche inversement dans Exchange</p></td>
<td><p>S/O</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>Avertissement</p></td>
<td><p>Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par application</p></td>
<td><p>Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par application</p>
<p>Vérifier les clients pour les abonnements inutiles</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>Avertissement</p></td>
<td><p>Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par lot</p></td>
<td><p>Tentative d’abonnement à un abonnement de présence supérieur à celui autorisé par lot</p>
<p>Vérifier les clients pour les abonnements inutiles</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Error</p></td>
<td><p>Impossible de récupérer les données inbande</p></td>
<td><p>Impossible de récupérer les données inbande</p>
<p>Si le problème persiste, contactez le support technique</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Error</p></td>
<td><p>Impossible de s’abonner à la présence</p></td>
<td><p>Impossible de s’abonner à la présence</p>
<p>Si le problème persiste, contactez le support technique</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Error</p></td>
<td><p>Échec de l’enregistrement du point de terminaison</p></td>
<td><p>Échec de l’enregistrement du point de terminaison</p>
<p>Si le problème persiste, contactez le support technique</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Error</p></td>
<td><p>Le MCU de messagerie instantanée n’est pas disponible</p></td>
<td><p>Le MCU de messagerie instantanée n’est pas disponible</p>
<p>Vérifier si la MCU de messagerie instantanée est en cours d’exécution</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>Message d’information</p></td>
<td><p>Récupération de l’échec de la connexion au MCU de messagerie instantanée</p></td>
<td><p>S/O</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Error</p></td>
<td><p>Le MCU AV n’est pas disponible</p></td>
<td><p>Le MCU AV n’est pas disponible</p>
<p>Vérifier si le MCU AV est en cours d’exécution</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>Message d’information</p></td>
<td><p>Récupération de l’échec de la connexion au MCU AV</p></td>
<td><p>S/O</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Error</p></td>
<td><p>CAR MCU n’est pas disponible</p></td>
<td><p>CAR MCU n’est pas disponible</p>
<p>Voir si MCU est en cours d’exécution</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>Message d’information</p></td>
<td><p>Récupération de l’échec de la connexion à MCU</p></td>
<td><p>S/O</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Error</p></td>
<td><p>Le MCU de données n’est pas disponible</p></td>
<td><p>Le MCU de données n’est pas disponible</p>
<p>Vérifier si le MCU de données est en cours d’exécution</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>Message d’information</p></td>
<td><p>Récupération de l’échec de la connexion au MCU de données</p></td>
<td><p>S/O</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Error</p></td>
<td><p>Impossible de rejoindre la MCU de messagerie instantanée</p></td>
<td><p>Impossible de rejoindre la MCU de messagerie instantanée</p>
<p>Vérifier si la MCU de messagerie instantanée est en cours d’exécution</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Error</p></td>
<td><p>Impossible de rejoindre le MCU AV</p></td>
<td><p>Impossible de rejoindre le MCU AV</p>
<p>Vérifier si le MCU AV est en cours d’exécution</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Error</p></td>
<td><p>Impossible de rejoindre en tant que MCU</p></td>
<td><p>Impossible de rejoindre en tant que MCU</p>
<p>Voir si MCU est en cours d’exécution</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Error</p></td>
<td><p>Impossible de rejoindre le MCU de données</p></td>
<td><p>Impossible de rejoindre le MCU de données</p>
<p>Vérifier si le MCU de données est en cours d’exécution</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Error</p></td>
<td><p>Impossible d’accéder à Active Directory pour la photo</p></td>
<td><p>La connexion à Active Directory n’est pas disponible</p>
<p>Assurez-vous que la connexion à Active Directory est disponible.</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>Message d’information</p></td>
<td><p>Récupération de l’échec de l’accès à Active Directory pour la photo</p></td>
<td><p>S/O</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>Avertissement</p></td>
<td><p>Impossible de désérialiser</p></td>
<td><p>Impossible de désérialiser</p>
<p>Si le problème persiste, contactez le support technique</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

