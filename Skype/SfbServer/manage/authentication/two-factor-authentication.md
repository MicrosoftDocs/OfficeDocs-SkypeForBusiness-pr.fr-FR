---
title: Gérer l’authentification à deux facteurs dans Skype Entreprise Server
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
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Résumé : Gérez l’authentification à deux facteurs dans Skype Entreprise Server.'
ms.openlocfilehash: d5d5500cbcab93f53e58626bf5826dcc060903e2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747170"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Gérer l’authentification à deux facteurs dans Skype Entreprise Server
 
**Résumé :** Gérer l’authentification à deux facteurs dans Skype Entreprise Server.
  
L’authentification à deux facteurs améliore la sécurité en exigeant que les utilisateurs fournissent deux formes d’authentification ou d’identification, à savoir une combinaison nom d’utilisateur/mot de passe et un jeton ou un certificat. C’est également ce que l’on appelle « quelque chose que vous avez, quelque chose que vous savez ». 
  
L’utilisation de cartes à puce est un exemple classique d’authentification à deux facteurs avec un certificat. Une carte à puce contient un certificat associé au compte d’utilisateur et peut être validée par rapport aux informations utilisateur et de certificat stockées sur un serveur. En comparant les informations utilisateur (nom d’utilisateur et mot de passe) au certificat fourni, le serveur valide les informations d’identification et authentifier l’utilisateur.
  
Prenons les sujets suivants lors de la configuration d’un environnement Skype Entreprise Server pour prendre en charge l’authentification à deux facteurs.
  
## <a name="client-support"></a>Prise en charge du client

Les mises à jour cumulatives pour le client de bureau Lync Server 2013 de juillet 2013 et le client Skype Entreprise sont les seuls clients qui actuellement la prise en charge de l’authentification à deux facteurs.
  
## <a name="topology-requirements"></a>Conditions requises pour la topologie

Les clients sont encouragés à déployer l’authentification à deux facteurs à l’aide de Skype Entreprise Server avec edge, directeur et pools d’utilisateurs. Pour activer l’authentification passive pour les utilisateurs, d’autres méthodes d’authentification doivent être désactivées pour d’autres rôles et services, notamment :
  
|**Configuration Type**|**Type de service**|**Rôle serveur**|**Type d’authentification à désactiver**|
|:-----|:-----|:-----|:-----|
|Service Web  <br/> |WebServer  <br/> |Directeur  <br/> |Kerberos, NTLM et certificat  <br/> |
|Service Web  <br/> |WebServer  <br/> |Serveur frontal  <br/> |Kerberos, NTLM et certificat  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Microsoft Edge  <br/> |Kerberos et NTLM  <br/> |
|Proxy  <br/> |Registrar  <br/> |Serveur frontal  <br/> |Kerberos et NTLM  <br/> |
   
À moins que ces types d’authentification ne soient désactivés au niveau du service, toutes les autres versions du client ne pourront pas se connecter correctement une fois l’authentification à deux facteurs activée dans votre déploiement.
  
## <a name="skype-for-business-service-discovery"></a>Skype Entreprise Découverte de service

Les enregistrements DNS utilisés par les clients internes et/ou externes pour découvrir les services Skype Entreprise doivent être configurés pour être résolus en un serveur Skype Entreprise qui n’est pas activé pour l’authentification à deux facteurs. Avec cette configuration, les utilisateurs des pools Skype Entreprise qui ne sont pas activés pour l’authentification à deux facteurs ne seront pas obligés d’entrer un code confidentiel pour s’authentifier, tandis que les utilisateurs des pools Skype Entreprise qui sont activés pour l’authentification à deux facteurs devront entrer leur code confidentiel pour s’authentifier.
  
## <a name="exchange-authentication"></a>Exchange Authentification

Les clients qui ont déployé l’authentification à deux facteurs pour Microsoft Exchange peuvent découvrir que certaines fonctionnalités du client ne sont pas disponibles. Ce comportement est de par sa conception, car le client Skype Entreprise ne prend pas en charge l’authentification à deux facteurs pour les fonctionnalités qui dépendent de Exchange’intégration.
  
## <a name="contacts"></a>Contacts

Skype Entreprise utilisateurs configurés pour tirer parti de la fonctionnalité magasin de contacts unifié trouveront que leurs contacts ne sont plus disponibles après la signature avec l’authentification à deux facteurs.
  
Vous devez utiliser l’cmdlet **Invoke-CsUcsRollback** pour supprimer les contacts utilisateur existants du magasin de contacts unifié et les stocker dans Skype Entreprise Server avant d’activer l’authentification à deux facteurs.
  
## <a name="skill-search"></a>Recherche de compétences

Les clients qui ont configuré la fonctionnalité Recherche de compétences dans leur environnement Skype Entreprise trouveront que cette fonctionnalité ne fonctionne pas lorsque Skype Entreprise est activé pour l’authentification à deux facteurs. Il s’agit d’une conception, car Microsoft SharePoint ne prend actuellement pas en charge l’authentification à deux facteurs.
  
## <a name="credentials"></a>Identifiants

Il existe un certain nombre de considérations de déploiement impliquant des informations d’Skype Entreprise enregistrées qui peuvent avoir un impact sur les utilisateurs configurés pour utiliser l’authentification à deux facteurs.
  
### <a name="deleting-saved-credentials"></a>Suppression des informations d’identification enregistrées

Les utilisateurs doivent utiliser l’option Supprimer mes informations de **sign-in** dans le client Skype Entreprise et supprimer leur dossier de profil SIP de %localappdata%\Microsoft\Office\15.0\Skype Entreprise avant d’essayer de se signer pour la première fois à l’aide de l’authentification à deux facteurs.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Avec la méthode d’authentification Kerberos ou NTLM, les informations d’identification Windows utilisateur sont utilisées automatiquement pour l’authentification. Dans un déploiement Skype Entreprise Server classique où Kerberos et/ou NTLM sont activés pour l’authentification, les utilisateurs ne doivent pas avoir à entrer leurs informations d’identification chaque fois qu’ils se connectent.
  
Si les utilisateurs sont involontairement invités à entrer leurs informations d’identification avant d’être invités à entrer leur code confidentiel, la clé de Registre **DisableNTCredentials** peut être involontairement configurée sur les ordinateurs clients, éventuellement par le biais de la stratégie de groupe.
  
Pour empêcher l’invite supplémentaire d’informations d’identification, créez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration Skype Entreprise à appliquer à tous les utilisateurs d’un pool donné à l’aide de la stratégie de groupe :
  
HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
REG_DWORD : DisableNTCredentials

Valeur : 0x0
  
### <a name="savepassword"></a>SavePassword

Lorsqu’un utilisateur se Skype Entreprise pour la première fois, il est invité à enregistrer son mot de passe. Si elle est sélectionnée, cette option permet de stocker le certificat client de l’utilisateur dans le magasin de certificats personnels et les informations d’identification Windows de l’utilisateur dans le Gestionnaire d’informations d’identification de l’ordinateur local.
  
Le paramètre de Registre **SavePassword** doit être désactivé lorsque Skype Entreprise est configuré pour prendre en charge l’authentification à deux facteurs. Pour empêcher les utilisateurs d’enregistrer leur mot de passe, modifiez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration Skype Entreprise pour l’appliquer à tous les utilisateurs d’un pool donné à l’aide de la stratégie de groupe :
  
HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
REG_DWORD : SavePassword
  
Valeur : 0x0
  
## <a name="ad-fs-20-token-replay"></a>Relecture de jeton AD FS 2.0

AD FS 2.0 fournit une fonctionnalité appelée détection de relecture de jeton, grâce à laquelle plusieurs demandes de jeton utilisant le même jeton peuvent être détectées, puis ignorées. Lorsque cette fonctionnalité est activée, la détection de relecture de jeton protège l’intégrité des demandes d’authentification dans le profil passif WS-Federation et le profil SAML WebSSO en vous assurer que le même jeton n’est jamais utilisé plusieurs fois.
  
Cette fonctionnalité doit être activée dans les situations où la sécurité est un problème très important, par exemple lors de l’utilisation de bornes. Pour plus d’informations sur la détection de relecture de jeton, voir [Best Practices for Secure Planning and Deployment of AD FS 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10)).
  
## <a name="guest-user-access"></a>Accès des utilisateurs invités

La configuration d’un proxy ADFS ou d’un proxy inverse pour prendre en charge Skype Entreprise’authentification à deux facteurs à partir de réseaux externes n’est pas couverte dans ces rubriques.
  
## <a name="see-also"></a>Voir aussi

[Configurer l’authentification à deux facteurs dans Skype Entreprise Server](configure-two-factor.md)
