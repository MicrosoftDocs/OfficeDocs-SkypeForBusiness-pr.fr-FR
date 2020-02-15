---
title: Planification de l’authentification moderne (ADAL) avec Skype entreprise
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
description: Cet article explique l’authentification moderne (basée sur la bibliothèque d’authentification Active Directory (ADAL) et OAuth 2,0).
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046287"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Utilisation de l’authentification moderne (ADAL) avec Skype entreprise
 
Cet article présente l’authentification moderne (basée sur la bibliothèque d’authentification Active Directory (ADAL) et le OAuth 2,0) qui se trouve dans la mise à jour cumulative de mars 2016 pour Skype entreprise pour Skype entreprise Server 2015 ou d’origine version pour Skype entreprise Server 2019.
  
## <a name="what-is-adal"></a>Qu’est-ce que ADAL ?

ADAL est l’acronyme de « Active Directory Authentication Library » et, avec OAuth 2,0, il s’agit d’un sous-jacente de l’authentification moderne. Cette bibliothèque de code est conçue pour mettre les ressources sécurisées dans votre répertoire à la disposition des applications clientes (par exemple Skype entreprise) via des jetons de sécurité. ADAL fonctionne avec OAuth 2,0 pour permettre davantage de scénarios d’authentification et d’autorisation, comme l’authentification multifacteur (MFA) et d’autres formes d’authentification SAML.
  
Diverses applications qui agissent comme des clients peuvent tirer parti de l’authentification moderne pour obtenir de l’aide sur l’accès aux ressources sécurisées. Dans Skype entreprise Server, cette technologie est utilisée entre les clients locaux et les serveurs locaux afin de donner aux utilisateurs un niveau d’autorisation approprié aux ressources.
  
Les conversations d’authentification modernes (qui sont basées sur ADAL et OAuth 2,0) ont des éléments en commun.
  
- Il existe un client qui demande une ressource, dans ce cas, le client est Skype entreprise.
    
- Il existe une ressource à laquelle le client a besoin d’un niveau d’accès spécifique, et cette ressource est sécurisée par un service d’annuaire, dans ce cas, la ressource est Skype entreprise Server.
    
- Il existe une connexion OAuth, en d’autres termes, une connexion dédiée à l' *autorisation* d’un utilisateur pour accéder à une ressource. (OAuth est également connu par le nom plus descriptif « l’authentification de serveur à serveur » et est souvent abrégé en S2S.)
    
Dans les conversations Skype entreprise Server moderne Authentication (ADAL), Skype entreprise Server communique via ADFS (ADFS 3,0 dans Windows Server 2012 R2). L’authentification peut se produire à l’aide d’un autre fournisseur d’identité (IdP), mais Skype entreprise Server doit être configuré pour communiquer avec ADFS directement. Si vous n’avez pas configuré ADFS pour qu’il fonctionne avec Skype entreprise Server, veuillez terminer l' [installation d’ADFS](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL est inclus dans la mise à jour cumulative de mars 2016 pour Skype entreprise Server 2015 et la mise à jour cumulative de mars 2016 pour Skype entreprise **doit** être installée et nécessaire pour une configuration réussie. Pour Skype entreprise Server 2019, il est disponible à partir de la version initiale du produit.
  
> [!NOTE]
> Lors de la publication initiale, l’authentification moderne dans un environnement local est prise en charge uniquement s’il n’y a pas de topologie Skype mixte impliquée. Par exemple, si l’environnement est purement Skype entreprise Server. Cette instruction peut être modifiée. 
  
Un package PowerShell incluant des fichiers. ps1 avec les commandes utilisées par ADAL doit être téléchargé pour une configuration réussie.

Pour plus d’informations sur l’implémentation de l’authentification moderne dans Skype entreprise, reportez-vous à : [comment utiliser l’authentification moderne (Adal) avec Skype entreprise](../../manage/authentication/use-adal.md)
