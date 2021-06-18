---
title: Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Résumé : Gérez OAuth et les applications partenaires dans Skype Entreprise Server.'
ms.openlocfilehash: ff926440d1f00601eacfb77aadb858063b3e48b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828299"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype Entreprise Server
 
**Résumé :** Gérer OAuth et les applications partenaires dans Skype Entreprise Server.
  
Skype Entreprise Server doit pouvoir communiquer en toute sécurité et en toute transparence avec d’autres applications et produits serveur. Par exemple, vous pouvez configurer Skype Entreprise Server de sorte que les données de contact et/ou d’archivage sont stockées dans Microsoft Exchange Server 2013 ; Toutefois, cela ne peut être effectué que si Skype Entreprise Server et Exchange sont en mesure de communiquer en toute sécurité les uns avec les autres. De même, vous pouvez planifier une conférence Skype Entreprise Server à partir d’Office Web Apps Server ; Là encore, cette action ne peut être effectuée que si les deux serveurs (SharePoint et Skype Entreprise Server) s’trustent mutuellement. Bien qu’il soit possible d’utiliser un mécanisme d’authentification pour la communication entre Skype Entreprise Server et Exchange, mais un mécanisme distinct pour la communication Skype Entreprise Server et SharePoint, une approche plus efficace et plus efficace consiste à utiliser une méthode normalisée pour l’authentification et l’autorisation de serveur à serveur.
  
L’utilisation d’une méthode normalisée unique pour l’authentification de serveur à serveur est l’approche prise par Skype Entreprise Server. Démarré avec la version Office Server 2013, Skype Entreprise Server (ainsi que d’autres produits Microsoft Server, notamment Exchange Server et SharePoint Server) ont pris en charge le protocole OAuth (Open Authorization) pour l’authentification et l’autorisation de serveur à serveur. Avec OAuth, un protocole d’autorisation standard utilisé par de nombreux sites web principaux, les informations d’identification et les mots de passe des utilisateurs ne sont pas transmis d’un ordinateur à un autre. Au lieu de cela, l’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité ; ces jetons accordent l’accès à un ensemble spécifique de ressources pendant une durée spécifique.
  
L’authentification OAuth implique généralement trois parties : un serveur d’autorisation unique et les deux domaines qui doivent communiquer entre eux. (Vous pouvez également utiliser l’authentification de serveur à serveur sans utiliser de serveur d’autorisation, un processus qui sera abordé plus loin dans ce document.) Les jetons de sécurité sont émis par le serveur d’autorisation (également appelé serveur de jetons de sécurité) vers les deux domaines qui doivent communiquer ; Ces jetons vérifient que les communications provenant d’un domaine doivent être fiables par l’autre domaine. Par exemple, le serveur d’autorisation peut émettre des jetons qui vérifient que les utilisateurs d’un domaine Skype Entreprise Server spécifique sont en mesure d’accéder à un domaine Exchange spécifié, et inversement.
  
> [!NOTE]
> Un domaine est tout simplement un conteneur de sécurité. Par défaut, Skype Entreprise Server utilise votre domaine SIP par défaut comme domaine OAuth. Des espaces de noms SIP supplémentaires sont ajoutés à la liste des autres noms du sujet dans le certificat OAuth. 
  
Skype Entreprise Server prend en charge trois scénarios d’authentification de serveur à serveur. Avec Skype Entreprise Server, vous pouvez :
  
- Configurez l’authentification de serveur à serveur entre une installation sur site de Skype Entreprise Server et une installation sur site d’Exchange et/ou de SharePoint Server.
    
- Configurez l’authentification de serveur à serveur entre deux composants Microsoft 365 ou Office 365 (par exemple, entre Microsoft Exchange Server et Skype Entreprise Server, ou entre Skype Entreprise Server et SharePoint).
    
- Configurez l’authentification de serveur à serveur dans un environnement entre différents locaux (autrement dit, l’authentification de serveur à serveur entre un serveur local et un composant Microsoft 365 ou Office 365).
    
Notez qu’à ce stade, seuls Exchange 2013, SharePoint Server, Lync Server 2013, Skype Entreprise Server 2015 et Skype Entreprise 2019 peuvent prendre en charge l’authentification de serveur à serveur. Si vous n’exécutez pas l’un de ces serveurs, vous ne pourrez pas implémenter entièrement l’authentification OAuth.
  
Notez également que l’authentification de serveur à serveur est facultative : si Skype Entreprise Server n’a pas besoin de communiquer avec d’autres serveurs (comme Exchange), l’authentification de serveur à serveur peut être ignorée. Si l’authentification de serveur à serveur est déjà configurée pour Lync Server 2013 et d’autres applications, il n’est pas nécessaire de la ré-utiliser pour Skype Entreprise Server. 
  
Toutefois, l’authentification de serveur à serveur est requise si vous souhaitez utiliser certaines fonctionnalités de Skype Entreprise Server, telles que le « magasin de contacts unifié ». Avec le magasin de contacts unifié, les informations de contact Skype Entreprise Server sont stockées dans Exchange plutôt que dans Skype Entreprise Server . Cela permet aux utilisateurs d’avoir un seul ensemble de contacts facilement accessibles à partir de Skype Entreprise, Outlook ou Outlook Web Access. Étant donné que le magasin de contacts unifié nécessite que Skype Entreprise Server partage des informations avec Exchange, vous devez utiliser l’authentification de serveur à serveur pour déployer la fonctionnalité. L’authentification de serveur à serveur est également requise si vous choisissez d’utiliser l’archivage Exchange, dans lequel les transcriptions des sessions de messagerie instantanée sont enregistrées en tant qu’e-mails Exchange plutôt qu’en tant qu’enregistrements de base de données individuels.
  
Pour que la version Microsoft 365 ou Office 365 de Skype Entreprise Server communique avec son équivalent Exchange, Skype Entreprise Server doit d’abord obtenir un jeton de sécurité auprès du serveur d’autorisation. Skype Entreprise Server utilise ensuite ce jeton de sécurité pour s’identifier à Exchange. Les versions Microsoft 365 ou Office 365 d’Exchange doivent passer par le même processus pour communiquer avec Skype Entreprise Server.
  
Toutefois, en ce qui concerne l’authentification de serveur à serveur entre deux serveurs Microsoft, il n’y a aucun besoin d’utiliser un serveur de jetons tiers. Les produits serveur tels que Skype Entreprise Server et Exchange ont un serveur de jetons intégré qui peut être utilisé à des fins d’authentification avec d’autres serveurs Microsoft (tels que SharePoint Server) qui prendre en charge l’authentification de serveur à serveur. Par exemple, Skype Entreprise Server peut émettre et signer un jeton de sécurité seul, puis utiliser ce jeton pour communiquer avec Exchange. Dans un cas comme celui-ci, aucun serveur de jeton tiers n'est nécessaire.
  
Pour configurer l’authentification de serveur à serveur pour une implémentation sur site de Skype Entreprise Server, vous devez faire deux choses :
  
- Affecter un certificat à l’émetteur de jeton Skype Entreprise Server intégré.
    
- Configurez le serveur avec qui Skype Entreprise Server communiquera en tant qu'« application partenaire ». Par exemple, si Skype Entreprise Server doit communiquer avec Exchange, vous devez configurer Exchange en tant qu’application partenaire.
    
> [!NOTE]
> Une « application partenaire » est toute application avec qui Skype Entreprise Server peut directement échanger des jetons de sécurité, sans avoir à passer par un serveur de jetons de sécurité tiers. 
  
Notez qu’OAuth est une partie essentielle du produit et ne peut pas être désactivé ou supprimé.
  
## <a name="see-also"></a>Voir aussi

[Affecter un certificat d’authentification de serveur à serveur à Skype Entreprise Server](assign-a-server-to-server-certificate.md)
  
[Configurer un environnement hybride dans Skype Entreprise Server](configure-a-hybrid-environment.md)
