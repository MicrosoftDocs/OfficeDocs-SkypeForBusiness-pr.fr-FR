---
title: 'Lync Server 2013 : personnalisation de l’attente musicale du parcage d’appel'
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
ms.openlocfilehash: 18f7ac9793c8275caa20725d2d303c5fca7f534f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516711"
---
# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="32c67-102">Personnalisation de l’attente musicale du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c67-102">Customize Call Park music on hold in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32c67-103">_**Dernière modification de la rubrique :** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="32c67-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="32c67-104">Vous pouvez spécifier votre propre fichier musical à utiliser pour l’attente musicale, au lieu du fichier de musique par défaut fourni avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32c67-104">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="32c67-105">Pour personnaliser l’attente musicale, utilisez l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="32c67-105">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32c67-106">Si vous personnalisez l’attente musicale et souhaitez utiliser la même musique pour plusieurs sites, vous devez configurer le fichier de musique pour chaque site exécutant l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="32c67-106">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="32c67-107">Pour personnaliser le fichier de musique</span><span class="sxs-lookup"><span data-stu-id="32c67-107">To customize the music file</span></span>

1.  <span data-ttu-id="32c67-108">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="32c67-108">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="32c67-109">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="32c67-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="32c67-110">Générer</span><span class="sxs-lookup"><span data-stu-id="32c67-110">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="32c67-111">Utilisez l’applet de commande <STRONG>Get-CsService</STRONG> pour identifier le service.</span><span class="sxs-lookup"><span data-stu-id="32c67-111">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="32c67-112">Pour plus d’informations, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span><span class="sxs-lookup"><span data-stu-id="32c67-112">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="32c67-113">L’exemple suivant montre comment obtenir le contenu d’un fichier (soothingmusic.wma) sous la forme d’un tableau d’octets et l’affecter à une variable.</span><span class="sxs-lookup"><span data-stu-id="32c67-113">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="32c67-114">Le fichier audio est ensuite affecté au fichier d’attente musicale du parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="32c67-114">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="32c67-115">Pour plus d’informations, consultez la rubrique [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span><span class="sxs-lookup"><span data-stu-id="32c67-115">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32c67-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32c67-116">See Also</span></span>


[<span data-ttu-id="32c67-117">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="32c67-117">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="32c67-118">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="32c67-118">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

