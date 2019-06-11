---
title: 'Lync Server 2013: planification de la connectivité de messagerie instantanée publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4432484fbd6056d51a38090a18dbe106851d7c0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Planification de la connectivité de messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-07_

La connectivité de messagerie instantanée publique est une classe de Fédération et est configurée pour permettre à vos utilisateurs de Lync Server 2013 internes et externes d’ajouter des contacts à partir de l’un des éléments suivants:

  - Contacts Messenger

  - Yahoo!\! contacts

  - Contacts AOL (America Online)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À compter du 1er septembre 2012, la licence de l’abonnement à l’utilisateur de la connectivité PIC (Public IM Connectivity) de Microsoft Lync n’est plus disponible pour l’achat de contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL (PIC) est une licence d’abonnement par utilisateur et par mois requise pour la Fédération de Lync Server ou d’Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, qui n’est pas renouvelé.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste, ce qui permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes par messagerie instantanée et vocale.</P></LI></UL>



</div>

Cette classe de Fédération exige les considérations en matière de planification suivantes:

  - Les utilisateurs de Windows Live Messenger peuvent utiliser la communication audio et vidéo d’égal à égal avec les utilisateurs de Lync Server 2013, en plus de la messagerie instantanée. Vos serveurs Edge doivent répondre à des exigences de port et de protocole spécifiques. Pour plus d’informations, reportez-vous à [la rubrique déterminer la configuration requise 2013 pour le pare-feu A](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - Le service de messagerie instantanée Yahoo n’est soumis à aucune configuration unique, autre que celles généralement utilisées dans le cadre de la planification et du déploiement du serveur de périphérie standard qui fournit la Fédération.

  - America Online nécessite que votre certificat de serveur Edge attribué au service Edge d’accès possède une utilisation améliorée de la clé par le client.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé de certification-connectivité de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Résumé de port-connectivité de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS Summary-connectivité de messagerie instantanée publique dans Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

