---
title: 'Lync Server 2013 : Prise en charge de la messagerie instantanée publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9da9be8db34306fc95f84ebdd40abc26bffd15e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-instant-messaging-support-in-lync-server-2013"></a>Prise en charge de la messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-07_

Lync Server 2013 prend en charge l’utilisation de fournisseurs de connectivité de messagerie instantanée publics, ainsi que l’utilisation du protocole XMPP (eXtensible Messaging and Presence Protocol) pour implémenter un type spécial de Fédération qui permet à un serveur Lync d’accéder à la configuration de la messagerie vocale configurée partenaires de domaine à l’aide du client 2013 Lync.

<div>

## <a name="public-im-connectivity-provider-support"></a>Prise en charge du fournisseur de connectivité de messagerie instantanée publique

Les partenaires de connectivité de messagerie instantanée publics actuellement pris en charge sont les suivants:

  - America Online

  - Windows Live

  - Yahoo!\!

Pour les communications avec les utilisateurs Windows Live, Lync Server 2013 prend en charge la messagerie instantanée et les appels audio et vidéo d’égal à égal. Pour les communications avec AOL et\!Yahoo, Lync Server 2013 prend en charge la messagerie instantanée d’égal à égal. Une licence séparée est éventuellement requise.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity («PIC USL») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, le contrat sous-jacent pour lequel le son est arrêté.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a>Prise en charge de la Fédération XMPP

La Fédération XMPP prend en charge les communications des utilisateurs Lync avec des utilisateurs de domaine XMPP configurés qui utilisent un fournisseur public, tel que GTalk. Les communications avec ces utilisateurs peuvent être les suivantes:

  - Messagerie instantanée et présence

  - Créer des contacts fédérés de XMPP dans le client Lync

</div>

</div>

<span> </span>

</div>

</div>

</div>

