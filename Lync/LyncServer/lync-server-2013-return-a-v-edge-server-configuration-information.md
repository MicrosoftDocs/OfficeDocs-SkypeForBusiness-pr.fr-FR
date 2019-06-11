---
title: 'Lync Server 2013: renvoi des informations de configuration de serveur Edge A/V'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15096099184525890328dbe1c89d891487b46d87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="d67b7-102">Renvoyer des informations de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d67b7-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d67b7-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d67b7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d67b7-104">Le service Edge A/V offre aux utilisateurs internes (qui sont connectés à votre réseau d’entreprise) un moyen de partager des fichiers audio et vidéo avec des utilisateurs externes (les utilisateurs qui ne sont pas connectés au réseau de votre organisation).</span><span class="sxs-lookup"><span data-stu-id="d67b7-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="d67b7-105">Le service Edge A/V est essentiellement géré à l’aide des paramètres de configuration d’un serveur à l’aide d’une/V, le paramétrage qui peut être configuré sur l’étendue du site ou au niveau de l’étendue de service (autrement dit, peut être configuré pour un serveur Edge A/V individuel).</span><span class="sxs-lookup"><span data-stu-id="d67b7-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="d67b7-106">Pour renvoyer des informations sur les paramètres de configuration A/V en usage dans votre organisation, vous devez utiliser Windows PowerShell et l’applet de passe Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d67b7-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="d67b7-107">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="d67b7-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="d67b7-108">Les informations renvoyées par l’applet de requête get-CsAVEdgeConfiguration se présentent comme suit:</span><span class="sxs-lookup"><span data-stu-id="d67b7-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="d67b7-109">Pour renvoyer des informations pour tous les paramètres de configuration de Microsoft A/V Edge</span><span class="sxs-lookup"><span data-stu-id="d67b7-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="d67b7-110">La commande suivante renvoie des informations sur l’ensemble des paramètres de configuration d’une bordure A/V actuellement utilisés au sein de votre organisation:</span><span class="sxs-lookup"><span data-stu-id="d67b7-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="d67b7-111">Pour renvoyer des informations sur les paramètres de configuration de périmètre A/V d’une application de site</span><span class="sxs-lookup"><span data-stu-id="d67b7-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="d67b7-112">Pour renvoyer des informations sur une collection spécifique de paramètres de configuration de bord A/V, spécifiez l’identité de cette collection lorsque vous exécutez l’applet de cmdlet Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d67b7-112">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="d67b7-113">Par exemple, cette commande renvoie uniquement des informations sur les paramètres appliqués au site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="d67b7-113">For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="d67b7-114">Pour renvoyer des informations sur les paramètres de configuration de périmètre d’une application de service A/V</span><span class="sxs-lookup"><span data-stu-id="d67b7-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="d67b7-115">Cette commande renvoie des informations uniquement pour les paramètres appliqués à un serveur Edge A/V spécifique.</span><span class="sxs-lookup"><span data-stu-id="d67b7-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d67b7-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d67b7-116">See Also</span></span>


[<span data-ttu-id="d67b7-117">Créer ou modifier un ensemble de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d67b7-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="d67b7-118">Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d67b7-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="d67b7-119">Serveurs périphériques audio/vidéo (A/V) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d67b7-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

