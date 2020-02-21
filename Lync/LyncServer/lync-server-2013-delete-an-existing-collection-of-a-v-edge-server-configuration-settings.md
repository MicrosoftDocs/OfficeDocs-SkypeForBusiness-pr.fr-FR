---
title: Supprimer une collection existante de paramètres de configuration de serveur Edge A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7043b2ce5fd35e36615b7b92d1561d725a86cc92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="26aa8-102">Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26aa8-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26aa8-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="26aa8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="26aa8-p101">Le service Edge A/V permet à vos utilisateurs internes (les utilisateurs connectés au réseau de votre organisation) de partager des fichiers audio et vidéo avec des utilisateurs externes (des utilisateurs qui ne sont pas connectés au réseau de votre organisation). La gestion du service Edge A/V s’effectue à l’aide des paramètres de configuration de ce service. Les paramètres peuvent être configurés au niveau du site ou du service (c’est-à-dire pour un serveur Edge A/V).</span><span class="sxs-lookup"><span data-stu-id="26aa8-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="26aa8-106">Lorsque vous installez Lync Server, une collection globale de paramètres de configuration Edge A/V est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="26aa8-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="26aa8-107">Cette collection globale ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="26aa8-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="26aa8-108">Toutefois, vous pouvez utiliser Windows PowerShell et l’applet de commande Remove-CsAVEdgeConfiguration pour « réinitialiser » la collection globale ; Cela signifie simplement que toutes les valeurs de propriété de la collection globale seront réinitialisées à leur valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="26aa8-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="26aa8-109">Par exemple, si vous avez affecté à la propriété MaxTokenLifetime un nombre d’heures égal à 16, la valeur par défaut (à savoir 8 heures) de cette propriété est rétablie.</span><span class="sxs-lookup"><span data-stu-id="26aa8-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="26aa8-p103">Toutefois, vous pouvez supprimer les collections de paramètres personnalisées que vous avez créées au niveau de l’étendue du site ou du service à l’aide de l’applet de commande Remove-CsAVEdgeConfiguration. Si vous supprimez les paramètres au niveau du site, les serveurs Edge A/V dans ce site sont alors gérés par les paramètres globaux. Si vous supprimez les paramètres au niveau du service, ce serveur est alors géré par ses paramètres de site (le cas échéant) ou par les paramètres globaux si aucun paramètre de site n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="26aa8-p103">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet. If you delete site settings then A/V Edge servers in that site will be managed by the global settings. If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="26aa8-113">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="26aa8-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="26aa8-114">Pour réinitialiser la collection globale</span><span class="sxs-lookup"><span data-stu-id="26aa8-114">To reset the global collection</span></span>

  - <span data-ttu-id="26aa8-115">La commande suivante réinitialise la collection globale des paramètres de configuration Edge A/V :</span><span class="sxs-lookup"><span data-stu-id="26aa8-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="26aa8-116">Pour supprimer une collection de l’étendue site</span><span class="sxs-lookup"><span data-stu-id="26aa8-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="26aa8-117">Cette commande supprime les paramètres de configuration Edge A/V appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="26aa8-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="26aa8-118">Pour supprimer une collection de l’étendue service</span><span class="sxs-lookup"><span data-stu-id="26aa8-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="26aa8-119">Cette commande supprime les paramètres appliqués au serveur Edge A/V atl-edge-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="26aa8-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="26aa8-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26aa8-120">See Also</span></span>


[<span data-ttu-id="26aa8-121">Renvoyer les informations de configuration du serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26aa8-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="26aa8-122">Créer ou modifier une collection de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26aa8-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="26aa8-123">Serveurs Edge audio/vidéo (A/V) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26aa8-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="26aa8-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="26aa8-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

