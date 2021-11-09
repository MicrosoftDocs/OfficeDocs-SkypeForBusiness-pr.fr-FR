---
title: Configurer une application partenaire sur site pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Résumé : Configurez une application partenaire sur site pour Skype Entreprise Server.'
ms.openlocfilehash: c922765e81c0507e6eca9e81047cce4dfbb6dd6c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846467"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Configurer une application partenaire sur site pour Skype Entreprise Server
 
**Résumé :** Configurez une application partenaire sur site pour Skype Entreprise Server.
  
Une fois que vous avez affecté le certificat OAuthTokenIssuer, vous devez configurer Skype Entreprise Server applications partenaires. (La procédure sur le point d’être abordée configure à la fois Microsoft Exchange Server 2013 et SharePoint en tant qu’applications partenaires, ce qui est facultatif.) Pour configurer une application partenaire sur site, vous devez commencer par copier le script Windows PowerShell suivant et coller le code dans Bloc-notes (ou tout autre éditeur de texte) :
  
```PowerShell
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
  
             New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl https://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
            }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Une fois le code copié, enregistrez le script avec une extension de fichier .PS1 (par exemple, C:\Scripts\ServerToServerAuth.ps1). Notez que, avant d’exécuter ce script, vous devez remplacer les URL de métadonnées et les URL de métadonnées utilisées par vos serveurs `https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1` `http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1` Exchange 2013 et SharePoint, respectivement. Consultez la documentation du produit Exchange 2013 et SharePoint pour plus d’informations sur la façon d’identifier l’URL des métadonnées du produit respectif.
  
Si vous examinez la dernière ligne du script, vous pouvez constater que l’applet de commande Set-CsOAuthConfiguration est appelée à l’aide de cette syntaxe :
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Le paramètre Realm n’étant pas utilisé lors de l’appel de Set-CsOAuthConfiguration, le domaine prend automatiquement le nom de domaine complet de votre organisation (par exemple, litwareinc.com). Si le nom de votre domaine est différent de celui de votre organisation, il est conseillé d’inclure le nom du domaine, comme ceci :
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

Après avoir apporté ces modifications, vous pouvez exécuter le script et configurer Exchange 2013 et SharePoint en tant qu’applications partenaires en exécutant le fichier de script à partir de Skype Entreprise Server Management Shell. Par exemple :
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

Notez que vous pouvez exécuter ce script même si Exchange 2013 et SharePoint Server ne sont pas installés :, aucun problème ne se produit si vous configurez SharePoint Server en tant qu’application partenaire même si SharePoint Server n’est pas installé.
  
Lorsque vous exécutez ce script, vous pouvez recevoir un message d’erreur semblable au suivant :
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Si vous recevez ce message d’erreur, de deux choses l’une : soit l’une des URL spécifiées dans le script n’est pas valide (autrement dit, l’une de vos URL des métadonnées n’est pas une URL des métadonnées réelle), soit l’une des URL des métadonnées n’a pas pu être contactée. Dans ce cas, vérifiez que les URL sont correctes et accessibles, puis réexécutez le script.
  
Après avoir créé l’application partenaire pour Skype Entreprise Server vous devez ensuite configurer Skype Entreprise Server en tant qu’application partenaire pour Exchange 2013. Vous pouvez configurer des applications partenaires pour Exchange 2013 en exécutant le script Configure-EnterprisePartnerApplication.ps1 ; Il vous suffit de spécifier l’URL des métadonnées pour Skype Entreprise Server et d’indiquer Skype Entreprise Server est la nouvelle application partenaire. 
  
Pour configurer Skype Entreprise Server en tant qu’application partenaire pour Exchange, ouvrez Exchange Management Shell et exécutez une commande semblable à celle-ci.
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


