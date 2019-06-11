---
title: 'Lync Server 2013 : Configuration de votre environnement pour le portail web d’administration de Lync Room System'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ef7596e65c44f871da8c26a0526a389dde72a45
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-05-22_

Pour utiliser le portail Web d’administration LRS (Lync Room System), vous devez installer ou configurer les éléments requis suivants.

<div>


> [!IMPORTANT]  
> Si le serveur est configuré à l’aide de l’authentification Kerberos et NTLM et qu’LRS s’exécute sur un ordinateur qui n’est pas joint au domaine, l’authentification Kerberos échoue et l’utilisateur ne verra pas l’état de LRS dans le portail d’administration. Pour résoudre ce problème, configurez le serveur à l’aide de l’authentification NTLM ou de l’authentification NTLM et TLS-DSK (sans Kerberos), ou joignez l’ordinateur LRS au domaine.



</div>

1.  Installez les mises à jour cumulatives de Lync Server 2013: juillet 2013 dans la topologie du serveur Lync.
    
    Pour obtenir la mise à jour ou découvrir ce qu’elle contient, voir [mises à jour de Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Créez un utilisateur Active Directory activé pour SIP.
    
    Le portail Web d’administration LRS utilise ces informations d’identification pour interroger les informations de Lync Server. Le nom d’utilisateur recommandé est LRSApp.

3.  Créez un groupe de sécurité Active Directory nommé LRSSupportAdminGroup.
    
    Créez le groupe avec une étendue globale et le type Sécurité. Les utilisateurs activés pour SIP ajoutés à ce groupe seront autorisés à afficher la liste des pièces et à exécuter certaines commandes, telles que la collecte de journaux.

4.  Créez un groupe de sécurité Active Directory nommé LRSFullAccessAdminGroup. 
    
    Pour pouvoir utiliser la fonctionnalité de portail d’administration, vous pouvez créer le groupe avec l’étendue du groupe en tant que type global et de groupe.
    
     
    
    ![Liste de groupes d’administrateurs avec le rôle groupe de sécurité] (images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Liste de groupes d’administrateurs avec le rôle groupe de sécurité")  
    
     

5.  Ajoutez LRSFullAccessAdminGroup en tant que membre de LRSSupportAdminGroup.
    
    ![Page membres de propriété LRSSupportAdminGroup] (images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Page membres de propriété LRSSupportAdminGroup")  
    
     

6.  Créez un utilisateur Active Directory activé pour SIP avec le nom LRSSupport. Ajoutez cet utilisateur au groupe LRSSupportAdminGroup.
    
    ![Page membres de propriété LRSSupportAdminGroup] (images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Page membres de propriété LRSSupportAdminGroup")  
    
     

7.  Installez ASP.NET MVC 4 pour Visual Studio 2010 SP1 et Visual Web Developer 2010 SP1, disponible dans le centre de téléchargement [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)Microsoft à l’adresse.

</div>

<span> </span>

</div>

</div>

</div>

