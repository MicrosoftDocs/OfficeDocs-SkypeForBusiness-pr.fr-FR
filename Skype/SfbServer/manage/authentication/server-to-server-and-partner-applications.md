---
title: Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Résumé : Gérez OAuth et les applications partenaires dans Skype Entreprise Server.'
ms.openlocfilehash: d49006bd01de80bd23d8f70954478b6b6a2bbea4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760742"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype Entreprise Server
 
**Résumé :** Gérez OAuth et les applications partenaires dans Skype Entreprise Server.
  
Skype Entreprise Server être en mesure de communiquer en toute sécurité et en toute transparence avec d’autres applications et produits serveur. Par exemple, vous pouvez configurer Skype Entreprise Server de sorte que les données de contact et/ou d’archivage sont stockées dans Microsoft Exchange Server 2013 ; Toutefois, cela ne peut être effectué que si Skype Entreprise Server et Exchange sont en mesure de communiquer en toute sécurité. De même, vous pouvez planifier une conférence Skype Entreprise Server à partir de Office Web Apps Server ; Là encore, cela ne peut être effectué que si les deux serveurs (SharePoint et Skype Entreprise Server) s’trustent mutuellement. Bien qu’il soit possible d’utiliser un mécanisme d’authentification pour la communication entre Skype Entreprise Server et Exchange mais un mécanisme distinct pour la communication Skype Entreprise Server et SharePoint, une meilleure et plus efficace approche consiste à utiliser une méthode normalisée pour tous Authentification et autorisation de serveur à serveur.
  
L’utilisation d’une méthode normalisée unique pour l’authentification de serveur à serveur est l’approche prise par Skype Entreprise Server. Démarré avec Office Servers 2013, Skype Entreprise Server (ainsi que d’autres produits Microsoft Server, notamment Exchange Server et SharePoint Server) ont pris en charge le protocole OAuth (Open Authorization) pour l’authentification et l’autorisation de serveur à serveur. Avec OAuth, un protocole d’autorisation standard utilisé par de nombreux sites web principaux, les informations d’identification et les mots de passe des utilisateurs ne sont pas transmis d’un ordinateur à un autre. Au lieu de cela, l’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité ; ces jetons accordent l’accès à un ensemble spécifique de ressources pendant une durée spécifique.
  
L’authentification OAuth implique généralement trois parties : un serveur d’autorisation unique et les deux domaines qui doivent communiquer entre eux. (Vous pouvez également utiliser l’authentification de serveur à serveur sans utiliser de serveur d’autorisation, un processus qui sera abordé plus loin dans ce document.) Les jetons de sécurité sont émis par le serveur d’autorisation (également appelé serveur de jetons de sécurité) vers les deux domaines qui doivent communiquer ; Ces jetons vérifient que les communications provenant d’un domaine doivent être fiables par l’autre domaine. Par exemple, le serveur d’autorisation peut émettre des jetons qui vérifient que les utilisateurs d’un domaine Skype Entreprise Server spécifique sont en mesure d’accéder à un domaine Exchange spécifique, et inversement.
  
> [!NOTE]
> Un domaine est tout simplement un conteneur de sécurité. Par défaut, Skype Entreprise Server utilise votre domaine SIP par défaut comme domaine OAuth. D’autres espaces de noms SIP sont ajoutés à la liste des autres noms du sujet dans le certificat OAuth. 
  
Skype Entreprise Server prend en charge trois scénarios d’authentification de serveur à serveur. Avec Skype Entreprise Server, vous pouvez :
  
- Configurez l’authentification de serveur à serveur entre une installation sur site de Skype Entreprise Server et une installation sur site de Exchange et/ou SharePoint Server.
    
- Configurez l’authentification de serveur à serveur entre deux composants Microsoft 365 ou Office 365 (par exemple, entre Microsoft Exchange Server et Skype Entreprise Server, ou entre Skype Entreprise Server et SharePoint).
    
- Configurez l’authentification de serveur à serveur dans un environnement entre différents locaux (autrement dit, l’authentification de serveur à serveur entre un serveur local et un composant Microsoft 365 ou Office 365).
    
Notez qu’à ce stade, seuls Exchange 2013, SharePoint Server, Lync Server 2013, Skype Entreprise Server 2015 et Skype Entreprise 2019 peuvent prendre en charge l’authentification de serveur à serveur . Si vous n’exécutez pas l’un de ces serveurs, vous ne pourrez pas implémenter entièrement l’authentification OAuth.
  
Notez également que l’authentification de serveur à serveur est facultative : si Skype Entreprise Server n’a pas besoin de communiquer avec d’autres serveurs (tels que Exchange), l’authentification de serveur à serveur peut être ignorée. Si l’authentification de serveur à serveur est déjà configurée pour Lync Server 2013 et d’autres applications, il n’est pas nécessaire de la ré-Skype Entreprise Server. 
  
Toutefois, l’authentification de serveur à serveur est requise si vous souhaitez utiliser certaines fonctionnalités de Skype Entreprise Server, telles que le « magasin de contacts unifié ». Avec le magasin de contacts unifié, Skype Entreprise Server coordonnées sont stockées dans Exchange au lieu de Skype Entreprise Server ; Cela permet aux utilisateurs d’avoir un seul ensemble de contacts facilement accessibles depuis Skype Entreprise, Outlook ou Outlook Web Access. Étant donné que le magasin de contacts unifié nécessite Skype Entreprise Server pour partager des informations avec Exchange, vous devez utiliser l’authentification de serveur à serveur pour déployer la fonctionnalité. L’authentification de serveur à serveur est également requise si vous choisissez d’utiliser l’archivage Exchange, dans lequel les transcriptions des sessions de messagerie instantanée sont enregistrées sous forme de messages électroniques Exchange plutôt que sous forme d’enregistrements de base de données individuels.
  
Pour que la version Microsoft 365 ou Office 365 de Skype Entreprise Server communique avec son équivalent Exchange, Skype Entreprise Server doit d’abord obtenir un jeton de sécurité auprès du serveur d’autorisation. Skype Entreprise Server utilise ensuite ce jeton de sécurité pour s’identifier pour Exchange. Les Microsoft 365 ou Office 365 versions de Exchange doivent passer par le même processus pour communiquer avec Skype Entreprise Server.
  
Toutefois, en ce qui concerne l’authentification de serveur à serveur entre deux serveurs Microsoft, il n’y a aucun besoin d’utiliser un serveur de jetons tiers. Les produits serveur tels que Skype Entreprise Server et Exchange ont un serveur de jetons intégré qui peut être utilisé à des fins d’authentification avec d’autres serveurs Microsoft (tels que SharePoint Server) qui prendre en charge l’authentification de serveur à serveur. Par exemple, Skype Entreprise Server pouvez émettre et signer un jeton de sécurité seul, puis utiliser ce jeton pour communiquer avec Exchange. Dans un cas comme celui-ci, aucun serveur de jeton tiers n'est nécessaire.
  
Pour configurer l’authentification de serveur à serveur pour une implémentation sur site de Skype Entreprise Server, vous devez faire deux choses :
  
- Affectez un certificat à l’émetteur de jeton Skype Entreprise Server intégré.
    
- Configurez le serveur avec Skype Entreprise Server pour qu’il soit une « application partenaire ». Par exemple, si Skype Entreprise Server doit communiquer avec Exchange, vous devrez configurer Exchange en tant qu’application partenaire.
    
> [!NOTE]
> Une « application partenaire » est toute application avec Skype Entreprise Server peut directement échanger des jetons de sécurité, sans avoir à passer par un serveur de jetons de sécurité tiers. 
  
Notez qu’OAuth est une partie essentielle du produit et ne peut pas être désactivé ou supprimé.
  
## <a name="see-also"></a>Voir aussi

[Affecter un certificat d’authentification de serveur à serveur à Skype Entreprise Server](assign-a-server-to-server-certificate.md)
  
[Configurer un environnement hybride dans Skype Entreprise Server](configure-a-hybrid-environment.md)
