---
title: Migration de la fédération XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9764554cf9984ceb35878b87032194a51aec3b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migration de la fédération XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-16_

Les versions précédentes d’Office Communications Server ont fourni une passerelle XMPP (extensible Messaging and Presence Protocol) qui pouvait être déployée en tant que rôle de serveur distinct pour permettre la Fédération avec des déploiements de XMPP. Dans Lync Server 2013, la fonctionnalité XMPP peut être déployée en tant que fonctionnalité. La fonctionnalité XMPP est installée en deux parties: en tant que proxy XMPP qui s’exécute sur le serveur Edge Lync Server 2013 et la passerelle XMPP qui s’exécute sur le serveur frontal 2013 Lync Server.

Du point de vue de la migration, un compte d’utilisateur Office Communications Server 2007 R2 peut être déplacé vers un pool Lync Server 2013 et continuer à utiliser la passerelle Office Communications Server 2007 R2 XMPP. Ce n’est possible que lorsque le partenaire fédéré de XMPP n’est pas configuré dans Lync Server 2013.

En résumé, si Office Communications Server a été déployé avec Office Communications Server 2007 R2 XMPP Gateway et XMPP Federation pour les utilisateurs antérieurs à Office Communications Server 2007 R2, vous pouvez migrer la Fédération XMPP vers Lync Server 2013:

1.  Déploiement d’un pool Lync Server 2013.

2.  Déploiement d’un serveur Edge Lync Server 2013.

3.  Déplacer tous les utilisateurs vers le pool Lync Server 2013.

4.  Créez des stratégies d’accès XMPP et des certificats pour le serveur de périphérie.

5.  Activez la Fédération XMPP dans Lync Server 2013. 

6.  Mettez à jour les entrées DNS de façon à ce qu’elle pointe vers la passerelle XMPP Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

