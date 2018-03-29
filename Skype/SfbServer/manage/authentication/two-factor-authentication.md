---
title: Gestion de l’authentification à deux facteurs dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Résumé : Gérer l’authentification à deux facteurs dans Skype pour Business Server 2015.'
ms.openlocfilehash: 5933afc311514e841d7fb96f41988d8f495d0bee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server-2015"></a>Gestion de l’authentification à deux facteurs dans Skype Entreprise Server 2015
 
**Résumé :** Gérer l’authentification à deux facteurs dans Skype pour Business Server 2015.
  
L’authentification à deux facteurs améliore la sécurité en exigeant que les utilisateurs fournissent deux formes d’authentification ou d’identification, à savoir un nom d’utilisateur/mot de passe et un jeton ou un certificat. Cela est également connu sous le nom « quelque chose que vous avez, quelque chose que vous savez. » 
  
Un exemple type d’authentification à deux facteurs avec un certificat est l’utilisation de cartes à puce. Une carte à puce contient un certificat associé au compte d’utilisateur. Elle peut être validée à partir d’informations utilisateur et de certificat stockées sur un serveur. En comparant les informations de l’utilisateur (nom et mot de passe d’utilisateur) au certificat fourni, le serveur valide les informations d’identification et authentifie l’utilisateur.
  
Prendre en compte les points suivants lors de la configuration d’un Skype pour environnement d’entreprise serveur 2015 pour prendre en charge de l’authentification à deux facteurs.
  
## <a name="client-support"></a>Prise en charge des clients

Les mises à jour cumulatives de Lync Server 2013 : juillet 2013 client ordinateur de bureau et le Skype pour client d’entreprise sont les seuls clients qui prend actuellement en charge l’authentification à deux facteurs.
  
## <a name="topology-requirements"></a>Conditions requises pour la topologie

Les clients sont vivement encouragés à déployer l’authentification à deux facteurs avec Skype dédié pour Business Server 2015 bord, directeur et les Pools de l’utilisateur. Pour activer l’authentification passive pour les utilisateurs, les autres méthodes d’authentification doivent être désactivées pour les autres rôles et services, dont les suivantes :
  
|**Type de configuration**|**Type de service**|**Rôle de serveur**|**Type d’authentification à désactiver**|
|:-----|:-----|:-----|:-----|
|Service web  <br/> |Serveur Web  <br/> |Directeur  <br/> |Kerberos, NTLM et par certificat  <br/> |
|Service web  <br/> |Serveur Web  <br/> |Serveur frontal  <br/> |Kerberos, NTLM et par certificat  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos et NTLM  <br/> |
|Proxy  <br/> |Serveur d’inscriptions avancé  <br/> |Serveur frontal  <br/> |Kerberos et NTLM  <br/> |
   
Sauf si ces types d’authentifications sont désactivés au niveau du service, toutes les autres versions du client ne pourront pas se connecter correctement une fois l’authentification à deux facteurs activée dans votre déploiement.
  
## <a name="skype-for-business-service-discovery"></a>Fonction de découverte automatique de Skype Entreprise

Enregistrements DNS utilisés par les clients internes ou externes pour découvrir Skype pour les services doivent être configurés pour résoudre à un Skype pour Business server qui n’est pas activé pour l’authentification à deux facteurs. Avec cette configuration, les utilisateurs de Skype pour les Pools d’entreprise qui ne sont pas activés pour l’authentification à deux facteurs pas devront entrer un code PIN pour authentifier, alors que les utilisateurs de Skype pour les Pools d’entreprise qui sont activés pour l’authentification à deux facteurs invité à entrer son code PIN pour authentifier.
  
## <a name="exchange-authentication"></a>Authentification Exchange

Les clients qui ont déployé l’authentification à deux facteurs pour Microsoft Exchange peuvent trouver que certaines fonctionnalités du client ne sont pas disponibles. Il s’agit actuellement à la conception, comme le Skype pour client d’entreprise ne gère pas l’authentification à deux facteurs pour les fonctionnalités qui dépendent d’intégration d’Exchange.
  
## <a name="contacts"></a>Contacts

Skype pour les utilisateurs professionnels qui sont configurés pour tirer parti de la fonctionnalité de magasin de contacts unifiée trouveront que leurs contacts ne sont plus disponibles après la connexion avec l’authentification à deux facteurs.
  
Vous devez utiliser l’applet de commande **Invoke-CsUcsRollback** pour supprimer les contacts des utilisateurs existants à partir du magasin de contacts unifiée et de les stocker dans Skype pour Business Server 2015 avant d’activer l’authentification à deux facteurs.
  
## <a name="skill-search"></a>Recherche de compétences

Les utilisateurs ayant configuré de la fonctionnalité de recherche de compétences dans leur Skype pour entreprises trouveront que cette fonctionnalité ne fonctionne pas lorsque Skype pour entreprise est activé pour l’authentification à deux facteurs. Ce comportement est normal, car Microsoft SharePoint ne prend pas en charge l’authentification à deux facteurs pour le moment.
  
## <a name="credentials"></a>Informations d’identification

Il existe un certain nombre de considérations relatives au déploiement impliquant Skype enregistré vos informations d’identification d’entreprise qui peut avoir un impact sur les utilisateurs qui sont configurés pour utiliser l’authentification à deux facteurs.
  
### <a name="deleting-saved-credentials"></a>Suppression des informations d’identification enregistrées

Les utilisateurs doivent utiliser l’option **Supprimer mes informations de connexion** dans le Skype pour le client Business et supprimer leur dossier de profil SIP à partir de %localappdata%\Microsoft\Office\15.0\Skype pour l’entreprise avant de tenter de vous connecter pour la première fois à l’aide de deux facteurs authentification.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Avec la méthode d’authentification Kerberos ou NTLM, les informations d’identification Windows de l’utilisateur sont utilisées automatiquement pour l’authentification. Dans un type Skype pour le déploiement de Business Server 2015 où Kerberos et/ou NTLM est activé pour l’authentification, les utilisateurs devront pas entrer leurs informations d’identification chaque fois qu’ils se connectent.
  
Si les utilisateurs sont invités à entrer leurs informations d’identification avant leur code confidentiel, la clé de Registre **DisableNTCredentials** est peut être configurée involontairement sur les ordinateurs clients, éventuellement par le biais de la stratégie de groupe.
  
Pour éviter l’invite de commande supplémentaire pour les informations d’identification, créez l’entrée de Registre suivante sur la station de travail ou utiliser le Skype pour le modèle d’administration d’entreprise à appliquer à tous les utilisateurs d’un pool donné à l’aide de la stratégie de groupe :
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Lorsqu’un utilisateur se connecte à Skype pour les entreprises pour la première fois, l’utilisateur est invité à enregistrer son mot de passe. Si activée, cette option permet de certificat de client de l’utilisateur sont stockées dans le magasin de certificats personnels et les informations d’identification Windows de l’utilisateur doivent être stockées dans le Gestionnaire d’informations d’identification de l’ordinateur local.
  
Le paramètre de Registre **SavePassword** doit être désactivé lorsque Skype pour entreprise est configuré pour prendre en charge de l’authentification à deux facteurs. Pour empêcher les utilisateurs d’enregistrer leurs mots de passe, modifiez l’entrée de Registre suivante sur la station de travail ou utiliser le Skype pour le modèle d’administration d’entreprise à appliquer à tous les utilisateurs d’un pool donné à l’aide de la stratégie de groupe :
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>Relecture des jetons d’AD FS 2.0

La fonctionnalité d’AD FS 2.0 de détection de relecture des jetons détecte et rejette les demandes de jeton multiples effectuées à l’aide d’un même jeton. Lorsqu’elle est activée, elle protège l’intégrité des demandes d’authentification dans le profil passif WS-Federation et le profil SAML WebSSO en vérifiant que le même jeton n’est pas utilisé plusieurs fois.
  
Cette fonctionnalité doit être activée dans les cas dans lesquels la sécurité constitue un aspect essentiel, par exemple, dans le cadre de l’utilisation des kiosques. Pour plus d’informations sur la détection de relecture de jeton, consultez [Méthodes conseillées pour sécuriser la planification et le déploiement d’AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).
  
## <a name="external-user-access"></a>Accès des utilisateurs externes

Configuration d’un Proxy d’ADFS ou un Reverse Proxy pour prendre en charge Skype pour l’authentification à deux facteurs métier à partir de réseaux externes n’est pas couverte dans ces rubriques.
  
## <a name="see-also"></a>Voir aussi

#### 

[Configurer l’authentification à deux facteurs dans Skype pour Business Server 2015](configure.md)
  
[Configurer l’authentification à deux facteurs dans Skype pour Business Server 2015](configure.md)

