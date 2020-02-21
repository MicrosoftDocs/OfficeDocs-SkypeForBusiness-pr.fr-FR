---
title: Migration de la Fédération XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61a48c579ed9afa3f1a09ed1c3a7129e9e24924d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migration de la Fédération XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Les versions précédentes de Lync Server et Office Communications Server ont fourni une passerelle XMPP (extensible Messaging and Presence Protocol) qui pourrait être déployée en tant que rôle serveur distinct afin d’autoriser la Fédération avec des déploiements XMPP. Dans Lync Server 2013, la fonctionnalité XMPP peut être déployée sous la forme d’une fonctionnalité. La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge Lync Server 2013 et la passerelle XMPP qui s’exécute sur le serveur frontal Lync Server 2013.

Du point de vue de la migration, un compte d’utilisateur Lync Server peut être déplacé vers un pool Lync Server 2013 et continuer à utiliser la passerelle XMPP héritée. Cela n’est possible que si le partenaire fédéré XMPP n’est pas configuré dans Lync Server 2013.

En résumé, si Lync Server 2010 a été déployé avec la passerelle XMPP et la passerelle XMPP Office Communications Server 2007 R2, la Fédération XMPP a été activée pour les utilisateurs hérités de Lync Server 2010, pour migrer la Fédération XMPP vers Lync Server 2013 :

1.  Déployez un pool Lync Server 2013.

2.  Déployez un serveur Edge Lync Server 2013.

3.  Déplacer tous les utilisateurs vers le pool Lync Server 2013

4.  Créez les certificats et stratégies d’accès XMPP appropriés pour le serveur Edge.

5.  Activez la Fédération XMPP dans Lync Server 2013. 

6.  Mettez à jour les entrées DNS de sorte qu’elles pointent vers la passerelle XMPP Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

