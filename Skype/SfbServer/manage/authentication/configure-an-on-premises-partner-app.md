---
title: Configuration d’une application partenaire locale pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Résumé : Configurer une application de partenaires locaux pour Skype pour Business Server 2015.'
ms.openlocfilehash: 4a31d97f7a4c2f717084c72cbc349c4f495597ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server-2015"></a>Configuration d’une application partenaire locale pour Skype Entreprise Server 2015
 
**Résumé :** Configurer une application de partenaires locaux pour Skype pour Business Server 2015.
  
Après avoir attribué le certificat OAuthTokenIssuer vous devez alors configurer votre Skype pour applications de partenaires Business Server 2015. (La procédure sur le point d’être présentés configure à la fois Microsoft Exchange Server 2013 et SharePoint en tant que les applications partenaires, qui est facultatif.) Pour configurer une application de partenaires locaux, vous devez démarrer en copiant le script Windows PowerShell suivant et en collant le code dans le bloc-notes (ou tout autre éditeur de texte) :
  
```
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

Une fois le code copié, enregistrez le script avec une extension de fichier .PS1 (par exemple, C:\Scripts\ServerToServerAuth.ps1). Notez que, avant d’exécuter ce script, vous devez remplacer les URL de métadonnées https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 et http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 avec les URL de métadonnées utilisés par vos serveurs Exchange 2013 et SharePoint, respectivement. Consultez la documentation du produit pour 2013 d’Exchange et SharePoint pour plus d’informations sur comment vous pouvez identifier les URL des métadonnées du produit respectives.
  
Si vous examinez la dernière ligne du script, vous pouvez constater que l’applet de commande Set-CsOAuthConfiguration est appelée à l’aide de cette syntaxe :
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Le paramètre Realm n’étant pas utilisé lors de l’appel de Set-CsOAuthConfiguration, le domaine prend automatiquement le nom du domaine complet de votre organisation (par exemple, litwareinc.com). Si le nom de votre domaine est différent de celui de votre organisation, il est conseillé d’inclure le nom du domaine, comme ceci :
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

Après avoir apporté ces modifications, vous pouvez exécuter le script et configurer Exchange 2013 et SharePoint en tant qu’applications de partenaires, en exécutant le fichier script dans le Skype pour Business Server Management Shell. Par exemple :
  
```
C:\Scripts\ServerToServerAuth.ps1
```

Notez que vous pouvez exécuter ce script même si vous n’avez pas à la fois 2013 Exchange et SharePoint Server installé :, aucun problème ne surviendra si, par exemple, configurer SharePoint Server sous la forme d’une application de partenaire, même si vous n’avez pas installé de SharePoint Server.
  
Lorsque vous exécutez ce script, un message d’erreur comme celui-ci peut s’afficher :
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Si ce message d’erreur s’affiche, soit l’une des URL spécifiées dans le script n’est pas valide (autrement dit, l’une de vos URL des métadonnées n’est pas une URL des métadonnées réelle), soit l’une des URL des métadonnées n’a pas pu être contactée. Dans ce cas, vérifiez que les URL sont correctes et accessibles, puis réexécutez le script.
  
Après avoir créé l’application partenaire pour Skype pour Business Server 2015, vous devez alors configurer Skype pour Business Server pour une application de partenaires pour Exchange 2013. Vous pouvez configurer les applications partenaires pour Exchange 2013 en exécutant le script Configure-EnterprisePartnerApplication.ps1 ; Il vous suffit de faire est de spécifier l’URL des métadonnées de Skype pour Business Server et d’indiquer que Skype pour Business Server est la nouvelle application de partenaire. 
  
Pour configurer Skype pour Business Server en tant que demande de partenariat pour Exchange, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


