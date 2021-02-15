---
title: Personnalisation de l’attente musicale du parc d’appel dansSkype pour les entreprises
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: Personnalisez l’attente musicale du parcier d’appel dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 766b51895acda27c0558352968d21a39764b13a6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837074"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="3bdd1-103">Personnalisation de l’attente musicale du parc d’appel dansSkype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="3bdd1-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="3bdd1-104">Personnalisez l’attente musicale du parcier d’appel dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="3bdd1-105">Vous pouvez spécifier votre propre fichier de musique à utiliser pour l’attente musicale, au lieu du fichier de musique par défaut qui est utilisé avec Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="3bdd1-106">Pour personnaliser l’attente musicale, utilisez l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3bdd1-107">Si vous personnalisez l’attente musicale et que vous souhaitez la même musique pour plusieurs sites, vous devez configurer le fichier de musique pour chaque site qui exécute l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="3bdd1-108">Pour personnaliser le fichier de musique</span><span class="sxs-lookup"><span data-stu-id="3bdd1-108">To customize the music file</span></span>

1. <span data-ttu-id="3bdd1-109">Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="3bdd1-110">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="3bdd1-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3bdd1-111">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="3bdd1-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="3bdd1-112">Utilisez l’applet de commande **Get-CsService** pour identifier le service.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="3bdd1-113">Pour plus d’informations, [voir Get-CsService.](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3bdd1-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="3bdd1-114">L’exemple suivant montre comment obtenir le contenu d’un fichier (soothingmusic.wma) sous la forme d’un tableau d’octets et l’affecter à une variable.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="3bdd1-115">Le fichier audio est ensuite affecté au fichier d’attente musicale du parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="3bdd1-116">Pour plus d’informations, [voir Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3bdd1-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="3bdd1-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3bdd1-117">See also</span></span>

[<span data-ttu-id="3bdd1-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="3bdd1-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="3bdd1-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="3bdd1-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
