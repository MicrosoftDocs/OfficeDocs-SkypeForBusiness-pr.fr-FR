---
title: Gérer l’authentification de serveur à serveur (OAuth) et les applications de partenariat dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Résumé: gérez les applications OAuth et Partner dans Skype entreprise Server.'
ms.openlocfilehash: 37c2af8a089bcae4b974761616e1ecd67c9e500b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297567"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gérer l’authentification de serveur à serveur (OAuth) et les applications de partenariat dans Skype entreprise Server
 
**Résumé:** Gestion des applications OAuth et partenaires dans Skype entreprise Server.
  
Skype entreprise Server doit être en mesure de communiquer en toute sécurité avec d’autres applications et des produits serveur. Par exemple, vous pouvez configurer Skype entreprise Server de façon à ce que les données de contact et/ou les données d’archivage soient stockées dans Microsoft Exchange Server 2013. Toutefois, vous ne pouvez effectuer cette opération que si Skype entreprise Server et Exchange sont en mesure de communiquer de façon sécurisée. De même, vous pouvez planifier une conférence Skype entreprise Server à partir d’Office Web Apps Server. là encore, vous ne pouvez effectuer cette opération que si les deux serveurs (SharePoint et Skype entreprise Server) s’approuvent les uns les autres. Même s’il est possible d’utiliser un mécanisme d’authentification pour la communication entre Skype entreprise Server et Exchange, mais un mécanisme distinct pour la communication entre Skype entreprise Server et SharePoint, il est préférable d’utiliser un méthode normalisée pour toutes les autorisations et authentification de serveur à serveur.
  
L’utilisation d’une méthode normalisée unique pour l’authentification de serveur à serveur est l’approche adoptée par Skype entreprise Server. À partir de la version 2013 de Office Servers, Skype entreprise Server (ainsi que d’autres produits Microsoft Server, dont Exchange Server et SharePoint Server) prenait en charge le protocole OAuth (Open Authorization) pour l’authentification de serveur à serveur et d'. Avec OAuth, un protocole d’autorisation standard utilisé par un certain nombre de sites Web importants, les informations d’identification d’utilisateur et les mots de passe ne sont pas transmis d’un ordinateur à un autre. Au lieu de cela, l’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité. Ces jetons octroient l’accès à un ensemble spécifique de ressources pour un certain temps.
  
L’authentification OAuth implique généralement trois parties: un seul serveur d’autorisation et les deux domaines qui doivent communiquer entre eux. (Vous pouvez également effectuer une authentification serveur à serveur sans recourir à un serveur d’autorisation, un processus qui sera abordé plus loin dans ce document.) Les jetons de sécurité sont émis par le serveur d’autorisation (également connu sous le nom de serveur de jetons de sécurité) pour les deux domaines qui doivent communiquer. Ces jetons vérifient que les communications provenant d’un domaine doivent être approuvées par l’autre domaine. Par exemple, le serveur d’autorisation peut émettre des jetons qui vérifient que les utilisateurs d’un domaine Skype entreprise Server spécifique sont en mesure d’accéder à un domaine Exchange spécifique, et inversement.
  
> [!NOTE]
> Un domaine est tout simplement un conteneur de sécurité. Par défaut, Skype entreprise Server utilise votre domaine SIP par défaut comme domaine OAuth. Des espaces de noms SIP supplémentaires sont ajoutés à la liste Autre nom du sujet du certificat dans le certificat OAuth. 
  
Skype entreprise Server prend en charge trois scénarios d’authentification de serveur à serveur. Avec Skype entreprise Server, vous pouvez:
  
- Configurer l’authentification de serveur à serveur entre une installation locale de Skype entreprise Server et une installation locale d’Exchange et/ou de SharePoint Server.
    
- Configurer l’authentification de serveur à serveur entre deux composants 365 d’Office (par exemple, entre Microsoft Exchange Server et Skype entreprise Server ou entre Skype entreprise Server et SharePoint).
    
- Configurer l’authentification de serveur à serveur dans un environnement local (c’est-à-dire, l’authentification de serveur à serveur entre un serveur local et un composant Office 365).
    
Notez que, à ce stade, seuls Exchange 2013, SharePoint Server, Lync Server 2013, Skype entreprise Server 2015 et Skype entreprise 2019 prennent en charge l’authentification de serveur à serveur. Si vous n’utilisez pas l’un de ces serveurs, vous ne serez pas en mesure de mettre entièrement en œuvre l’authentification OAuth.
  
Il est également important de noter que l’authentification serveur à serveur est facultative: si Skype entreprise Server n’a pas besoin de communiquer avec d’autres serveurs (par exemple, Exchange), l’authentification de serveur à serveur peut être ignorée entièrement. Si l’authentification serveur à serveur est déjà configurée pour Lync Server 2013 et d’autres applications, il n’est pas nécessaire de la relancer pour Skype entreprise Server. 
  
Toutefois, l’authentification serveur à serveur est requise si vous souhaitez utiliser certaines des fonctionnalités de Skype entreprise Server, comme le «magasin de contacts unifié». Avec un magasin de contacts unifié, les informations de contact de Skype entreprise Server sont stockées dans Exchange plutôt que dans Skype entreprise Server. Cela permet aux utilisateurs de disposer d’un ensemble unique de contacts facilement accessible à partir de Skype entreprise, Outlook ou Outlook Web Access. Dans la mesure où le magasin de contacts unifié nécessite Skype entreprise Server pour partager des informations avec Exchange, vous devez utiliser l’authentification de serveur à serveur pour déployer la fonctionnalité. L’authentification de serveur à serveur est également nécessaire si vous choisissez d’utiliser l’archivage Exchange, dans lequel les transcriptions de sessions de messagerie instantanée sont enregistrées sous forme de messages électroniques Exchange plutôt que d’enregistrements de base de données individuels.
  
Pour la version 365 d’Office de Skype entreprise Server permettant de communiquer avec son équivalent Exchange, Skype entreprise Server doit d’abord obtenir un jeton de sécurité du serveur d’autorisation. Skype entreprise Server utilise alors ce jeton de sécurité pour s’identifier auprès d’Exchange. La version 365 Office d’Exchange doit suivre le même processus pour communiquer avec Skype entreprise Server.
  
Toutefois, en ce qui concerne l’authentification de serveur à serveur entre deux serveurs Microsoft, il n’est pas nécessaire d’utiliser un serveur de jetons tiers. Les produits serveur tels que Skype entreprise Server et Exchange disposent d’un serveur à jetons intégré qui peut être utilisé à des fins d’authentification avec d’autres serveurs Microsoft (par exemple, SharePoint Server) qui prennent en charge l’authentification de serveur à serveur. Par exemple, Skype entreprise Server peut émettre et signer un jeton de sécurité, puis utiliser ce jeton pour communiquer avec Exchange. Dans ce cas, aucun serveur de jetons tiers n’est nécessaire.
  
Pour configurer l’authentification de serveur à serveur pour une implémentation locale de Skype entreprise Server, vous devez effectuer deux opérations:
  
- Affectez un certificat à l’émetteur de jeton Skype entreprise Server intégré.
    
- Configurez le serveur avec lequel Skype entreprise Server va communiquer en tant que «application partenaire». Par exemple, si Skype entreprise Server doit communiquer avec Exchange, vous devez configurer Exchange en tant qu’application partenaire.
    
> [!NOTE]
> Une «application partenaire» est une application dont Skype entreprise Server peut directement échanger des jetons de sécurité sans avoir à passer par un serveur de jetons de sécurité tiers. 
  
Notez qu’OAuth est un composant de base du produit et ne peut être ni désactivé ni supprimé.
  
## <a name="see-also"></a>Voir aussi

[Affecter un certificat d’authentification de serveur à serveur à Skype entreprise Server](assign-a-server-to-server-certificate.md)
  
[Configuration d’un environnement hybride dans Skype entreprise Server](configure-a-hybrid-environment.md)
