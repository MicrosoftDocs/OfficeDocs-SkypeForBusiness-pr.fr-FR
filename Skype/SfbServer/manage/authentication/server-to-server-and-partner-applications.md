---
title: Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Résumé : Gérer les applications OAuth et partenaire dans Skype pour Business Server.'
ms.openlocfilehash: 77fd070ace850035d129dc247decdcf7988219cf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893145"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype pour Business Server
 
**Résumé :** Gérer les applications OAuth et partenaire dans Skype pour Business Server.
  
Skype pour Business Server doit être en mesure d’en toute sécurité et en toute transparence, de communiquer avec d’autres applications et les produits serveur. Par exemple, vous pouvez configurer Skype pour Business Server afin que les données et les données d’archivage le contact est stocké dans Microsoft Exchange Server 2013 ; Toutefois, cela n’est possible si Skype pour Business Server et Exchange est en mesure de communiquer en toute sécurité entre eux. De même, vous pouvez planifier une Skype pour conférence Business Server à partir d’Office Web Apps Server ; là encore, cela n’est possible si les deux serveurs (SharePoint et Skype pour Business Server) une relation d’approbation. Bien qu’il soit possible d’utiliser un mécanisme d’authentification pour la communication entre Skype pour Business Server et Exchange mais un mécanisme distinct de Skype pour les communications Business Server et SharePoint, une meilleure et plus efficace consiste à utiliser un méthode standardisé pour tous les autorisation et d’authentification de serveur à serveur.
  
À l’aide d’un seul, méthode standardisée pour l’authentification de serveur à serveur est l’approche Skype pour Business Server. Participer à une version d’Office 2013 de serveurs, Skype pour Business Server (ainsi que d’autres produits Microsoft Server, y compris Exchange Server et SharePoint Server) pris en charge le protocole OAuth (Open Authorization) pour l’authentification de serveur à serveur et autorisation. Avec OAuth, un protocole standard d’autorisation utilisé par un nombre de sites principaux, les informations d’identification utilisateur et les mots de passe ne sont pas transmis d’un ordinateur à un autre. Au lieu de cela, l’authentification et autorisation repose sur l’échange de jetons de sécurité ; Ces jetons accordent l’accès à un ensemble spécifique de ressources pour une durée spécifique.
  
Authentification OAuth implique trois parties : un serveur d’autorisation unique et les deux domaines qui doivent communiquer entre eux. (Vous pouvez également faire authentification de serveur à serveur sans l’aide d’un serveur d’autorisation, un processus qui seront abordé plus loin dans ce document). Jetons de sécurité émis par le serveur d’autorisation (également appelé un jeton serveur de sécurité) pour les deux domaines qui doivent communiquer ; Ces jetons de vérifier que les communications provenant d’un domaine doit être approuvées par le domaine d’autres. Par exemple, le serveur d’autorisation peut-être émettre des jetons de vérifier que les utilisateurs d’un Skype spécifique pour le domaine du serveur d’entreprise sont en mesure d’accéder à un domaine Exchange spécifié et vice versa.
  
> [!NOTE]
> Un domaine est tout simplement un conteneur de sécurité. Par défaut, Skype pour Business Server utilise votre domaine SIP de par défaut en tant que son domaine OAuth. Des espaces de noms SIP supplémentaires sont ajoutés à la liste Autre nom du sujet du certificat dans le certificat OAuth. 
  
Skype pour Business Server prend en charge trois scénarios d’authentification de serveur à serveur. Avec Skype pour Business Server, vous pouvez :
  
- Configurer l’authentification de serveur à serveur entre une installation locale de Skype pour Business Server et une installation locale de SharePoint Server ou d’Exchange.
    
- Configurer l’authentification de serveur à serveur entre une paire de composants Office 365 (par exemple, entre Microsoft Exchange Server et Skype pour Business Server ou entre Skype pour Business Server et SharePoint).
    
- Configurer l’authentification de serveur à serveur dans un environnement intersite (autrement dit, l’authentification serveur à serveur entre un serveur local et un composant d’Office 365).
    
Notez que, à ce stade, seul Exchange 2013, SharePoint Server, Lync Server 2013, Skype pour Business Server 2015 et Skype pour Business 2019 prennent en charge l’authentification de serveur à serveur ; Si vous n’exécutez pas un de ces serveurs, vous ne pourrez pas entièrement implémenter l’authentification OAuth.
  
Il convient également de souligner ce serveur pour l’authentification est facultative : si Skype pour Business Server ne doit pas communiquer avec d’autres serveurs (tels que Exchange), puis l’authentification serveur à serveur permettre être ignorée. Si l’authentification de serveur à serveur est déjà configurée pour Lync Server 2013 et d’autres applications, il est inutile à nouveau faire pour Skype pour Business Server. 
  
Toutefois, l’authentification de serveur à serveur est requise si vous souhaitez utiliser certaines des fonctionnalités dans Skype pour Business Server, tels que le « magasin de contacts unifié. » Avec le magasin de contacts unifié, Skype Business Server informations de contact est stocké dans Exchange au lieu de dans Skype pour Business Server ; Cela permet aux utilisateurs d’avoir un seul ensemble de contacts est facilement accessible à partir de Skype pour les professionnels, Outlook ou Outlook Web Access. Étant donné que le magasin de contacts unifié nécessite Skype pour Business Server partager des informations avec Exchange, vous devez utiliser l’authentification de serveur à serveur afin de déployer la fonctionnalité. Authentification de serveur à serveur est également requise si vous choisissez d’utiliser Exchange d’archivage, dans lequel les transcriptions des sessions de messagerie instantanée sont enregistrées en tant que messages électroniques Exchange plutôt que sous forme d’enregistrements de base de données spécifique.
  
La version de Skype pour Business Server communiquer avec son équivalent Exchange Office 365 Skype pour Business Server doit d’abord obtenir un jeton de sécurité à partir du serveur d’autorisation. Skype pour Business Server utilise ensuite ce jeton de sécurité pour identifier à Exchange. La version d’Office 365 d’Exchange doit passer par le même processus pour pouvoir communiquer avec Skype pour Business Server.
  
Toutefois, en ce qui concerne l’authentification de serveur à serveur entre deux serveurs Microsoft, il n’est pas nécessaire d’utiliser un serveur de jetons tiers. Produits serveur tels que Skype pour Business Server et Exchange ont un serveur de jetons intégré qui peut être utilisé pour l’authentification avec d’autres serveurs Microsoft (tels que SharePoint Server) qui prennent en charge l’authentification de serveur à serveur. Par exemple, Skype pour Business Server permettre émettre et signer un jeton de sécurité à lui-même, puis utiliser ce jeton pour communiquer avec Exchange. Dans ce cas, aucun serveur de jetons tiers n’est nécessaire.
  
Pour configurer l’authentification de serveur à serveur pour une implémentation locale de Skype pour Business Server, vous devez effectuer deux opérations :
  
- Assigner un certificat à le Skype intégrée pour l’émetteur de jeton Business Server.
    
- Configurer le serveur qui communique avec Skype pour Business Server comme « application partenaire ». Par exemple, si Skype pour Business Server doit communiquer avec Exchange, vous devez configurer Exchange pour qu’il soit une application partenaire.
    
> [!NOTE]
> « Application partenaire » est n’importe quelle application Skype pour Business Server peut directement échanger les jetons de sécurité, sans avoir à passer par un serveur de jeton de sécurité tiers. 
  
Notez qu’OAuth est un composant de base du produit et ne peut être ni désactivé ni supprimé.
  
## <a name="see-also"></a>Voir aussi

[Affecter un certificat d’authentification de serveur à serveur à Skype pour Business Server](assign-a-server-to-server-certificate.md)
  
[Configurer un environnement hybride dans Skype pour Business Server](configure-a-hybrid-environment.md)
