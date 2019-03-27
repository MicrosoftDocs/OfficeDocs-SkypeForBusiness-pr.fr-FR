---
title: Planification de nouveau l’authentification (ADAL) avec Skype pour les entreprises
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: Cet article explique ce que l’authentification moderne (lequel est basé sur la bibliothèque de l’authentification Active Directory (ADAL) et OAuth 2.0) est.
ms.openlocfilehash: 0c3aeef2480494e45a4d18589b3e3cdc6d9c5357
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891208"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Comment utiliser l’authentification moderne (ADAL) avec Skype Entreprise
 
Cet article présente modernes d’authentification (qui est basé sur la bibliothèque de l’authentification Active Directory (ADAL) et OAuth 2.0) qui peuvent se trouver dans le 2016 mars mise à jour Cumulative pour Skype pour les entreprises pour Skype pour Business Server 2015, ou d’initial version de Skype pour Business Server 2019.
  
## <a name="what-is-adal"></a>Qu’est-ce que la bibliothèque ADAL ?

ADAL est l’acronyme de « Active Directory authentification Library », et ainsi que OAuth 2.0, il s’agit d’une base d’authentification moderne. Cette bibliothèque de code est conçue pour libérer des ressources sécurisées dans votre répertoire vers des applications clientes (par exemple, Skype pour les entreprises) par le biais des jetons de sécurité. ADAL fonctionne avec OAuth 2.0 pour activer les autres scénarios d’authentification et d’autorisation, telles que l’authentification multifacteur (MFA) et plusieurs formes d’authentification SAML
  
Diverses applications qui agissent en tant que clients peuvent exploiter l’authentification moderne afin d’obtenir de l’aide pour sécuriser des ressources. Dans Skype pour Business Server, cette technologie est utilisée entre les clients locaux et les serveurs locaux afin de donner aux utilisateurs un niveau d’autorisation aux ressources approprié.
  
Les conversations d’authentification moderne (qui sont basées sur la bibliothèque ADAL et OAuth 2.0) ont certains éléments en commun.
  
- Il existe un client effectue une demande pour une ressource, dans ce cas, le client est Skype pour les entreprises.
    
- Il existe une ressource à laquelle le client a besoin d’un niveau spécifique d’accès, et cette ressource est sécurisée par un service d’annuaire, dans ce cas la ressource est Skype pour Business Server.
    
- Il existe une connexion OAuth, en d’autres termes, une connexion est dédiée *à* un utilisateur pour accéder à une ressource. (OAuth est également connue sous le nom plus descriptif d’authentification « serveur à serveur » et est souvent abrégée S2S.)
    
Dans Skype pour les conversations Business Server modernes d’authentification (ADAL), Skype pour Business Server communique par le biais de services ADFS (3.0 ADFS dans Windows Server 2012 R2). L’authentification peut se produire avec un autre fournisseur d’identité (IdP), mais Skype Entreprise Server doit être configuré pour communiquer directement avec ADFS. Si vous n’avez pas configuré pour fonctionner avec Skype pour Business Server ADFS, veuillez effectuer l' [installation des services AD FS](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL est incluse dans le 2016 mars mise à jour Cumulative pour Skype pour Business Server 2015 et le 2016 mars mise à jour Cumulative pour Skype pour Business **doit** être installé et est nécessaire pour la configuration réussie. Skype pour Business Server 2019, il est disponible dans la version initiale du produit.
  
> [!NOTE]
> Dans la version initiale, l’authentification moderne dans un environnement local est uniquement prise en charge s’il n’y a pas de topologie Skype mixte impliquée. Par exemple, si l’environnement est purement Skype pour Business Server. Cet énoncé pourrait être modifié. 
  
Un package PowerShell comprenant des fichiers .ps1 avec les commandes utilisées par la bibliothèque ADAL doit être téléchargé pour que la configuration aboutisse.

Pour plus d’informations sur la façon d’implémenter l’authentification moderne dans Skype pour les entreprises, reportez-vous à : [comment utiliser l’authentification moderne (ADAL) avec Skype pour les entreprises](../../manage/authentication/use-adal.md)
