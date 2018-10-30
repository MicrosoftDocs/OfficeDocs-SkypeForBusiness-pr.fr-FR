---
title: 'Lync Server 2013 : Vue d’ensemble de l’accès des utilisateurs'
TOCTitle: Vue d’ensemble de l’accès des utilisateurs
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398775(v=OCS.15)
ms:contentKeyID: 49298201
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble de l’accès des utilisateurs externes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Dans cette documentation, nous utilisons le terme *utilisateur externe* pour désigner une catégorie étendue d’utilisateurs qui communiquent avec vos utilisateurs Lync Server 2013 et Lync 2013 en dehors du pare-feu. Parmi les utilisateurs externes que vous pouvez autoriser à communiquer avec des utilisateurs internes Lync Server 2013 (à savoir, des utilisateurs qui se connectent à Lync Server depuis le pare-feu) figurent :

  - **Utilisateurs distants**   Utilisateurs de votre organisation qui se connectent à Lync Server à l’extérieur du pare-feu.

  - **Utilisateurs fédérés**   Utilisateurs disposant d’un compte auprès d’une organisation partenaire ou d’un client approuvé, tel que Lync Server 2010, Lync Server 2013 ou Office Communications Server 2007 R2. Les utilisateurs fédérés peuvent aussi être membres d’organisations partenaires définies utilisant le protocole XMPP (Extensible Messaging and Presence Protocol) par le biais du proxy XMPP sur le serveur Edge et de la passerelle XMPP sur le pool ou serveur frontal. Une relation d’approbation définie, appelée fédération, n’est ni liée ni dépendante d’une relation d’approbation des services de domaine Active Directory.
    
    > [!NOTE]  
    > Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo!. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.

  - **Utilisateurs de connectivité de messagerie instantanée publique**   Contacts établis par vos utilisateurs par le biais de services de connectivité de messagerie instantanée publics (Windows Live, Yahoo\! et AOL).

  - **Utilisateurs mobiles**   Les utilisateurs membres de votre organisation qui utilisent un téléphone de type smartphone ou une tablette exécutant un client Lync Mobile se connectent à votre déploiement interne et sont en mesure de communiquer avec d’autres classes d’utilisateurs. L’utilisateur mobile utilise les services de mobilité publiés par le biais du proxy inverse pour accéder au déploiement interne. Pour plus d’informations sur les fonctionnalités disponibles dans Lync Mobile, reportez-vous aux tableaux de comparaison de clients mobiles à l’adresse [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777).

  - **Utilisateurs anonymes**   Utilisateurs qui ne disposent pas d’un compte d’utilisateur dans les services de domaine Active Directory de l’organisation ou dans un domaine fédéré pris en charge, mais qui peuvent être invités à participer à distance à une conférence sur site.

Votre déploiement Edge fournit un accès externe pour les types de communication suivants :

  - **Messagerie instantanée et présence**   Des utilisateurs externes autorisés peuvent participer à des conversations et des conférences par messagerie instantanée et obtenir des informations sur le statut de présence d’une personne. Les utilisateurs de services de messagerie instantanée publics et les utilisateurs fédérés peuvent participer à des conversations de messagerie instantanée avec des utilisateurs de Lync Server de votre organisation et accéder aux informations de présence, mais ils ne peuvent pas participer à des conférences de groupe par messagerie instantanée à l’aide de Lync Server. Il s’agit à proprement parler de communications P2P. Le transfert de fichiers n’est pas pris en charge pour les utilisateurs de services de messagerie instantanée publics et les communications P2P avec audio/vidéo ne sont pas prises en charge pour les utilisateurs Windows Messenger 2011, ce qui n’est pas le cas des autres utilisateurs de services de messagerie instantanée publics.
    
    Les protocoles SIP et XMPP sont tous deux pris en charge. Pour fournir des services pour le protocole XMPP, reportez-vous à [Planification pour la fédération SIP, la fédération XMPP et la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - **Conférence web**   Des utilisateurs externes autorisés peuvent participer à des conférences hébergées sur votre déploiement de Lync Server. Les utilisateurs distants, fédérés et anonymes peuvent être autorisés à participer à une conférence web, ce qui n’est pas le cas des utilisateurs de messagerie instantanée publique. Selon les options choisies, les utilisateurs autorisés à participer à une conférence web peuvent participer au partage de Bureau et d’application. Ils peuvent également agir en tant qu’organisateurs ou présentateurs de réunions.

  - **Conférence A/V**   Les utilisateurs externes autorisés peuvent participer à des conférences audio et vidéo hébergées par votre déploiement de Lync Server. L’audio/vidéo dans les communications P2P est prise en charge pour les utilisateurs de Windows Messenger 2011, mais pas pour les autres utilisateurs de fournisseurs de services de messagerie instantanée publics.

Pour contrôler les communications vous pouvez configurer une ou plusieurs stratégies qui définissent le mode de communication entre les utilisateurs situés à l’intérieur et à l’extérieur de votre organisation. Vous pouvez également configurer des paramètres et appliquer des stratégies pour des utilisateurs internes individuels ou pour des types spécifiques d’utilisateurs externes afin de contrôler les communications avec les utilisateurs externes.

Rôles Lync Server 2013 utilisés pour fournir un accès externe :

**Serveur Edge**   Le serveur Edge est un serveur ou un pool de serveurs qui exécute les services qui autorisent l’accès externe à la messagerie instantanée et à la présence, ainsi qu’aux services de conférence, d’audio/vidéo et autres services multimédias (par exemple, le transfert de fichiers). Si vous le souhaitez, vous pouvez configurer le serveur Edge de façon à se fédérer avec d’autres déploiements de Lync Server ou Office Communications Server 2007 R2, et avec d’autres déploiements XMPP. L’activation et la configuration de la fonctionnalité de connectivité de messagerie instantanée publique facultative s’effectue par le biais du serveur Edge.

**Directeur**   Le directeur est un serveur ou pool de serveurs facultatif exécutant le rôle  directeurLync Server 2013 qui pré-authentifie les demandes utilisateur et achemine les demandes vers le serveur frontal ou pool de serveurs frontaux de démarrage des utilisateurs, mais n’héberge aucun compte d’utilisateur.

**Proxy inverse**   Proxy inverse est un terme généralisé pour les serveurs spécialisés qui publient des ressources disponibles sur le réseau interne et extraient des informations pour les clients à partir de la ressource publiée. Lync Server 2013 utilise le proxy inverse pour publier plusieurs fonctionnalités, telles que les réunions de conférence, les emplacements de connexion aux conférences, le carnet d’adresses, l’extension des listes de distribution, le téléchargement de contenu de réunion, les mises à jour de périphériques, les services de mobilité et bien d’autres encore. Tout proxy inverse pouvant répondre aux exigences de publication des emplacements de ressources nécessaires peut être utilisé. Microsoft Forefront Threat Management Gateway (TMG) 2010 est utilisé comme exemple afin d’illustrer les règles de publication nécessaires, mais il n’est pas obligatoire.

> [!IMPORTANT]  
> Lync Server 2013 prend en charge les protocoles IPv4 et IPv6. Windows Server 2008 R2, Windows Server 2012 et Windows Server 2012 R2 utilisent une double pile capable d’utiliser simultanément les protocoles IPv4 et IPv6. Cela est important en raison de la nature transitionnelle d’un déploiement basculant d’IPv4 à IPv6. Le protocole IPv4 peut être pris en charge dans certaines zones, tandis que dans d’autres zones du déploiement, le protocole IPv6 peut être utilisé. Cela revêt une importance particulière pour les déploiements internes et Internet. Les clients externes doivent communiquer par le biais du proxy inverse pour utiliser des services tels que la mobilité, les réunions, le téléchargement de carnet d’adresses et autres. Actuellement, Forefront Threat Management Gateway 2010 et Internet Security and Acceleration Server 2006 ne prennent pas en charge l’adressage IPv6, quelle que soit la version de système d’exploitation sur laquelle ils sont déployés. Vous devez planifier en conséquence l’utilisation des protocoles IPv6 et IPv4 en fonction des clients externes.
