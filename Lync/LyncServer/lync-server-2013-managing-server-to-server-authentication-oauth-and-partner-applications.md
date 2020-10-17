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
ms.openlocfilehash: 2bea847e1d0c4d9c42808a93f3c56bcd7391bece
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507161"
---
# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-05-14_

Microsoft Lync Server 2013 doit être en mesure de communiquer de manière sécurisée avec d’autres applications et produits serveurs. Par exemple, vous pouvez configurer Lync Server 2013 de manière à ce que les données de contact et/ou les données d’archivage soient stockées dans Microsoft Exchange Server 2013 ; Toutefois, cette opération ne peut être réalisée que si Lync Server et Exchange sont en mesure de communiquer de manière sécurisée. De même, vous pouvez planifier une conférence Lync Server à partir de Microsoft SharePoint Server. Cependant, cette opération ne peut être réalisée que si les deux serveurs (SharePoint et Lync Server) s’approuvent mutuellement. Bien qu’il soit possible d’utiliser un mécanisme d’authentification pour la communication Lync à Exchange et un mécanisme distinct pour la communication Lync à SharePoint, une approche plus efficace consiste à utiliser une méthode standardisée pour l’authentification et l’autorisation de serveur à serveur.

L’utilisation d’une méthode standardisée unique pour l’authentification de serveur à serveur est l’approche adoptée par Lync Server 2013. Pour la version 2013, Lync Server 2013 (ainsi que d’autres produits serveur Microsoft, y compris Exchange 2013 et Microsoft SharePoint Server) prennent en charge le protocole OAuth (Open Authorization) pour l’authentification et l’autorisation de serveur à serveur. Avec OAuth, un protocole d’autorisation standard utilisé par un certain nombre de sites principaux, les informations d’identification de l’utilisateur et les mots de passe ne sont pas transmis d’un ordinateur à un autre. Au lieu de cela, l’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité ; Ces jetons accordent l’accès à un ensemble spécifique de ressources pour une durée spécifique.

L’authentification OAuth implique généralement trois parties : un serveur d’autorisation unique et les deux domaines qui doivent communiquer les uns avec les autres. (Vous pouvez également effectuer l’authentification de serveur à serveur sans utiliser de serveur d’autorisation, un processus qui sera abordé plus loin dans ce document.) Les jetons de sécurité sont émis par le serveur d’autorisation (également appelé serveur de jetons de sécurité) pour les deux domaines qui doivent communiquer ; Ces jetons vérifient que les communications provenant d’un domaine doivent être approuvées par l’autre domaine. Par exemple, le serveur d’autorisation peut émettre des jetons qui vérifient que les utilisateurs d’un domaine Lync Server 2013 spécifique sont en mesure d’accéder à un domaine Exchange 2013 spécifié, et inversement.

<div>


> [!NOTE]
> Un domaine est tout simplement un conteneur de sécurité. Par défaut, Lync Server 2013 utilise votre domaine SIP par défaut comme domaine OAuth. Des espaces de noms SIP supplémentaires sont ajoutés à la liste autre nom de l’objet dans le certificat OAuth.



</div>

Lync Server 2013 prend en charge trois scénarios d’authentification de serveur à serveur. Avec Lync Server 2013, vous pouvez :

  - Configurez l’authentification de serveur à serveur entre une installation locale de Lync Server 2013 et une installation locale d’Exchange 2013 et/ou de Microsoft SharePoint Server.

  - Configurez l’authentification de serveur à serveur entre une paire de composants Microsoft 365 (par exemple, entre Microsoft Exchange et Microsoft Lync Server, ou entre Microsoft Lync Server et Microsoft SharePoint).

  - Configurez l’authentification de serveur à serveur dans un environnement intersite (c’est-à-dire, l’authentification de serveur à serveur entre un serveur local et un composant Microsoft 365).

Notez que, à ce stade, seuls Exchange 2013, SharePoint Server et Lync Server 2013 prennent en charge l’authentification de serveur à serveur ; Si vous n’exécutez pas l’un de ces serveurs, vous ne serez pas en mesure d’implémenter entièrement l’authentification OAuth.

Il est également important de noter que vous n’avez pas besoin d’utiliser l’authentification de serveur à serveur : l’authentification de serveur à serveur n’est pas nécessaire pour déployer Lync Server 2013. Si Lync Server 2013 n’a pas besoin de communiquer avec d’autres serveurs (par exemple, Exchange 2013), l’authentification de serveur à serveur n’est pas nécessaire.

Toutefois, l’authentification de serveur à serveur est requise si vous voulez utiliser certaines des nouvelles fonctionnalités de Lync Server, telles que le magasin de contacts unifié. Avec le magasin de contacts unifié, les informations de contact de Lync Server 2013 sont stockées dans Exchange 2013 et non dans Lync Server ; Cela permet aux utilisateurs de disposer d’un seul ensemble de contacts directement accessible à partir de Lync, de Microsoft Outlook ou de Microsoft Outlook Web Access. Étant donné que le magasin de contacts unifié nécessite que Lync Server 2013 partage des informations avec Exchange 2013, vous devez utiliser l’authentification de serveur à serveur pour déployer la fonctionnalité. L’authentification de serveur à serveur est également requise si vous choisissez d’utiliser l’archivage Exchange, dans lequel les transcriptions des sessions de messagerie instantanée sont enregistrées en tant qu’e-mails Exchange 2013 et non en tant qu’enregistrements de base de données individuels.

Pour que la version Microsoft 365 de Lync Server communique avec son homologue Exchange, Lync Server 2013 doit d’abord obtenir un jeton de sécurité à partir du serveur d’autorisation. Lync Server utilise ensuite ce jeton de sécurité pour s’identifier auprès d’Exchange. La version 365 de Microsoft Exchange doit suivre le même processus afin de communiquer avec Lync Server 2013.

Toutefois, en ce qui concerne l’authentification de serveur à serveur entre deux serveurs Microsoft, il n’y a aucun besoin d’utiliser un serveur de jetons tiers. Les produits serveur tels que Lync Server 2013 et Exchange 2013 disposent d’un serveur de jetons intégré qui peut être utilisé à des fins d’authentification avec d’autres serveurs Microsoft (par exemple, SharePoint Server) qui prennent en charge l’authentification de serveur à serveur. Par exemple, Lync Server 2013 peut émettre et signer un jeton de sécurité par lui-même, puis utiliser ce jeton pour communiquer avec Exchange 2013. Dans un cas comme celui-ci, aucun serveur de jeton tiers n'est nécessaire.

Pour configurer l’authentification de serveur à serveur pour une implémentation locale de Lync Server 2013, vous devez effectuer les deux opérations suivantes :

  - Assigner un certificat à l’émetteur de jetons intégré à Lync Server.

  - Configurez le serveur avec lequel Lync Server 2013 doit communiquer en tant qu’application partenaire. Par exemple, si Lync Server 2013 doit communiquer avec Exchange 2013, vous devrez configurer Exchange en tant qu’application partenaire.

<div>


> [!NOTE]
> Une application partenaire est une application avec laquelle Lync Server 2013 peut directement échanger des jetons de sécurité, sans avoir à passer par un serveur de jetons de sécurité tiers.



</div>

Notez que OAuth est un élément essentiel du produit et qu’il ne peut pas être désactivé ou supprimé.

<div>

## <a name="see-also"></a>Voir aussi


[Affectation d’un certificat d’authentification de serveur à serveur à Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Configuration de Microsoft Lync Server 2013 dans un environnement intersite](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

