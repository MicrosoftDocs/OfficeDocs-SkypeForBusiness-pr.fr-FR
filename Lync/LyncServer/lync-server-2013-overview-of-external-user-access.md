---
title: 'Lync Server 2013 : Vue d’ensemble de l’accès des utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a527df5a3bc7b296d17860c7a02876dbc31fbc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Vue d’ensemble de l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-07_

Dans cette documentation, nous utilisons le terme *utilisateur externe* pour définir une grande catégorie d’utilisateurs qui communiquent avec vos utilisateurs de lync Server 2013 et de Lync 2013 en dehors du pare-feu. Les utilisateurs externes qu’il est possible d’autoriser à communiquer Lync Server 2013 avec des utilisateurs internes (c’est-à-dire, les utilisateurs qui se connectent à Lync Server à partir du pare-feu) peuvent inclure les éléments suivants:

  - **Utilisateurs**   distants utilisateurs de votre organisation qui se connectent à Lync Server depuis l’extérieur du pare-feu.

  - **Utilisateurs fédérés utilisateurs**   disposant d’un compte auprès d’une organisation de clients ou de partenaires approuvés, par exemple Lync Server 2010, Lync Server 2013 ou Office Communications Server 2007 R2. Les utilisateurs fédérés peuvent également être membres d’organisations partenaires définies utilisant le protocole XMPP (extensible Messaging and Presence Protocol) par le biais du proxy XMPP du serveur Edge et de la passerelle XMPP du serveur ou du pool frontal. Une relation d’approbation définie, appelée Fédération, n’est pas liée ou ne dépend pas d’une relation d’approbation des services de domaine Active Directory.
    
    <div>
    

    > [!NOTE]  
    > Date de fin de vie du 2014 juin pour AOL et Yahoo! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.

    
    </div>

  - **Connexion publique à la messagerie instantanée utilisateurs**   contacts que vos utilisateurs ont établi par le biais de services de connectivité de messagerie instantanée publics (Windows Live, Yahoo\! et AOL).

  - **Utilisateurs mobiles les**   utilisateurs qui sont membres de votre organisation qui utilisent un smartphone ou une tablette exécutant un client mobile Lync se connectent à votre déploiement interne et sont en mesure de communiquer avec les autres classes d’utilisateurs. L’utilisateur mobile utilise les services de mobilité publiés par le biais du proxy inverse pour accéder au déploiement interne. Pour plus d’informations sur les fonctionnalités disponibles pour Lync mobile, voir les tableaux de comparaison des [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777)clients mobiles à l’adresse.

  - **Utilisateurs anonymes**   utilisateurs qui n’ont pas de compte d’utilisateur dans les services de domaine Active Directory de votre organisation ou qui ont reçu des invitations à distance dans une conférence locale.

Votre déploiement Edge fournit un accès externe pour les types de communication suivants:

  - **Messagerie instantanée et présence**   les utilisateurs externes autorisés peuvent participer aux conversations et conférences par messagerie instantanée, et ils peuvent obtenir des informations sur le statut de présence d’un autre utilisateur. Les utilisateurs de fournisseurs de services de messagerie instantanée publics peuvent participer à des conversations par messagerie instantanée avec des utilisateurs de Lync Server individuels au sein de votre organisation et accéder aux informations de présence, mais ils ne peuvent pas participer à des conférences par messagerie instantanée à l’aide de Lync Server. Ce type de communication est strictement égal à égal. Le transfert de fichiers n’est pas pris en charge pour les utilisateurs de fournisseurs de services de messagerie instantanée publics, et les communications audio/vidéo dans les communications d’égal à égal sont prises en charge pour les utilisateurs Windows Messenger 2011, mais pas pour les autres utilisateurs de fournisseurs de services de messagerie instantanée publics.
    
    Les protocoles SIP et XMPP sont tous deux pris en charge. Pour fournir des services pour XMPP, voir [planification du protocole SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - ****   Les utilisateurs externes autorisés de conférences Web peuvent participer à des conférences hébergées sur votre déploiement de Lync Server. Les utilisateurs distants, les utilisateurs fédérés et les utilisateurs anonymes peuvent être activés pour la participation à des conférences Web, mais les utilisateurs de messagerie instantanée publique ne peuvent pas participer à des conférences. En fonction des options que vous sélectionnez, les utilisateurs activés pour les conférences Web peuvent participer au partage de bureau et d’application et peuvent agir en tant qu’organisateurs ou présentateurs de la réunion.

  - ****   Les utilisateurs externes autorisés de conférence A/V peuvent participer à des conférences audio et vidéo que votre déploiement de Lync Server héberge. L’audio/vidéo dans les communications d’égal à égal est pris en charge pour les utilisateurs Windows Messenger 2011, mais pas pour les autres utilisateurs de fournisseurs de services de messagerie instantanée publics.

Afin de contrôler les communications, vous pouvez configurer une ou plusieurs stratégies qui déterminent la façon dont les utilisateurs internes et externes à votre organisation communiquent entre eux. Vous pouvez également configurer les paramètres et appliquer des stratégies aux utilisateurs internes individuels ou à des types d’utilisateurs externes spécifiques pour contrôler les communications avec les utilisateurs externes.

Rôles Lync Server 2013 utilisés pour fournir un accès externe:

**Serveur Edge le**   serveur Edge est un serveur ou un pool de serveurs qui exécutent les services autorisant l’accès externe à la messagerie instantanée et aux services de présence, de conférence, de contenu audio et vidéo, ainsi que d’autres médias (par exemple, les services de transfert de fichiers). Le cas échéant, vous pouvez configurer le serveur de périphérie pour qu’il se fédérer avec d’autres déploiements Lync Server ou Office Communications Server 2007 R2, ainsi que d’autres déploiements de XMPP. La fonctionnalité de connectivité de messagerie instantanée publique optionnelle est activée et configurée via le serveur Edge.

**Director**   il s’agit d’un serveur ou d’un pool de serveurs facultatif exécutant le rôle directeur du 2013 serveur Lync Server, qui pré-authentifie les demandes des utilisateurs et achemine les demandes au serveur frontal ou au pool frontal des utilisateurs, mais n’a pas de compte d’utilisateur.

**Proxy inverse un**   proxy inverse est un terme général pour les serveurs spécialisés qui publient des ressources disponibles sur le réseau interne et récupèrent les informations relatives aux clients à partir de la ressource publiée. Lync Server 2013 utilise le proxy inverse pour publier un certain nombre de fonctionnalités, telles que les réunions de conférence, les lieux de participation de conférence, le carnet d’adresses, l’extension de la liste de distribution, le téléchargement du contenu de la réunion, les mises à jour de l’appareil, les services de mobilité, etc. Tout proxy inverse susceptible de satisfaire les exigences de publication des emplacements de ressources nécessaires peut être utilisé. Le 2010 de Microsoft Forefront Threat Management Gateway (TMG) est utilisé comme exemple dans le cadre de l’illustration des règles de publication nécessaires, mais qu’il n’est pas nécessaire de Forefront TMG 2010.

<div>


> [!IMPORTANT]  
> Lync Server 2013 prend en charge les protocoles IPv4 et IPv6. Windows Server&nbsp;2008&nbsp;r2, Windows Server 2012 et Windows Server 2012 R2 utilisent une pile double capable d’utiliser simultanément IPv4 et IPv6. C’est important en raison de la nature de la transition d’un déploiement entre IPv4 et IPv6. IPv4 peut être pris en charge dans certains domaines, qui peuvent être utilisés dans d’autres parties du déploiement IPv6. C’est particulièrement important pour les déploiements Internet et interne. Les clients externes doivent communiquer par le biais du proxy inverse pour utiliser les services tels que la mobilité, les réunions, le téléchargement du carnet d’adresses, etc. Pour l’instant, les versions de Forefront Threat Management 2010 et Internet Security et Acceleration Server 2006 ne prennent pas en charge l’adressage IPv6, quelle que soit la version du système d’exploitation sur laquelle elles sont déployées. Vous devez planifier en conséquence en ce qui concerne l’utilisation de IPv6 et D’ipv4 en ce qui concerne les clients externes.



</div>

</div>

<span> </span>

</div>

</div>

</div>

