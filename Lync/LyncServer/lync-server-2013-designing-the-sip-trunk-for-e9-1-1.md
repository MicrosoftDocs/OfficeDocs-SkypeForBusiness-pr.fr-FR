---
title: 'Lync Server 2013: conception du Trunk SIP pour E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bee3985efd3510b62bfe43b3aa5742f63679093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>Designing the SIP Trunk pour E9-1-1 dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-03_

Lync Server utilise des lignes SIP pour connecter un appel d’urgence au fournisseur de services E9-1-1. Vous pouvez configurer des jonctions SIP de services d’urgence pour le service E9-1-1 au niveau d’un site central, de plusieurs sites centraux ou de chaque site de succursale. Cependant, si la liaison de réseau étendu (WAN) entre le site de l’appelant et le site qui héberge la jonction SIP de service d’urgence n’est pas disponible, tout appel passé par un utilisateur au niveau du site déconnecté nécessitera un enregistrement d’utilisation téléphonique spécifique dans la stratégie de voix de l’utilisateur qui acheminera l’appel au centre d’intervention en cas d’appels d’urgence via la passerelle RTC. Il en va de même si les limites relatives aux appels simultanés du service Contrôle d’admission des appels sont appliquées.

<div>


> [!NOTE]  
> Il existe deux façons d’implémenter une ligne SIP dans un environnement serveur Lync: 
> <UL>
> <LI>
> <P>Utiliser des serveurs de médiation multi-résidents qui utilisent leurs interfaces routées vers l’extérieur pour communiquer avec le fournisseur de Trunks SIP.</P>
> <LI>
> <P>Utilisez un contrôleur de bordure de session (SBC) local pour fournir un point de délimitation sécurisé entre les serveurs de médiation et les services du fournisseur de Trunks SIP.</P></LI></UL>Si vous choisissez cette dernière méthode, assurez-vous que la marque et le modèle du contrôleur SBC que vous choisissez ont été certifiés et que celui-ci prend en charge le transfert des données d’emplacement PIDF-LO (Presence Information Data Format Location Object) dans le cadre de sa requête SIP INVITE. Dans le cas contraire, les appels parviennent au fournisseur de services d’urgence sans leurs informations d’emplacement. Pour plus d’informations sur la certification SBCs, voir la section «infrastructure qualifie <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>pour Microsoft Lync» à l’adresse.<BR>Les fournisseurs de services E9-1-1 vous permettent d’accéder à une paire de contrôleurs SBC à des fins de redondance. Vous devez prendre plusieurs décisions concernant la topologie du serveur de médiation et la configuration de l’acheminement des appels. Allez-vous traiter les deux contrôleurs SBC comme des homologues égaux et utiliser le routage par tourniquet (round robin) pour les appels qu’ils s’échangent, ou allez-vous désigner l’un des contrôleurs SBC en tant que serveur principal et l’autre en tant que serveur secondaire ?



</div>

Pour plus d’informations sur le déploiement d’une connexion SIP dans Lync Server, voir [comment implémenter le trunking SIP dans Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md). Pour faciliter le déploiement de jonctions SIP pour E9-1-1, répondez d’abord aux questions suivantes.

  - **Devez-vous déployer la jonction SIP sur une connexion en bail dédiée ou une connexion Internet partagée ?**  
    Il est important que les appels d’urgence se connectent en permanence. Une ligne dédiée fournit une connexion qui n’est pas préemptée par un autre trafic réseau. En outre, elle permet d’implémenter la qualité de service (QoS). N’oubliez pas que si vous vous connectez à des fournisseurs de services d’urgence via le réseau Internet public et si vous devez garantir la confidentialité des appels d’urgence, un chiffrement IPsec est nécessaire.

<!-- end list -->

  - **Votre déploiement E9-1-1 est-il conçu pour la tolérance au désastre?**  
    Puisqu’il s’agit d’une solution d’urgence, la résistance est importante. Déployez vos serveurs de médiation principaux et secondaires et les Trunks SIP dans les emplacements tolérants aux sinistres. Il peut s’avérer utile de déployer votre serveur de médiation principal le plus proche des utilisateurs qu’il prend en charge, et d’acheminer les appels de basculement par le biais du serveur de médiation secondaire (situé dans un autre emplacement géographique).

<!-- end list -->

  - **Devez-vous déployer une jonction SIP (Session Initiation Protocol) distincte pour chaque succursale ?**  
    Lync Server offre plusieurs stratégies de gestion de la résilience vocale dans les succursales, notamment: utilisation de réseaux de données résilients, déploiement d’une ligne SIP dans chaque succursale ou transfert d’appels vers la passerelle locale au cours des pannes. Pour plus d’informations, voir [trunking SIP site dans Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **Le contrôle d’admission des appels est-il activé ?**  
    Lync Server ne gère pas les appels d’urgence de la même manière que les appels ordinaires. Pour cette raison, la gestion de la bande passante ou le service Contrôle d’admission des appels peut avoir un impact négatif sur une configuration E9-1-1. Les appels d’urgence sont bloqués ou acheminés vers la passerelle RTC locale si un service Contrôle d’admission des appels est activé et si la limite configurée est dépassée sur une liaison où les appels d’urgence sont acheminés. Comme indiqué précédemment dans cette rubrique, ce type d’appel ne dispose pas de données d’emplacement et doit être acheminé manuellement vers le centre d’intervention en cas d’appels d’urgence.

</div>

<span> </span>

</div>

</div>

</div>

