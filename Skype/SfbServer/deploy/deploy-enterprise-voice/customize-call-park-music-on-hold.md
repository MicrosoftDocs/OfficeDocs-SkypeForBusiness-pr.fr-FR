---
title: Personnalisation de l’attente musicale du parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personnaliser le parc de l’appel de musique sur Maintenez dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 5af98ee95c59f7fd945232f77d713255ca1c42d5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="customize-call-park-music-on-hold-inskype-for-business-2015"></a><span data-ttu-id="35773-103">Personnalisation de l’attente musicale du parcage d’appel dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="35773-103">Customize Call Park music on hold inSkype for Business 2015</span></span>
 
<span data-ttu-id="35773-104">Personnaliser le parc de l’appel de musique sur Maintenez dans Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="35773-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="35773-105">Vous pouvez spécifier votre propre fichier de musique à utiliser de la musique en attente, et non le fichier de musique par défaut qui est fourni avec Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="35773-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="35773-106">Pour personnaliser la musique en attente, utilisez l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile** .</span><span class="sxs-lookup"><span data-stu-id="35773-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35773-107">Si vous personnalisez musique en attente et que vous souhaitez que la musique même pour plusieurs sites, vous devez configurer le fichier de musique pour chaque site qui exécute l’application d’appel Park.</span><span class="sxs-lookup"><span data-stu-id="35773-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="35773-108">Pour personnaliser le fichier de musique</span><span class="sxs-lookup"><span data-stu-id="35773-108">To customize the music file</span></span>

1. <span data-ttu-id="35773-109">Ouvrez une session sur l’ordinateur où est installé Skype pour Business Server Management Shell en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires, comme décrit dans **Déléguer les autorisations de configuration**.</span><span class="sxs-lookup"><span data-stu-id="35773-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="35773-110">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="35773-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="35773-111">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="35773-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="35773-112">Utilisez l’applet de commande **Get-CsService** pour identifier le service.</span><span class="sxs-lookup"><span data-stu-id="35773-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="35773-113">Pour plus d’informations, consultez [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="35773-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="35773-114">L’exemple ci-dessous montre comment obtenir le contenu d’un fichier (soothingmusic.wma) sous forme de tableau d’octets et l’affecter à une variable.</span><span class="sxs-lookup"><span data-stu-id="35773-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="35773-115">Le fichier audio est ensuite affecté au fichier d’attente musicale du parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="35773-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="35773-116">Pour plus d’informations, voir [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="35773-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="35773-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35773-117">See also</span></span>

#### 

[<span data-ttu-id="35773-118">Ensemble-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="35773-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="35773-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="35773-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)

