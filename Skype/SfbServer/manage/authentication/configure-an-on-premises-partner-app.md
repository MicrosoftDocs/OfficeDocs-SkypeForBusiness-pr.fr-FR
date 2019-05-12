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
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="f0bd3-103">Configurer une application de partenaire locale pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f0bd3-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="f0bd3-104">**Résumé :** Configurer une application de partenaire locale pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="f0bd3-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="f0bd3-105">Une fois que vous avez assigné le certificat OAuthTokenIssuer, vous devez alors configurer votre Skype pour les applications partenaires Business Server.</span><span class="sxs-lookup"><span data-stu-id="f0bd3-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="f0bd3-106">(La procédure sur le point d’être présentés configure à la fois Microsoft Exchange Server 2013 et SharePoint en tant que les applications partenaires, qui est facultative.) Pour configurer une application de partenaire locale, vous devez démarrer en copiant le script Windows PowerShell suivant et en collant le code dans le bloc-notes (ou tout autre éditeur de texte) :</span><span class="sxs-lookup"><span data-stu-id="f0bd3-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
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

<span data-ttu-id="f0bd3-107">Une fois le code copié, enregistrez le script avec une extension de fichier .PS1 (par exemple, C:\Scripts\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="f0bd3-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="f0bd3-108">Notez que, avant d’exécuter ce script, vous devez remplacer les URL des métadonnées https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 et http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 avec les URL des métadonnées utilisés par vos serveurs Exchange 2013 et SharePoint, respectivement.</span><span class="sxs-lookup"><span data-stu-id="f0bd3-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="f0bd3-109">Voir la documentation du produit pour Exchange 2013 et SharePoint pour plus d’informations sur comment vous pouvez identifier les URL des métadonnées du produit respectifs.</span><span class="sxs-lookup"><span data-stu-id="f0bd3-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="f0bd3-110">Si vous examinez la dernière ligne du script, vous pouvez constater que l’applet de commande Set-CsOAuthConfiguration est appelée à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="f0bd3-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="f0bd3-p103">Le paramètre Realm n’étant pas utilisé lors de l’appel de Set-CsOAuthConfiguration, le domaine prend automatiquement le nom du domaine complet de votre organisation (par exemple, litwareinc.com). Si le nom de votre domaine est différent de celui de votre organisation, il est conseillé d’inclure le nom du domaine, comme ceci :</span><span class="sxs-lookup"><span data-stu-id="f0bd3-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="f0bd3-113">Après avoir apporté les modifications que vous pouvez exécuter le script et configurer Exchange 2013 et SharePoint en tant qu’applications partenaires, en exécutant le fichier de script à partir de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f0bd3-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f0bd3-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f0bd3-114">For example:</span></span>
  
```
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="f0bd3-115">Notez que vous pouvez exécuter ce script même si vous n’avez pas à la fois Exchange 2013 et SharePoint Server installé :, aucun problème ne survient si, par exemple, configurer SharePoint Server comme application partenaire, même si vous n’avez pas installé de SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="f0bd3-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="f0bd3-116">Lorsque vous exécutez ce script, un message d’erreur comme celui-ci peut s’afficher :</span><span class="sxs-lookup"><span data-stu-id="f0bd3-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="f0bd3-p105">Si ce message d’erreur s’affiche, soit l’une des URL spécifiées dans le script n’est pas valide (autrement dit, l’une de vos URL des métadonnées n’est pas une URL des métadonnées réelle), soit l’une des URL des métadonnées n’a pas pu être contactée. Dans ce cas, vérifiez que les URL sont correctes et accessibles, puis réexécutez le script.</span><span class="sxs-lookup"><span data-stu-id="f0bd3-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="f0bd3-119">Après avoir créé l’application partenaire pour Skype pour Business Server, vous devez alors configurer Skype pour Business Server comme application partenaire pour Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f0bd3-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="f0bd3-120">Vous pouvez configurer les applications partenaires pour Exchange 2013 en exécutant le script Configure-enterprisepartnerapplication.ps1 ; Il vous souhaitez est spécifier l’URL des métadonnées pour Skype pour Business Server et indiquer que Skype pour Business Server est la nouvelle application partenaire.</span><span class="sxs-lookup"><span data-stu-id="f0bd3-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="f0bd3-121">Pour configurer Skype pour Business Server comme application partenaire pour Exchange, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci</span><span class="sxs-lookup"><span data-stu-id="f0bd3-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


