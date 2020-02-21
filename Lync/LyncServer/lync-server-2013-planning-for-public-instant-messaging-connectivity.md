---
title: 'Lync Server 2013 : planification de la connectivité de messagerie instantanée publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52bc8a563a45e75b01932ee716df90f1cf2ca7da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Planification de la connectivité de messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

La connectivité de messagerie instantanée publique est une classe de Fédération et est configurée pour permettre à vos utilisateurs de Lync Server 2013 internes et externes d’ajouter des contacts à partir de l’un des éléments suivants :

  - Contacts Messenger

  - Yahoo\! contacts

  - Contacts AOL (America Online)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>À partir du 2012 1er septembre, la licence d’abonnement aux utilisateurs de la connectivité PIC de Microsoft Lync public (PIC) n’est plus disponible pour l’achat de contrats de nouvelle ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</P>
> <LI>
> <P>La fonction USL PIC est une licence d’abonnement mensuel, mensuelle, nécessaire pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !. Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent qui n’est pas renouvelé.</P>
> <LI>
> <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes via la messagerie instantanée et la voix.</P></LI></UL>



</div>

Cette classe de fédération nécessite les considérations de planification suivantes :

  - Les utilisateurs de Windows Live Messenger peuvent utiliser la communication audio/vidéo d’égal à égal avec les utilisateurs de Lync Server 2013, en plus de la messagerie instantanée. Vos serveurs Edge doivent répondre à des exigences spécifiques en matière de port et de protocole. Pour plus d’informations, reportez-vous à [la rubrique determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - La messagerie instantanée Yahoo n’a pas de configuration spécifique, à l’exception de celles généralement utilisées dans la planification et le déploiement du serveur Edge standard qui fournit la Fédération.

  - Pour America Online, le certificat de serveur Edge attribué au service Edge d’accès a une utilisation améliorée de la clé (EKU) par le client.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé des certificats-connectivité de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Résumé des ports-connectivité de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [Résumé des enregistrements DNS-connectivité de messagerie instantanée publique dans Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

