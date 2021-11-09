---
title: Planification de l’authentification moderne (ADAL) avec Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Cet article explique ce qu’est l’authentification moderne (basée sur la bibliothèque d’authentification Active Directory (ADAL) et OAuth 2.0).
ms.openlocfilehash: 40bf87317b68e258fc6576b1ce7be7b8decc6939
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834080"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Comment utiliser l’authentification moderne (ADAL) avec Skype Entreprise
 
Cet article présente l’authentification moderne (basée sur la bibliothèque d’authentification Active Directory (ADAL) et OAuth 2.0) qui se trouve dans la mise à jour cumulative de mars 2016 pour Skype Entreprise pour Skype Entreprise Server 2015 ou à partir de la version initiale pour Skype Entreprise Server 2019.
  
## <a name="what-is-adal"></a>Qu’est-ce qu’ADAL ?

ADAL est l’acronyme de la « bibliothèque d’authentification Active Directory » et, avec OAuth 2.0, il s’agit d’un sous-programme de l’authentification moderne. Cette bibliothèque de code est conçue pour rendre les ressources sécurisées dans votre répertoire accessibles aux applications clientes (comme Skype Entreprise) via des jetons de sécurité. ADAL fonctionne avec OAuth 2.0 pour activer davantage de scénarios d’authentification et d’autorisation, tels que l’authentification multifacteur (MFA) et d’autres formes d’authentification SAML.
  
De nombreuses applications qui agissent en tant que clients peuvent tirer parti de l’authentification moderne pour obtenir de l’aide sur la sécurisation des ressources. Dans Skype Entreprise Server, cette technologie est utilisée entre les clients locaux et les serveurs locaux afin de donner aux utilisateurs un niveau d’autorisation approprié pour les ressources.
  
Les conversations d’authentification moderne (basées sur ADAL et OAuth 2.0) ont certains éléments en commun.
  
- Il existe un client qui demande une ressource, dans ce cas, le client est Skype Entreprise.
    
- Il existe une ressource à laquelle le client a besoin d’un niveau d’accès spécifique, et cette ressource est sécurisée par un service d’annuaire, dans ce cas, la ressource est Skype Entreprise Server.
    
- Il existe une connexion OAuth, en d’autres  termes, une connexion dédiée à l’autorisation d’un utilisateur à accéder à une ressource. (OAuth est également connu sous le nom plus descriptif « Th de serveur à serveur » et est souvent abrégé en S2S.)
    
Dans Skype Entreprise Server d’authentification moderne (ADAL), Skype Entreprise Server communique via ADFS (ADFS 3.0 dans Windows Server 2012 R2). L’authentification peut se produire à l’aide d’un autre fournisseur d’identité (IdP), mais le serveur Skype Entreprise doit être configuré pour communiquer directement avec ADFS. Si vous n’avez pas configuré ADFS pour qu’il fonctionne Skype Entreprise Server terminez [l’installation ADFS.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))
  
ADAL est inclus dans la mise à jour cumulative de mars 2016 pour Skype Entreprise Server 2015,  et la mise à jour cumulative de mars 2016 pour Skype Entreprise doit être installée et nécessaire pour réussir la configuration. Pour Skype Entreprise Server 2019, il est disponible à partir de la version initiale du produit.
  
> [!NOTE]
> Lors de la version initiale, l’authentification moderne dans un environnement local n’est prise en charge que si aucune topologie Skype n’est impliquée. Par exemple, si l’environnement est purement Skype Entreprise Server. Cette instruction peut faire l’objet de changements. 
  
Un package PowerShell incluant .ps1 fichiers avec les commandes utilisées par ADAL doit être téléchargé pour que la configuration soit réussie.

Pour plus d’informations sur l’implémenter l’authentification moderne dans Skype Entreprise, voir : Comment utiliser l’authentification moderne [(ADAL) avec Skype Entreprise](/microsoft-365/enterprise/hybrid-modern-auth-overview)