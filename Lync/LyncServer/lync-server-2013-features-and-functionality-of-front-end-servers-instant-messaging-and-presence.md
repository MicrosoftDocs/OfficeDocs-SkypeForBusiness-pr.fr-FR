---
title: 'Lync Server 2013 : fonctionnalités des serveurs frontaux, de la messagerie instantanée et de la présence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8e25a74dcffe76f16b12a8c80f8ad8f980370dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Fonctionnalités des serveurs frontaux, de la messagerie instantanée et de la présence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-17_

Les serveurs frontaux fournissent la plupart des fonctionnalités Lync Server. Deux éditions sont disponibles : Lync Server Enterprise Edition, conçu principalement pour les grandes organisations et Lync Server Standard Edition, conçu principalement pour les organisations de petite taille qui souhaitent un investissement matériel réduit et ne sont pas Exigez une haute disponibilité. Les deux éditions prennent en charge toutes les charges de travail Lync Server, y compris la messagerie instantanée, la présence, les conférences et voix entreprise.

La messagerie instantanée permet aux utilisateurs de communiquer en temps réel les uns avec les autres sur leurs ordinateurs à l’aide des messages textuels.. Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge. Un participant à une conversation de messagerie instantanée peut ajouter un troisième participant à la conversation à tout moment. Lorsque cela arrive, la fenêtre Conversation change pour prendre en charge des fonctionnalités de conférence.

<div>


> [!IMPORTANT]
> Les clients Lync et Communicator impliqués dans une communication une vers une, sont souvent appelés P2P (peer-to-peer). Techniquement, les deux clients communiquent dans une conversation une à une, avec l’unité de contrôle multipoint de messagerie instantanée (IMMCU) au milieu. Le IMMCU est un composant de serveur frontal. La mise en place du IMMCU dans le flux de travail de communication requis permet l’enregistrement des détails des appels et d’autres fonctionnalités activées par le serveur frontal. La communication provient d’un port source dynamique sur le client vers le port de serveur frontal TLS/TCP/5061 (en supposant l’utilisation de la sécurité de la couche de transport recommandée). Par conception, la communication P2P (ainsi que la messagerie instantanée multipartie) n’est possible que lorsque Lync Server et le IMMCU sont actifs et disponibles.



</div>

La *présence* fournit aux utilisateurs des informations sur l’état de présence des autres utilisateurs sur le réseau. Le statut de présence d’un utilisateur fournit des informations pour permettre aux autres utilisateurs de décider s’ils doivent essayer de contacter l’utilisateur et s’ils doivent pour cela utiliser la messagerie instantanée, le téléphone ou la messagerie électronique. La présence permet une communication instantanée lorsque cela est possible, mais fournit aussi des informations indiquant si un utilisateur est en réunion ou hors du bureau, indiquant que la communication instantanée n’est pas possible. Cet état de présence est affiché sous la forme d’une icône de présence dans Lync et d’autres applications prenant en charge la présence, y compris le client de messagerie et de collaboration Microsoft Outlook, les technologies Microsoft SharePoint, Microsoft Word et la feuille de calcul Microsoft Excel application. L’icône de présence indique la disponibilité actuelle de l’utilisateur et sa volonté à communiquer.

</div>

<span> </span>

</div>

</div>

</div>

