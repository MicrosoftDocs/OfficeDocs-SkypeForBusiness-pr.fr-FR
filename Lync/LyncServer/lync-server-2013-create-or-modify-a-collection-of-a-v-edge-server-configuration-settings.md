---
title: Création ou modification d’une collection de paramètres de configuration de serveur Edge A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2890dd69b8b5fdff58ed2b047b642456657eb0d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c3244-102">Créer ou modifier une collection de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3244-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3244-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c3244-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c3244-p101">Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). La gestion du service Edge A/V s’effectue à l’aide des paramètres de configuration de ce service. Les paramètres peuvent être configurés au niveau du site ou du service (c’est-à-dire pour un serveur Edge A/V).</span><span class="sxs-lookup"><span data-stu-id="c3244-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="c3244-106">Lorsque vous installez Lync Server, une collection globale de paramètres de configuration Edge A/V est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="c3244-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="c3244-107">En outre, vous pouvez utiliser Windows PowerShell et la cmdlet New-CsAVEdgeConfiguration pour créer de nouveaux paramètres au niveau de l’étendue site ou de l’étendue service (c’est-à-dire, pour un serveur Edge A/V individuel).</span><span class="sxs-lookup"><span data-stu-id="c3244-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="c3244-108">Si vous créez des paramètres, gardez à l’esprit les aspects suivants :</span><span class="sxs-lookup"><span data-stu-id="c3244-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="c3244-109">Les paramètres configurés au niveau du service (c’est-à-dire sur un serveur) prévalent sur tous les autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="c3244-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="c3244-p103">Les paramètres configurés au niveau du site prévalent sur les paramètres configurés au niveau global. Les paramètres au niveau du service, quant à eux, prévalent sur les paramètres au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="c3244-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="c3244-112">Les paramètres au niveau global seront utilisés uniquement si aucun autre paramètre du service n’est configuré sur le serveur et s’il n’existe aucun paramètre pour le site où ce serveur est situé.</span><span class="sxs-lookup"><span data-stu-id="c3244-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="c3244-113">Tous vos paramètres peuvent ensuite être modifiés à l’aide de l’applet de commande Set-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c3244-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="c3244-114">Pour plus d’informations, reportez-vous aux rubriques d’aide pour les cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) et [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="c3244-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="c3244-115">Pour créer des paramètres de configuration de serveur Edge A/V au niveau de l’étendue site</span><span class="sxs-lookup"><span data-stu-id="c3244-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="c3244-116">La commande suivante crée une collection de paramètres de configuration Edge A/V pour le site Redmond :</span><span class="sxs-lookup"><span data-stu-id="c3244-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="c3244-117">Pour créer des paramètres de configuration Edge A/V personnalisés au niveau de l’étendue site</span><span class="sxs-lookup"><span data-stu-id="c3244-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="c3244-p105">Dans la mesure où aucun paramètre supplémentaire n’a été inclus, ces nouveaux paramètres utilisent les valeurs par défaut pour le service Edge A/V. Vous pouvez également ajouter des paramètres et des valeurs de paramètres supplémentaires pour créer une collection personnalisée. Par exemple, cette commande définit la propriété MaxTokenLifetime à 4 heures (04 heures : 00 minute : 00 seconde) :</span><span class="sxs-lookup"><span data-stu-id="c3244-p105">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service. Alternatively, you can add additional parameters and parameter values to create a custom collection. For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="c3244-121">Pour créer des paramètres de configuration Edge A/V personnalisés au niveau de l’étendue service</span><span class="sxs-lookup"><span data-stu-id="c3244-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="c3244-122">Cette commande crée une collection similaire appliquée au serveur Edge A/V atl-edge-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="c3244-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="c3244-123">Pour modifier les paramètres de configuration Edge A/V existants</span><span class="sxs-lookup"><span data-stu-id="c3244-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="c3244-124">Dans cet exemple, l’applet de commande Set-CsAVEdgeConfiguration est utilisée pour changer la durée de vie maximale du jeton du site Redmond en la définissant à 12 heures :</span><span class="sxs-lookup"><span data-stu-id="c3244-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3244-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3244-125">See Also</span></span>


[<span data-ttu-id="c3244-126">Renvoyer les informations de configuration du serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3244-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="c3244-127">Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3244-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="c3244-128">Serveurs Edge audio/vidéo (A/V) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3244-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="c3244-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3244-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="c3244-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c3244-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

