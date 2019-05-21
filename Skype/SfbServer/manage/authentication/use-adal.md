---
title: Comment utiliser l’authentification moderne (ADAL) avec Skype Entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: Cet article explique comment utiliser l’authentification moderne (qui est basée sur la bibliothèque d’authentification Active Directory (ADAL) et la 2,0 OAuth, disponible dans la mise à jour cumulative de mars 2016 de Skype entreprise Server 2015.
ms.openlocfilehash: 9fe4470e1f8f6e2cd345cd176250fb1ffb16448f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286122"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Comment utiliser l’authentification moderne (ADAL) avec Skype Entreprise
 
Cet article explique comment utiliser l’authentification moderne (qui est basée sur la bibliothèque d’authentification Active Directory (ADAL) et la 2,0 OAuth, disponible dans la mise à jour cumulative de mars 2016 pour Skype entreprise Server 2015 ou à partir de l’initiale version de Skype entreprise Server 2019.
  
## <a name="whats-in-this-article"></a>Quel est le contenu de cet article ?

[Configurer ADAL dans votre pool et définir AD FS en tant que serveur du jeton de sécurité](use-adal.md#BKMK_Config)
  
[Autres options d'activation de la connexion à la bibliothèque ADAL (par exemple, applications clientes Office)](use-adal.md#BKMK_Options)
  
[Clients pour lesquels l’authentification moderne/la bibliothèque ADAL n’est pas prise en charge](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a>Configurer ADAL dans votre pool et définir AD FS en tant que serveur du jeton de sécurité
<a name="BKMK_Config"> </a>

Dans ce processus, vous connectez votre installation d’AD FS à un pool Skype entreprise Server configuré pour ADAL.
  
1. Installez la mise à jour cumulative 2016 de mars (ou une version plus récente) pour Skype entreprise Server 2015 vers votre pool Skype entreprise Server ou Standard Edition Server. (Programmez les fenêtres de maintenance si nécessaire, pour exécuter Windows Update en vue de l’installation automatique.)
    
2. Sur votre serveur AD FS local, [Téléchargez](https://aka.ms/sfbadalscripts) le script Setup-AdfsOAuthTrustForSfB. (Vous devez effectuer cette opération par batterie de serveurs AD FS ou serveur AD FS indépendant. Il n’est pas nécessaire d’effectuer cette opération sur les proxys AD FS ou les proxys d’application Web.)
    
3. Notez le nom de domaine complet (FQDN) du service Web interne et externe pour votre pool Skype entreprise Server ou Standard Edition Server. Cela doit être effectué pour tous les pools Skype Entreprise.
    
4. Depuis PowerShell sur le ou les serveurs AD FS, exécutez `Setup-AdfsOAuthTrustForSfB.ps1` (pour windows server 2012 R2) ou `Setup-Adfs2016OAuthTrustForSfB.ps1` (pour Windows Server 2016 ou version ultérieure). Vous devez entrer les URL appropriées pour les noms de domaine complets des services Web internes et externes. Voici un exemple :
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    Pour les pools supplémentaires, vous devez ajouter manuellement les URL des services Web de réserve à l’approbation de la partie de confiance de Skype entreprise Server dans AD FS.
    
    > [!IMPORTANT]
    > Il n’est pas possible d’utiliser l’authentification passive pour un pool et d’utiliser également la bibliothèque ADAL. Vous devez désactiver l’authentification passive afin d’utiliser la bibliothèque ADAL. Pour les applets de méthode PowerShell permettant de définir l’authentification d’un pool, voir [cet](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.
  
    > [!TIP]
    > Si vous avez d’autres pools, vous devez les [](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) ajouter en tant qu’identifiants à l’approbation de la partie de confiance dans AD FS. > accédez à votre serveur AD FS et ouvrez AD FS Management. Développez relations \> d’approbation de confiance entre les parties. Cliquez avec le bouton droit sur l’approbation de la partie de confiance qui apparaît dans \> \> la liste et cliquez avec le bouton droit sur l’URL \> du pool supplémentaire, puis cliquez sur Ajouter. 
  
5. Revenez à votre serveur frontal Skype entreprise Server frontal ou Standard Edition Server. À partir de cet emplacement, vous devez exécuter des cmdlets qui créent un serveur OAuth et modifier cette configuration OAuth pour fonctionner avec Skype entreprise. Vous ne devez effectuer cette étape qu’une fois par déploiement de Skype entreprise Server. Voici un exemple :
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > L’URL d’identité qui s’affiche dans cette commande est en fait le nom du service de fédération AD FS que vous pouvez voir dans gestion d’AD FS lorsque \> vous cliquez avec le bouton droit sur Propriétés du service. Le «type» est toujours «ADFS» et «MetadataURL» est toujours \<votre nom\> de service AD FS + «/FederationMetadata/2007-06/FederationMetadata.Xml». 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Toujours sur votre serveur frontal Skype entreprise Server ou Standard Edition standard, testez la nouvelle configuration en entrant l’adresse SIP d’un utilisateur et le nom de domaine complet (FQDN) du pool. Vous ne devez effectuer cette étape qu’une fois par déploiement de Skype entreprise Server. Voici un exemple :
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Lorsque vous y êtes invité, veillez à entrer les informations d’identification de l’utilisateur du test. Vérifiez que le test s’effectue correctement.
    
    > [!NOTE]
    > Lorsque votre URL STS est résolue vers AD FS en *interne* , l’invite qui s’affiche est une invite de **sécurité Windows** . Si l’URL est résolue en externe, une invite nommée **Connectez-vous** s’affiche. En règle générale, il devrait y avoir une invite **Windows Security** ici. Notez que ce comportement varie, en particulier si vous avez exécuté une authentification basée sur les formulaires (ou FBA).
  
Sachez également que lorsque l’URL de STS est résolue vers un serveur AD FS interne et que l’authentification intégrée de Windows est activée dans les navigateurs, les ordinateurs qui se connectent à des applications clientes peuvent avoir des échecs d’authentification, sauf si le navigateur est explicitement configuré pour inviter les utilisateurs à entrer leurs informations d’identification dans une zone de sécurité du navigateur donnée. Prenons l’exemple d’un kiosque. Le compte qui est connecté au système d’exploitation peut être différent du compte d’utilisateur se connectant au client Skype Entreprise. Si tel est le cas, vous verrez peut-être les échecs décrits ici.
    
Pour afficher et modifier ce paramètre de navigateur dans Internet Explorer, cliquez \> sur outils (ou sur l' \> engrenage) \> sur options \> Internet, puis sur la zone sécurité (par exemple, Intranet local). Dans cette boîte de dialogue, cliquez sur le bouton « Personnaliser le niveau » et faites défiler toute la liste dans la boîte de dialogue des paramètres. Sous connexion \> de \> l’utilisateur, vous verrez une option permettant de demander le nom d’utilisateur et le mot de passe. Si vous avez des kiosques pour lesquels l’utilisateur qui démarre le client Skype Entreprise est différent (dispose d’un autre compte) de l’utilisateur connecté à l’ordinateur, vous voudrez peut-être essayer de configurer cette option sur « ACTIVÉ » pour ces ordinateurs dans une stratégie de groupe.
    
Enfin, et c’est important, vous pouvez recevoir plusieurs invites, étant donné que le système de sécurité collecte les informations dont il a besoin pour authentifier ou autoriser votre compte.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Autres options d'activation de la connexion à la bibliothèque ADAL (par exemple, applications clientes Office)
<a name="BKMK_Options"> </a>

Dans la mesure où ADAL est configuré pour Skype entreprise et (automatiquement) pour les applications clientes Office 2016 sur différentes plateformes, vous pouvez l’utiliser pour Exchange Online (où il n’est pas «activé» par défaut) ou dans les clients Office 2013.
  
> [!IMPORTANT]
> Vous avez besoin de savoir ce que vous pouvez attendre des connexions d’authentification modernes de vos applications clientes? Découvrez [le fonctionnement de l’authentification moderne pour les applications clientes office 2013 et office 2016](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
Pour activer l’authentification moderne dans Exchange Online, vous devez exécuter certaines cmdlets PowerShell. Dans le cas des applications clientes Office 2013, vous devrez modifier certaines clés de Registre sur les ordinateurs clients.
  
- Connectez-vous à Exchange Online et exécutez les applets de commande suivantes:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Définissez ces clés de Registre pour chaque périphérique ou ordinateur sur lequel vous souhaitez activer l’authentification moderne. Vous aurez besoin d’un objet GPO dans les grandes organisations. Pour plus d’informations sur la création d’un objet de stratégie de groupe, voir l’article créer un objet de stratégie de groupe pour modifier le [ ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)Registre sur un ordinateur appartenant à un domaine.
    
|Clé de Registre  <br/> |Type  <br/> |Valeur  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Une fois ces clés définies, configurez vos applications Office de façon à ce qu’elles [utilisent l’authentification multifacteur (MFA) avec Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> Pour désactiver l’authentification moderne sur les appareils pour Office 2013, définissez la clé de Registre HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL sur une valeur égale à zéro. Sachez qu’une clé de Registre similaire (HKCU\SOFTWARE\Microsoft\Office\ **16,0** \Common\Identity\EnableADAL) peut également être utilisée pour désactiver l’authentification moderne sur les appareils pour Office 2016.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clients pour lesquels l’authentification moderne/la bibliothèque ADAL n’est pas prise en charge
<a name="BKMK_Support"> </a>

Certaines versions de client ne prennent pas en charge OAuth. Vous pouvez vérifier votre version de client Office dans le Panneau de configuration, où vous pouvez ajouter et supprimer des programmes, afin de comparer votre numéro de version aux versions (ou plages de versions) répertoriées ici :
  
- Client Office 15,0. [0000-4766].\*
    
- Client Office 16,0. [0000-4293].\*
    
- Client Office 16.0.6001.[0000-1032]
    
- Client Office 16,0. [6000-6224].\*
    
> [!NOTE]
> Pour en savoir plus, reportez-vous à la page d’authentification moderne de Skype entreprise sur site. pour en savoir plus, consultez [la configuration de Skype entreprise sur site pour utiliser l’authentification moderne hybride](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication)
