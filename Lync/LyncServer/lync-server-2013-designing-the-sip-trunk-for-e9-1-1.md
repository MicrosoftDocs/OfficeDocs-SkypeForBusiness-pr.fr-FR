---
title: 'Lync Server 2013 : conception de la jonction SIP pour E9-1-1'
description: 'Lync Server 2013 : conception de la jonction SIP pour E9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ced3c92cb14739367c4e54da933a536cb66deb08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542600"
---
# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>Conception de la jonction SIP pour E9-1-1 dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Lync Server utilise des jonctions SIP pour connecter un appel d’urgence au fournisseur de services E9-1-1. Vous pouvez configurer des jonctions SIP de services d’urgence pour le service E9-1-1 au niveau d’un site central, de plusieurs sites centraux ou de chaque site de succursale. Toutefois, si la liaison de réseau étendu (WAN) entre le site de l’appelant et le site qui héberge la jonction SIP de service d’urgence n’est pas disponible, tout appel passé par un utilisateur au niveau du site déconnecté nécessitera un enregistrement d’utilisation téléphonique spécifique dans la stratégie de voix de l’utilisateur qui acheminera l’appel au centre d’intervention en cas d’appels d’urgence via la passerelle PSTN. Il en va de même si les limites relatives aux appels simultanés du service Contrôle d’admission des appels sont appliquées.

<div>


> [!NOTE]  
> Il existe deux façons d’implémenter une jonction SIP dans un environnement Lync Server : 
> <UL>
> <LI>
> <P>Utilisez des serveurs de médiation multirésidents qui utilisent leurs interfaces routées publiquement vers l’extérieur pour communiquer avec le fournisseur de jonctions SIP.</P>
> <LI>
> <P>Utilisez un contrôleur de frontière de session (SBC) local pour fournir un point de démarcation sécurisé entre les serveurs de médiation et les services du fournisseur de jonctions SIP.</P></LI></UL>Si vous choisissez cette dernière méthode, assurez-vous que la marque et le modèle du contrôleur SBC que vous choisissez ont été certifiés et que celui-ci prend en charge le transfert des données d’emplacement PIDF-LO (Presence Information Data Format Location Object) dans le cadre de sa requête SIP INVITE. Dans le cas contraire, les appels arrivent au fournisseur de services d’urgence sans leurs informations d’emplacement. Pour plus d’informations sur les contrôleurs SBC certifiés, voir « infrastructure Qualified for Microsoft Lync » à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A> .<BR>Les fournisseurs de services E9-1-1 vous permettent d’accéder à une paire de contrôleurs SBC à des fins de redondance. Vous devez prendre plusieurs décisions concernant la topologie du serveur de médiation et la configuration du routage des appels. Allez-vous traiter les deux contrôleurs SBC comme des homologues égaux et utiliser le routage par tourniquet (round robin) pour les appels qu’ils s’échangent, ou allez-vous désigner l’un des contrôleurs SBC en tant que serveur principal et l’autre en tant que serveur secondaire ?



</div>

Pour plus d’informations sur le déploiement d’une jonction SIP dans Lync Server, voir [comment implémenter la jonction SIP dans Lync server 2013 ?](lync-server-2013-how-do-i-implement-sip-trunking.md). Pour faciliter le déploiement de jonctions SIP pour E9-1-1, répondez d’abord aux questions suivantes.

  - **Devez-vous déployer la jonction SIP sur une connexion en bail dédiée ou une connexion Internet partagée ?**  
    Il est important que les appels d’urgence se connectent en permanence. Une ligne dédiée fournit une connexion qui n’est pas préemptée par un autre trafic réseau. En outre, elle permet d’implémenter la qualité de service (QoS). N’oubliez pas que si vous vous connectez à des fournisseurs de services d’urgence via le réseau Internet public et si vous devez garantir la confidentialité des appels d’urgence, un chiffrement IPsec est nécessaire.

<!-- end list -->

  - **Votre déploiement E9-1-1 est-il conçu pour la tolérance aux catastrophes ?**  
    Puisqu’il s’agit d’une solution d’urgence, la résilience est importante. Déployez vos serveurs de médiation principaux et secondaires et les jonctions SIP dans des emplacements tolérants aux sinistres. Il est recommandé de déployer votre serveur de médiation le plus proche des utilisateurs pris en charge et d’acheminer les appels de basculement via le serveur de médiation secondaire (situé dans un autre emplacement géographique).

<!-- end list -->

  - **Devez-vous déployer une jonction SIP distincte pour chaque succursale ?**  
    Lync Server offre plusieurs stratégies de gestion de la résistance des communications vocales dans les succursales, notamment : les réseaux de données résistants, le déploiement d’une jonction SIP au niveau de chaque succursale ou le transfert d’appels vers la passerelle locale pendant les pannes. Pour plus d’informations, reportez-vous à la rubrique [Branch site SIP Trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **Le contrôle d’admission des appels (CAC) est-il activé ?**  
    Lync Server ne gère pas les appels d’urgence de la même manière qu’un appel ordinaire. Pour cette raison, la gestion de la bande passante ou le service Contrôle d’admission des appels peut avoir un impact négatif sur une configuration E9-1-1. Les appels d’urgence sont bloqués ou acheminés vers la passerelle PSTN locale si un service Contrôle d’admission des appels est activé et si la limite configurée est dépassée sur une liaison où les appels d’urgence sont acheminés. Comme indiqué précédemment dans cette rubrique, ce type d’appel ne dispose pas de données d’emplacement et doit être acheminé manuellement vers le centre d’intervention en cas d’appels d’urgence.

</div>

<span> </span>

</div>

</div>

</div>

