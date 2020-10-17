---
title: 'Lync Server 2013 : configuration de votre environnement pour le portail Web d’administration de Lync Room System'
description: 'Lync Server 2013 : configuration de votre environnement pour le portail Web d’administration de Lync Room System.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c942e1db799a7336a3eafb5571e82584694ddbf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542200"
---
# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Configuration de votre environnement Lync Server 2013 pour le portail Web d’administration de Lync Room System

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-22_

Pour utiliser le portail Web d’administration de Lync Room System (LRS), vous devez installer ou configurer les éléments prérequis suivants.

<div>


> [!IMPORTANT]  
> Si le serveur est configuré avec l’authentification Kerberos et NTLM et que LRS est en cours d’exécution sur un ordinateur qui n’est pas lié au domaine, l’authentification Kerberos échoue et l’utilisateur ne voit pas l’état de LRS dans le portail d’administration. Pour résoudre ce problème, configurez le serveur avec l’authentification NTLM ou l’authentification NTLM et TLS-DSK (sans Kerberos) ou associez l’ordinateur LRS au domaine.



</div>

1.  Installez les mises à jour cumulatives de Lync Server 2013 : juillet 2013 dans la topologie Lync Server.
    
    Pour obtenir la mise à jour ou voir ce qu’elle contient, consultez la rubrique [mises à jour pour Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Créez un utilisateur Active Directory compatible SIP.
    
    Le portail Web d’administration LRS utilise ces informations d’identification pour demander des informations à Lync Server. Le nom d’utilisateur recommandé est LRSApp.

3.  Créez un groupe de sécurité Active Directory avec le nom LRSSupportAdminGroup.
    
    Créez le groupe avec une étendue de groupe globale et de type de groupe comme sécurité. Les utilisateurs à extension SIP qui sont ajoutés à ce groupe seront autorisés à afficher la liste des salles et à exécuter certaines commandes, telles que la collecte des journaux.

4.  Créez un groupe de sécurité Active Directory avec le nom LRSFullAccessAdminGroup.
    
    Créez le groupe avec une étendue de groupe comme global et un type de groupe pour les utilisateurs activés pour la sécurité. SIP qui sont ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration.
    
     
    
    ![Liste des groupes d’administration avec le rôle de groupe de sécurité](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Liste des groupes d’administration avec le rôle de groupe de sécurité")  
    
     

5.  Ajoutez LRSFullAccessAdminGroup en tant que membre de LRSSupportAdminGroup.
    
    ![Page des membres de propriétés LRSSupportAdminGroup](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Page des membres de propriétés LRSSupportAdminGroup")  
    
     

6.  Créez un utilisateur Active Directory activé pour SIP avec le nom LRSSupport. Ajoutez cet utilisateur à LRSSupportAdminGroup.
    
    ![Page des membres de propriétés LRSSupportAdminGroup](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Page des membres de propriétés LRSSupportAdminGroup")  
    
     

7.  Installez ASP.NET MVC 4 pour Visual Studio 2010 SP1 et Visual Web Developer 2010 SP1, disponible dans le centre de téléchargement Microsoft à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967) .

</div>

<span> </span>

</div>

</div>

</div>

