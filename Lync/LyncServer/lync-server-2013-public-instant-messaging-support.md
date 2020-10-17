---
title: 'Lync Server 2013 : prise en charge de la messagerie instantanée publique'
description: 'Lync Server 2013 : prise en charge de la messagerie instantanée publique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e071e8b79be82d865a85a9488e48dd0a4264c7f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565570"
---
# <a name="public-instant-messaging-support-in-lync-server-2013"></a>Prise en charge de la messagerie instantanée publique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

Lync Server 2013 prend en charge l’utilisation de fournisseurs de connectivité de messagerie instantanée publique sous licence, ainsi que l’utilisation du protocole XMPP (eXtensible Messaging and Presence Protocol) pour mettre en œuvre un type spécial de Fédération qui permet à un serveur Lync d’accéder à des partenaires de domaine XMPP configurés à l’aide du client Lync 2013.

<div>

## <a name="public-im-connectivity-provider-support"></a>Prise en charge des fournisseurs de services de messagerie instantanée publics

Les partenaires de connectivité PIC (Public Instant Messaging) actuellement pris en charge sont les suivants :

  - America Online

  - Windows Live

  - Yahoo\!

Pour les communications avec les utilisateurs de Windows Live, Lync Server 2013 prend en charge les appels audio et vidéo d’égal à égal. Pour les communications avec AOL et Yahoo \! , Lync Server 2013 prend en charge la messagerie instantanée P2P. Une licence distincte peut être nécessaire.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a>Prise en charge de la fédération XMPP

La fédération XMPP prend en charge la communication des utilisateurs Lync avec les utilisateurs du domaine XMPP configuré qui utilisent un fournisseur public, tel que GTalk. Les communications avec ces utilisateurs peuvent inclure :

  - la messagerie instantanée d’égal à égal et la présence ;

  - la création de contacts XMPP fédérés dans le client Lync.

</div>

</div>

<span> </span>

</div>

</div>

</div>

