---
title: "Conf. d’une application partenaire locale pour Microsoft Lync Server 2013"
TOCtitle: "Conf. d’une application partenaire locale pour Microsoft Lync Server 2013"
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204975(v=OCS.15)
ms:contentKeyID: 49297492
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’une application partenaire locale pour Microsoft Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-04_

Après avoir affecté le certificat OAuthTokenIssuer, vous devez configurer vos applications partenaires Microsoft Lync Server 2013. (La procédure traitée ici configure Microsoft Exchange Server 2013 et Microsoft SharePoint comme applications partenaires.) Pour configurer une application partenaire sur site, vous devez d’abord copier le script Windows PowerShell suivant et coller le code dans le Bloc-notes (ou tout autre éditeur de texte) :

    if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
       {
           Remove-CsPartnerApplication app
       }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
    New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
               }
         }
    
    $shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
            
    if ($shp -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
        }
    else
        {
           if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.sharepoint
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Une fois le code copié, enregistrez le script avec une extension de fichier .PS1 (par exemple, C:\\Scripts\\ServerToServerAuth.ps1). Notez qu’avant d’exécuter ce script, vous devez remplacer les URL des métadonnées https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 et http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx par les URL des métadonnées utilisées par vos serveurs Exchange 2013 et SharePoint, respectivement. Pour plus d’informations sur la façon d’identifier l’URL des métadonnées de chaque produit, voir la documentation du produit pour Exchange 2013 et SharePoint.

Si vous examinez la dernière ligne du script, vous pouvez constater que l’applet de commande Set-CsOAuthConfiguration est appelée à l’aide de cette syntaxe :

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Le paramètre Realm n’étant pas utilisé lors de l’appel de Set-CsOAuthConfiguration, le domaine prend automatiquement le nom de domaine complet de votre organisation (par exemple, litwareinc.com). Si le nom de votre domaine est différent de celui de votre organisation, il est conseillé d’inclure le nom du domaine, comme ceci :

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

Après avoir apporté ces modifications, vous pouvez exécuter le script et configurer Exchange 2013 et SharePoint comme applications partenaires en exécutant le fichier de script à partir de Lync Server 2013 Management Shell. Par exemple :

    C:\Scripts\ServerToServerAuth.ps1

Notez que vous pouvez exécuter ce script même si Exchange 2013 et SharePoint Server ne sont pas tous les deux installés. Par exemple, aucun problème ne se produit si vous configurez SharePoint Server comme application partenaire et que SharePoint Server n’est pas installé.

Lorsque vous exécutez ce script, vous pouvez recevoir un message d’erreur semblable au suivant :

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

Si vous recevez ce message d’erreur, de deux choses l’une : soit l’une des URL spécifiées dans le script n’est pas valide (autrement dit, l’une de vos URL des métadonnées n’est pas une URL des métadonnées réelle), soit l’une des URL des métadonnées n’a pas pu être contactée. Dans ce cas, vérifiez que les URL sont correctes et accessibles, puis réexécutez le script.

Après avoir créé l’application partenaire pour Lync Server 2013, vous devez configurer Lync Server comme application partenaire pour Exchange 2013. Vous pouvez configurer des applications partenaires pour Exchange 2013 en exécutant le script Configure-EnterprisePartnerApplication.1 ; pour cela, il vous suffit de spécifier l’URL des métadonnées pour Lync Server et d’indiquer que Lync Server est la nouvelle application partenaire.

Pour configurer Lync Server comme application partenaire pour Exchange, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci.

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

