---
title: 'Lync Server 2013 : nouvelles fonctionnalités pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43df9901b7bac37bb812eeb00c54537151496eb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534311"
---
# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Nouvelles fonctionnalités pour l’accès des utilisateurs externes dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-17_

Lync Server 2013 introduit de nouvelles fonctionnalités qui étendent les fonctionnalités et les méthodes de communication pour vos utilisateurs. De plus, Lync Server 2013 introduit les modifications apportées aux services existants afin d’améliorer l’intégration et l’extension des services disponibles pour votre organisation. Vous trouverez ci-dessous un résumé des modifications susceptibles d’avoir un impact sur la planification et le déploiement des services de serveur Edge Lync Server 2013.

  - **Prise en charge de l’adressage IPv6**     Lync Server 2013 prend en charge l’adressage IPv6 pour tous les services de serveur Edge. Si vous avez fourni des adresses IPv6 pour les interfaces par le biais de la configuration dans Windows Server, vous pouvez utiliser des adresses IPv6 dans votre configuration de serveur Edge par le biais de la configuration d’adresse IP dans le générateur de topologie.
    
    <div>
    

    > [!IMPORTANT]  
    > L’utilisation d’adresses IPv6 dans Lync Server 2013 dépend de la prise en charge D’ipv6 dans les routeurs et les pare-feu déployés par votre organisation, ainsi que de la prise en charge par le biais de votre fournisseur de services Internet.

    
    </div>

  - **Protocole XMPP (extensible Messaging and Presence Protocol)**     Lync Server 2013 introduit un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP déployée sur vos serveurs frontaux. Vous pouvez déployer Fédération XMPP comme un composant facultatif. L’ajout et la configuration du proxy XMPP et de la passerelle XMPP permettent à vos utilisateurs Microsoft Lync 2013 d’ajouter des contacts à partir de partenaires XMPP pour la messagerie instantanée et la présence.
    
    <div>
    

    > [!NOTE]  
    > Actuellement, les services XMPP de Lync Server 2013 fournissent uniquement la messagerie instantanée et la présence entre les clients Lync et les contacts XMPP.

    
    </div>

  - **Services de mobilité pour les clients mobiles**     Introduit dans une mise à jour client pour Lync Server 2010, les services de mobilité dans Lync Server 2013 autorisent les clients mobiles Microsoft Lync sur les téléphones mobiles et les tablettes utilisant des appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. En outre, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, telles que cliquer pour participer à une conférence, appeler via le bureau, atteindre un seul numéro, messagerie vocale et notification d’appel en absence.
    
    <div>
    

    > [!NOTE]  
    > Les services de mobilité utilisent le proxy inverse et les services publiés qui sont déployés sur vos serveurs frontaux. Il est inutile d’apporter des modifications aux serveurs Edge.

    
    </div>

  - **Les directeurs sont facultatifs**     Le rôle du serveur directeur dans la topologie Lync Server 2013 n’a pas changé. Il héberge toujours des services Web, pré-authentifie les demandes des utilisateurs entrantes et dirige les utilisateurs externes vers leur pool d’accueil. Le fait de changer le directeur d’un rôle recommandé en un rôle facultatif ne diminue pas la valeur du directeur, mais met en évidence la réduction du nombre de serveurs et d’autres exigences matérielles (par exemple, les programmes d’équilibrage de la charge matérielle pour les directeurs) sans compromettre les fonctionnalités et les fonctionnalités. Étant donné que les serveurs frontaux peuvent effectuer le même travail que le directeur sans impact sur les services fournis, vous pouvez éventuellement déployer des directeurs si vous le souhaitez. Vous pouvez en toute sécurité exclure le directeur en toute confiance que les serveurs frontaux fourniront les mêmes services à leur place.

<div>

## <a name="see-also"></a>Voir aussi


[Planification et configuration D’ipv6 dans Lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Planification de la Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

