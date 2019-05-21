---
title: Gestion des paramètres du groupe de réponse au niveau de l’application dans Skype entreprise
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Gestion des paramètres du groupe de réponse au niveau de l’application, tels que les paramètres de musique et de rappel, dans Skype entreprise Server voix entreprise.
ms.openlocfilehash: 500ed8942fb859ce41340c94d0568e9e87b1c3d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288525"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="11f0e-103">Gestion des paramètres du groupe de réponse au niveau de l’application dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="11f0e-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="11f0e-104">Gestion des paramètres du groupe de réponse au niveau de l’application, tels que les paramètres de musique et de rappel, dans Skype entreprise Server voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="11f0e-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="11f0e-105">Les paramètres au niveau de l’application de l’application Response Group incluent la configuration par défaut de l’attente de musique, le fichier audio de musique par défaut, la période de grâce aux retours de l’agent et la configuration du contexte d’appel.</span><span class="sxs-lookup"><span data-stu-id="11f0e-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="11f0e-106">Vous pouvez définir un seul ensemble de paramètres de niveau application par pool.</span><span class="sxs-lookup"><span data-stu-id="11f0e-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="11f0e-107">Pour afficher les paramètres de niveau application, utilisez l’applet de commande **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="11f0e-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="11f0e-108">Pour modifier les paramètres de niveau application, utilisez l’applet de commande **Set-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="11f0e-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="11f0e-p102">L’attente musicale par défaut est lue lorsqu’un appel est mis en attente uniquement si aucune attente musicale personnalisée n’est définie. Le contexte de l’appel est disponible uniquement pour les files d’attentes assignées à des flux de travail interactifs. Si le contexte de l’appel est activé, un agent peut afficher des informations telles que le délai d’attente de l’appelant ou des questions et réponses de flux de travail lorsqu’un appel est reçu.</span><span class="sxs-lookup"><span data-stu-id="11f0e-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="11f0e-112">Pour modifier les paramètres au niveau de l’application de Response Group</span><span class="sxs-lookup"><span data-stu-id="11f0e-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="11f0e-113">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="11f0e-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="11f0e-114">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="11f0e-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="11f0e-115">Dans la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="11f0e-115">At the command line, run:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="11f0e-116">Exemple :</span><span class="sxs-lookup"><span data-stu-id="11f0e-116">For example:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="11f0e-p103">Pour spécifier un fichier audio à utiliser comme attente musicale par défaut, vous devez d’abord importer le fichier audio. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="11f0e-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="11f0e-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11f0e-119">See also</span></span>

[<span data-ttu-id="11f0e-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="11f0e-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="11f0e-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="11f0e-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="11f0e-122">Importation-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="11f0e-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
