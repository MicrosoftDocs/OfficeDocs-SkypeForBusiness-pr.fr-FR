---
title: Configurer une application partenaire sur site pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Résumé : Configurez une application partenaire sur site pour Skype Entreprise Server.'
ms.openlocfilehash: 82db666dbbd94fdae8a99bca13954d33d6d5805f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828434"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="03802-103">Configurer une application partenaire sur site pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="03802-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="03802-104">**Résumé :** Configurez une application partenaire sur site pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="03802-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="03802-105">Une fois que vous avez affecté le certificat OAuthTokenIssuer, vous devez configurer vos applications partenaires Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="03802-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="03802-106">(La procédure sur le point d’être abordée configure à la fois Microsoft Exchange Server 2013 et SharePoint pour qu’ils agissent en tant qu’applications partenaires, ce qui est facultatif.) Pour configurer une application partenaire sur site, vous devez commencer par copier le script Windows PowerShell suivant et coller le code dans le Bloc-notes (ou tout autre éditeur de texte) :</span><span class="sxs-lookup"><span data-stu-id="03802-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
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

<span data-ttu-id="03802-107">Une fois le code copié, enregistrez le script avec une extension de fichier .PS1 (par exemple, C:\Scripts\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="03802-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="03802-108">Notez que, avant d’exécuter ce script, vous devez remplacer les URL de métadonnées et les URL de métadonnées utilisées respectivement par vos serveurs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 Exchange 2013 et SharePoint.</span><span class="sxs-lookup"><span data-stu-id="03802-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="03802-109">Pour plus d’informations sur l’identification de l’URL des métadonnées du produit respectif, voir la documentation produit pour Exchange 2013 et SharePoint.</span><span class="sxs-lookup"><span data-stu-id="03802-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="03802-110">Si vous examinez la dernière ligne du script, vous pouvez constater que l’applet de commande Set-CsOAuthConfiguration est appelée à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="03802-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="03802-p103">Le paramètre Realm n’étant pas utilisé lors de l’appel de Set-CsOAuthConfiguration, le domaine prend automatiquement le nom de domaine complet de votre organisation (par exemple, litwareinc.com). Si le nom de votre domaine est différent de celui de votre organisation, il est conseillé d’inclure le nom du domaine, comme ceci :</span><span class="sxs-lookup"><span data-stu-id="03802-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="03802-113">Après avoir apporté ces modifications, vous pouvez exécuter le script et configurer Exchange 2013 et SharePoint en tant qu’applications partenaires en exécutant le fichier de script à partir de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="03802-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="03802-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="03802-114">For example:</span></span>
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="03802-115">Notez que vous pouvez exécuter ce script même si Exchange 2013 et SharePoint Server ne sont pas installés :, aucun problème ne se produit si vous configurez SharePoint Server en tant qu’application partenaire même si SharePoint Server n’est pas installé.</span><span class="sxs-lookup"><span data-stu-id="03802-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="03802-116">Lorsque vous exécutez ce script, vous pouvez recevoir un message d’erreur semblable au suivant :</span><span class="sxs-lookup"><span data-stu-id="03802-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="03802-p105">Si vous recevez ce message d’erreur, de deux choses l’une : soit l’une des URL spécifiées dans le script n’est pas valide (autrement dit, l’une de vos URL des métadonnées n’est pas une URL des métadonnées réelle), soit l’une des URL des métadonnées n’a pas pu être contactée. Dans ce cas, vérifiez que les URL sont correctes et accessibles, puis réexécutez le script.</span><span class="sxs-lookup"><span data-stu-id="03802-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="03802-119">Après avoir créé l’application partenaire pour Skype Entreprise Server, vous devez configurer Skype Entreprise Server comme application partenaire pour Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="03802-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="03802-120">Vous pouvez configurer des applications partenaires pour Exchange 2013 en exécutant le script Configure-EnterprisePartnerApplication.ps1 ; Il vous suffit de spécifier l’URL des métadonnées pour Skype Entreprise Server et d’indiquer que Skype Entreprise Server est la nouvelle application partenaire.</span><span class="sxs-lookup"><span data-stu-id="03802-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="03802-121">Pour configurer Skype Entreprise Server en tant qu’application partenaire pour Exchange, ouvrez l’Exchange Management Shell et exécutez une commande semblable à celle-ci</span><span class="sxs-lookup"><span data-stu-id="03802-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


