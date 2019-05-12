---
title: Configurer une application de partenaire locale pour Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Résumé : Configurer une application de partenaire locale pour Skype pour Business Server.'
ms.openlocfilehash: a13157d590d6cdd067ed2a0a717fd744adb9de4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913376"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Configurer une application de partenaire locale pour Skype pour Business Server
 
**Résumé :** Configurer une application de partenaire locale pour Skype pour Business Server.
  
Une fois que vous avez assigné le certificat OAuthTokenIssuer, vous devez alors configurer votre Skype pour les applications partenaires Business Server. (La procédure sur le point d’être présentés configure à la fois Microsoft Exchange Server 2013 et SharePoint en tant que les applications partenaires, qui est facultative.) Pour configurer une application de partenaire locale, vous devez démarrer en copiant le script Windows PowerShell suivant et en collant le code dans le bloc-notes (ou tout autre éditeur de texte) :
  
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

Une fois le code copié, enregistrez le script avec une extension de fichier .PS1 (par exemple, C:\Scripts\ServerToServerAuth.ps1). Notez que, avant d’exécuter ce script, vous devez remplacer les URL des métadonnées https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 et http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 avec les URL des métadonnées utilisés par vos serveurs Exchange 2013 et SharePoint, respectivement. Voir la documentation du produit pour Exchange 2013 et SharePoint pour plus d’informations sur comment vous pouvez identifier les URL des métadonnées du produit respectifs.
  
Si vous examinez la dernière ligne du script, vous pouvez constater que l’applet de commande Set-CsOAuthConfiguration est appelée à l’aide de cette syntaxe :
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Le paramètre Realm n’étant pas utilisé lors de l’appel de Set-CsOAuthConfiguration, le domaine prend automatiquement le nom du domaine complet de votre organisation (par exemple, litwareinc.com). Si le nom de votre domaine est différent de celui de votre organisation, il est conseillé d’inclure le nom du domaine, comme ceci :
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

Après avoir apporté les modifications que vous pouvez exécuter le script et configurer Exchange 2013 et SharePoint en tant qu’applications partenaires, en exécutant le fichier de script à partir de la Skype pour Business Server Management Shell. Par exemple :
  
```
C:\Scripts\ServerToServerAuth.ps1
```

Notez que vous pouvez exécuter ce script même si vous n’avez pas à la fois Exchange 2013 et SharePoint Server installé :, aucun problème ne survient si, par exemple, configurer SharePoint Server comme application partenaire, même si vous n’avez pas installé de SharePoint Server.
  
Lorsque vous exécutez ce script, un message d’erreur comme celui-ci peut s’afficher :
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Si ce message d’erreur s’affiche, soit l’une des URL spécifiées dans le script n’est pas valide (autrement dit, l’une de vos URL des métadonnées n’est pas une URL des métadonnées réelle), soit l’une des URL des métadonnées n’a pas pu être contactée. Dans ce cas, vérifiez que les URL sont correctes et accessibles, puis réexécutez le script.
  
Après avoir créé l’application partenaire pour Skype pour Business Server, vous devez alors configurer Skype pour Business Server comme application partenaire pour Exchange 2013. Vous pouvez configurer les applications partenaires pour Exchange 2013 en exécutant le script Configure-enterprisepartnerapplication.ps1 ; Il vous souhaitez est spécifier l’URL des métadonnées pour Skype pour Business Server et indiquer que Skype pour Business Server est la nouvelle application partenaire. 
  
Pour configurer Skype pour Business Server comme application partenaire pour Exchange, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


