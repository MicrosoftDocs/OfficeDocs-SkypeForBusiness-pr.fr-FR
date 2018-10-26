---
title: "Lync Server 2013 : Prise en ch. de l’int. d’Exchange Server et de SharePoint"
TOCTitle: Prise en charge de l’intégration d’Exchange Server et de SharePoint
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205005(v=OCS.15)
ms:contentKeyID: 49297710
ms.date: 01/19/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge de l’intégration d’Exchange Server et de SharePoint dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2017-01-18_

Lync Server 2013 et Lync 2013 peuvent communiquer de manière sécurisée et transparente avec d’autres applications et produits serveur, dont Office 2013, Exchange 2013 et SharePoint, si vous intégrez ces produits. L’intégration de Lync Server 2013 et d’Office permet aux utilisateurs d’accéder en contexte aux fonctionnalités de messagerie instantanée, de présence améliorée, de téléphonie et de conférence de Lync. Les utilisateurs Office peuvent accéder aux fonctionnalités Lync à partir du client de messagerie et de collaboration Outlook 2013 et d’autres programmes Office ou à partir d’une page Microsoft SharePoint Server 2010. Ils peuvent également afficher un enregistrement des conversations Lync dans le dossier Historique des conversations Outlook. Intégré à Exchange 2013 ou à Exchange Online, Lync Server 2013 prend également en charge les éléments suivants :

  - magasin de contacts unifié, qui permet aux utilisateurs de stocker toutes les informations de contact dans Exchange 2013 ou Exchange Online afin qu’elles soient disponibles globalement via Lync 2013, Exchange, Outlook et Outlook Web App ;

  - historique des conversations et historique des conférences web, stockés dans des dossiers utilisateur Exchange ;

  - contenu archivé à partir de Lync, comme le contenu de messagerie instantanée et de réunion, pouvant être conservé dans le stockage Exchange.

> [!NOTE]  
> Lync Server 2013 prend en charge l’intégration dans les versions antérieures de Microsoft Exchange Server et SharePoint, mais toutes les fonctionnalités ne sont pas prises en charge dans ces versions antérieures, notamment l’intégration du stockage d’archives dans Microsoft Exchange.<br />
Si vous êtes en train de faire migrer vos utilisateurs vers Exchange 2013, vous pouvez utiliser à la fois le stockage Exchange et le stockage Lync Server de manière provisoire, jusqu’à ce que vous ayez terminé cette migration. L’utilisation définitive du stockage Exchange et Lync Server n’est pas prise en charge.

L’intégration de Lync Server 2013 dans Exchange 2013 et SharePoint Server requiert une authentification de serveur à serveur entre les serveurs qui exécutent Lync Server 2013, Microsoft Exchange Server et SharePoint Server. Lync Server 2013 prend en charge le protocole OAuth (Open Authorization) pour l’authentification de serveur à serveur et l’autorisation. Pour une authentification de serveur à serveur locale entre deux serveurs Microsoft, il n’est pas nécessaire d’utiliser un serveur de jetons tiers. Lync Server 2013, Exchange 2013 et SharePoint comportent un serveur de jetons intégré qui peut servir à des fins d’authentification. Par exemple, Lync Server 2013 peut émettre et signer un jeton de sécurité par lui-même, puis utiliser ce jeton pour communiquer avec Exchange 2013. Le cas échéant, il n’est pas nécessaire d’utiliser un serveur de jetons tiers.

Lync Server 2013 prend en charge les deux scénarios d’authentification de serveur à serveur. Ceux-ci impliquent la configuration de l’authentification de serveur à serveur entre :

  - une installation locale de Lync Server 2013 et une installation locale d’Exchange 2013 et/ou de SharePoint Server ;

  - une paire de composants Office (par exemple, entre Microsoft Exchange 365 et Microsoft Lync Server 365 ou entre Microsoft Lync Server 365 et Microsoft SharePoint 365).

> [!NOTE]  
> L’authentification de serveur à serveur entre un serveur local et un composant Office 365 n’est pas prise en charge dans cette version de Lync Server 2013. Cela signifie, entre autres, que vous ne pouvez pas configurer une authentification de serveur à serveur entre une installation locale de Lync Server 2013 et Microsoft Exchange 365.

Pour plus d’informations sur l’authentification de serveur à serveur, reportez-vous à [Gestion de l’authentification serveur à serveur (Oauth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou la documentation des opérations.

