---
title: Prise en charge de Lync Server 2013 pour la connectivité de messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cd3c8cf89b9d5e1637db893b57e6b5955fbcee9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>Prise en charge de la connectivité de messagerie instantanée publique

Cet article fournit des informations sur la prise en charge de la connectivité PIC (Public IM Connectivity). La fonction PIC est une fonctionnalité de Microsoft Lync qui permet aux organisations de permettre à leurs utilisateurs Lync de se connecter aux utilisateurs de certains services de messagerie instantanée publique via leurs clients et identités Lync.

Les utilisateurs finaux peuvent être en mesure de rester en contact avec leurs clients, leurs partenaires et leurs fournisseurs. La prise en charge d’un client de communication en temps réel dans le cadre de la mise à jour des fonctionnalités de contrôle, de conformité et d’archivage de Lync a un avantage. Lync-connectivité Skype, [publique disponible dans le 2013 de, s'](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)appuie sur l’ancien que Lync/Office Communications Server (OCS)/Live Communications Server (LCS) est d’abord établi avec la technologie pic de connexion à MSN/Windows Live, AOL et Yahoo.Pour plus d’informations sur Lync-connectivité Skype, voir la [connectivité Lync-Skype](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx). La Fédération avec Windows Live, AOL et Yahoo sont chacune sur une voie pour la fin de vie.Cette page décrit l’état de chaque service.

Pour utiliser la photo, les clients ont été obligés d’activer le service pour chaque fournisseur de services de messagerie instantanée publique. La configuration requise et les détails relatifs à cette action dépendent du fournisseur de services de messagerie instantanée et du programme de licence sous-jacent du client.

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft a mis en place Windows Live Messenger et Skype. En avril 2013, les utilisateurs de Messenger ont migré vers Skype lors de la connexion. Les clients Lync qui comptent sur une Fédération avec Messenger pourront toujours communiquer avec leurs contacts Messenger, même après la mise à jour de ces contacts sur Skype. Il n’y a rien que les administrateurs Lync ou les utilisateurs finaux de Lync doivent effectuer pour maintenir la continuité du service et la gestion de cette fonctionnalité dans Lync reste la même que celle des communications avec Messenger. 

Lorsque les utilisateurs de Messenger se connectent à Skype par le biais de leur compte Microsoft (c’est-à-dire, les mêmes informations d’identification utilisées pour Messenger) tous leurs contacts Messenger, y compris les contacts Lync fédérés, le suivent dans Skype. Le partage de présence et la messagerie instantanée entre Skype et Lync pour ces contacts sont disponibles. 

Lync-connectivité Skype : l’ajout, le partage de présence, la messagerie instantanée et les appels audio entre Lync et les utilisateurs Skype sont également désormais disponibles pour tous les clients Lync.

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo !\! et la messagerie instantanée sur AOL

Fédération avec Yahoo\! et AOL sont tous deux sur une voie pour la fin de vie des clients de Lync (et Office Communications Server). La capacité de Microsoft à fournir chacun de ces services est subordonné à la prise en charge de Yahoo\! et AOL, et les accords sous-jacents de ces derniers sont en panne. Pour Yahoo\! et AOL, le service va passer à la 2014 du 1er juin.

  - **Yahoo** -service va passer à la 2014 du 1er juin, et les clients continuent d’avoir besoin d’une licence pour la licence d’abonnement utilisateur de Microsoft Lync public ConnectivityÀ compter du 1er septembre, 2012, la USL., n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.Les clients disposant de licences achetées avant cette date seront en mesure de continuer à se fédérer avec Yahoo\! jusqu’à la date d’arrêt du service ou son expiration de la licence.Lisez [l’annonce](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) publiée sur le blog de l’équipe Lync.Les clients disposant de licences de PIC pour des accords qui dépassent le 30 juin, 2014 recevront un crédit au prorata du montant des paiements pour la période suivante : 30 juin 2014.

  - **AOL** : le 30 juin 2014, la connectivité de messagerie instantanée de Lync (« PIC ») ne sera plus disponible.Pour limiter les perturbations du client lorsque le service se termine, nous avons abandonné le approvisionnement des domaines de clients supplémentaires. Jusqu’au 30 juin 2014, les clients n’ont rien à faire pour continuer à prendre en charge les communications fédérées avec AIM. Au-delà de cette date (ou pour les clients souhaitant mettre en place des domaines supplémentaires), un service de substitution est disponible directement auprès d’AOL. Pour plus d’informations sur le nouveau service d’AOL, voir [établissement de la Fédération directe avec AIM](http://aimenterprise.aol.com/pic.php)  (ouvre la nouvelle page sur AOL.com).  

</div>

<div>

## <a name="public-im-provider-summary"></a>Résumé du fournisseur de messagerie instantanée publique

Le tableau suivant récapitule les fournisseurs de services de messagerie instantanée publics, les fonctionnalités de Fédération avec Lync et les exigences en matière de licences.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fournisseur de services de messagerie instantanée publique</th>
<th>Fonctionnalités fédérées</th>
<th>Conditions de licence</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>Messagerie instantanée, présence, audio</p></td>
<td><p>Licences d’accès client Lync Server, Lync Online (plan 1/2/3)</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>Messagerie instantanée, présence, audio/vidéo</p></td>
<td><p>Licences d’accès client de Lync Server (prises en charge dans la mesure où WLM est en marché)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>Messagerie instantanée, présence</p></td>
<td><p>Licences d’accès client de Lync Server ; pris en charge par le 2014 juin pour les clients existants.</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>Messagerie instantanée, présence</p></td>
<td><p>Il est nécessaire de disposer d’une licence d’abonnement utilisateur Microsoft Lync public Connectivity supplémentaire (« PIC USL ») en plus des licences d’accès client Lync Server. À compter du tarif de septembre 2012, la fonction USL de la photo n’est plus disponible à l’achat. Les clients disposant de licences actives peuvent continuer à se fédérer avec Yahoo ! Messenger tant que le service n’a pas été arrêté le 30 juin 2014.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

