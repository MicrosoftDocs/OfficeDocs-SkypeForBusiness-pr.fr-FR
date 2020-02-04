---
title: Gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01de2856b8923fff76cf33dda7d7e6ba21889c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Gestion des applications d’authentification de serveur à serveur (OAuth) et de partenaire dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-05-14_

Microsoft Lync Server 2013 doit être en mesure de communiquer en toute sécurité avec d’autres applications et produits serveur. Par exemple, vous pouvez configurer Lync Server 2013 de manière à ce que les données de contact et/ou les données d’archivage soient stockées dans Microsoft Exchange Server 2013. Toutefois, cela ne peut être fait que si Lync Server et Exchange sont en mesure de communiquer de façon sécurisée. De même, vous pouvez planifier une conférence Lync Server à partir de Microsoft SharePoint Server ; Toutefois, cela ne peut être fait que si les deux serveurs (SharePoint et Lync Server) approuvent les uns les autres. Même s’il est possible d’utiliser un mécanisme d’authentification pour la communication Lync-to-Exchange et un mécanisme distinct pour la communication entre Lync et SharePoint, il est préférable d’utiliser une méthode normalisée pour tous les serveurs à serveur. authentification et autorisation.

L’utilisation d’une méthode normalisée unique pour l’authentification de serveur à serveur est l’approche adoptée par Lync Server 2013. Pour la version 2013, Lync Server 2013 (ainsi que d’autres produits Microsoft Server, y compris Exchange 2013 et Microsoft SharePoint Server) prennent en charge le protocole OAuth (Open Authorization) pour l’authentification et l’autorisation de serveur à serveur. Avec OAuth, un protocole d’autorisation standard utilisé par un certain nombre de sites Web importants, les informations d’identification d’utilisateur et les mots de passe ne sont pas transmis d’un ordinateur à un autre. Au lieu de cela, l’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité. Ces jetons octroient l’accès à un ensemble spécifique de ressources pour un certain temps.

L’authentification OAuth implique généralement trois parties : un seul serveur d’autorisation et les deux domaines qui doivent communiquer entre eux. (Vous pouvez également effectuer une authentification serveur à serveur sans recourir à un serveur d’autorisation, un processus qui sera abordé plus loin dans ce document.) Les jetons de sécurité sont émis par le serveur d’autorisation (également connu sous le nom de serveur de jetons de sécurité) pour les deux domaines qui doivent communiquer. Ces jetons vérifient que les communications provenant d’un domaine doivent être approuvées par l’autre domaine. Par exemple, le serveur d’autorisation peut émettre des jetons qui vérifient que les utilisateurs d’un domaine Lync Server 2013 spécifique sont en mesure d’accéder à un domaine Exchange 2013 spécifié, et inversement.

<div>


> [!NOTE]
> Un domaine est tout simplement un conteneur de sécurité. Par défaut, Lync Server 2013 utilise votre domaine SIP par défaut comme domaine OAuth. Des espaces de noms SIP supplémentaires sont ajoutés à la liste Autre nom du sujet du certificat dans le certificat OAuth.



</div>

Lync Server 2013 prend en charge trois scénarios d’authentification de serveur à serveur. Avec Lync Server 2013, vous pouvez :

  - Configurer l’authentification de serveur à serveur entre une installation locale de Lync Server 2013 et une installation locale d’Exchange 2013 et/ou Microsoft SharePoint Server.

  - Configurer l’authentification de serveur à serveur entre deux composants 365 d’Office (par exemple, entre Microsoft Exchange et Microsoft Lync Server ou entre Microsoft Lync Server et Microsoft SharePoint).

  - Configurer l’authentification de serveur à serveur dans un environnement local (c’est-à-dire, l’authentification de serveur à serveur entre un serveur local et un composant Office 365).

Notez que, à ce stade, seuls Exchange 2013, SharePoint Server et Lync Server 2013 prennent en charge l’authentification de serveur à serveur. Si vous n’utilisez pas l’un de ces serveurs, vous ne serez pas en mesure de mettre entièrement en œuvre l’authentification OAuth.

Il est également important de noter que vous n’avez pas besoin d’utiliser l’authentification de serveur à serveur : l’authentification serveur à serveur n’est pas nécessaire pour déployer Lync Server 2013. Si Lync Server 2013 n’a pas besoin de communiquer avec d’autres serveurs (par exemple, Exchange 2013), l’authentification de serveur à serveur n’est pas nécessaire.

Toutefois, l’authentification serveur à serveur est requise si vous voulez utiliser certaines des nouvelles fonctionnalités de Lync Server, comme le « magasin de contacts unifié ». Le magasin de contacts unifié, les informations de contact de Lync Server 2013 sont stockées dans Exchange 2013 au lieu de Lync Server. Cela permet aux utilisateurs de disposer d’un ensemble unique de contacts facilement accessible à partir de Lync, Microsoft Outlook ou Microsoft Outlook Web Access. Dans la mesure où le magasin de contacts unifié nécessite Lync Server 2013 pour partager des informations avec Exchange 2013, vous devez utiliser l’authentification de serveur à serveur pour déployer la fonctionnalité. L’authentification de serveur à serveur est également nécessaire si vous choisissez d’utiliser l’archivage Exchange, dans lequel les transcriptions de sessions de messagerie instantanée sont enregistrées en tant que messages électroniques Exchange 2013 plutôt que les enregistrements de base de données individuels.

Pour la version 365 d’Office de Lync Server permettant de communiquer avec son équivalent Exchange, Lync Server 2013 doit d’abord obtenir un jeton de sécurité du serveur d’autorisation. Lync Server utilise alors ce jeton de sécurité pour s’identifier auprès d’Exchange. La version 365 Office d’Exchange doit suivre le même processus pour communiquer avec Lync Server 2013.

Toutefois, en ce qui concerne l’authentification de serveur à serveur entre deux serveurs Microsoft, il n’est pas nécessaire d’utiliser un serveur de jetons tiers. Les produits serveur tels que Lync Server 2013 et Exchange 2013 disposent d’un serveur à jetons intégré qui peut être utilisé à des fins d’authentification avec d’autres serveurs Microsoft (par exemple, SharePoint Server) qui prennent en charge l’authentification de serveur à serveur. Par exemple, Lync Server 2013 peut émettre et signer un jeton de sécurité en soi, puis utiliser ce jeton pour communiquer avec Exchange 2013. Dans ce cas, aucun serveur de jetons tiers n’est nécessaire.

Pour configurer l’authentification de serveur à serveur pour une implémentation locale de Lync Server 2013, vous devez effectuer deux opérations :

  - Affectez un certificat à l’émetteur de jeton intégré de Lync Server.

  - Configurez le serveur avec lequel Lync Server 2013 communiquera en tant que « application partenaire ». Par exemple, si Lync Server 2013 doit communiquer avec Exchange 2013, vous devez configurer Exchange en tant qu’application partenaire.

<div>


> [!NOTE]
> Une « application partenaire » est une application sur laquelle Lync Server 2013 peut directement échanger des jetons de sécurité, sans avoir à passer par un serveur de jetons de sécurité tiers.



</div>

Notez qu’OAuth est un composant de base du produit et ne peut être ni désactivé ni supprimé.

<div>

## <a name="see-also"></a>Voir aussi


[Attribution d’un certificat d’authentification de serveur à serveur à Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Configuration de Microsoft Lync Server 2013 dans un environnement local](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

