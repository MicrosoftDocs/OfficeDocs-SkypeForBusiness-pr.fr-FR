---
title: 'Lync Server 2013 : personnaliser le parc d’appels en attente de musique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 301625a36d23c69d02dfdcde8c4985def53630af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="c7e8d-102">Personnaliser le parc d’appels en attente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7e8d-102">Customize Call Park music on hold in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7e8d-103">_**Dernière modification de la rubrique :** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="c7e8d-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="c7e8d-104">Vous pouvez spécifier votre propre fichier audio à utiliser pour la musique en attente au lieu du fichier de musique par défaut fourni avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7e8d-104">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="c7e8d-105">Pour personnaliser l’attente musicale, utilisez l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="c7e8d-105">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7e8d-106">Si vous personnalisez de la musique pendant l’attente et que vous souhaitez utiliser la même musique pour plusieurs sites, vous devez configurer le fichier de musique pour chaque site exécutant l’application de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="c7e8d-106">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="c7e8d-107">Pour personnaliser le fichier de musique</span><span class="sxs-lookup"><span data-stu-id="c7e8d-107">To customize the music file</span></span>

1.  <span data-ttu-id="c7e8d-108">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c7e8d-108">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c7e8d-109">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c7e8d-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c7e8d-110">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="c7e8d-110">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c7e8d-111">Utilisez l’applet de commande <STRONG>Get-CsService</STRONG> pour identifier le service.</span><span class="sxs-lookup"><span data-stu-id="c7e8d-111">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="c7e8d-112">Pour plus d’informations, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span><span class="sxs-lookup"><span data-stu-id="c7e8d-112">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="c7e8d-113">L’exemple ci-dessous montre comment obtenir le contenu d’un fichier (soothingmusic.wma) sous forme de tableau d’octets et l’affecter à une variable.</span><span class="sxs-lookup"><span data-stu-id="c7e8d-113">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="c7e8d-114">Le fichier audio est ensuite affecté au fichier d’attente musicale du parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="c7e8d-114">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="c7e8d-115">Pour plus d’informations, consultez la rubrique [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span><span class="sxs-lookup"><span data-stu-id="c7e8d-115">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7e8d-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7e8d-116">See Also</span></span>


[<span data-ttu-id="c7e8d-117">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="c7e8d-117">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="c7e8d-118">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="c7e8d-118">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

