---
title: Planification de l’authentification moderne (ADAL) avec Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: Cet article décrit l’authentification moderne (qui est basée sur la bibliothèque d’authentification Active Directory (ADAL) et la 2,0 OAuth) est.
ms.openlocfilehash: c984e2468e1735a46c5246806afc57dd67327990
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297294"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Comment utiliser l’authentification moderne (ADAL) avec Skype Entreprise
 
Cet article présente l’authentification moderne (qui est basée sur la bibliothèque d’authentification Active Directory (ADAL) et la 2,0 OAuth, disponible dans la mise à jour cumulative de mars 2016 de Skype entreprise pour Skype entreprise Server 2015 ou à partir de l’initiale version de Skype entreprise Server 2019.
  
## <a name="what-is-adal"></a>Qu’est-ce que la bibliothèque ADAL ?

ADAL est l’acronyme de’Active Directory Authentication Library’et, en plus de la 2,0 OAuth, il s’agit d’une authentification moderne. Cette bibliothèque de codes est conçue pour rendre les ressources sécurisées dans votre annuaire accessibles aux applications clientes (comme Skype entreprise) via des jetons de sécurité. ADAL fonctionne avec OAuth 2,0 pour permettre d’utiliser davantage de scénarios d’authentification et d’autorisation, par exemple, l’authentification multifacteur (MFA) et d’autres formes d’authentification SAML.
  
Diverses applications qui agissent en tant que clients peuvent exploiter l’authentification moderne afin d’obtenir de l’aide pour sécuriser des ressources. Dans Skype entreprise Server, cette technologie est utilisée entre des clients locaux et des serveurs locaux afin de fournir aux utilisateurs un niveau d’autorisation approprié aux ressources.
  
Les conversations d’authentification moderne (qui sont basées sur la bibliothèque ADAL et OAuth 2.0) ont certains éléments en commun.
  
- Un client effectue une demande de ressource, dans le cas présent, le client est Skype entreprise.
    
- Il existe une ressource dont le client a besoin d’un niveau d’accès spécifique et cette ressource est sécurisée par un service d’annuaire, dans ce cas, la ressource est Skype entreprise Server.
    
- Il existe une connexion OAuth, en d’autres termes, une connexion qui est dédiée à l' *autorisation* d’un utilisateur pour accéder à une ressource. (OAuth est également connue sous le nom plus descriptif d’authentification « serveur à serveur » et est souvent abrégée S2S.)
    
Dans les conversations d’authentification moderne de Skype entreprise Server (ADAL), Skype entreprise Server communique via ADFS (ADFS 3,0 dans Windows Server 2012 R2). L’authentification peut se produire avec un autre fournisseur d’identité (IdP), mais Skype Entreprise Server doit être configuré pour communiquer directement avec ADFS. Si vous n’avez pas configuré ADFS pour fonctionner avec Skype entreprise Server, procédez à l' [installation d’ADFS](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL est inclus dans la mise à jour cumulative de mars 2016 pour Skype entreprise Server 2015 et la mise à jour cumulative de mars 2016 de Skype entreprise **doit** être installée et requise pour une configuration réussie. Pour Skype entreprise Server 2019, il est disponible à partir de la version initiale du produit.
  
> [!NOTE]
> Dans la version initiale, l’authentification moderne dans un environnement local est uniquement prise en charge s’il n’y a pas de topologie Skype mixte impliquée. Par exemple, si l’environnement est purement Skype entreprise Server. Cet énoncé pourrait être modifié. 
  
Un package PowerShell comprenant des fichiers .ps1 avec les commandes utilisées par la bibliothèque ADAL doit être téléchargé pour que la configuration aboutisse.

Pour plus d’informations sur la manière d’implémenter l’authentification moderne dans Skype entreprise, reportez-vous à la rubrique: [comment utiliser l’authentification moderne (Adal) avec Skype entreprise](../../manage/authentication/use-adal.md)
