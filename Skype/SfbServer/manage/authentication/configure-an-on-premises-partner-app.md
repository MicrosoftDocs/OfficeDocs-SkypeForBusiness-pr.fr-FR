---
title: Configurer une application partenaire locale pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Résumé : configurez une application partenaire locale pour Skype entreprise Server.'
ms.openlocfilehash: 3f8aa3bfc7407ccf6409d00c540cfeab724913ab
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818826"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Configurer une application partenaire locale pour Skype entreprise Server
 
**Résumé :** Configurer une application partenaire locale pour Skype entreprise Server.
  
Une fois que vous avez attribué le certificat OAuthTokenIssuer, vous devez configurer vos applications de partenariat Skype entreprise Server. (La procédure à suivre est décrite dans la configuration de Microsoft Exchange Server 2013 et de SharePoint pour agir en tant qu’application partenaire (facultatif). Pour configurer une application partenaire locale, vous devez commencer par copier le script Windows PowerShell suivant et en le collant dans le bloc-notes (ou dans tout autre éditeur de texte) :
  
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

Une fois le code copié, enregistrez le script avec une extension de fichier .PS1 (par exemple, C:\Scripts\ServerToServerAuth.ps1). Notez que, avant d’exécuter ce script, vous devez remplacer les URL https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 de métadonnées et http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 les URL de métadonnées utilisées par vos serveurs Exchange 2013 et SharePoint, respectivement. Pour plus d’informations sur l’identification de l’URL de métadonnées du produit correspondant, voir la documentation du produit pour Exchange 2013 et SharePoint.
  
Si vous examinez la dernière ligne du script, vous pouvez constater que l’applet de commande Set-CsOAuthConfiguration est appelée à l’aide de cette syntaxe :
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Le paramètre Realm n’étant pas utilisé lors de l’appel de Set-CsOAuthConfiguration, le domaine prend automatiquement le nom du domaine complet de votre organisation (par exemple, litwareinc.com). Si le nom de votre domaine est différent de celui de votre organisation, il est conseillé d’inclure le nom du domaine, comme ceci :
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

Après avoir effectué ces modifications, vous pouvez exécuter le script et configurer Exchange 2013 et SharePoint en tant qu’applications partenaires en exécutant le fichier de script à partir de Skype entreprise Server Management Shell. Par exemple :
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

Notez que vous pouvez exécuter ce script même si Exchange 2013 et SharePoint Server n’est pas installé sur votre ordinateur : aucun problème ne se produit si vous le souhaitez, par exemple, configurer SharePoint Server en tant qu’application partenaire même si SharePoint Server n’est pas installé.
  
Lorsque vous exécutez ce script, un message d’erreur comme celui-ci peut s’afficher :
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Si ce message d’erreur s’affiche, soit l’une des URL spécifiées dans le script n’est pas valide (autrement dit, l’une de vos URL des métadonnées n’est pas une URL des métadonnées réelle), soit l’une des URL des métadonnées n’a pas pu être contactée. Dans ce cas, vérifiez que les URL sont correctes et accessibles, puis réexécutez le script.
  
Après la création de l’application partenaire pour Skype entreprise Server, vous devez ensuite configurer Skype entreprise Server en tant qu’application partenaire pour Exchange 2013. Vous pouvez configurer les applications partenaires pour Exchange 2013 en exécutant le script Configure-EnterprisePartnerApplication. ps1 ; pour cela, il vous suffit de spécifier l’URL de métadonnées de Skype entreprise Server et de signaler que Skype entreprise Server est la nouvelle application partenaire. 
  
Pour configurer Skype entreprise Server en tant qu’application partenaire pour Exchange, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


