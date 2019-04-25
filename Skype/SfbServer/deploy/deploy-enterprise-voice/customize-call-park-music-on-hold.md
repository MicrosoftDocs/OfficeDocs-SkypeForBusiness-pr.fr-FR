---
title: Personnaliser une musique de parcage d’appel d’attente inSkype pour les entreprises
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personnaliser la mise en garde d’appels musicale dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: e3d1ccdf70278173bf5a3a448e5330a24879d117
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223183"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="d6fe4-103">Personnaliser une musique de parcage d’appel d’attente inSkype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="d6fe4-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="d6fe4-104">Personnaliser la mise en garde d’appels musicale dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d6fe4-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d6fe4-105">Vous pouvez spécifier votre propre fichier de musique à utiliser pour une musique d’attente, plutôt que le fichier de musique par défaut fourni avec Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="d6fe4-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="d6fe4-106">Pour personnaliser l’attente musicale, utilisez l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="d6fe4-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6fe4-107">Si vous personnalisez l’attente musicale et que vous voulez utiliser la même musique pour plusieurs sites, vous devez configurer le fichier de musique pour chaque site qui exécute l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="d6fe4-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="d6fe4-108">Pour personnaliser le fichier de musique</span><span class="sxs-lookup"><span data-stu-id="d6fe4-108">To customize the music file</span></span>

1. <span data-ttu-id="d6fe4-109">Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.</span><span class="sxs-lookup"><span data-stu-id="d6fe4-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="d6fe4-110">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d6fe4-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d6fe4-111">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="d6fe4-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="d6fe4-112">Utilisez l’applet de commande **Get-CsService** pour identifier le service.</span><span class="sxs-lookup"><span data-stu-id="d6fe4-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="d6fe4-113">Pour plus d’informations, voir [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d6fe4-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="d6fe4-114">L’exemple ci-dessous montre comment obtenir le contenu d’un fichier (soothingmusic.wma) sous forme de tableau d’octets et l’affecter à une variable.</span><span class="sxs-lookup"><span data-stu-id="d6fe4-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="d6fe4-115">Le fichier audio est ensuite affecté au fichier d’attente musicale du parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="d6fe4-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="d6fe4-116">Pour plus d’informations, voir [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d6fe4-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="d6fe4-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6fe4-117">See also</span></span>

[<span data-ttu-id="d6fe4-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="d6fe4-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="d6fe4-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="d6fe4-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
