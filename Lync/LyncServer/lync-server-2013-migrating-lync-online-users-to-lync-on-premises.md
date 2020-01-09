---
title: 'Lync Server 2013 : migration des utilisateurs Lync Online vers Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47fb8d24a2bb112ab07d35097414141b9eaaa606
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Migration des utilisateurs Lync Online vers Lync local dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Ces étapes sont nécessaires uniquement pour la migration des comptes d’utilisateurs qui ont été activés pour Lync dans Lync Online avant de déployer Lync en local. Pour déplacer des utilisateurs qui ont été activés pour Lync local, puis transférés plus tard vers Lync Online, voir <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">administration des utilisateurs dans un déploiement 2013 Lync Server</A>.<BR>De plus, tous les utilisateurs en cours de déplacement doivent disposer de comptes dans l’instance locale d’Active Directory.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Migration des comptes d’utilisateurs activés dans Lync Online vers Lync local

1.  Tout d’abord, assurez-vous que votre organisation est configurée pour l’environnement hybride.
    
      - Installez l’outil de synchronisation Azure Active Directory. Pour plus d’informations, <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>reportez-vous à.
    
      - Pour permettre à vos utilisateurs d’utiliser l’authentification unique pour Lync Online, installez les services ADFS ( <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>Active Directory Federation Services).
    
      - Sur votre déploiement local, dans Lync Server Management Shell, entrez les applets de commande suivantes pour créer le fournisseur d’hébergement pour Lync Online :
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Vérifiez que, sur votre serveur Edge local, vous disposez de la chaîne de certificats qui permet de se connecter à Lync Online, comme indiqué dans le tableau suivant. Vous pouvez télécharger cette chaîne à l’adresse suivante :https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


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
    <td><p>Certificat racine de CyberTrust Baltimore</p></td>
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

3.  Dans votre Active Directory local, activez les comptes d’utilisateurs concernés pour Lync local. Pour un utilisateur individuel, tapez l’applet de commande suivante :
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    Vous pouvez également créer un script qui lit les noms d’utilisateur dans un fichier et les transmet comme informations à l’applet de commande Enable-CsUser :
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Exécutez DirSync pour synchroniser les utilisateurs Lync Online avec les utilisateurs Lync locaux mis à jour.

5.  Mettez à jour les enregistrements DNS pour acheminer l’ensemble du trafic SIP vers Lync local :
    
      - Mettez à jour **lyncdiscover.contoso.com**  Un enregistrement pour pointer vers le nom de domaine complet (FQDN) du serveur proxy inverse local.
    
      - Mettez à jour le ***\_SIP\_ *. tls.contoso.com** SRV enregistrement pour la résolution vers l’adresse IP ou VIP publique du service Edge d’accès de Lync local.
    
      - Mettez à jour ***\_sipfederationtls *\_ . tcp.contoso.com** SRV enregistrement pour la résolution vers l’adresse IP ou VIP publique du service Edge d’accès de Lync local.
    
      - Si votre organisation utilise un « DNS split » (également appelé « DNS split-brain »), vérifiez que les utilisateurs qui résolvent des noms par le biais de la zone DNS interne sont dirigés vers le pool frontal.

6.  Tapez l' `Get-CsUser` applet de recherche pour vérifier certaines propriétés des utilisateurs que vous allez déplacer. Vous voulez vous assurer que HostingProviderProxyFQDN est défini sur `"sipfed.online.lync.com"` et que les adresses SIP sont correctement définies.

7.  Déplacez les utilisateurs Lync Online vers Lync local.
    
    Pour déplacer un seul utilisateur, tapez ce qui suit :
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de commande **Get-CsUSer**  avec le paramètre –Filter pour sélectionner les utilisateurs comportant une propriété spécifique. Par exemple, vous pouvez sélectionner tous les utilisateurs de Lync Online en filtrant pour {Hosting Provider-EQ "sipfed.online.lync.om"}. Vous pouvez ensuite rediriger les utilisateurs renvoyés vers l’applet de commande **Move-CsUSer**, comme indiqué ci-dessous.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    Le format de l’URL spécifiée pour le paramètre **hostedmigrationoverrideurl doit correspondre** doit être l’URL du pool sur lequel le service de migration hébergé est en cours d’exécution, au format suivant : *nom de domaine complet\<\>https:///HostedMigration/hostedmigrationService.svc*.
    
    Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Pour déterminer l’URL du service de migration hébergée de votre client Office 365
    
    1.  Connectez-vous à votre client Office 365 en tant qu’administrateur.
    
    2.  Ouvrez le **Centre d’administration Lync**.
    
    3.  Avec le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresses jusqu’à **Lync.com**. L’URL doit se présenter comme dans l’exemple suivant :
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :
        
        `https://admin0a.online.lync.com`
    
    5.  Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.
        
        L’URL obtenue, qui est la valeur de **HostedMigrationOverrideUrl**, doit se présenter comme suit :
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > La taille maximale par défaut pour les fichiers journaux de transaction de la base de données rtcxds est de 16 Go. Cette taille peut être insuffisante si vous déplacez simultanément un grand nombre d’utilisateurs, notamment si la mise en miroir est activée. Pour résoudre ce problème, vous pouvez augmenter la taille du fichier ou sauvegarder régulièrement les fichiers journaux. Pour plus d’informations, <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>reportez-vous à.

    
    </div>

8.  Il s’agit d’une étape facultative. Pour une intégration à Exchange 2013 Online, vous devez utiliser un autre fournisseur d’hébergement. Pour plus d’informations, reportez-vous à la rubrique [configuration d’une intégration de Lync Server 2013 en local avec Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

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
    <th>Valeur correcte pour l’utilisateur de Lync Online</th>
    <th>Valeur correcte pour les utilisateurs Lync local</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV :</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP-UserEnabled</p></td>
    <td><p>Activé</p></td>
    <td><p>Vrai</p></td>
    <td><p>Vrai</p></td>
    </tr>
    </tbody>
    </table>


10. Chaque utilisateur déplacé aura besoin de se déconnecter de Lync, puis de vous reconnecter. Lorsque l’utilisateur se reconnecte, il doit vérifier ses listes de contacts et ajouter des contacts, si nécessaire.
    
    Notez que les réunions planifiées ne sont pas déplacées de Lync Online vers Lync local. Les utilisateurs doivent replanifier ces réunions après les avoir déplacées.
    
    Une fois que les enregistrements DNS sont mis à jour et que tous les utilisateurs sont dirigés vers le site, l’attribut HostingProvider indique à l’utilisateur de Lync d’utiliser des enregistrements SRV ou de le diriger vers le fournisseur en ligne « sipfed.online.lync.com ».

</div>

</div>

<span> </span>

</div>

</div>

</div>

