---
title: Créer ou modifier un ensemble de paramètres de configuration de serveur Edge A/V
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
ms.openlocfilehash: 5c4b45b34b5c52d0eb138fbc16c37e5aaee7262b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="79649-102">Créer ou modifier un ensemble de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79649-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79649-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="79649-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="79649-104">Le service Edge A/V offre aux utilisateurs internes (qui sont connectés à votre réseau d’entreprise) un moyen de partager des fichiers audio et vidéo avec des utilisateurs externes (les utilisateurs qui ne sont pas connectés au réseau de votre organisation).</span><span class="sxs-lookup"><span data-stu-id="79649-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="79649-105">Le service Edge A/V est essentiellement géré à l’aide des paramètres de configuration d’un serveur à l’aide d’une/V, le paramétrage qui peut être configuré sur l’étendue du site ou au niveau de l’étendue de service (autrement dit, peut être configuré pour un serveur Edge A/V individuel).</span><span class="sxs-lookup"><span data-stu-id="79649-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="79649-106">Lorsque vous installez Lync Server, une collection globale des paramètres de configuration de Microsoft Edge a/V est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="79649-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="79649-107">De plus, vous pouvez utiliser Windows PowerShell et l’applet de nouvelle applet de nouveau-CsAVEdgeConfiguration pour créer des paramètres au niveau de l’étendue du site ou l’étendue du service (autrement dit, pour un serveur Edge A/V individuel).</span><span class="sxs-lookup"><span data-stu-id="79649-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="79649-108">Si vous créez de nouveaux paramètres, n’oubliez pas que :</span><span class="sxs-lookup"><span data-stu-id="79649-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="79649-109">Les paramètres configurés au niveau de l’étendue de service (autrement dit, sur un serveur individuel) sont prioritaires sur tout.</span><span class="sxs-lookup"><span data-stu-id="79649-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="79649-110">Les paramètres configurés lors de l’étendue du site sont prioritaires sur les paramètres configurés au niveau de l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="79649-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="79649-111">Toutefois, les paramètres d’étendue de service remplacent également les paramètres d’étendue de site.</span><span class="sxs-lookup"><span data-stu-id="79649-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="79649-112">Les paramètres au niveau de l’étendue globale seront utilisés uniquement s’il n’y a aucun paramètre de service configuré sur le serveur individuel et s’il n’y a aucun paramètre de site pour le site sur lequel se trouve le serveur.</span><span class="sxs-lookup"><span data-stu-id="79649-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="79649-113">Vous pouvez ensuite modifier les paramètres à l’aide de l’applet de applet Set-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="79649-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="79649-114">Pour plus d’informations, consultez les rubriques d’aide pour les applets de [nouvelle-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) et [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="79649-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="79649-115">Pour créer des paramètres de configuration de niveau A/V sur l’étendue du site</span><span class="sxs-lookup"><span data-stu-id="79649-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="79649-116">La commande suivante crée une nouvelle collection de paramètres de configuration Edge A/V pour le site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="79649-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="79649-117">Pour créer des paramètres de configuration de bord A/V personnalisés sur l’étendue du site</span><span class="sxs-lookup"><span data-stu-id="79649-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="79649-118">Aucun paramètre supplémentaire n’ayant été inclus, ces nouveaux paramètres utiliseront les valeurs par défaut pour le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="79649-118">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service.</span></span> <span data-ttu-id="79649-119">Vous pouvez également ajouter des paramètres et des valeurs de paramètre supplémentaires pour créer une collection personnalisée.</span><span class="sxs-lookup"><span data-stu-id="79649-119">Alternatively, you can add additional parameters and parameter values to create a custom collection.</span></span> <span data-ttu-id="79649-120">Par exemple, cette commande définit la propriété MaxTokenLifetime sur 4 heures (04 heures : 00 minutes : 00 secondes) :</span><span class="sxs-lookup"><span data-stu-id="79649-120">For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="79649-121">Pour créer des paramètres de configuration de bord A/V personnalisés sur l’étendue du service</span><span class="sxs-lookup"><span data-stu-id="79649-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="79649-122">Cette commande crée une collection similaire appliquée au serveur Edge A/V atl-edge-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="79649-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="79649-123">Pour modifier les paramètres de configuration de bord A/V existants</span><span class="sxs-lookup"><span data-stu-id="79649-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="79649-124">Dans cet exemple, l’applet de passe Set-CsAVEdgeConfiguration est utilisée pour remplacer la durée de vie du jeton maximale du site de Redmond par 12 heures :</span><span class="sxs-lookup"><span data-stu-id="79649-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79649-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79649-125">See Also</span></span>


[<span data-ttu-id="79649-126">Renvoyer des informations de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79649-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="79649-127">Supprimer une collection existante de paramètres de configuration de serveur Edge A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79649-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="79649-128">Serveurs périphériques audio/vidéo (A/V) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79649-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="79649-129">[Nouveau-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="79649-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="79649-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="79649-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

