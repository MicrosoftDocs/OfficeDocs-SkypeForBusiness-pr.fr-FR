---
title: Prise en charge de Lync Server 2013 pour la connectivité de messagerie instantanée publique
description: Prise en charge de Lync Server 2013 pour la connectivité de messagerie instantanée publique.
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
ms.openlocfilehash: d4a58d71eb23012da960cf4505f1a55fd08df32c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573250"
---
# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>Prise en charge de la connectivité de messagerie instantanée publique

Cet article fournit des informations sur la prise en charge de la connectivité PIC (Public IM Connectivity). PIC est une fonctionnalité de Microsoft Lync qui permet aux organisations de permettre aux utilisateurs de communiquer avec des utilisateurs de certains services de messagerie instantanée (IM) publics via leurs clients et identités Lync.

Les utilisateurs finaux peuvent se connecter aux clients, partenaires et fournisseurs en fonction de leurs termes. Il bénéficie de la prise en charge d’un seul client de communications en temps réel tout en conservant les fonctionnalités de contrôle, de conformité et d’archivage de Lync. La connectivité Lync-Skype [accessible publiquement en mai 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), repose sur l’ancienneté que Lync/Office Communications Server (OCS)/Live Communications Server (LCS) a établi en premier lieu avec PIC lors de la connexion à MSN/Windows Live, AOL et Yahoo.Pour plus d’informations sur la connectivité Lync-Skype, voir [Lync-Skype Connectivity](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx). La Fédération avec Windows Live, AOL et Yahoo se situent dans un chemin d’accès à la fin de vie.Cette page décrit l’état de chaque service.

Pour utiliser PIC, les clients doivent activer le service pour chaque fournisseur de services de messagerie instantanée public. Les conditions requises et les détails relatifs à cette opération dépendent du fournisseur de services de messagerie instantanée et du programme de gestion des licences sous-jacent du client.

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft a mis en place Windows Live Messenger et Skype. En avril 2013, les utilisateurs de Messenger ont été migrés vers Skype lors de la connexion. Les clients Lync qui comptent sur la Fédération avec Messenger continueront à pouvoir communiquer avec leurs contacts Messenger, même après la mise à jour de ces contacts vers Skype. Il n’y a rien que les administrateurs Lync ou les utilisateurs finaux Lync doivent effectuer pour maintenir la continuité du service, et la gestion de cette fonctionnalité dans Lync reste identique à celle des communications avec Messenger. 

Lorsque les utilisateurs de Messenger se connectent à Skype à l’aide de leurs comptes Microsoft (c’est-à-dire, les mêmes informations d’identification utilisées pour Messenger), tous leurs contacts Messenger, y compris les contacts Lync fédérés, les suivent dans Skype. Le partage de présence et la messagerie instantanée entre Skype et Lync pour ces contacts sont disponibles. 

Lync-Skype connectivité-l’ajout, le partage de présence, la messagerie instantanée et l’appel audio entre Lync et les utilisateurs Skype sont également disponibles pour tous les clients Lync.

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo\! et AOL Instant Messenger

Fédération avec Yahoo\! en effet, AOL se trouve à la fois sur un chemin de fin de vie pour les clients de Lync (et Office Communications Server). La capacité de Microsoft à fournir chacun de ces services a été subordonnée à la prise en charge de Yahoo\! et AOL, et les accords sous-jacents de ceux-ci sont démontés. Pour Yahoo\! et AOL, le service se poursuivra jusqu’au 2014 juin.

  - **Yahoo** -service se poursuivra jusqu’au 2014 juin, et les clients continueront à utiliser la licence d’abonnement utilisateur Microsoft LYNC Public IM Connectivity (« PIC USL »).Depuis le 1er septembre, le 2012, la couche USL, n’est plus disponible à l’achat pour les contrats de nouvelle ou de renouvellement.Les clients disposant de licences achetées avant cette date seront en mesure de continuer à fédérer avec Yahoo.\! jusqu’à la date antérieure de l’arrêt du service ou de leur expiration de la licence.Lisez [l’annonce](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) sur le blog de l’équipe Lync.Les clients disposant de licences PIC sur des accords qui dépassent le 30 juin 2014 recevront un crédit proportionnellement au montant des paiements couvrant le délai suivant : 30 juin 2014.

  - **AOL** -le 30 juin 2014, le service de connectivité de messagerie instantanée de Lync (« PIC ») ne sera plus disponible.Afin de limiter le nombre d’interruptions client lorsque le service se termine, nous avons abandonné la mise en service des domaines de client supplémentaires. Jusqu’au 30 juin 2014, les clients n’ont rien besoin de faire quoi que ce soit pour continuer à prendre en charge les communications fédérées avec AIM. Au-delà de cette date (ou pour les clients qui souhaitent configurer des domaines supplémentaires en attendant), un service de remplacement est disponible directement auprès d’AOL. Pour plus d’informations sur le nouveau service d’AOL, consultez la rubrique établissement de la [Fédération directe avec AIM](http://aimenterprise.aol.com/pic.php)    (ouvre la nouvelle page sur AOL.com).  

</div>

<div>

## <a name="public-im-provider-summary"></a>Résumé des fournisseurs de messagerie instantanée publics

Le tableau suivant fournit un résumé des fournisseurs de services de messagerie instantanée publics, des fonctionnalités de Fédération avec Lync et des exigences en matière de licences.


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
<td><p>Licences d’accès client Lync Server, Lync Online plan 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>Messagerie instantanée, présence, audio/vidéo</p></td>
<td><p>Licences d’accès au client Lync Server (prises en charge tant que WLM est sur le marché)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>Messagerie instantanée, présence</p></td>
<td><p>Licences d’accès au client Lync Server ; pris en charge jusqu’en juin 2014 pour les clients existants.</p></td>
</tr>
<tr class="even">
<td><p>Payant</p></td>
<td><p>Messagerie instantanée, présence</p></td>
<td><p>Nécessite une licence d’abonnement utilisateur Microsoft Lync public Connectivity supplémentaire (« PIC USL ») en plus des licences d’accès au client Lync Server. À partir de la liste de prix de septembre 2012, la fonction USL n’est plus disponible à l’achat. Les clients disposant de licences actives peuvent continuer à fédérer avec Yahoo ! Messenger jusqu’à la date d’arrêt du service le 30 juin 2014.</p></td>
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

