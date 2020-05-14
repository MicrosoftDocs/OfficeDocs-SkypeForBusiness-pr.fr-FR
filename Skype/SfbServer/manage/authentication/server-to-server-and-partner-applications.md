---
title: Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Résumé : gérez les applications OAuth et partenaires dans Skype entreprise Server.'
ms.openlocfilehash: f784dd0a2dab05fb3b97497fab7d3866dda1a753
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221668"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype entreprise Server
 
**Résumé :** Gérer les applications OAuth et partenaires dans Skype entreprise Server.
  
Skype entreprise Server doit être en mesure de communiquer de manière sécurisée avec d’autres applications et produits serveurs. Par exemple, vous pouvez configurer Skype entreprise Server de manière à ce que les données de contact et/ou les données d’archivage soient stockées dans Microsoft Exchange Server 2013 ; Toutefois, cette opération n’est possible que si Skype entreprise Server et Exchange sont en mesure de communiquer de manière sécurisée. De même, vous pouvez planifier une conférence Skype entreprise Server à partir d’Office Web Apps Server ; là encore, cette opération est possible uniquement si les deux serveurs (SharePoint et Skype entreprise Server) s’approuvent mutuellement. Bien qu’il soit possible d’utiliser un mécanisme d’authentification pour la communication entre Skype entreprise Server et Exchange, mais un mécanisme distinct pour la communication de Skype entreprise Server et de SharePoint, une approche plus efficace consiste à utiliser une méthode standardisée pour l’authentification et l’autorisation de serveur à serveur.
  
L’utilisation d’une méthode standardisée unique pour l’authentification de serveur à serveur est l’approche adoptée par Skype entreprise Server. Démarré avec la version Office Server 2013, Skype entreprise Server (ainsi que d’autres produits serveur Microsoft, y compris Exchange Server et SharePoint Server) prenait en charge le protocole OAuth (Open Authorization) pour l’authentification et l’autorisation de serveur à serveur. Avec OAuth, un protocole d’autorisation standard utilisé par un certain nombre de sites principaux, les informations d’identification de l’utilisateur et les mots de passe ne sont pas transmis d’un ordinateur à un autre. Au lieu de cela, l’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité ; Ces jetons accordent l’accès à un ensemble spécifique de ressources pour une durée spécifique.
  
L’authentification OAuth implique généralement trois parties : un serveur d’autorisation unique et les deux domaines qui doivent communiquer les uns avec les autres. (Vous pouvez également effectuer l’authentification de serveur à serveur sans utiliser de serveur d’autorisation, un processus qui sera abordé plus loin dans ce document.) Les jetons de sécurité sont émis par le serveur d’autorisation (également appelé serveur de jetons de sécurité) pour les deux domaines qui doivent communiquer ; Ces jetons vérifient que les communications provenant d’un domaine doivent être approuvées par l’autre domaine. Par exemple, le serveur d’autorisation peut émettre des jetons qui vérifient que les utilisateurs d’un domaine Skype entreprise Server spécifique sont en mesure d’accéder à un domaine Exchange spécifié, et inversement.
  
> [!NOTE]
> Un domaine est tout simplement un conteneur de sécurité. Par défaut, Skype entreprise Server utilise votre domaine SIP par défaut comme domaine OAuth. Des espaces de noms SIP supplémentaires sont ajoutés à la liste autre nom de l’objet dans le certificat OAuth. 
  
Skype entreprise Server prend en charge trois scénarios d’authentification de serveur à serveur. Avec Skype entreprise Server, vous pouvez :
  
- Configurez l’authentification de serveur à serveur entre une installation locale de Skype entreprise Server et une installation locale d’Exchange et/ou de SharePoint Server.
    
- Configurez l’authentification de serveur à serveur entre une paire de composants Microsoft 365 ou Office 365 (par exemple, entre Microsoft Exchange Server et Skype entreprise Server, ou entre Skype entreprise Server et SharePoint).
    
- Configurez l’authentification de serveur à serveur dans un environnement intersite (c’est-à-dire, l’authentification de serveur à serveur entre un serveur local et un composant Microsoft 365 ou Office 365).
    
Notez que, à ce stade, seuls Exchange 2013, SharePoint Server, Lync Server 2013, Skype entreprise Server 2015 et Skype entreprise 2019 prennent en charge l’authentification de serveur à serveur ; Si vous n’exécutez pas l’un de ces serveurs, vous ne pourrez pas totalement implémenter l’authentification OAuth.
  
Il convient également de remarquer que l’authentification de serveur à serveur est facultative : si Skype entreprise Server n’a pas besoin de communiquer avec d’autres serveurs (par exemple, Exchange), l’authentification de serveur à serveur peut être ignorée. Si l’authentification de serveur à serveur est déjà configurée pour Lync Server 2013 et d’autres applications, il n’est pas nécessaire de la relancer pour Skype entreprise Server. 
  
Toutefois, l’authentification de serveur à serveur est requise si vous souhaitez utiliser certaines des fonctionnalités de Skype entreprise Server, telles que le magasin de contacts unifié. Avec le magasin de contacts unifié, les informations de contact de Skype entreprise Server sont stockées dans Exchange et non dans Skype entreprise Server ; Cela permet aux utilisateurs de disposer d’un seul ensemble de contacts directement accessible à partir de Skype entreprise, Outlook ou Outlook Web Access. Étant donné que le magasin de contacts unifié nécessite que Skype entreprise Server partage des informations avec Exchange, vous devez utiliser l’authentification de serveur à serveur pour déployer la fonctionnalité. L’authentification de serveur à serveur est également requise si vous choisissez d’utiliser l’archivage Exchange, dans lequel les transcriptions des sessions de messagerie instantanée sont enregistrées sous forme de messages électroniques Exchange plutôt que sous forme d’enregistrements de base de données individuels.
  
Pour que la version Microsoft 365 ou Office 365 de Skype entreprise Server communique avec son homologue Exchange, Skype entreprise Server doit d’abord obtenir un jeton de sécurité auprès du serveur d’autorisation. Skype entreprise Server utilise ensuite ce jeton de sécurité pour s’identifier auprès d’Exchange. Les versions de Microsoft 365 ou Office 365 d’Exchange doivent passer par le même processus afin de communiquer avec Skype entreprise Server.
  
Toutefois, en ce qui concerne l’authentification de serveur à serveur entre deux serveurs Microsoft, il n’y a aucun besoin d’utiliser un serveur de jetons tiers. Les produits serveur tels que Skype entreprise Server et Exchange disposent d’un serveur de jetons intégré qui peut être utilisé à des fins d’authentification avec d’autres serveurs Microsoft (par exemple, SharePoint Server) qui prennent en charge l’authentification de serveur à serveur. Par exemple, Skype entreprise Server peut émettre et signer un jeton de sécurité lui-même, puis utiliser ce jeton pour communiquer avec Exchange. Dans un cas comme celui-ci, aucun serveur de jeton tiers n'est nécessaire.
  
Pour configurer l’authentification de serveur à serveur pour une implémentation locale de Skype entreprise Server, vous devez effectuer les deux opérations suivantes :
  
- Affectez un certificat à l’émetteur de jeton Skype entreprise Server intégré.
    
- Configurez le serveur avec lequel Skype entreprise Server doit communiquer en tant qu’application partenaire. Par exemple, si Skype entreprise Server doit communiquer avec Exchange, vous devrez configurer Exchange en tant qu’application partenaire.
    
> [!NOTE]
> Une application partenaire est une application pour laquelle Skype entreprise Server peut directement échanger des jetons de sécurité, sans avoir à passer par un serveur de jetons de sécurité tiers. 
  
Notez que OAuth est un élément essentiel du produit et qu’il ne peut pas être désactivé ou supprimé.
  
## <a name="see-also"></a>Voir aussi

[Affecter un certificat d’authentification de serveur à serveur à Skype entreprise Server](assign-a-server-to-server-certificate.md)
  
[Configuration d’un environnement hybride dans Skype entreprise Server](configure-a-hybrid-environment.md)
