---
title: "Gest. de l’auth. serv. à serv. (Oauth) et des app. partenaires dans LS 2013"
TOCtitle: "Gest. de l’auth. serv. à serv. (Oauth) et des app. partenaires dans LS 2013"
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204817(v=OCS.15)
ms:contentKeyID: 49296883
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion de l’authentification serveur à serveur (Oauth) et des applications partenaires dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-05-14_

Microsoft Lync Server 2013 doit être capable communiquer en toute sécurité et transparence avec d’autres applications et serveurs. Par exemple, vous pouvez configurer Lync Server 2013 de sorte que les données de contact et/ou les données d’archivage soient stockées dans Microsoft Exchange Server 2013. Toutefois, cela n’est possible que si Lync Server et Exchange peuvent communiquer de manière sécurisée l’un avec l’autre. De la même manière, vous pouvez planifier une conférence Lync Server dans Microsoft SharePoint Server. Une fois encore, cela n’est possible que si les deux serveurs (SharePoint et Lync Server) s’approuvent l’un l’autre. Même s’il est possible d’utiliser un mécanisme d’authentification pour la communication de Lync vers Exchange et un autre mécanisme pour la communication de Lync vers SharePoint, la meilleure approche et la plus efficace est d’utiliser une méthode normalisée pour tous les mécanismes d’authentification et d’autorisation de serveur à serveur.

L’utilisation d’une méthode unique et normalisée pour l’authentification de serveur à serveur est l’approche adoptée par Lync Server 2013. Pour la version 2013, Lync Server 2013 (ainsi que d’autres produits Microsoft Server, y compris Exchange 2013 et Microsoft SharePoint Server) prennent en charge le protocole OAuth (Open Authorization) pour l’authentification et l’autorisation de serveur à serveur. OAuth est un protocole d’autorisation standard utilisé par un certain nombre de sites web majeurs, avec lequel les informations d’identification et le mot de passe de l’utilisateur ne sont pas transmis d’un ordinateur à l’autre. En réalité l’authentification et l’autorisation reposent sur l’échange de jetons de sécurité. Ces jetons accordent l’accès à un ensemble spécifique de ressources sur une période définie.

L’authentification OAuth implique généralement trois parties : un serveur d’autorisation unique et deux domaines devant communiquer l’un avec l’autre. (Vous pouvez aussi avoir une authentification serveur à serveur sans serveur d’autorisation, ce processus sera abordé plus loin dans ce document). Les jetons de sécurité sont émis par le serveur d’autorisation (aussi connu comme serveur de jetons de sécurité) vers les deux domaines qui doivent communiquer. Ces jetons vérifient que les communications provenant de l’un des domaines peuvent être approuvées par l’autre domaine. Par exemple, le serveur d’autorisation peut émettre des jetons qui vérifient que les utilisateurs d’un domaine Lync Server 2013 spécifique sont en mesure d’accéder à un domaine Exchange 2013 spécifié, et vice versa.

> [!NOTE]  
> Un domaine est tout simplement un conteneur de sécurité. Par défaut, Lync Server 2013 utilise votre domaine SIP par défaut en tant que domaine OAuth.

Lync Server 2013 prend en charge trois scénarios d’authentification de serveur à serveur. Avec Lync Server 2013 vous pouvez effectuer ce qui suit :

  - Configurer l’authentification de serveur à serveur entre des installations locales de Lync Server 2013 et de Exchange 2013, et/ou Microsoft SharePoint Server.

  - Configurer l’authentification de serveur à serveur entre une paire de composants Office 365 (par exemple, entre Microsoft Exchange et Microsoft Lync Server, ou entre Microsoft Lync Server et Microsoft SharePoint).

  - Configurer l’authentification de serveur à serveur dans un environnement intersite (c’est-à-dire une authentification de serveur à serveur entre un serveur local et un composant Office 365).

Notez que, à l’heure actuelle, seuls Exchange 2013, SharePoint Server et Lync Server 2013 prennent en charge l’authentification de serveur à serveur. Si vous n’exécutez pas l’un de ces serveurs, vous ne pourrez pas pleinement implémenter l’authentification OAuth.

Notez également que vous n’avez pas besoin d’utiliser l’authentification de serveur à serveur : elle n’est pas nécessaire pour le déploiement de Lync Server 2013. Si Lync Server 2013 n’a pas besoin de communiquer avec d’autres serveurs (tels que Exchange 2013), l’authentification de serveur à serveur n’est pas nécessaire.

Toutefois, l’authentification de serveur à serveur est nécessaire si vous voulez utiliser certaines nouvelles fonctionnalités de Lync Server, comme le « magasin de contacts unifié ». Ce dernier permet de stocker les informations de contact de Lync Server 2013 dans Exchange 2013 plutôt que dans Lync Server. Les utilisateurs n’ont plus qu’un seul ensemble de contacts facilement accessible dans Lync, Microsoft Outlook ou Microsoft Outlook Web Access. Le magasin de contacts unifié ayant besoin de Lync Server 2013 pour partager des informations avec Exchange 2013, vous devez utiliser l’authentification de serveur à serveur pour déployer la fonctionnalité. Cette authentification est également nécessaire si vous choisissez d’utiliser l’archivage Exchange, dans lequel les transcriptions des sessions de messagerie instantanées sont enregistrées en tant que messages électroniques Exchange 2013 et non en tant qu’enregistrements de base de données individuels.

Pour que la version Office 365 de Lync Server communique avec son homologue Exchange, Lync Server 2013 doit d’abord obtenir un jeton de sécurité du serveur d’autorisation. Lync Server utilise ensuite ce jeton de sécurité pour s’identifier auprès d’Exchange. La version Office 365 de Exchange doit suivre le même processus pour pouvoir communiquer avec Lync Server 2013.

Toutefois, en ce qui concerne l’authentification de serveur à serveur entre deux serveurs Microsoft, il n’y a aucun besoin d’utiliser un serveur de jetons tiers. Les serveurs tels que Lync Server 2013 et Exchange 2013 disposent d’un serveur de jetons intégré qui peut être utilisé à des fins d’authentification avec d’autres serveurs Microsoft (comme un serveur SharePoint) prenant en charge l’authentification de serveur à serveur. Par exemple, Lync Server 2013 peut émettre et signer lui-même un jeton de sécurité, puis l’utiliser pour communiquer avec Exchange 2013. Dans ce cas, nul besoin de compter sur un serveur de jetons tiers.

Pour configurer l’authentification de serveur à serveur pour une implémentation locale de Lync Server 2013, vous devez effectuer les deux actions suivantes :

  - Assigner un certificat à l’émetteur de jetons intégré à Lync Server.

  - Configurer le serveur avec lequel Lync Server 2013 va communiquer en tant qu’« application partenaire ». Par exemple, si Lync Server 2013 doit communiquer avec Exchange 2013, vous devez configurer Exchange en tant qu’application partenaire.

> [!NOTE]  
> Une « application partenaire » est une application avec laquelle Lync Server 2013 peut directement échanger les jetons de sécurité, sans passer par un serveur de jetons de sécurité tiers.

Notez que OAuth est un composant de base du produit et ne peut être ni désactivé ni retiré.

## Voir aussi

#### Concepts

[Attribution d’un certificat d’authentification de serveur à serveur à Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Configuration de Microsoft Lync Server 2013 dans un environnement intersites](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)

