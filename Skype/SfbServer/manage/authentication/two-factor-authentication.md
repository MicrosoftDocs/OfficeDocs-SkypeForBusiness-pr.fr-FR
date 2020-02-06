---
title: Gestion de l’authentification à deux facteurs dans Skype entreprise Server
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
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Résumé : gestion de l’authentification à deux facteurs dans Skype entreprise Server.'
ms.openlocfilehash: 90dc286e247c0c6eeb75bb884071b85e57663278
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818716"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Gestion de l’authentification à deux facteurs dans Skype entreprise Server
 
**Résumé :** Gestion de l’authentification à deux facteurs dans Skype entreprise Server.
  
L’authentification à deux facteurs améliore la sécurité en exigeant que les utilisateurs fournissent deux formes d’authentification ou d’identification, à savoir un nom d’utilisateur/mot de passe et un jeton ou un certificat. Ce problème est également connu sous le nom de « ce que vous connaissez ». 
  
Un exemple type d’authentification à deux facteurs avec un certificat est l’utilisation de cartes à puce. Une carte à puce contient un certificat associé au compte d’utilisateur. Elle peut être validée à partir d’informations utilisateur et de certificat stockées sur un serveur. En comparant les informations de l’utilisateur (nom et mot de passe d’utilisateur) au certificat fourni, le serveur valide les informations d’identification et authentifie l’utilisateur.
  
Prenez en compte les sujets suivants lorsque vous configurez un environnement Skype entreprise Server pour prendre en charge l’authentification à deux facteurs.
  
## <a name="client-support"></a>Prise en charge des clients

Les mises à jour cumulatives de Lync Server 2013 : le client de bureau 2013 de juillet et le client Skype entreprise sont les seuls clients qui prennent actuellement en charge l’authentification à deux facteurs.
  
## <a name="topology-requirements"></a>Conditions requises pour la topologie

Les clients sont fortement encouragés à déployer l’authentification à deux facteurs à l’aide de Skype entreprise Server dédié avec Edge, directeur et pools d’utilisateurs. Pour activer l’authentification passive pour les utilisateurs, les autres méthodes d’authentification doivent être désactivées pour les autres rôles et services, dont les suivantes :
  
|**Type de configuration**|**Type de service**|**Rôle du serveur**|**Type d’authentification à désactiver**|
|:-----|:-----|:-----|:-----|
|Service web  <br/> |WebServer  <br/> |Directeur  <br/> |Kerberos, NTLM et par certificat  <br/> |
|Service web  <br/> |WebServer  <br/> |Serveur frontal  <br/> |Kerberos, NTLM et par certificat  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos et NTLM  <br/> |
|Proxy  <br/> |Serveur d’inscriptions avancé  <br/> |Serveur frontal  <br/> |Kerberos et NTLM  <br/> |
   
Sauf si ces types d’authentifications sont désactivés au niveau du service, toutes les autres versions du client ne pourront pas se connecter correctement une fois l’authentification à deux facteurs activée dans votre déploiement.
  
## <a name="skype-for-business-service-discovery"></a>Fonction de découverte automatique de Skype Entreprise

Les enregistrements DNS utilisés par les clients internes et/ou externes pour détecter les services Skype entreprise doivent être configurés pour s’authentifier auprès d’un serveur Skype entreprise qui n’est pas activé pour l’authentification à deux facteurs. Dans le cadre de cette configuration, les utilisateurs des groupes Skype entreprise qui ne sont pas activés pour l’authentification à deux facteurs ne seront pas obligés d’entrer un code confidentiel pour s’authentifier, tandis que les utilisateurs de groupes Skype entreprise activés pour l’authentification à deux facteurs seront requis pour entrer son code confidentiel pour s’authentifier.
  
## <a name="exchange-authentication"></a>Authentification Exchange

Les clients qui ont déployé l’authentification à deux facteurs pour Microsoft Exchange peuvent constater que certaines fonctionnalités du client ne sont pas disponibles. Cette fonction est actuellement à l’étude, car le client Skype entreprise ne prend pas en charge l’authentification à deux facteurs pour les fonctionnalités qui dépendent de l’intégration d’Exchange.
  
## <a name="contacts"></a>Contacts

Les utilisateurs de Skype entreprise qui sont configurés pour tirer parti de la fonctionnalité de magasin de contacts unifiée pourront constater que leurs contacts ne sont plus disponibles une fois que vous êtes connecté à l’aide de l’authentification à deux facteurs.
  
Pour activer l’authentification à deux facteurs, vous devez utiliser l’applet de passe **Invoke-CsUcsRollback** pour supprimer les contacts des utilisateurs existants du magasin de contacts unifié et les stocker dans Skype entreprise Server.
  
## <a name="skill-search"></a>Recherche de compétences

Les clients qui ont configuré la fonction de recherche de compétences dans leur environnement Skype entreprise constateront que cette fonctionnalité n’est pas compatible avec l’authentification à deux facteurs dans Skype entreprise. Ce comportement est normal, car Microsoft SharePoint ne prend pas en charge l’authentification à deux facteurs pour le moment.
  
## <a name="credentials"></a>Informations d’identification

Diverses considérations de déploiement impliquent des informations d’identification Skype entreprise enregistrées qui peuvent avoir un impact sur les utilisateurs qui sont configurés pour utiliser l’authentification à deux facteurs.
  
### <a name="deleting-saved-credentials"></a>Suppression des informations d’identification enregistrées

Les utilisateurs doivent utiliser l’option **Supprimer mes informations de connexion** dans le client Skype entreprise et supprimer leur dossier de profil SIP de%LocalAppData%\Microsoft\Office\15.0\Skype entreprise avant d’essayer de vous connecter pour la première fois à l’aide de l’authentification à deux facteurs.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

À l’aide de la méthode d’authentification Kerberos ou NTLM, les informations d’identification Windows de l’utilisateur sont automatiquement utilisées pour l’authentification. Dans le cas d’un déploiement standard de Skype entreprise Server sur lequel Kerberos et/ou NTLM est activé pour l’authentification, l’utilisateur ne doit pas entrer ses informations d’identification chaque fois qu’il se connecte.
  
Si les utilisateurs sont invités à entrer leurs informations d’identification avant leur code confidentiel, la clé de Registre **DisableNTCredentials** est peut être configurée involontairement sur les ordinateurs clients, éventuellement par le biais de la stratégie de groupe.
  
Pour éviter l’invite supplémentaire pour les informations d’identification, créez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration de Skype entreprise pour appliquer à tous les utilisateurs pour un pool donné à l’aide d’une stratégie de groupe :
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Lorsqu’un utilisateur se connecte à Skype entreprise pour la première fois, l’utilisateur est invité à enregistrer son mot de passe. Si cette option est sélectionnée, le certificat client de l’utilisateur doit être stocké dans le magasin de certificats personnels et les informations d’identification Windows de l’utilisateur doivent être stockées dans le gestionnaire d’informations d’identification de l’ordinateur local.
  
Le paramètre de Registre **SavePassword** doit être désactivé lorsque Skype entreprise est configuré pour prendre en charge l’authentification à deux facteurs. Pour empêcher les utilisateurs d’enregistrer leur mot de passe, modifiez l’entrée de Registre suivante sur la station de travail locale ou utilisez le modèle d’administration de Skype entreprise pour appliquer à tous les utilisateurs pour un pool donné via une stratégie de groupe :
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>Relecture des jetons d’AD FS 2.0

La fonctionnalité d’AD FS 2.0 de détection de relecture des jetons détecte et rejette les demandes de jeton multiples effectuées à l’aide d’un même jeton. Lorsqu’elle est activée, elle protège l’intégrité des demandes d’authentification dans le profil passif WS-Federation et le profil SAML WebSSO en vérifiant que le même jeton n’est pas utilisé plusieurs fois.
  
Cette fonctionnalité doit être activée dans les cas dans lesquels la sécurité constitue un aspect essentiel, par exemple, dans le cadre de l’utilisation des kiosques. Pour plus d’informations sur la détection de relecture de jeton, voir recommandations en matière [de planification et de déploiement sécurisés d’AD FS 2,0](https://go.microsoft.com/fwlink/p/?LinkId=309215).
  
## <a name="external-user-access"></a>Accès des utilisateurs externes

La configuration d’un proxy ADFS ou d’un proxy inverse pour la prise en charge de l’authentification à deux facteurs de Skype entreprise par le biais de réseaux externes n’est pas abordée dans les rubriques suivantes.
  
## <a name="see-also"></a>Voir aussi

[Configurer l’authentification à deux facteurs dans Skype entreprise Server](configure-two-factor.md)
  
