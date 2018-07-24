---
title: Comment utiliser l’authentification moderne (ADAL) avec Skype Entreprise
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: Cet article explique comment utiliser modernes d’authentification (qui est basé sur la bibliothèque de l’authentification Active Directory (ADAL) et OAuth 2.0) qui peuvent se trouver dans le 2016 mars mise à jour Cumulative pour Skype pour les entreprises pour Skype pour Business Server 2015.
ms.openlocfilehash: 4bf802d2710c9c271c54cf2e127cf51b24875db1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966572"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Comment utiliser l’authentification moderne (ADAL) avec Skype Entreprise
 
Cet article explique comment utiliser modernes d’authentification (qui est basé sur la bibliothèque de l’authentification Active Directory (ADAL) et OAuth 2.0) qui peuvent se trouver dans le 2016 mars mise à jour Cumulative pour Skype pour les entreprises pour Skype pour Business Server 2015.
  
## <a name="whats-in-this-article"></a>Quel est le contenu de cet article ?

[Qu’est-ce que la bibliothèque ADAL ?](use-adal.md#BKMK_ADAL)
  
[Configurez la bibliothèque ADAL dans votre pool et définissez ADFS en tant que serveur de jetons de sécurité](use-adal.md#BKMK_Config)
  
[Autres options d'activation de la connexion à la bibliothèque ADAL (par exemple, applications clientes Office)](use-adal.md#BKMK_Options)
  
[Clients pour lesquels l’authentification moderne/la bibliothèque ADAL n’est pas prise en charge](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a>Qu’est-ce que la bibliothèque ADAL ?
<a name="BKMK_ADAL"> </a>

ADAL est l’acronyme de « Active Directory authentification Library », et ainsi que OAuth 2.0, il s’agit d’une base d’authentification moderne. Cette bibliothèque de code est conçue pour libérer des ressources sécurisées dans votre répertoire vers des applications clientes (par exemple, Skype pour les entreprises) par le biais des jetons de sécurité. ADAL fonctionne avec OAuth 2.0 pour activer les autres scénarios d’authentification et d’autorisation, telles que l’authentification multifacteur (MFA) et plusieurs formes d’authentification SAML
  
Diverses applications qui agissent en tant que clients peuvent exploiter l’authentification moderne afin d’obtenir de l’aide pour sécuriser des ressources. Dans Skype pour Business Server, cette technologie est utilisée entre les clients locaux et les serveurs locaux afin de donner aux utilisateurs un niveau d’autorisation aux ressources approprié.
  
Les conversations d’authentification moderne (qui sont basées sur la bibliothèque ADAL et OAuth 2.0) ont certains éléments en commun.
  
- Il existe un client effectue une demande pour une ressource, dans ce cas, le client est Skype pour les entreprises.
    
- Il existe une ressource à laquelle le client a besoin d’un niveau spécifique d’accès, et cette ressource est sécurisée par un service d’annuaire, dans ce cas la ressource est Skype pour Business Server.
    
- Il existe une connexion OAuth, en d’autres termes, une connexion est dédiée *à* un utilisateur pour accéder à une ressource. (OAuth est également connue sous le nom plus descriptif d’authentification « serveur à serveur » et est souvent abrégée S2S.)
    
Dans Skype pour les conversations Business Server modernes d’authentification (ADAL), Skype pour Business Server communique par le biais de services ADFS (3.0 ADFS dans Windows Server 2012 R2). L’authentification peut se produire à l’aide d’un autre fournisseur d’identité (IdP), mais Skype pour Business server doit être configuré pour communiquer avec ADFS, directement. Si vous n’avez pas configuré pour fonctionner avec Skype pour Business Server ADFS, veuillez effectuer l' [installation des services AD FS](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL est incluse dans le 2016 mars mise à jour Cumulative pour Skype pour Business Server 2015 et le 2016 mars mise à jour Cumulative pour Skype pour Business **doit** être installé et est nécessaire pour la configuration réussie.
  
> [!NOTE]
> Dans la version initiale, l’authentification moderne dans un environnement local est uniquement prise en charge s’il n’y a pas de topologie Skype mixte impliquée. Par exemple, si l’environnement est purement Skype pour Business Server. Cet énoncé pourrait être modifié. 
  
Un package PowerShell comprenant des fichiers .ps1 avec les commandes utilisées par la bibliothèque ADAL doit être téléchargé pour que la configuration aboutisse.
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a>Configurez la bibliothèque ADAL dans votre pool et définissez ADFS en tant que serveur de jetons de sécurité
<a name="BKMK_Config"> </a>

Dans ce processus, vous vous connectez votre installation des services AD FS pour un Skype pour le pool Business Server qui est configuré pour ADAL.
  
1. Installer le 2016 mars mise à jour Cumulative pour Skype pour Business Server 2015 à votre Skype pour le pool de serveurs d’entreprise ou serveur Standard Edition server. (Programmez les fenêtres de maintenance si nécessaire, pour exécuter Windows Update en vue de l’installation automatique.)
    
2. Sur vos serveurs ADFS sur site, [Téléchargez](https://aka.ms/sfbadalscripts) le AdfsOAuthTrustForSfB-le programme d’installation. (Cela doit être effectué par une batterie de serveurs ADFS ou des serveurs ADFS indépendants. Cela ne doit pas être effectué sur un proxy ou des proxys ADFS).
    
3. Prenez note des interne et externe Service Web de noms de domaine complets (FQDN) pour votre Skype pour le pool de serveurs d’entreprise ou serveur Standard Edition server. Cela doit être effectué pour tous les pools Skype Entreprise.
    
4. Depuis PowerShell sur le(s) serveur(s) ADFS, exécutez la configuration Setup-Adfs OAuthTrustForSfB. Vous devrez saisir l’URL appropriée pour les FQDN des services Web interne et externe. Voici un exemple :
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    Pour des pools supplémentaires, vous devez ajouter manuellement les URL de Services Web Pool à la Skype Business Server Relying Party faire confiance dans ADFS.
    
    > [!IMPORTANT]
    > Il n’est pas possible d’utiliser l’authentification passive pour un pool et d’utiliser également la bibliothèque ADAL. Vous devez désactiver l’authentification passive afin d’utiliser la bibliothèque ADAL. Pour les applets de commande PowerShell comment configurer l’authentification pour un Pool, consultez [cet](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.
  
    > [!TIP]
    > Si vous avez des pools supplémentaires vous devez les ajouter en tant [qu’identificateurs](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) le Relying Party approuver dans ADFS. > accédez à votre serveur AD FS et ouvrir la gestion des services AD FS. Développez des relations d’approbation \> approbations de parties de confiance. Avec le bouton droit de la partie de confiance approbation indiqué et avec le bouton droit pour les propriétés \> identificateurs \> tapez l’URL de Pool supplémentaires \> cliquez sur Ajouter. 
  
5. Revenez à votre Skype pour Business Server frontal ou Standard Edition server. À partir de là, vous devez exécuter les applets de commande que créer un serveur OAuth et de modifier cette configuration OAuth pour fonctionner avec Skype pour les entreprises. Vous ne devrez effectuer cette étape une fois par Skype pour le déploiement de serveur d’entreprise. Voici un exemple :
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > L’URL « Identités » s’affiche dans cette commande est réellement le nom Service ADFS fédération vous pouvez voir dans la gestion d’ADFS lorsque vous cliquez sur Service \> propriétés. « Type » est toujours ADFS, et le « MetadataURL » est toujours \<nom du service ADFS votre\> + « / FederationMetadata/2007-06/FederationMetadata.xml ». 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Toujours sur votre Skype pour Business Server frontal ou Standard Edition server, testez la nouvelle configuration en entrant l’adresse SIP d’un utilisateur et le nom de domaine complet du pool. Vous ne devrez effectuer cette étape une fois par Skype pour le déploiement de serveur d’entreprise. Voici un exemple :
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Lorsque vous y êtes invité, veillez à entrer les informations d’identification de l’utilisateur du test. Vérifiez que le test s’effectue correctement.
    
    > [!NOTE]
    > Lorsque votre URL STS résout ADFS *en interne* , l’invite que vous verrez sera une invite de **Sécurité Windows** . Si l’URL est résolue en externe, une invite nommée **Connectez-vous** s’affiche. En règle générale, il devrait y avoir une invite **Windows Security** ici. Notez que ce comportement varie, en particulier si vous avez exécuté une authentification basée sur les formulaires (ou FBA).
  
Sachez également que lorsque l’URL STS est résolue vers un serveur ADFS interne et que l’authentification Windows intégrée est activée dans les navigateurs, les ordinateurs sur lesquels de nombreux utilisateurs se connectent à des applications clientes peuvent ne pas réussir à les authentifier, à moins que le navigateur ne soit configuré de manière explicite pour inviter les utilisateurs à donner leurs informations d’identification dans une zone de sécurité donnée du navigateur. Prenons l’exemple d’un kiosque. Le compte qui est connecté au système d’exploitation peut être différent du compte d’utilisateur se connectant au client Skype Entreprise. Si tel est le cas, vous verrez peut-être les échecs décrits ici.
    
Vous pouvez voir et modifier ce paramètre de navigateur dans Internet Explorer en cliquant sur \> outils (ou la vitesse) \> Options Internet \> onglet sécurité \> et la Zone de sécurité (tels que l’Intranet Local). Dans cette boîte de dialogue, cliquez sur le bouton « Personnaliser le niveau » et faites défiler toute la liste dans la boîte de dialogue des paramètres. Sous authentification utilisateur \> connexion \> vous voyez une option pour 'Demander nom d’utilisateur et mot de passe'. Si vous avez des kiosques pour lesquels l’utilisateur qui démarre le client Skype Entreprise est différent (dispose d’un autre compte) de l’utilisateur connecté à l’ordinateur, vous voudrez peut-être essayer de configurer cette option sur « ACTIVÉ » pour ces ordinateurs dans une stratégie de groupe.
    
Enfin, et c’est important, vous pouvez recevoir plusieurs invites, étant donné que le système de sécurité collecte les informations dont il a besoin pour authentifier ou autoriser votre compte.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Autres options d'activation de la connexion à la bibliothèque ADAL (par exemple, applications clientes Office)
<a name="BKMK_Options"> </a>

Maintenant que ADAL est configuré pour votre Skype pour les entreprises (automatiquement) et pour les applications de client Office 2016 plateformes, vous souhaiterez peut-être exploiter pour Exchange Online (où il se n'agit pas « On » par défaut), ou dans les clients Office 2013.
  
> [!IMPORTANT]
> Besoin de savoir à quoi s’attendre à partir des connexions d’authentification moderne à partir de vos applications client ? Jetez un œil à [moderne comment fonctionne l’authentification pour les applications clientes Office 2013 et Office 2016](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
Pour activer l’authentification moderne pour Exchange Online, vous devrez exécuter certaines applets de commande PowerShell. Dans le cas d’applications de client Office 2013, vous devrez modifier certaines clés de Registre sur les ordinateurs clients.
  
- Se connecter à Exchange Online et exécutez les applets de commande suivantes :
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Définissez ces clés de Registre pour chaque périphérique ou ordinateur sur lequel vous souhaitez activer l’authentification moderne. Vous aurez besoin d’un objet GPO dans les grandes organisations. Pour plus d’informations sur la création d’un objet de stratégie de groupe, voir la « créer un objet de stratégie de groupe permet de modifier le Registre sur un ordinateur faisant partie du domaine » de [cet ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)article.
    
|Clé de Registre  <br/> |Type  <br/> |Valeur  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Une fois ces clés sont définies, définissez vos applications Office à [utiliser l’authentification multifactorielle (MFA) avec Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> Pour désactiver l’authentification moderne sur des appareils pour Office 2013, définissez la clé de Registre HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL sur une valeur égale à zéro. N’oubliez pas qu’une clé de Registre similaire (HKCU\SOFTWARE\Microsoft\Office\ **16,0** \Common\Identity\EnableADAL) peut également servir pour désactiver l’authentification moderne sur les appareils Office 2016.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clients pour lesquels l’authentification moderne/la bibliothèque ADAL n’est pas prise en charge
<a name="BKMK_Support"> </a>

Certaines versions de client ne prennent pas en charge OAuth. Vous pouvez vérifier votre version de client Office dans le Panneau de configuration, où vous pouvez ajouter et supprimer des programmes, afin de comparer votre numéro de version aux versions (ou plages de versions) répertoriées ici :
  
- Client Office 15.0. [0000-4766].\*
    
- Client Office 16.0. [0000-4293].\*
    
- Client Office 16.0.6001.[0000-1032]
    
- Client Office 16.0. [6000-6224].\*
    

