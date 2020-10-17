---
title: 'Lync Server 2013 : configuration des itinéraires des communications vocales pour les appels sortants'
description: 'Lync Server 2013 : configuration des itinéraires des communications vocales pour les appels sortants.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd0d712295ecdd0e9a517330abcff36021e996d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542210"
---
# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="cdba8-103">Configuration des itinéraires des communications vocales pour les appels sortants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdba8-103">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdba8-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cdba8-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cdba8-105">Un itinéraire de communications vocales Lync Server 2013 associe les numéros de téléphone de destination à une ou plusieurs passerelles de réseau téléphonique commuté (PSTN) ou à des jonctions SIP, ainsi qu’un ou plusieurs enregistrements d’utilisation PSTN.</span><span class="sxs-lookup"><span data-stu-id="cdba8-105">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="cdba8-106">**Pour afficher les itinéraires des communications vocales à l’aide du panneau de configuration Lync Server**</span><span class="sxs-lookup"><span data-stu-id="cdba8-106">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="cdba8-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdba8-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cdba8-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cdba8-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="cdba8-109">Cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="cdba8-109">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="cdba8-110">Cliquez sur **Itinéraire**.</span><span class="sxs-lookup"><span data-stu-id="cdba8-110">Click **Route**.</span></span>

4.  <span data-ttu-id="cdba8-p102">Double-cliquez sur un itinéraire de communications vocales pour afficher les autres propriétés de la liste des itinéraires de communications vocales ou sélectionnez l’itinéraire, puis cliquez sur **Modifier**. Cliquez ensuite sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="cdba8-p102">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**. Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cdba8-113">Vous ne pouvez afficher les informations détaillées que d’un seul itinéraire à la fois.</span><span class="sxs-lookup"><span data-stu-id="cdba8-113">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="cdba8-114">**Pour afficher les itinéraires des communications vocales à l’aide de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cdba8-114">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="cdba8-115">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cdba8-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="cdba8-116">Les itinéraires des communications vocales peuvent être affichés à l’aide de Windows PowerShell et de l’applet de commande **Get-CsVoiceRoute** .</span><span class="sxs-lookup"><span data-stu-id="cdba8-116">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="cdba8-117">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdba8-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cdba8-118">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="cdba8-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="cdba8-119">Pour afficher des informations sur tous vos itinéraires vocaux, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="cdba8-119">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="cdba8-120">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="cdba8-120">That will return information similar to this:</span></span>
    
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
> <span data-ttu-id="cdba8-121">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="cdba8-121">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cdba8-122">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="cdba8-122">In This Section</span></span>

  - [<span data-ttu-id="cdba8-123">Créer un itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdba8-123">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="cdba8-124">Modifier un itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdba8-124">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cdba8-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cdba8-125">See Also</span></span>


[<span data-ttu-id="cdba8-126">Gestion du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdba8-126">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

