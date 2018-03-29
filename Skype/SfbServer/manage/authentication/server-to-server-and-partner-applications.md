---
title: Gestion de l’authentification serveur à serveur (OAuth) et des applications partenaires dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Résumé : Gérer les applications OAuth et partenaire dans Skype pour Business Server 2015.'
ms.openlocfilehash: 41886b0275bd7284f6716c322595f1c360171360
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server-2015"></a>Gestion de l’authentification serveur à serveur (OAuth) et des applications partenaires dans Skype Entreprise Server 2015
 
**Résumé :** Gérer les applications OAuth et partenaire dans Skype pour Business Server 2015.
  
Skype pour Business Server 2015 doit pouvoir en toute sécurité et en toute transparence, communiquer avec d’autres applications et les produits de serveur. Par exemple, vous pouvez configurer Skype pour Business Server 2015 afin que le contact données et/ou d’archivage des données stockées dans Microsoft Exchange Server 2013 ; Toutefois, cela n’est possible si Skype pour Business Server et Exchange est en mesure de communiquer de manière sécurisée avec un autre. De même, vous pouvez planifier un Skype pour conférence de Business Server à partir d’Office Web Apps Server ; là encore, cela n’est possible si les deux serveurs (SharePoint et Skype pour Business Server) une relation d’approbation. Bien qu’il soit possible d’utiliser un mécanisme d’authentification pour la communication entre Skype pour Business Server et Exchange mais un mécanisme distinct pour Skype pour la communication Business Server et SharePoint, une meilleure et la plus efficace consiste à utiliser un méthode standardisée pour tous les serveur pour l’authentification et l’autorisation.
  
À l’aide d’un seul, une méthode standardisée pour l’authentification de serveur à serveur est l’approche adoptée par Skype pour Business Server 2015. Pour le 2013 release, Skype pour Business Server 2015 (comme autres produits Microsoft Server, y compris Exchange 2013 et SharePoint Server) prend en charge le protocole OAuth (autorisation Ouvrir) pour l’authentification de serveur à serveur et de l’autorisation. Avec OAuth, un protocole d’autorisation standard utilisé par un certain nombre de sites principaux, les informations d’identification de l’utilisateur et les mots de passe pas transférés à partir d’un ordinateur à l’autre. Au lieu de cela, l’authentification et l’autorisation est basée sur l’échange de jetons de sécurité ; Ces jetons d’accordent l’accès à un ensemble spécifique de ressources pour une durée spécifique.
  
Authentification OAuth implique généralement trois parties : un serveur d’autorisation unique et les deux domaines qui doivent communiquer entre eux. (Vous pouvez également faire d’authentification de serveur à serveur sans utiliser un serveur d’autorisation, un processus qui sera abordé plus loin dans ce document). Jetons de sécurité sont émis par le serveur d’autorisation (également appelé un jeton serveur de sécurité) pour les deux domaines qui doivent communiquer ; Ces jetons de vérifier que les communications provenant d’un domaine doit être approuvées par l’autre domaine. Par exemple, le serveur d’autorisation peut émettre des jetons de vérifier que les utilisateurs d’un Skype spécifique Business Server 2015 Kerberos sont en mesure d’accéder à un domaine de Exchange 2013 spécifié et vice versa.
  
> [!NOTE]
> Un domaine est tout simplement un conteneur de sécurité. Par défaut, Skype pour Business Server 2015 utilise votre domaine SIP de par défaut en tant que son domaine OAuth. Des espaces de noms SIP supplémentaires sont ajoutés à la liste Autre nom du sujet du certificat dans le certificat OAuth. 
  
Skype pour Business Server 2015 prend en charge trois scénarios d’authentification de serveur à serveur. Avec Skype pour Business Server 2015, vous pouvez :
  
- Configurer l’authentification de serveur à serveur entre une installation sur site de Skype pour Business Server 2015 et une installation sur site de SharePoint Server et/ou d’Exchange 2013.
    
- Configurer l’authentification de serveur à serveur entre deux composants d’Office 365 (par exemple, entre Microsoft Exchange Server et Skype pour Business Server ou entre Skype pour Business Server 2015 et SharePoint).
    
- Configurer l’authentification de serveur à serveur dans un environnement de coexistence (c'est-à-dire au serveur d’authentification entre un serveur local et un composant d’Office 365).
    
Notez que, à ce stade, seuls Exchange 2013, SharePoint Server, Lync Server 2013 et Skype pour Business Server 2015 prise en charge de l’authentification serveur ; Si vous n’exécutez pas un de ces serveurs vous ne pourrez pas implémenter l’authentification OAuth.
  
Il convient également de préciser que-serveur authentification est facultative : si Skype pour 2015 de serveur d’entreprise n’a pas besoin de communiquer avec d’autres serveurs (par exemple, Exchange 2013) puis l’authentification de serveur à serveur peut être ignorée. Si l’authentification du serveur-serveur est déjà configurée pour Lync Server 2013 et d’autres applications, il est inutile de nouveau faire pour Skype pour Business Server 2015. 
  
Toutefois, l’authentification de serveur à serveur est nécessaire si vous souhaitez utiliser certaines des fonctionnalités dans Skype pour 2015 de serveur d’entreprise, telles que le « unifié magasin de contacts. » Avec le magasin de contacts unifiée, Skype pour les informations de contact de Business Server 2015 est stocké dans Exchange 2013 plutôt dans Skype pour le serveur de l’entreprise ; Cela permet aux utilisateurs d’avoir un seul ensemble de contacts qui est facilement accessible à partir de Skype pour entreprise, Outlook ou Outlook Web Access. Parce que le magasin de contacts unifié nécessite Skype pour 2015 de serveur d’entreprise partager des informations avec Exchange 2013, vous devez utiliser l’authentification de serveur à serveur pour déployer la fonctionnalité. L’authentification de serveur à serveur est également requise si vous choisissez d’utiliser Exchange d’archivage, dans lequel les transcriptions des sessions de messagerie instantanées sont enregistrées comme les e-mails Exchange 2013 plutôt que comme des enregistrements de base de données individuels.
  
Pour la version de Skype pour Business Server communiquer avec son équivalent Exchange Office 365 Skype pour Business Server 2015 doit d’abord obtenir un jeton de sécurité à partir du serveur d’autorisation. Skype pour Business Server utilise ensuite ce jeton de sécurité pour s’identifier sur Exchange. La version d’Office 365 d’Exchange doit passer par le même processus pour communiquer avec Skype pour Business Server 2015.
  
Toutefois, en ce qui concerne l’authentification de serveur à serveur entre deux serveurs Microsoft, il n’est pas nécessaire d’utiliser un serveur de jetons tiers. Produits serveur tels que Skype pour Business Server 2015 et Exchange 2013 ont un serveur jeton qui peut être utilisé à des fins d’authentification avec d’autres serveurs Microsoft (par exemple, SharePoint Server) prenant en charge l’authentification de serveur à serveur. Par exemple, Skype pour Business Server 2015 peut émettre et signe un jeton de sécurité par lui-même, puis l’utilisation de ce jeton pour communiquer avec Exchange 2013. Dans ce cas, aucun serveur de jetons tiers n’est nécessaire.
  
Pour configurer l’authentification de serveur à serveur pour une implémentation sur site de Skype pour Business Server 2015, vous devez faire deux choses :
  
- Affecter un certificat à la Skype intégré pour l’émetteur de jeton Business Server 2015.
    
- Configurer le serveur Skype pour Business Server 2015 va communiquer avec une application « partenaire ». Par exemple, si Skype pour Business Server 2015 doit communiquer avec Exchange 2013, vous devrez configurer Exchange pour une application de partenaire.
    
> [!NOTE]
> Une application « partenaire » est une application qui Skype pour Business Server 2015 peut échanger directement des jetons de sécurité, sans avoir à passer par un serveur de jeton de sécurité de tiers. 
  
Notez qu’OAuth est un composant de base du produit et ne peut être ni désactivé ni supprimé.
  
## <a name="see-also"></a>Voir aussi

#### 

[Attribuer un certificat d’authentification de serveur à serveur à Skype pour Business Server 2015](assign-a-server-to-server-certificate.md)
  
[Configurer un environnement hybride dans Skype pour Business Server 2015](configure-a-hybrid-environment.md)

