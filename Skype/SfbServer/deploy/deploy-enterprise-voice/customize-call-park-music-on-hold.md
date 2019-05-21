---
title: Personnalisation du parc d’appels en attente dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personnalisez le parc d’appels en attente dans Skype entreprise Server Voice.
ms.openlocfilehash: 4111bcc42a3820e3957f526e360264aa7d098d05
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286175"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="8872a-103">Personnalisation du parc d’appels en attente dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="8872a-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="8872a-104">Personnalisez le parc d’appels en attente dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="8872a-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="8872a-105">Vous pouvez spécifier votre propre fichier audio à utiliser pour la musique lors de la mise en attente, au lieu du fichier de musique par défaut fourni avec Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8872a-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="8872a-106">Pour personnaliser l’attente musicale, utilisez l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="8872a-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8872a-107">Si vous personnalisez de la musique pendant l’attente et que vous souhaitez utiliser la même musique pour plusieurs sites, vous devez configurer le fichier de musique pour chaque site exécutant l’application de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="8872a-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="8872a-108">Pour personnaliser le fichier de musique</span><span class="sxs-lookup"><span data-stu-id="8872a-108">To customize the music file</span></span>

1. <span data-ttu-id="8872a-109">Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans **autorisations de configuration de délégué**.</span><span class="sxs-lookup"><span data-stu-id="8872a-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="8872a-110">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8872a-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8872a-111">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="8872a-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="8872a-112">Utilisez l’applet de commande **Get-CsService** pour identifier le service.</span><span class="sxs-lookup"><span data-stu-id="8872a-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="8872a-113">Pour plus d’informations, consultez la rubrique [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8872a-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="8872a-114">L’exemple ci-dessous montre comment obtenir le contenu d’un fichier (soothingmusic.wma) sous forme de tableau d’octets et l’affecter à une variable.</span><span class="sxs-lookup"><span data-stu-id="8872a-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="8872a-115">Le fichier audio est ensuite affecté au fichier d’attente musicale du parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="8872a-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="8872a-116">Pour plus d’informations, consultez la rubrique [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8872a-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="8872a-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8872a-117">See also</span></span>

[<span data-ttu-id="8872a-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="8872a-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="8872a-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="8872a-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
