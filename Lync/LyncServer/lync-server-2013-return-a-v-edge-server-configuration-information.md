---
title: 'Lync Server 2013 : renvoi des informations de configuration du serveur Edge A/V'
description: 'Lync Server 2013 : renvoi des informations de configuration du serveur Edge A/V.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f72fccfe51b946dc0dc285aee12a07e59c844b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575440"
---
# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="5ece6-103">Renvoyer les informations de configuration du serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ece6-103">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ece6-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5ece6-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5ece6-p101">Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). La gestion du service Edge A/V s’effectue à l’aide des paramètres de configuration de ce service. Les paramètres peuvent être configurés au niveau du site ou du service (c’est-à-dire pour un serveur Edge A/V).</span><span class="sxs-lookup"><span data-stu-id="5ece6-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="5ece6-107">Pour renvoyer des informations sur les paramètres de configuration Edge A/V utilisés dans votre organisation, vous devez utiliser Windows PowerShell et l’applet de commande Get-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5ece6-107">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="5ece6-108">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="5ece6-108">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="5ece6-109">Les informations retournées par l’applet de commande Get-CsAVEdgeConfiguration ressemblent à ceci :</span><span class="sxs-lookup"><span data-stu-id="5ece6-109">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="5ece6-110">Pour renvoyer des informations sur tous vos paramètres de configuration de serveur Edge A/V</span><span class="sxs-lookup"><span data-stu-id="5ece6-110">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="5ece6-111">La commande suivante retourne les informations relatives à tous les paramètres de configuration de serveur Edge A/V actuellement utilisés dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="5ece6-111">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="5ece6-112">Pour retourner des informations pour les paramètres de configuration Edge A/V d’étendue site</span><span class="sxs-lookup"><span data-stu-id="5ece6-112">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="5ece6-p103">Pour retourner les informations relatives à une collection spécifique de paramètres de configuration Edge A/V, spécifiez l’identité de cette collection lors de l’exécution de l’applet de commande Get-CsAVEdgeConfiguration. Par exemple, la commande suivante retourne uniquement les informations relatives aux paramètres appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="5ece6-p103">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet. For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="5ece6-115">Pour renvoyer des informations sur les paramètres de configuration Edge A/V à étendue de service</span><span class="sxs-lookup"><span data-stu-id="5ece6-115">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="5ece6-116">La commande suivante retourne uniquement les informations relatives aux paramètres appliqués à un serveur Edge A/V spécifique :</span><span class="sxs-lookup"><span data-stu-id="5ece6-116">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ece6-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ece6-117">See Also</span></span>


[<span data-ttu-id="5ece6-118">Créer ou modifier une collection de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ece6-118">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="5ece6-119">Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ece6-119">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="5ece6-120">Serveurs Edge audio/vidéo (A/V) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ece6-120">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

