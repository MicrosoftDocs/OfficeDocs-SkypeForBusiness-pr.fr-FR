---
title: Migration de la fédération XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e446a4981a3b9b255311ff5720e2c6dc36d61e9a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migration de la fédération XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-16_

Les versions précédentes d’Office Communications Server proposaient une passerelle XMPP (extensible Messaging and Presence Protocol) qui pourrait être déployée en tant que rôle serveur distinct pour permettre la Fédération avec des déploiements XMPP. Dans Lync Server 2013, la fonctionnalité XMPP peut être déployée sous la forme d’une fonctionnalité. La fonctionnalité XMPP est installée en deux parties : en tant que proxy XMPP qui s’exécute sur le serveur Edge Lync Server 2013 et la passerelle XMPP qui s’exécute sur le serveur frontal Lync Server 2013.

Du point de vue de la migration, un compte d’utilisateur Office Communications Server 2007 R2 peut être déplacé vers un pool Lync Server 2013 et continuer à utiliser la passerelle XMPP Office Communications Server 2007 R2. Cela n’est possible que si le partenaire fédéré XMPP n’est pas configuré dans Lync Server 2013.

En résumé, si Office Communications Server a été déployé avec la passerelle XMPP Office Communications Server 2007 R2 et que la Fédération XMPP a été activée pour les utilisateurs hérités d’Office Communications Server 2007 R2, pour migrer la Fédération XMPP vers Lync Server 2013 :

1.  Déployez un pool Lync Server 2013.

2.  Déployez un serveur Edge Lync Server 2013.

3.  Déplacez tous les utilisateurs vers le pool Lync Server 2013.

4.  Créez les certificats et stratégies d’accès XMPP appropriés pour le serveur Edge.

5.  Activez la Fédération XMPP dans Lync Server 2013. 

6.  Mettez à jour les entrées DNS de sorte qu’elles pointent vers la passerelle XMPP Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

