---
title: Planification de la Fédération XMPP (extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4308bd09d571c41349ed9362affa220cf9723e3a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526531"
---
# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Planification de la Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Les versions précédentes de Lync Server et Office Communications Server ont fourni une passerelle XMPP (extensible Messaging and Presence Protocol) qui pourrait être déployée en tant que rôle serveur distinct afin d’autoriser la Fédération avec des déploiements XMPP. Dans Microsoft Lync Server 2013, la fonctionnalité XMPP peut être déployée sous la forme d’une fonctionnalité. La fonctionnalité XMPP est installée en deux parties : un proxy XMPP qui s’exécute sur le serveur Edge et la passerelle XMPP qui s’exécute sur les serveurs frontaux.

Le déploiement et la configuration de XMPP sont abordés dans le déploiement de l' [accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) vous prévoyez de prendre en charge XMPP dans votre organisation en définissant des règles de port et de protocole sur votre pare-feu, la configuration des certificats et l’ajout d’enregistrements DNS. Les rubriques suivantes de cette section résument les informations dont vous aurez besoin pour planifier la Fédération XMPP pour votre déploiement.

<div>


> [!IMPORTANT]
> La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé des certificats-Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Résumé des ports-Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Résumé des enregistrements DNS-Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration de la Fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés XMPP dans Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[Gérer les partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))  
[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))  
[Get-applet csxmppgatewayconfiguration ne](https://technet.microsoft.com/library/JJ204869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

