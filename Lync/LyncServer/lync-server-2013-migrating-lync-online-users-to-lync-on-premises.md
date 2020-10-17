---
title: 'Lync Server 2013 : migration des utilisateurs Lync Online vers Lync local'
description: 'Lync Server 2013 : migration des utilisateurs Lync Online vers Lync local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 620bc07def8e3c1f6b761c6398b452b4dbcd3b04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561000"
---
# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Migration des utilisateurs Lync Online vers Lync sur site dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> Ces étapes sont nécessaires uniquement pour la migration des comptes d’utilisateurs qui ont été activés à l’origine pour Lync dans Lync Online, avant le déploiement de Lync sur site. Pour déplacer les utilisateurs activés à l’origine pour Lync sur site, puis déplacés vers Lync Online, reportez-vous à <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">la rubrique Administering users in a Hybrid Lync Server 2013 Deployment</A>.<BR>De plus, tous les utilisateurs déplacés doivent disposer de comptes dans l’annuaire Active Directory local.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Migration des comptes d’utilisateur activés à l’origine dans Lync Online vers Lync local

1.  Tout d’abord, assurez-vous que votre organisation est configurée pour l’environnement hybride.
    
      - Installez l’outil de synchronisation Azure Active Directory. Pour plus d'informations, reportez-vous à l'article <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.
    
      - Pour permettre à vos utilisateurs d’utiliser l’authentification unique pour Lync Online, installez les services ADFS (Active Directory Federation Services) <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> .
    
      - Sur votre déploiement local, dans Lync Server Management Shell, tapez les applets de commande suivantes pour créer le fournisseur d’hébergement pour Lync Online :
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  Vérifiez que, sur vos serveurs Edge locaux, vous disposez de la chaîne de certificats qui permet la connexion à Lync Online, comme illustré dans le tableau suivant. Vous pouvez télécharger cette chaîne ici : https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


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
    <td><p>Microsoft Internet Authority (nouveau certificat d’autorité de certification)</p></td>
    <td><p>Autorité de certification intermédiaire</p></td>
    </tr>
    <tr class="odd">
    <td><p>CA2 d’authentification de l’ordinateur MSIT (nouvelle émission de CA2)</p></td>
    <td><p>Autorité de certification intermédiaire</p></td>
    </tr>
    </tbody>
    </table>

3.  Dans votre annuaire Active Directory local, activez les comptes d’utilisateur affectés pour Lync sur site. Vous pouvez effectuer cette opération pour un utilisateur individuel en tapant l’applet de commande suivante :
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    Vous pouvez aussi créer un script qui lit les noms d’utilisateur à partir d’un fichier et les fournit en tant qu’entrée à l’applet de commande Enable-CsUser :
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  Exécutez DirSync pour synchroniser les utilisateurs Lync Online avec les utilisateurs de Lync sur site mis à jour.

5.  Mettre à jour certains enregistrements DNS pour diriger tout le trafic SIP vers Lync en local :
    
      - Mettez à jour l’enregistrement **Lyncdiscover.contoso.com** A de sorte qu’il pointe vers le nom de domaine complet du serveur proxy inverse local.
    
      - Mettez à jour le *** \_ SIP *. \_ **enregistrement SRV TLS.contoso.com à convertir en adresse IP publique ou adresse IP virtuelle du service Edge d’accès de Lync sur site.
    
      - Mettre à jour les *** \_ sipfederationtls *. \_ **enregistrement SRV TCP.contoso.com à convertir en adresse IP publique ou adresse IP virtuelle du service Edge d’accès de Lync sur site.
    
      - Si votre organisation utilise le DNS fractionné (parfois appelé « DNS split-brain »), assurez-vous que les utilisateurs résolvent les noms par le biais de la zone DNS interne sont dirigés vers le pool frontal.

6.  Tapez l' `Get-CsUser` applet de commande pour vérifier certaines propriétés des utilisateurs que vous allez déplacer. Vous voulez vous assurer que le HostingProviderProxyFQDN est défini sur `"sipfed.online.lync.com"` et que les adresses SIP sont définies correctement.

7.  Déplacez les utilisateurs Lync Online vers Lync local.
    
    Pour déplacer un seul utilisateur, tapez ce qui suit :
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    Vous pouvez déplacer plusieurs utilisateurs à l’aide de la cmdlet **Get-CsUSer** avec le paramètre – Filter pour sélectionner les utilisateurs avec une propriété spécifique. Par exemple, vous pouvez sélectionner tous les utilisateurs Lync Online en filtrant pour {Hosting Provider – EQ "sipfed.online.lync.om"}. Vous pouvez ensuite rediriger les utilisateurs renvoyés vers l’applet de commande **Move-CsUSer** , comme indiqué ci-dessous.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être l’URL du pool où le service de migration hébergée est en cours d’exécution, au format suivant : *https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc*.
    
    Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du panneau de configuration Lync Online pour votre compte d’organisation Microsoft 365 ou Office 365.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a>Pour déterminer l’URL du service de migration hébergée pour votre Organizaton
    
    1.  Connectez-vous à votre organisation Microsoft 365 ou Office 365 en tant qu’administrateur.
    
    2.  Ouvrez le **Centre d’administration Lync**.
    
    3.  Avec le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresse jusqu’à **Lync.com**. Un exemple d’URL doit ressembler à ce qui suit :
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  Remplacez **webdir** dans l’URL par **administrateur**, de la façon suivante :
        
        `https://admin0a.online.lync.com`
    
    5.  Ajoutez la chaîne suivante à l’URL : **/HostedMigration/hostedmigrationservice.svc**.
        
        L’URL résultante, qui est la valeur de **HostedMigrationOverrideUrl**, doit ressembler à ce qui suit :
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > La taille maximale par défaut pour les fichiers journaux des transactions de la base de données rtcxds est de 16 Go. Cela n’est peut-être pas assez grand si vous déplacez un grand nombre d’utilisateurs à la fois, en particulier si vous avez activé la mise en miroir. Pour contourner ce risque, vous pouvez augmenter la taille du fichier ou sauvegarder les fichiers journaux régulièrement. Pour plus d’informations, reportez-vous à <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> .

    
    </div>

8.  Il s’agit d’une étape facultative. Si vous avez besoin d’une intégration à Exchange 2013 Online, vous devez utiliser un fournisseur d’hébergement supplémentaire. Pour plus d’informations, reportez-vous à la rubrique [Configuring on-premises Lync Server 2013 Integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).

9.  Les utilisateurs sont déplacés. Pour vérifier qu’un utilisateur a des valeurs correctes pour les attributs indiqués dans le tableau suivant, tapez cette applet de commande :
    
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
    <th>Nom de l’attribut</th>
    <th>Valeur correcte pour l’utilisateur Lync Online</th>
    <th>Valeur correcte pour les utilisateurs de Lync sur site</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV</p></td>
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
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. Chaque utilisateur qui a été déplacé doit se déconnecter de Lync, puis se reconnecter. Lorsqu’ils se connectent, ils doivent vérifier leurs listes de contacts et ajouter des contacts si nécessaire.
    
    Notez que les réunions planifiées ne sont pas migrées de Lync Online vers Lync en local. Les utilisateurs devront replanifier ces réunions après leur déplacement.
    
    Une fois que les enregistrements DNS sont mis à jour et que tous les utilisateurs sont dirigés vers le site, l’attribut HostingProvider indique à l’utilisateur Lync d’utiliser des enregistrements SRV ou de les diriger vers le fournisseur en ligne « sipfed.online.lync.com ».

</div>

</div>

<span> </span>

</div>

</div>

</div>

