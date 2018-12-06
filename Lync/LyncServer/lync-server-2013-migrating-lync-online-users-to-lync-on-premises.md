---
title: Migration des utilisateurs Lync Online vers Lync local
TOCTitle: Migration des utilisateurs Lync Online vers Lync local
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62247319
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des utilisateurs Lync Online vers Lync local

 

_**Dernière rubrique modifiée :** 2016-12-08_

> [!IMPORTANT]  
> Ces étapes ne sont nécessaires que pour la migration de comptes d’utilisateur activés à l’origine pour Lync dans Lync Online, avant le déploiement de Lync sur site. Pour déplacer les utilisateurs activés initialement pour Lync local, puis déplacés vers Lync Online, voir <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administration des utilisateurs dans un déploiement Lync Server 2013 hybride</a>.<br />
De plus, tous les utilisateurs en cours de déplacement doivent disposer de comptes dans l’instance Active Directory sur site.

## Migration des comptes d’utilisateur activés initialement dans Lync Online vers Lync local

1.  Tout d’abord, vérifiez que votre organisation est configurée pour l’environnement hybride.
    
      - Installez l’outil de synchronisation Windows Azure Active Directory. Pour plus d’information, voir <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Pour activer vos utilisateurs pour qu’ils utilisent l’authentification unique pour Lync Online, installez Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.
    
      - Dans votre déploiement local, dans Lync Server Management Shell, tapez les applets de commandes pour créer le fournisseur d’hébergement Lync Online :
        
        ```
        Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
        ```
        ```
        New-CSHostingProvider -Identity LyncOnline -Name LyncOnlin -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
        ```

2.  Confirmez que, sur vos serveurs Edge, la chaîne de certificat qui permet la connexion à Lync Online est présente, comme indiqué dans le tableau ci-dessous. Vous pouvez télécharger cette chaîne ici : [https://corp.sts.microsoft.com/Onboard/ADFS\_Onboarding\_Pack/corp\_sts\_certs.zip](https://corp.sts.microsoft.com/onboard/adfs_onboarding_pack/corp_sts_certs.zip) .
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Certificat</th>
    <th>Magasin de certificats</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>Autorité de certification racine de confiance</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet Authority (Nouveau certificat de l’autorité de certification racine)</p></td>
    <td><p>Autorité de certification intermédiaire</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine Auth CA2 (Nouvelle autorité de certification émettrice CA2)</p></td>
    <td><p>Autorité de certification intermédiaire</p></td>
    </tr>
    </tbody>
    </table>


3.  Dans votre instance Active Directory locale, activez les comptes d’utilisateur concernés pour Lync local. Pour un utilisateur individuel, tapez l’applet de commande suivante :
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    Vous pouvez également créer un script qui lit les noms d’utilisateur dans un fichier et les transmet comme informations à l’applet de commande Enable-CsUser :
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Exécutez DirSync pour synchroniser les utilisateurs Lync Online avec les utilisateurs Lync locaux à jour.

5.  Mettez à jour les enregistrements DNS pour acheminer tout le trafic SIP vers Lync local :
    
      - Mettez à jour **lyncdiscover.contoso.com** Un enregistrement pour pointer vers le nom de domaine complet (FQDN) du serveur proxy inverse local.
    
      - Mettez à jour l’enregistrement SRV ***\_sip*.\_tls.contoso.com** pour résoudre vers l’adresse IP publique ou l’adresse VIP du service Edge d’accès de Lync local.
    
      - Mettez à jour l’enregistrement SRV ***\_sipfederationtls*.\_tcp.contoso.com** pour résoudre vers l’adresse IP publique ou l’adresse VIP du service Edge d’accès de Lync local.
    
      - Si votre organisation utilise un « DNS split » (également appelé « DNS split-brain »), vérifiez que les utilisateurs qui résolvent des noms par le biais de la zone DNS interne sont dirigés vers le pool frontal.

6.  Tapez l’applet de commande `Get-CsUser` pour vérifier des propriétés concernant les utilisateurs que vous allez déplacer. Vérifiez que HostingProviderProxyFQDN possède la valeur `"sipfed.online.lync.com"` et que les adresses SIP sont définies correctement.

7.  Déplacez les utilisateurs Lync Online vers Lync local.
    
    Pour déplacer un seul utilisateur, tapez ce qui suit :
    
    ```
    $cred = Get-Credential
    ```
    ```
    Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
    ```
    
    Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de commande **Get-CsUSer** avec le paramètre –Filter pour sélectionner les utilisateurs comportant une propriété spécifique. Par exemple, pour sélectionner tous les utilisateurs Lync Online, filtrez sur {Hosting Provider –eq “sipfed.online.lync.om”}. Vous pouvez ensuite rediriger les utilisateurs renvoyés vers l’applet de commande **Move-CsUSer**, comme indiqué ci-dessous.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    L’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit correspondre à celle du pool où le service de migration hébergée s’exécute, au format suivant : *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.
    
    Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.
    
    ## Pour déterminer l’URL du service de migration hébergée de votre client Office 365
    
    1.  Connectez-vous à votre client Office 365 en tant qu’administrateur.
    
    2.  Ouvrez le **Centre d’administration Lync**.
    
    3.  Une fois le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresse jusqu’à **lync.com**. L’URL doit ressembler au format de l’exemple suivant :
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :
        
        `https://admin0a.online.lync.com`
    
    5.  Ajoutez la chaîne suivante à l’URL : **/HostedMigration/hostedmigrationservice.svc**.
        
        L’URL obtenue, qui est la valeur de **HostedMigrationOverrideUrl**, doit se présenter comme suit :
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]  
    > La taille maximale par défaut pour les fichiers journaux de transaction de la base de données rtcxds est de 16 Go. Cette taille peut être insuffisante si vous déplacez simultanément un grand nombre d’utilisateurs, notamment si la mise en miroir est activée. Pour résoudre ce problème, vous pouvez augmenter la taille du fichier ou sauvegarder régulièrement les fichiers journaux. Pour plus d’informations, voir <a href="http://support.microsoft.com/kb/2756725" class="uri">http://support.microsoft.com/kb/2756725</a>.

8.  Il s’agit d’une étape facultative. Pour une intégration à Exchange 2013 Online, vous devez faire appel à un autre fournisseur d’hébergement. Pour plus d’informations, voir [Configuration de l’intégration de Lync Server 2013 local avec Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Les utilisateurs sont maintenant déplacés. Pour vérifier qu’un utilisateur possède des valeurs correctes pour les attributs affichés dans le tableau ci-dessous, tapez cette applet de commande :
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Attribut Active Directory</th>
    <th>Nom Attribut</th>
    <th>Valeur correcte pour l’utilisateur Lync Online</th>
    <th>Valeur correcte pour les utilisateurs Lync locaux</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV:</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>sRTCSIP-UserEnabled</p></td>
    <td><p>Activé</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. Chaque utilisateur déplacé devra se déconnecter de Lync, puis se reconnecter. Lorsque l’utilisateur se reconnecte, il doit vérifier ses listes de contacts et ajouter des contacts, si nécessaire.
    
    Notez que les réunions planifiées ne sont pas migrées de Lync Online vers Lync local. Les utilisateurs doivent replanifier ces réunions après les avoir déplacées.
    
    Après la mise à jour des enregistrements DNS et la redirection de tous les utilisateurs vers l’environnement local, l’attribut HostingProvider indique à l’utilisateur Lync d’utiliser les enregistrements SRV ou le dirige vers le fournisseur en ligne « sipfed.online.lync.com ».

