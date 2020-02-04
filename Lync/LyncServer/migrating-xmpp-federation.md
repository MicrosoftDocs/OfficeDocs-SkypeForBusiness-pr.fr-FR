---
title: Migration de la fédération XMPP
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
ms.openlocfilehash: 3b72dabd60ea42a84fcf9b15d1d739bc063ddf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migration de la fédération XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Les versions précédentes de Lync Server et d’Office Communications Server ont fourni une passerelle XMPP (extensible Messaging and Presence Protocol) qui pouvait être déployée en tant que rôle de serveur distinct pour permettre la Fédération avec des déploiements de XMPP. Dans Lync Server 2013, la fonctionnalité XMPP peut être déployée en tant que fonctionnalité. La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge Lync Server 2013 et la passerelle XMPP qui s’exécute sur le serveur frontal 2013 Lync Server.

Du point de vue de la migration, vous pouvez déplacer un compte d’utilisateur Lync Server vers un pool Lync Server 2013 et continuer à utiliser la passerelle XMPP héritée. Ce n’est possible que lorsque le partenaire fédéré de XMPP n’est pas configuré dans Lync Server 2013.

En résumé, si Lync Server 2010 a été déployé à l’aide d’Office Communications Server 2007 R2 XMPP Gateway et XMPP Federation pour les utilisateurs hérités de Lync Server 2010, vous pouvez migrer la Fédération XMPP vers Lync Server 2013 :

1.  Déploiement d’un pool Lync Server 2013.

2.  Déploiement d’un serveur Edge Lync Server 2013.

3.  Déplacer tous les utilisateurs vers le pool Lync Server 2013

4.  Créez des stratégies d’accès XMPP et des certificats pour le serveur de périphérie.

5.  Activez la Fédération XMPP dans Lync Server 2013. 

6.  Mettez à jour les entrées DNS de façon à ce qu’elle pointe vers la passerelle XMPP Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

