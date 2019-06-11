---
title: 'Lync Server 2013 : Nouvelles fonctionnalités liées à l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d365c4e32c5eaebbd0368cd85b41be7886a59df
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Nouvelles fonctionnalités liées à l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-17_

Lync Server 2013 introduit de nouvelles fonctionnalités qui étendent les fonctionnalités et méthodes de communication pour vos utilisateurs. Par ailleurs, Lync Server 2013 introduit des modifications apportées aux services existants pour améliorer l’intégration et l’extension des services disponibles pour votre organisation. Vous trouverez ci-dessous un résumé des modifications qui peuvent affecter votre planification et le déploiement de Lync Server 2013 Edge Server services.

  - **Prise en charge de l’adressage**   IPv6 Lync Server 2013 prend en charge l’adressage IPv6 pour tous les services Edge Server. Si vous avez fourni des adresses IPv6 pour les interfaces via une configuration dans Windows Server, vous pouvez utiliser des adresses IPv6 dans votre configuration de serveur Edge via la configuration d’adresse IP dans le générateur de topologie.
    
    <div>
    

    > [!IMPORTANT]  
    > L’utilisation des adresses IPv6 dans Lync Server 2013 dépend de la prise en charge du protocole IPv6 dans les routeurs et pare-feu déployés par votre organisation, ainsi que de la prise en charge par le biais de votre fournisseur d’accès à Internet.

    
    </div>

  - **Le protocole XMPP (extensible Messaging and Presence Protocol)**   Lync Server 2013 introduit un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP déployée sur vos serveurs frontaux. Vous pouvez déployer la Fédération XMPP en tant que composant facultatif. L’ajout et la configuration du proxy XMPP et de la passerelle XMPP permettent aux utilisateurs de Microsoft Lync 2013 d’ajouter des contacts des partenaires de XMPP pour la messagerie instantanée et la présence.
    
    <div>
    

    > [!NOTE]  
    > Pour l’instant, les services XMPP dans Lync Server 2013 ne fournissent que la messagerie instantanée et la présence entre les clients Lync et les contacts de type XMPP.

    
    </div>

  - **Services de mobilité pour les clients**   mobiles introduits dans une mise à jour de clients pour Lync Server 2010, les services de mobilité dans Lync Server 2013 permettent aux clients mobiles Microsoft Lync sur les téléphones mobiles et les tablettes utilisant Apple iOS, Android, Windows pris en charge. Des appareils mobiles téléphone ou Nokia pour effectuer des opérations telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. De plus, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, par exemple, cliquer pour participer à une conférence, appeler par le biais de votre bureau, joindre un numéro de téléphone unique et envoyer une notification d’appel manqué.
    
    <div>
    

    > [!NOTE]  
    > Les services de mobilité utilisent le proxy inverse et les services publiés déployés sur vos serveurs frontaux. Aucune modification n’est requise sur les serveurs de périphérie.

    
    </div>

  - **Les directeurs sont un rôle**   facultatif que le rôle du serveur directeur dans la topologie Lync Server 2013 n’a pas changé. Il héberge toujours les services Web, pré-authentifie les demandes des utilisateurs entrantes, et redirige les utilisateurs externes vers leur liste de ressources personnelles. Le fait de changer le directeur d’un rôle recommandé en un rôle facultatif n’a pas pour effet de réduire la valeur du directeur, mais souligne le nombre de serveurs et autres exigences matérielles (par exemple, les équilibreurs de charge matérielle pour le directeur), sans fonctionnalités et fonctionnalités inprometes. Étant donné que les serveurs front-end peuvent faire la même chose que le directeur sans avoir d’impact sur les services fournis, vous pouvez éventuellement déployer des directeurs si vous le souhaitez. Vous pouvez exclure en toute sécurité le directeur en ayant confiance aux serveurs frontaux pour fournir les mêmes services à leur emplacement.

<div>

## <a name="see-also"></a>Voir aussi


[Planification et configuration du protocole IPv6 dans Lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Planification de la Fédération des protocoles de messagerie et de présence extensibles dans Lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

