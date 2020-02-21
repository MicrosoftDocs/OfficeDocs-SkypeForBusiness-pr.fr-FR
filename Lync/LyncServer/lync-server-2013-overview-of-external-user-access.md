---
title: 'Lync Server 2013 : vue d’ensemble de l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdf596a16fbed1cab1b622b373febb0f173344cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Vue d’ensemble de l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Dans cette documentation, nous utilisons le terme *utilisateur externe* pour définir une grande catégorie d’utilisateurs qui communiquent avec vos utilisateurs lync Server 2013 et Lync 2013 depuis l’extérieur du pare-feu. Les utilisateurs externes que vous pouvez autoriser pour communiquer Lync Server 2013 avec des utilisateurs internes (c’est-à-dire, les utilisateurs qui se connectent à Lync Server à l’intérieur du pare-feu) peuvent inclure les éléments suivants :

  - **Utilisateurs distants**   utilisateurs de votre organisation qui se connectent à Lync Server depuis l’extérieur du pare-feu.

  - **Utilisateurs fédérés**   utilisateurs disposant d’un compte avec une organisation client ou partenaire approuvée, comme Lync Server 2010, Lync Server 2013 ou Office Communications Server 2007 R2. Les utilisateurs fédérés peuvent également être membres des organisations partenaires définies à l’aide du protocole XMPP (extensible Messaging and Presence Protocol) via le proxy XMPP sur le serveur Edge et la passerelle XMPP sur le serveur ou le pool frontal. Une relation d’approbation définie, appelée Fédération, n’est ni liée ni dépendante d’une relation d’approbation des services de domaine Active Directory.
    
    <div>
    

    > [!NOTE]  
    > Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.

    
    </div>

  - **Les utilisateurs**   de la connectivité de messagerie instantanée publique contactent vos utilisateurs par le biais des services de connectivité de messagerie instantanée publique (Windows Live, Yahoo\! et AOL).

  - **Utilisateurs mobiles les**   utilisateurs qui sont membres de votre organisation qui utilisent un téléphone intelligent ou une tablette exécutant un client Lync mobile peuvent se connecter à votre déploiement interne et être en mesure de communiquer avec les autres classes d’utilisateurs. L’utilisateur mobile utilise des services de mobilité publiés via le proxy inverse pour accéder au déploiement interne. Pour plus d’informations sur les fonctionnalités disponibles pour Lync mobile, consultez les tableaux de comparaison des [https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777)clients mobiles à l’adresse.

  - **Utilisateurs anonymes**   utilisateurs qui n’ont pas de compte d’utilisateur dans les services de domaine Active Directory de votre organisation ou dans un domaine fédéré pris en charge, mais qui ont reçu des invitations à participer à distance à une conférence sur site.

Votre déploiement Edge fournit un accès externe aux types de communication suivants :

  - **La messagerie instantanée et la présence**   les utilisateurs externes autorisés peuvent participer à des conversations et conférences de messagerie instantanée, et ils peuvent obtenir des informations sur l’état de présence d’un autre. Les utilisateurs de fournisseurs de services de messagerie instantanée publics peuvent participer à des conversations par messagerie instantanée avec des utilisateurs de Lync Server individuels dans votre organisation et accéder aux informations de présence, mais ils ne peuvent pas participer à des conférences de messagerie instantanée à l’aide de Lync Server. Il s’agit d’une communication d’égal à égal. Le transfert de fichiers n’est pas pris en charge pour les utilisateurs de fournisseurs de services de messagerie instantanée publics, et les communications d’égal à égal sont prises en charge pour les utilisateurs de Windows Messenger 2011, mais pas pour les autres utilisateurs de fournisseurs de services de messagerie instantanée publics.
    
    Les protocoles SIP et XMPP sont pris en charge. Pour fournir des services pour XMPP, reportez-vous à la rubrique [Planning for SIP, XMPP Federation et public Instant Messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - **Conférence Web les**   utilisateurs externes autorisés peuvent participer à des conférences hébergées sur votre déploiement Lync Server. Les utilisateurs distants, les utilisateurs fédérés et les utilisateurs anonymes peuvent être activés pour la participation à la conférence Web, mais les utilisateurs de messagerie instantanée publique ne peuvent pas participer à des conférences. En fonction des options que vous sélectionnez, les utilisateurs activés pour la conférence Web peuvent participer au partage de bureau et d’applications et peuvent agir comme des organisateurs de réunions ou des présentateurs.

  - **Conférence A/V**   les utilisateurs externes autorisés peuvent participer à des conférences audio et vidéo que votre déploiement Lync Server héberge. L’audio/vidéo dans les communications P2P est prise en charge pour les utilisateurs de Windows Messenger 2011, mais pas pour les autres utilisateurs de fournisseurs de services de messagerie instantanée publics.

Afin de contrôler les communications, vous pouvez configurer une ou plusieurs stratégies qui définissent la façon dont les utilisateurs internes et externes à votre organisation communiquent les uns avec les autres. Vous pouvez également configurer des paramètres et appliquer des stratégies pour des utilisateurs internes individuels ou pour des types spécifiques d’utilisateurs externes afin de contrôler les communications avec des utilisateurs externes.

Rôles Lync Server 2013 utilisés pour fournir un accès externe :

**Serveur Edge le**   serveur Edge est un serveur ou un pool de serveurs qui exécutent les services qui permettent l’accès externe aux services de messagerie instantanée et de présence, de conférence, audio/vidéo et autres médias (par exemple, transfert de fichiers). Vous pouvez également configurer le serveur Edge pour qu’il se fédérer avec d’autres déploiements Lync Server ou Office Communications Server 2007 R2, ainsi que d’autres déploiements XMPP. La fonctionnalité optionnelle de connectivité PIC (Public IM Connectivity) est activée et configurée via le serveur Edge.

**Directeur**   le directeur est un serveur ou un pool de serveurs facultatif exécutant le rôle directeur Lync Server 2013 qui pré-authentifie les demandes de l’utilisateur et achemine les demandes au serveur frontal ou au pool frontal des utilisateurs, mais il n’héberge aucun compte d’utilisateur.

**Proxy inverse un**   proxy inverse est un terme général pour les serveurs spécialisés qui publient des ressources disponibles sur le réseau interne et récupèrent des informations pour les clients à partir de la ressource publiée. Lync Server 2013 utilise le proxy inverse pour publier un certain nombre de fonctionnalités, telles que des réunions de conférence, des emplacements de participation à des conférences, le carnet d’adresses, l’expansion de la liste de distribution, le téléchargement de contenu de réunion, les mises à jour de périphériques, les services de mobilité, et bien plus encore. Tout proxy inverse pouvant répondre à la configuration requise pour la publication des emplacements de ressources nécessaires peut être utilisé. Microsoft Forefront Threat Management Gateway (TMG) 2010 est utilisé à titre d’exemple pour illustrer les règles de publication nécessaires, mais Forefront TMG 2010 n’est pas obligatoire.

<div>


> [!IMPORTANT]  
> Lync Server 2013 prend en charge IPv4 et IPv6. Windows Server&nbsp;2008&nbsp;r2, Windows Server 2012 et Windows Server 2012 R2 utilisent une double pile pouvant utiliser IPv4 et IPv6 simultanément. Ceci est important en raison de la nature transitoire d’un déploiement passant de IPv4 à IPv6. IPv4 peut être pris en charge dans certaines zones, où le protocole IPv6 peut être utilisé dans d’autres zones du déploiement. Ceci est particulièrement important pour les déploiements Internet et internes. Les clients externes doivent communiquer via le proxy inverse pour utiliser des services tels que la mobilité, les réunions, le téléchargement de carnet d’adresses et d’autres. Actuellement, Forefront Threat Management Gateway 2010 et Internet Security and Acceleration Server 2006 ne prennent pas en charge l’adressage IPv6, quelle que soit la version du système d’exploitation sur lequel elles sont déployées. Vous devez planifier en conséquence pour votre utilisation de IPv6 et D’ipv4, car ils sont liés à des clients externes.



</div>

</div>

<span> </span>

</div>

</div>

</div>

