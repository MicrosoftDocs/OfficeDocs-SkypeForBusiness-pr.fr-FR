---
title: 'Lync Server 2013 : gestion des paramètres de groupe Response Group au niveau de l’application'
description: 'Lync Server 2013 : gestion des paramètres de groupe Response Group au niveau de l’application.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd362cbe8ce738a16639b89edd79439b564444ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555270"
---
# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="b4ad8-103">Gestion des paramètres de groupe Response Group au niveau de l’application dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4ad8-103">Managing application-level Response Group settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4ad8-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b4ad8-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b4ad8-105">Les paramètres au niveau de l’application pour l’application Response Group incluent la configuration de l’attente musicale par défaut, le fichier audio de l’attente musicale par défaut, la période de grâce de l’appel d’invocation d’agent et la configuration du contexte de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b4ad8-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="b4ad8-106">Vous pouvez définir un seul jeu de paramètres de niveau application par pool.</span><span class="sxs-lookup"><span data-stu-id="b4ad8-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="b4ad8-107">Pour afficher les paramètres de niveau application, utilisez l’applet de commande **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b4ad8-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="b4ad8-108">Pour modifier les paramètres de niveau application, utilisez l’applet de commande **Set-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b4ad8-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="b4ad8-p102">L’attente musicale par défaut est lue lorsqu’un appel est mis en attente uniquement si aucune attente musicale personnalisée n’est définie. Le contexte de l’appel est disponible uniquement pour les files d’attentes assignées à des flux de travail interactifs. Si le contexte de l’appel est activé, un agent peut afficher des informations telles que le délai d’attente de l’appelant ou des questions et réponses de flux de travail lorsqu’un appel est reçu.</span><span class="sxs-lookup"><span data-stu-id="b4ad8-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="b4ad8-112">Pour modifier les paramètres de niveau application du groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="b4ad8-112">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="b4ad8-113">Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.</span><span class="sxs-lookup"><span data-stu-id="b4ad8-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="b4ad8-114">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b4ad8-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b4ad8-115">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b4ad8-115">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="b4ad8-116">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b4ad8-116">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="b4ad8-p103">Pour spécifier un fichier audio à utiliser comme attente musicale par défaut, vous devez d’abord importer le fichier audio. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b4ad8-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4ad8-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4ad8-119">See Also</span></span>


[<span data-ttu-id="b4ad8-120">Get-applet csrgsconfiguration</span><span class="sxs-lookup"><span data-stu-id="b4ad8-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="b4ad8-121">Set-applet csrgsconfiguration</span><span class="sxs-lookup"><span data-stu-id="b4ad8-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="b4ad8-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="b4ad8-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

