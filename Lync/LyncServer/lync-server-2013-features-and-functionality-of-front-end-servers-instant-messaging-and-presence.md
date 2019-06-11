---
title: 'Lync Server 2013 : Fonctionnalités de serveurs frontaux, de messagerie instantanée et de présence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739825eed3c8a3ba8239849e0c17c449180a2d95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Fonctionnalités de serveurs frontaux, de messagerie instantanée et de présence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-17_

Les serveurs front-end fournissent la plupart des fonctionnalités de Lync Server. Il existe deux éditions disponibles: Lync Server Enterprise Edition, principalement conçu pour les grandes organisations et Lync Server Standard Edition, conçu essentiellement pour les petites organisations qui souhaitent investir plus en ressources matérielles et ne pas Exigez une haute disponibilité. Les deux éditions prennent en charge toutes les charges de travail du serveur Lync, notamment la messagerie instantanée, la présence, les conférences et l’voix entreprise.

La messagerie instantanée permet aux utilisateurs de communiquer en temps réel les uns avec les autres sur leurs ordinateurs à l’aide des messages textuels. Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge. Un participant à une conversation de messagerie instantanée peut ajouter un troisième participant à la conversation à tout moment. Lorsque cela arrive, la fenêtre Conversation change pour prendre en charge des fonctionnalités de conférence.

<div>


> [!IMPORTANT]
> Les clients Lync et Communicator intervenant dans le cadre d’une communication une à une, sont souvent désignés sous le nom d’égal à égal. Techniquement, les deux clients communiquent en une seule conversation avec l’unité de contrôle multipoint (IMMCU) de messagerie instantanée au milieu. IMMCU est un composant du serveur frontal. Le placement du IMMCU dans le flux de travail de communication requis autorise l’enregistrement des détails des appels et d’autres fonctionnalités que le serveur frontal autorise. La communication provient d’un port source dynamique du client vers le port de serveur frontal TLS/TCP/5061 (en partant du principe que l’utilisation de la sécurité de couche de transport recommandée). Par conception, la communication d’égal à égal (et la messagerie instantanée à plusieurs parties) est possible uniquement lorsque Lync Server et IMMCU est actif et disponible.



</div>

La *présence* fournit des informations aux utilisateurs sur l’état d’autres personnes sur le réseau. Le statut de présence d’un utilisateur fournit des informations pour permettre aux autres utilisateurs de décider s’ils doivent essayer de contacter l’utilisateur et s’ils doivent pour cela utiliser la messagerie instantanée, le téléphone ou la messagerie électronique. La présence permet une communication instantanée lorsque cela est possible, mais fournit aussi des informations indiquant si un utilisateur est en réunion ou hors du bureau, indiquant que la communication instantanée n’est pas possible. Ce statut de présence s’affiche sous la forme d’une icône de présence dans Lync et d’autres applications prenant en charge la présence, dont le client de messagerie et de collaboration Microsoft Outlook, Microsoft SharePoint technologies, Microsoft Word et la feuille de calcul Microsoft Excel. logiciel. L’icône de présence indique la disponibilité actuelle de l’utilisateur et sa volonté à communiquer.

</div>

<span> </span>

</div>

</div>

</div>

