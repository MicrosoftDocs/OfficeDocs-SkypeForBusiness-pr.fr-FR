---
title: 'Lync Server 2013: créer un appareil pour tester la fonctionnalité de mise à jour'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad2fa5283561e1096cfe7e3053db59c3cd2e40e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="85429-102">Créer un appareil pour tester la fonctionnalité de mise à jour dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85429-102">Create a device to test update functionality in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85429-103">_**Dernière modification de la rubrique:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="85429-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="85429-104">Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production.</span><span class="sxs-lookup"><span data-stu-id="85429-104">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="85429-105">Vous pouvez tester globalement un appareil (dans tout votre environnement Lync Server) ou sur un site unique.</span><span class="sxs-lookup"><span data-stu-id="85429-105">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="85429-106">Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série.</span><span class="sxs-lookup"><span data-stu-id="85429-106">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="85429-107">Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page **périphérique de test** du panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85429-107">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="85429-108">Pour ajouter un périphérique de test</span><span class="sxs-lookup"><span data-stu-id="85429-108">To add a test device</span></span>

1.  <span data-ttu-id="85429-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85429-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="85429-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="85429-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="85429-111">Dans la barre de navigation gauche, cliquez sur **clients**, puis sur **tester l’appareil**.</span><span class="sxs-lookup"><span data-stu-id="85429-111">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="85429-112">Cliquez sur **nouveau**, puis sur **périphérique de test global** ou **appareil de test de site**.</span><span class="sxs-lookup"><span data-stu-id="85429-112">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="85429-113">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="85429-113">Do one of the following:</span></span>
    
      - <span data-ttu-id="85429-114">Si vous avez cliqué sur **périphérique de test global**, passez à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="85429-114">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="85429-115">Si vous avez cliqué sur l' **appareil de test de site**, sélectionnez un site dans la liste des sites disponibles, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="85429-115">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="85429-116">Dans **nouvel appareil de test**, tapez un nom pour l’appareil dans nom de l' **appareil**.</span><span class="sxs-lookup"><span data-stu-id="85429-116">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="85429-117">Sous **type d’identificateur**, cliquez sur **adresse Mac** ou **numéro de série**.</span><span class="sxs-lookup"><span data-stu-id="85429-117">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="85429-118">Dans la zone **identificateur unique** , tapez l’adresse Mac ou le numéro de série de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="85429-118">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="85429-119">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="85429-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="85429-120">Création de périphériques de test à l’aide d’applets de contrôle Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="85429-120">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="85429-121">Les appareils de test peuvent être créés à l’aide de Windows PowerShell et de l’applet de contrôle New-CsTestDevice.</span><span class="sxs-lookup"><span data-stu-id="85429-121">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="85429-122">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85429-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="85429-123">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="85429-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="85429-124">Lors de la création de périphériques de test à l’aide de cette applet de contrôle, vous devez effectuer deux opérations:</span><span class="sxs-lookup"><span data-stu-id="85429-124">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="85429-125">Spécifiez MACAddress ou SerialNumber en tant que IdentifierType.</span><span class="sxs-lookup"><span data-stu-id="85429-125">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="85429-126">Incluez l’étendue lors de la spécification de l’identité de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="85429-126">Include the scope when specifying the device Identity.</span></span> <span data-ttu-id="85429-127">Pour créer un nouvel appareil à l’étendue globale, utilisez une syntaxe semblable à celle-ci:</span><span class="sxs-lookup"><span data-stu-id="85429-127">To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="85429-128">Pour créer un périphérique de test à l’étendue du site, utilisez une syntaxe semblable à celle-ci:</span><span class="sxs-lookup"><span data-stu-id="85429-128">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="85429-129">Pour créer un périphérique de test à l’aide de l’adresse MAC</span><span class="sxs-lookup"><span data-stu-id="85429-129">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="85429-130">Cette commande crée un appareil de test à l’étendue globale et utilise l’adresse MAC comme IdentifierType:</span><span class="sxs-lookup"><span data-stu-id="85429-130">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="85429-131">Pour créer un périphérique de test à l’aide du numéro de série</span><span class="sxs-lookup"><span data-stu-id="85429-131">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="85429-132">Cette commande crée un nouveau périphérique de test sur l’étendue du site (pour le site de Redmond) et utilise le numéro de série en tant que IdentifierType:</span><span class="sxs-lookup"><span data-stu-id="85429-132">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="85429-133">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de [nouvelle-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .</span><span class="sxs-lookup"><span data-stu-id="85429-133">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

