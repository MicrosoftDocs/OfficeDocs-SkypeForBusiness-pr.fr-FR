---
title: Déplacer les utilisateurs Skype pour Business Online sur site
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Résumé : Découvrez comment déplacer des comptes d’utilisateurs en ligne dans les locaux de Skype pour Business Server.'
ms.openlocfilehash: e429aebc6847146ad5bef2b34d6ccfa7d2997ec6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a>Déplacer les utilisateurs Skype pour Business Online sur site
 
**Résumé :** Découvrez comment déplacer des comptes d’utilisateurs en ligne dans les locaux de Skype pour Business Server.
  
Vous devrez peut-être déplacer des comptes d’utilisateurs à partir d’online à sur site pour garantir que les utilisateurs hébergement en ligne et sur site sont identifiables à une de l’autre. Pour être détectable par une de l’autre, tous les utilisateurs doivent avoir une présence dans le local d’Active Directory. Pour plus d’informations, consultez [planification de la connectivité d’hybride entre Skype pour Business Server et Skype pour l’activité en ligne](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md). Vous souhaiterez déplacer des utilisateurs en ligne sur le site, par exemple, si : 
  
- Vous avez des utilisateurs qui doivent être créés sur un site et ensuite vers le nuage.
    
- Votre organisation a déployé Skype pour Business Online avant de déployer Skype pour Business Server. Par conséquent, vous avez des utilisateurs qui ont été créés initialement dans le nuage et maintenant devez être déplacées à dans les locaux d’avant de les déplacer à Skype pour entreprise en ligne. 
    
Cette rubrique décrit deux scénarios :
  
- [Déplacer des utilisateurs en ligne — qui étaient à l’origine en ligne — à sur site](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)
    
- [Déplacer en ligne utilisateurs (ce qui étaient initialement sur un site) sur le site](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)
    
## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a>Déplacer des utilisateurs en ligne — qui étaient à l’origine en ligne — à sur site
<a name="BKMK_originallyonline"> </a>

Cette section s’applique uniquement aux utilisateurs qui ont créé et activé en ligne, mais qui n’ont pas d’un compte dans les locaux sur Active Directory. 
  
Avant de commencer à déplacer les utilisateurs en ligne vers votre environnement local, vérifiez que toutes les conditions suivantes sont vraies :
  
- Votre environnement local doit être déployé et validé complètement. Pour plus d’informations, consultez [déploiement de Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) ou [Déployer un Skype pour Business Server 2015](../../deploy/deploy.md), selon quelle version vous utilisez dans les locaux. 
    
- Vos clients en ligne doit être configuré pour l’accès distant de PowerShell.
    
    Pour ce faire, installez d’abord le Skype pour module de connecteur Business Online pour Windows PowerShell, ce que vous pouvez obtenir ici : [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
    
    Après avoir installé le module, vous pouvez établir une session à distance en tapant les applets de commande suivantes dans le Skype pour Business Server Management Shell :
    
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

    Pour plus d’informations sur la façon d’établir une session PowerShell à distance avec Skype pour professionnels en ligne, consultez [connexion à Lync Online en utilisant Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).
    
    Pour plus d’informations sur l’utilisation de la Skype pour module de PowerShell en ligne Business connector, reportez-vous [à l’aide de Windows PowerShell pour gérer Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).
    
- Vos clients en ligne doivent être configurés pour un espace d’adressage partagé SIP. Pour ce faire, commencez une session Powershell distante avec Skype pour l’activité en ligne. Ensuite, exécutez l’applet de commande suivante :
    
  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > L’attribut SharedSipAddressSpace doit rester « True », jusqu'à ce que pour le déplacement en ligne est final et aucun utilisateur reste dans les locaux. 
  
Une fois que vous avez terminé ces étapes, vous pouvez migrer les comptes d’utilisateur comme décrit dans la procédure suivante :
  
### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a>Déplacer des comptes d’utilisateur à l’origine en ligne à un déploiement sur site

1. Vérifiez tout d’abord que votre organisation est configurée pour l’environnement hybride, dont les outils Azure Active Directory Connect et de synchronisation. Pour plus d’informations, consultez [planification de la connectivité d’hybride entre Skype pour Business Server et Skype pour l’activité en ligne](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
    
  - Dans votre déploiement sur site, le Skype pour Business Server Management Shell, tapez les applets de commande suivantes pour créer le fournisseur d’hébergement pour Skype pour l’activité en ligne. Vous pouvez utiliser les valeurs de votre choix pour les paramètres Identité et Nom.
    
  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. Vérifiez que sur vos serveurs de bord sur place, la chaîne de certificats qui permet la connexion à Skype pour Business Online, comme indiqué dans le tableau suivant. Vous pouvez télécharger cette chaîne ici : [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).
    
|**Certificat**|**Magasin de certificats**|
|:-----|:-----|
|Certificat racine de CyberTrust Baltimore  <br/> |Autorité de certification racine de confiance  <br/> |
|Microsoft Internet Authority (Nouveau certificat de l’autorité de certification racine)  <br/> |Autorité de certification intermédiaire  <br/> |
|MSIT Machine Auth CA2 (Nouvelle autorité de certification émettrice CA2)  <br/> |Autorité de certification intermédiaire  <br/> |
   
3. Dans Active Directory sur site, activer les comptes d’utilisateur concernés pour Skype pour 2015 de serveur d’entreprise dans les locaux. Pour un utilisateur individuel, tapez l’applet de commande suivante : 
    
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

4. Synchroniser les utilisateurs en ligne avec les utilisateurs de la mise à jour sur site. Pour plus d’informations, consultez [Outils d’intégration de répertoire](https://go.microsoft.com/fwlink/p/?LinkId=530320).
    
5. Mettre à jour les enregistrements DNS suivants pour diriger le trafic SIP à votre déploiement sur site :
    
  - Mettez à jour **lyncdiscover.contoso.com**  Un enregistrement pour pointer vers le nom de domaine complet (FQDN) du serveur proxy inverse local.
    
  - Mise à jour de la ** *_sip* . _tls.contoso.com** SRV enregistrement pour résoudre l’adresse IP ou VIP publique du service des locaux de Lync Edge d’accès.
    
  - Mise à jour de la ** *_sipfederationtls* . _tcp.contoso.com** SRV enregistrement pour résoudre l’adresse IP ou VIP publique du service Edge d’accès de Skype pour Business Server 2015 sur site.
    
  - Si votre entreprise utilise fractionnée DNS (parfois appelé « Déconnexion évitée DNS »), assurez-vous que les utilisateurs de la résolution de noms par le biais de la zone DNS interne sont dirigés vers le Pool fin avant.
    
6. Type de la `Get-CsUser` applet de commande pour vérifier certaines propriétés sur les utilisateurs que vous allez déplacer. Vérifiez que HostingProviderProxyFQDN possède la valeur `"sipfed.online.lync.com"` et que les adresses SIP (Session Initiation Protocol) sont définies correctement.
    
7. Déplacer des utilisateurs en ligne sur le site.
    
    Pour déplacer un seul utilisateur, tapez ce qui suit :
    
  ```
  $cred = Get-Credential
  ```

  ```
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de commande **Get-CsUSer** -paramètre de filtre pour sélectionner les utilisateurs à une propriété spécifique. Par exemple, vous pouvez sélectionner tous les utilisateurs en ligne par filtrage des {fournisseur d’hébergement - eq « sipfed.online.lync.om »}. Vous pouvez ensuite canaliser les utilisateurs retournées à l’applet de commande **Move-CsUSer** , comme illustré ci-dessous.
    
  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être une URL vers le pool dans lequel le service hébergé de Migration est en cours d’exécution, dans le format suivant : _Https://\<nom de domaine complet Pool\>/HostedMigration/ hostedmigrationService.svc_.
    
    Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.
    
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Pour déterminer l’URL du service de migration hébergée de votre client Office 365

1. Connectez-vous à votre client Office 365 en tant qu’administrateur.
    
2. Ouvrez le **Centre d’administration Skype Entreprise**.
    
3. Une fois le **Centre d’administration Skype Entreprise** affiché, sélectionnez l’URL et copiez-la dans la barre d’adresse jusqu’à **lync.com**. L’URL doit se présenter comme dans l’exemple suivant :
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant : 
    
     `https://admin0a.online.lync.com`
    
5. Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.
    
    L’URL résultante, qui est la valeur de la **HostedMigrationOverrideUrl**, doit se présenter comme suit :
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]
    > La taille maximale par défaut pour les fichiers journaux de transaction de la base de données rtcxds est de 16 Go. Cela est assez grand pour si vous déplacez un grand nombre d’utilisateurs à la fois, surtout si vous avez activé de la mise en miroir. Pour résoudre ce problème, vous pouvez augmenter la taille du fichier ou sauvegarder régulièrement les fichiers journaux. Pour plus d’informations, voir [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725). 
  
8. Il s’agit d’une étape facultative. Pour une intégration à Exchange 2013 Online, vous devez utiliser un autre fournisseur d’hébergement. Pour plus d’informations, consultez [configurer une intégration entre Skype sur site pour Business Server 2015 et Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).
    
9. Les utilisateurs sont maintenant déplacés. Pour vérifier qu’un utilisateur possède des valeurs correctes pour les attributs affichés dans le tableau ci-dessous, tapez cette applet de commande : 
    
  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|**Attribut de répertoire actif**|**Nom de l’attribut**|**Valeur correcte pour l’utilisateur en ligne**|**Valeur correcte pour les utilisateurs locaux**|
|:-----|:-----|:-----|:-----|
|msRTCSIP-DeploymentLocator  <br/> |HostingProvider  <br/> |sipfed.Online.Lync.com  <br/> |SRV :  <br/> |
|msRTCSIP-PrimaryUserAddress  <br/> |SIPAddress  <br/> |SIP:username@contoso.com  <br/> |SIP:username@contoso.com  <br/> |
|sRTCSIP-UserEnabled  <br/> |Activé  <br/> |True  <br/> |True  <br/> |
   
10. Chaque utilisateur déplacé devra se déconnecter, puis se reconnecter. Lorsque l’utilisateur se reconnecte, il doit vérifier ses listes de contacts et ajouter des contacts, si nécessaire.
    
    Notez que les réunions planifiées ne sont pas migrées de la version en ligne vers la version locale. Les utilisateurs doivent replanifier ces réunions après les avoir déplacées.
    
    Une fois que les enregistrements DNS sont mis à jour et tous les utilisateurs sont dirigés vers les locaux, l’attribut HostingProvider dirige l’utilisateur vers les utilisent des enregistrements SRV ou de les diriger vers le fournisseur en ligne « sipfed.online.lync.com ».
    
## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a>Déplacer en ligne utilisateurs (ce qui étaient initialement sur un site) sur le site
<a name="BKMK_originallyonprem"> </a>

Cette section s’applique uniquement aux utilisateurs qui ont été créés et activés pour un déploiement sur site et ensuite vers un déploiement sur site en ligne. 
  
- Exécuter les applets de commande suivantes pour atteindre un utilisateur à partir de Skype pour Business Online sur site, remplacez la valeur pour les paramètres **d’identité** et de la **cible** de valeurs correctes pour votre environnement :
    
  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être une URL vers le pool dans lequel le service hébergé de Migration est en cours d’exécution, dans le format suivant :
  
 _Https://\<nom de domaine complet du Pool\>/HostedMigration/hostedmigrationService.svc_. Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Pour déterminer l’URL du service de migration hébergée de votre client Office 365

1. Connectez-vous à votre client Office 365 en tant qu’administrateur.
    
2. Ouvrez le **Centre d’administration Skype Entreprise**.
    
3. Une fois le **Centre d’administration Skype Entreprise** affiché, sélectionnez l’URL et copiez-la dans la barre d’adresse jusqu’à **lync.com**. L’URL doit se présenter comme dans l’exemple suivant :
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant : 
    
     `https://admin0a.online.lync.com`
    
5. Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.
    
    L’URL résultante, qui est la valeur de la **HostedMigrationOverrideUrl**, doit se présenter comme suit :
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

