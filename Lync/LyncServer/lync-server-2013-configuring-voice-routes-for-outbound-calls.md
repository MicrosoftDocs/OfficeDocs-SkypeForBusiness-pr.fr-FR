---
title: 'Lync Server 2013 : Configuration des itinéraires de communications vocales pour les appels sortants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e91525f5d35110560b28059f774be8d2cb5df6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="38d96-102">Configuration des itinéraires de communications vocales pour les appels sortants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d96-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38d96-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="38d96-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="38d96-104">Un itinéraire vocal de Lync Server 2013 associe des numéros de téléphone de destination à une ou plusieurs passerelles de réseau téléphonique commuté (PSTN) ou des Trunks SIP et un ou plusieurs enregistrements d’utilisation PSTN.</span><span class="sxs-lookup"><span data-stu-id="38d96-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="38d96-105">**Pour afficher les itinéraires vocaux à l’aide du panneau de configuration de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="38d96-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="38d96-106">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38d96-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="38d96-107">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="38d96-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="38d96-108">Cliquez sur **gamme vocale**.</span><span class="sxs-lookup"><span data-stu-id="38d96-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="38d96-109">Cliquez sur **Itinéraire**.</span><span class="sxs-lookup"><span data-stu-id="38d96-109">Click **Route**.</span></span>

4.  <span data-ttu-id="38d96-110">Double-cliquez sur un itinéraire vocal pour afficher d’autres propriétés dans la liste des itinéraires vocaux, ou sélectionnez l’itinéraire, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="38d96-110">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**.</span></span> <span data-ttu-id="38d96-111">Cliquez ensuite sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="38d96-111">Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38d96-112">Vous pouvez uniquement afficher des informations détaillées sur un itinéraire à la fois.</span><span class="sxs-lookup"><span data-stu-id="38d96-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="38d96-113">**Pour afficher les itinéraires vocaux à l’aide de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="38d96-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="38d96-114">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="38d96-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="38d96-115">Les itinéraires vocaux peuvent être affichés à l’aide de Windows PowerShell et de l’applet **de passe Get-CsVoiceRoute** .</span><span class="sxs-lookup"><span data-stu-id="38d96-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="38d96-116">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38d96-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="38d96-117">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="38d96-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="38d96-118">Pour afficher des informations sur l’ensemble de vos itinéraires vocaux, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="38d96-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="38d96-119">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="38d96-119">That will return information similar to this:</span></span>
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> <span data-ttu-id="38d96-120">Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-voice-routes.md">itinéraires vocaux dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="38d96-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="38d96-121">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="38d96-121">In This Section</span></span>

  - [<span data-ttu-id="38d96-122">Créer un itinéraire vocal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d96-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="38d96-123">Modifier un itinéraire vocal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d96-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38d96-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="38d96-124">See Also</span></span>


[<span data-ttu-id="38d96-125">Gestion du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d96-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

