---
title: Configuration d’une application partenaire locale pour Lync Server 2013
description: Configuration d’une application partenaire locale pour Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0401634c6cb7afc451652ffbaf55cdc01a7ca89
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570920"
---
# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a><span data-ttu-id="801eb-103">Configuration d’une application partenaire locale pour Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="801eb-103">Configuring an on-premises partner application for Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="801eb-104">_**Dernière modification de la rubrique :** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="801eb-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="801eb-105">Une fois que vous avez affecté le certificat OAuthTokenIssuer, vous devez configurer vos applications partenaires Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="801eb-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Microsoft Lync Server 2013 partner applications.</span></span> <span data-ttu-id="801eb-106">(La procédure sur le point d’être abordée configure Microsoft Exchange Server 2013 et Microsoft SharePoint pour agir en tant qu’applications partenaires.) Pour configurer une application partenaire sur site, vous devez commencer par copier le script Windows PowerShell suivant et le coller dans le bloc-notes (ou tout autre éditeur de texte) :</span><span class="sxs-lookup"><span data-stu-id="801eb-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and Microsoft SharePoint to act as partner applications.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>

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

<span data-ttu-id="801eb-107">Après avoir copié le code, enregistrez le script à l’aide d’un fichier. Extension de fichier PS1 (par exemple, C : \\ Scripts \\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="801eb-107">After copying the code, save the script using a .PS1 file extension (for example, C:\\Scripts\\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="801eb-108">Notez que, avant d’exécuter ce script, vous devez remplacer les URL de métadonnées https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 et http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx les URL de métadonnées utilisées par vos serveurs Exchange 2013 et SharePoint, respectivement.</span><span class="sxs-lookup"><span data-stu-id="801eb-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="801eb-109">Pour plus d’informations sur l’identification de l’URL de métadonnées du produit respectif, voir la documentation du produit pour Exchange 2013 et SharePoint.</span><span class="sxs-lookup"><span data-stu-id="801eb-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>

<span data-ttu-id="801eb-110">Si vous examinez la dernière ligne du script, vous pouvez constater que l’applet de commande Set-CsOAuthConfiguration est appelée à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="801eb-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="801eb-p103">Le paramètre Realm n’étant pas utilisé lors de l’appel de Set-CsOAuthConfiguration, le domaine prend automatiquement le nom de domaine complet de votre organisation (par exemple, litwareinc.com). Si le nom de votre domaine est différent de celui de votre organisation, il est conseillé d’inclure le nom du domaine, comme ceci :</span><span class="sxs-lookup"><span data-stu-id="801eb-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

<span data-ttu-id="801eb-113">Après avoir effectué ces modifications, vous pouvez exécuter le script et configurer Exchange 2013 et SharePoint en tant qu’applications partenaires en exécutant le fichier de script à partir de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="801eb-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="801eb-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="801eb-114">For example:</span></span>

    C:\Scripts\ServerToServerAuth.ps1

<span data-ttu-id="801eb-115">Notez que vous pouvez exécuter ce script même si Exchange 2013 et SharePoint Server ne sont pas installés :, par exemple, si vous configurez SharePoint Server en tant qu’application partenaire même si SharePoint Server n’est pas installé.</span><span class="sxs-lookup"><span data-stu-id="801eb-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>

<span data-ttu-id="801eb-116">Lorsque vous exécutez ce script, vous pouvez recevoir un message d’erreur semblable au suivant :</span><span class="sxs-lookup"><span data-stu-id="801eb-116">When you run this script you might receive an error message similar to the following:</span></span>

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

<span data-ttu-id="801eb-p105">Si vous recevez ce message d’erreur, de deux choses l’une : soit l’une des URL spécifiées dans le script n’est pas valide (autrement dit, l’une de vos URL des métadonnées n’est pas une URL des métadonnées réelle), soit l’une des URL des métadonnées n’a pas pu être contactée. Dans ce cas, vérifiez que les URL sont correctes et accessibles, puis réexécutez le script.</span><span class="sxs-lookup"><span data-stu-id="801eb-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>

<span data-ttu-id="801eb-119">Après avoir créé l’application partenaire pour Lync Server 2013, vous devez configurer Lync Server pour qu’il soit une application partenaire pour Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="801eb-119">After creating the partner application for Lync Server 2013 you must then configure Lync Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="801eb-120">Vous pouvez configurer les applications partenaires pour Exchange 2013 en exécutant le script Configure-EnterprisePartnerApplication.ps1 ; il vous suffit de spécifier l’URL de métadonnées pour Lync Server et d’indiquer que Lync Server est la nouvelle application partenaire.</span><span class="sxs-lookup"><span data-stu-id="801eb-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Lync Server and indicate that Lync Server is the new partner application.</span></span>

<span data-ttu-id="801eb-121">Pour configurer Lync Server comme application partenaire pour Exchange, ouvrez l’environnement de commande Exchange Management Shell et exécutez une commande similaire à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="801eb-121">To configure Lync Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

