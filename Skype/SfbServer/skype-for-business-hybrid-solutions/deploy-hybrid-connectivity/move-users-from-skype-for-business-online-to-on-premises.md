---
title: Déplacer les utilisateurs de Skype pour Business en ligne et en local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Résumé : Découvrez comment déplacer les comptes d’utilisateurs en ligne et localement dans Skype pour Business Server.'
ms.openlocfilehash: a2d49033e499d9a52af04fcb9e23d8ed483859f5
ms.sourcegitcommit: c18710a46018fe4c1d0ceb99710f18bbc25aad54
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/09/2018
ms.locfileid: "22301441"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a>Déplacer les utilisateurs de Skype pour Business en ligne et en local
 
**Résumé :** Découvrez comment déplacer les comptes d’utilisateurs en ligne et localement dans Skype pour Business Server.
  
Vous devrez peut-être déplacer des comptes d’utilisateurs d’en ligne et sur site pour vous assurer que les utilisateurs hébergement en ligne et dans les locaux sont accessibles à l’autre. Pour être accessibles à l’autre, tous les utilisateurs doivent avoir une présence dans Active Directory local. Pour plus d’informations, voir [planification de la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md). Vous pouvez souhaiter déplacer des utilisateurs en ligne sur site, par exemple, si : 
  
- Vous devez les nouveaux utilisateurs qui doivent être créés dans les locaux et ensuite vers le nuage.
    
- Votre organisation a déployé Skype pour Business Online avant de déployer Skype pour Business Server. Par conséquent, vous avez des utilisateurs qui ont été créés dans le nuage tout d’abord et maintenant devez être déplacés vers localement avant de les déplacer vers Skype pour Business Online. 
    
Cette rubrique décrit les deux scénarios :
  
- [Déplacer des utilisateurs en ligne, qui ont été initialement en ligne — à local](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)
    
- [Déplacer des utilisateurs en ligne (ceux qui ont été initialement sur site) pour sur site](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)
    
## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a>Déplacer des utilisateurs en ligne, qui ont été initialement en ligne — à local
<a name="BKMK_originallyonline"> </a>

Cette section s’applique uniquement aux utilisateurs qui ont été créés et activés en ligne, mais qui n’ont pas d’un compte dans l’environnement local sur Active Directory. 
  
Avant de commencer à déplacer les utilisateurs en ligne vers votre environnement local, vérifiez que toutes les conditions suivantes sont vraies :
  
- Votre environnement local doit être déployé et validé complètement. Pour plus d’informations, voir [déploiement de Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) ou [Déployer de Skype pour Business Server 2015](../../deploy/deploy.md), selon la version que vous utilisez le localement. 
    
- Votre client en ligne doit être configuré pour l’accès à distance PowerShell.
    
    Pour ce faire, installez d’abord la Skype pour module connecteur Business en ligne pour Windows PowerShell, vous pouvez obtenir ici : [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
    
    Après avoir installé le module, vous pouvez établir une session à distance en tapant les cmdlets suivantes dans le Skype pour Business Server Management Shell :
    
  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    Pour plus d’informations sur l’utilisation de PowerShell avec Skype pour Business Online, voir [configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
- Votre client en ligne doit être configuré pour un espace d’adressage SIP partagé. Pour ce faire, commencez par démarrer une session Powershell distante avec Skype pour Business Online. Ensuite, exécutez l’applet de commande suivante :
    
  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > L’attribut SharedSipAddressSpace doit rester « True », jusqu'à ce que le déplacement vers online est final et aucun utilisateur reste dans les locaux. 
  
Une fois que vous avez terminé ces étapes, vous pouvez migrer les comptes d’utilisateurs comme décrit dans la procédure suivante :
  
### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a>Déplacer les comptes d’utilisateur à l’origine activés en ligne à un déploiement sur site

1. Vérifiez tout d’abord que votre organisation est configurée pour l’environnement hybride, dont les outils Azure Active Directory Connect et de synchronisation. Pour plus d’informations, voir [planification de la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
    
  - Dans votre déploiement sur site, dans la Skype pour Business Server Management Shell, tapez les applets de commande suivantes pour créer le fournisseur d’hébergement pour Skype pour Business en ligne. Vous pouvez utiliser les valeurs de votre choix pour les paramètres Identité et Nom.
    
  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. Vérifiez que sur les serveurs de périphérie locale, vous avez la chaîne de certificats qui permet la connexion à Skype pour Business Online, comme indiqué dans le tableau suivant. Vous pouvez télécharger cette chaîne ici : [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).
    
|**Certificat**|**Magasin de certificats**|
|:-----|:-----|
|Certificat racine de CyberTrust Baltimore  <br/> |Autorité de certification racine de confiance  <br/> |
|Microsoft Internet Authority (Nouveau certificat de l’autorité de certification racine)  <br/> |Autorité de certification intermédiaire  <br/> |
|MSIT Machine Auth CA2 (Nouvelle autorité de certification émettrice CA2)  <br/> |Autorité de certification intermédiaire  <br/> |
   
3. Dans Active Directory sur site, activez les comptes d’utilisateur affecté pour Skype pour Business Server 2015 localement. Pour un utilisateur individuel, tapez l’applet de commande suivante : 
    
  ```
  Enable-CsUser
-Identity "username " 
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    Vous pouvez également créer un script qui lit les noms d’utilisateur dans un fichier et les transmet comme informations à l’applet de commande Enable-CsUser :
    
  ```
  Enable-CsUser
-Identity $Identity 
-SipAddress $SipAddress 
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. Synchroniser les utilisateurs en ligne avec les mise à jour les utilisateurs locaux. Pour plus d’informations, voir [Outils de l’intégration d’annuaire](https://go.microsoft.com/fwlink/p/?LinkId=530320).
    
5. Mettre à jour les enregistrements DNS suivants pour diriger tout le trafic SIP à votre déploiement sur site :
    
  - Mettez à jour **lyncdiscover.contoso.com**  Un enregistrement pour pointer vers le nom de domaine complet (FQDN) du serveur proxy inverse local.
    
  - Mise à jour la ** *_sip* . _tls.contoso.com** enregistrement SRV pour résoudre l’adresse IP ou l’adresse IP publique du service Edge d’accès de Lync sur site.
    
  - Mise à jour la ** *_sipfederationtls* . _tcp.contoso.com** enregistrement SRV pour résoudre l’adresse IP ou l’adresse IP publique du service Edge d’accès de Skype pour Business Server 2015 locale.
    
  - Si votre organisation utilise fractionnées DNS (parfois appelée « DNS split-brain »), assurez-vous que les utilisateurs de la résolution de noms par le biais de la zone DNS interne sont dirigés vers le Pool frontal.
    
6. Type de la `Get-CsUser` applet de commande pour vérifier certaines propriétés sur les utilisateurs que vous prévoyez de déplacer. Vérifiez que HostingProviderProxyFQDN possède la valeur `"sipfed.online.lync.com"` et que les adresses SIP (Session Initiation Protocol) sont définies correctement.
    
7. Déplacer des utilisateurs en ligne en local.
    
    Pour déplacer un seul utilisateur, tapez ce qui suit :
    
  ```
  $cred = Get-Credential
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de commande **Get-CsUSer** avec le paramètre - Filter pour sélectionner les utilisateurs avec une propriété spécifique. Par exemple, vous pouvez sélectionner tous les utilisateurs en ligne en filtrant les {fournisseur d’hébergement - eq « sipfed.online.lync.om »}. Vous pouvez ensuite canaliser renvoyées aux utilisateurs de l’applet de commande **Move-CsUSer** , comme indiqué ci-dessous.
    
  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être une URL vers le pool dans lequel s’exécute le service de Migration hébergé, dans le format suivant : _Https://\<nom complet du Pool\>/HostedMigration/ hostedmigrationService.svc_.
    
    Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.
    
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Pour déterminer l’URL du service de migration hébergée de votre client Office 365

1. Connectez-vous à votre client Office 365 en tant qu’administrateur.
    
2. Ouvrez le **Centre d’administration Skype Entreprise**.
    
3. Une fois le **Centre d’administration Skype Entreprise** affiché, sélectionnez l’URL et copiez-la dans la barre d’adresse jusqu’à **lync.com**. L’URL doit se présenter comme dans l’exemple suivant :
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant : 
    
     `https://admin0a.online.lync.com`
    
5. Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.
    
    L’URL qui en résulte, qui est la valeur de la **HostedMigrationOverrideUrl**, doit se présenter comme suit :
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]
    > La taille maximale par défaut pour les fichiers journaux de transaction de la base de données rtcxds est de 16 Go. Cela ne peut pas être suffisamment importante si vous déplacez un grand nombre d’utilisateurs à la fois, en particulier si vous avez activé de mise en miroir. Pour résoudre ce problème, vous pouvez augmenter la taille du fichier ou sauvegarder régulièrement les fichiers journaux. Pour plus d’informations, voir [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725). 
  
8. Il s’agit d’une étape facultative. Pour une intégration à Exchange 2013 Online, vous devez utiliser un autre fournisseur d’hébergement. Pour plus d’informations, voir [configurer l’intégration entre locale Skype pour Business Server 2015 et Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).
    
9. Les utilisateurs sont maintenant déplacés. Pour vérifier qu’un utilisateur possède des valeurs correctes pour les attributs affichés dans le tableau ci-dessous, tapez cette applet de commande : 
    
  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|**Attribut Active Directory**|**Nom Attribut**|**Valeur correcte pour l’utilisateur Online**|**Valeur correcte pour les utilisateurs locaux**|
|:-----|:-----|:-----|:-----|
|msRTCSIP-DeploymentLocator  <br/> |HostingProvider  <br/> |sipfed.Online.Lync.com  <br/> |SRV :  <br/> |
|msRTCSIP-PrimaryUserAddress  <br/> |SIPAddress  <br/> |SIP:username@contoso.com  <br/> |SIP:username@contoso.com  <br/> |
|msRTCSIP-UserEnabled  <br/> |Activé  <br/> |True  <br/> |True  <br/> |
   
10. Chaque utilisateur déplacé devra se déconnecter, puis se reconnecter. Lorsque l’utilisateur se reconnecte, il doit vérifier ses listes de contacts et ajouter des contacts, si nécessaire.
    
    Notez que les réunions planifiées ne sont pas migrées de la version en ligne vers la version locale. Les utilisateurs doivent replanifier ces réunions après les avoir déplacées.
    
    Une fois que les enregistrements DNS sont mises à jour et tous les utilisateurs sont dirigés vers le site, l’attribut HostingProvider dirige l’utilisateur à utiliser les enregistrements SRV ou les diriger vers le fournisseur en ligne « sipfed.online.lync.com ».
    
## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a>Déplacer des utilisateurs en ligne (ceux qui ont été initialement sur site) pour sur site
<a name="BKMK_originallyonprem"> </a>

Cette section s’applique uniquement aux utilisateurs qui ont été créés et activés pour un déploiement sur site et ensuite vers à partir d’un déploiement sur site en ligne. 
  
- Exécutez les applets de commande suivante pour déplacer un utilisateur de Skype pour Business Online retour vers le site, en remplaçant la valeur pour les paramètres **Identity** et **cible** pour corriger les valeurs pour votre environnement :
    
  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être une URL vers le pool dans lequel s’exécute le service de Migration hébergé, dans le format suivant :
  
 _Https://\<nom de domaine complet du Pool\>/HostedMigration/hostedmigrationService.svc_. Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Pour déterminer l’URL du service de migration hébergée de votre client Office 365

1. Connectez-vous à votre client Office 365 en tant qu’administrateur.
    
2. Ouvrez le **Centre d’administration Skype Entreprise**.
    
3. Une fois le **Centre d’administration Skype Entreprise** affiché, sélectionnez l’URL et copiez-la dans la barre d’adresse jusqu’à **lync.com**. L’URL doit se présenter comme dans l’exemple suivant :
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant : 
    
     `https://admin0a.online.lync.com`
    
5. Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.
    
    L’URL qui en résulte, qui est la valeur de la **HostedMigrationOverrideUrl**, doit se présenter comme suit :
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

