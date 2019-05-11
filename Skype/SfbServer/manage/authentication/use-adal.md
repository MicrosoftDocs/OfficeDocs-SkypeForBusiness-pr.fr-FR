---
title: Comment utiliser l’authentification moderne (ADAL) avec Skype Entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: Cet article explique comment utiliser modernes d’authentification (qui est basé sur la bibliothèque de l’authentification Active Directory (ADAL) et OAuth 2.0) qui peuvent se trouver dans le 2016 mars mise à jour Cumulative pour Skype pour les entreprises pour Skype pour Business Server 2015.
ms.openlocfilehash: 0bad5080bb90ae2260733df09e3ae7bc0808ee78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919499"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Comment utiliser l’authentification moderne (ADAL) avec Skype Entreprise
 
Cet article explique comment utiliser modernes d’authentification (qui est basé sur la bibliothèque de l’authentification Active Directory (ADAL) et OAuth 2.0) qui peuvent se trouver dans le 2016 mars mise à jour Cumulative pour Skype pour les entreprises pour Skype pour Business Server 2015, ou d’initial version de Skype pour Business Server 2019.
  
## <a name="whats-in-this-article"></a>Quel est le contenu de cet article ?

[Configurer ADAL dans votre pool et définir des services AD FS en tant que serveur de jetons de sécurité](use-adal.md#BKMK_Config)
  
[Autres options d'activation de la connexion à la bibliothèque ADAL (par exemple, applications clientes Office)](use-adal.md#BKMK_Options)
  
[Clients pour lesquels l’authentification moderne/la bibliothèque ADAL n’est pas prise en charge](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a>Configurer ADAL dans votre pool et définir des services AD FS en tant que serveur de jetons de sécurité
<a name="BKMK_Config"> </a>

Dans ce processus, vous vous connectez votre installation d’AD FS pour une Skype pour le pool Business Server qui est configuré pour ADAL.
  
1. Installer le 2016 mars mise à jour Cumulative (ou version ultérieure) pour Skype pour Business Server 2015 à votre Skype pour le pool de serveurs d’entreprise ou serveur Standard Edition server. (Programmez les fenêtres de maintenance si nécessaire, pour exécuter Windows Update en vue de l’installation automatique.)
    
2. Sur votre site ou les serveurs AD FS, [Téléchargez](https://aka.ms/sfbadalscripts) le AdfsOAuthTrustForSfB-le programme d’installation. (Cette opération doit être effectuée pour chaque batterie de serveurs AD FS ou indépendante ou les serveurs AD FS. Il est inutile sur les proxys AD FS ou des proxys d’applications Web.)
    
3. Prenez note des interne et externe Service Web de noms de domaine complets (FQDN) pour votre Skype pour le pool de serveurs d’entreprise ou serveur Standard Edition server. Cela doit être effectué pour tous les pools Skype Entreprise.
    
4. À partir de PowerShell sur l’ou les serveurs AD FS, exécutez `Setup-AdfsOAuthTrustForSfB.ps1` (pour Windows Server 2012 R2) ou `Setup-Adfs2016OAuthTrustForSfB.ps1` (pour Windows Server 2016 ou version ultérieure). Vous devrez entrer l’URL correctes pour les noms internes et externes Web Service domaine complet (FQDN). Voici un exemple :
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    Pour des pools supplémentaires, vous devez ajouter manuellement les URL de Services Web Pool à la Skype Business Server Relying Party faire confiance dans AD FS.
    
    > [!IMPORTANT]
    > Il n’est pas possible d’utiliser l’authentification passive pour un pool et d’utiliser également la bibliothèque ADAL. Vous devez désactiver l’authentification passive afin d’utiliser la bibliothèque ADAL. Pour les applets de commande PowerShell comment configurer l’authentification pour un Pool, consultez [cet](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.
  
    > [!TIP]
    > Si vous avez des pools supplémentaires, à que vous devez les ajouter en tant [qu’identificateurs](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) Relying Party faire confiance dans AD FS.>, accédez à votre serveur AD FS et ouvrez Gestion AD FS. Développez des relations d’approbation \> approbations de parties de confiance. Avec le bouton droit de la partie de confiance approbation indiqué et avec le bouton droit pour les propriétés \> identificateurs \> tapez l’URL de Pool supplémentaires \> cliquez sur Ajouter. 
  
5. Revenez à votre Skype pour Business Server frontal ou Standard Edition server. À partir de là, vous devez exécuter les applets de commande que créer un serveur OAuth et de modifier cette configuration OAuth pour fonctionner avec Skype pour les entreprises. Vous ne devrez effectuer cette étape une fois par Skype pour le déploiement de serveur d’entreprise. Voici un exemple :
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > L’URL « Identité » s’affiche dans cette commande est réellement le AD FS fédération nom de Service que vous pouvez voir dans Gestion AD FS lorsque vous cliquez sur Service \> propriétés. « Type » est toujours « ADFS », et le « MetadataURL » est toujours \<le nom de votre service AD FS\> + « / FederationMetadata/2007-06/FederationMetadata.xml ». 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Toujours sur votre Skype pour Business Server frontal ou Standard Edition server, testez la nouvelle configuration en entrant l’adresse SIP d’un utilisateur et le nom de domaine complet du pool. Vous ne devrez effectuer cette étape une fois par Skype pour le déploiement de serveur d’entreprise. Voici un exemple :
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Lorsque vous y êtes invité, veillez à entrer les informations d’identification de l’utilisateur du test. Vérifiez que le test s’effectue correctement.
    
    > [!NOTE]
    > Lorsque votre URL STS résout AD FS *en interne* , l’invite que vous verrez sera une invite de **Sécurité Windows** . Si l’URL est résolue en externe, une invite nommée **Connectez-vous** s’affiche. En règle générale, il devrait y avoir une invite **Windows Security** ici. Notez que ce comportement varie, en particulier si vous avez exécuté une authentification basée sur les formulaires (ou FBA).
  
Également à l’esprit, lorsque l’URL STS correspond à un serveur AD FS interne et l’authentification Windows intégrée est activée dans les navigateurs, les ordinateurs où différents utilisateurs se connectent à des applications clientes peuvent avoir des échecs d’authentification, sauf si le navigateur est explicitement configuré pour demander aux utilisateurs leurs informations d’identification dans une Zone de sécurité du navigateur donné. Prenons l’exemple d’un kiosque. Le compte qui est connecté au système d’exploitation peut être différent du compte d’utilisateur se connectant au client Skype Entreprise. Si tel est le cas, vous verrez peut-être les échecs décrits ici.
    
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
    
> [!NOTE]
> Authentification moderne hybride est également disponible avec Skype pour les professionnels sur site, si vous voulez savoir plus, visitez le site [comment configurer Skype pour les entreprises locale pour utiliser l’authentification moderne hybride](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication)
