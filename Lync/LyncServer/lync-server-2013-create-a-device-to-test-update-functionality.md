---
title: 'Lync Server 2013 : création d’un appareil pour tester la fonctionnalité de mise à jour'
description: 'Lync Server 2013 : créez un appareil pour tester la fonctionnalité de mise à jour.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d45d8970dc72abc8ea6095c879272394e34c54d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542170"
---
# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="5902a-103">Créer un appareil pour tester la fonctionnalité de mise à jour dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5902a-103">Create a device to test update functionality in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5902a-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5902a-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5902a-105">Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier la fonctionnalité des nouvelles mises à jour avant de les déployer sur des périphériques de production.</span><span class="sxs-lookup"><span data-stu-id="5902a-105">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="5902a-106">Vous pouvez tester un appareil globalement (dans l’ensemble de votre environnement Lync Server) ou au sein d’un même site.</span><span class="sxs-lookup"><span data-stu-id="5902a-106">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="5902a-107">Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série.</span><span class="sxs-lookup"><span data-stu-id="5902a-107">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="5902a-108">Lorsque vous ajoutez un périphérique, il apparaît dans la liste sur la page **périphérique de test** du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5902a-108">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="5902a-109">Pour ajouter un périphérique de test</span><span class="sxs-lookup"><span data-stu-id="5902a-109">To add a test device</span></span>

1.  <span data-ttu-id="5902a-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5902a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5902a-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5902a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="5902a-112">Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Périphérique de test**.</span><span class="sxs-lookup"><span data-stu-id="5902a-112">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="5902a-113">Cliquez sur **Nouveau**, puis sur **Périphérique de test global** ou **Périphérique de test sur site**.</span><span class="sxs-lookup"><span data-stu-id="5902a-113">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="5902a-114">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5902a-114">Do one of the following:</span></span>
    
      - <span data-ttu-id="5902a-115">Si vous avez cliqué sur **Périphérique de test global**, passez à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="5902a-115">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="5902a-116">Si vous avez cliqué sur **Périphérique de test sur site**, sélectionnez un site dans la liste des sites disponibles, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5902a-116">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="5902a-117">Dans **Nouveau périphérique de test**, tapez un nom de périphérique dans **Nom du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="5902a-117">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="5902a-118">Sous **Type d’identificateur**, cliquez sur **Adresse MAC** ou **Numéro de série**.</span><span class="sxs-lookup"><span data-stu-id="5902a-118">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="5902a-119">Dans la zone **Identificateur unique**, tapez l’adresse MAC ou le numéro de série du périphérique.</span><span class="sxs-lookup"><span data-stu-id="5902a-119">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="5902a-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5902a-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5902a-121">Création de périphériques de test à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5902a-121">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5902a-122">Les périphériques de test peuvent être créés à l’aide de Windows PowerShell et de l’applet de commande New-CsTestDevice.</span><span class="sxs-lookup"><span data-stu-id="5902a-122">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="5902a-123">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5902a-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5902a-124">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="5902a-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="5902a-125">Lors de la création de périphériques de test à l’aide de cette applet de commande, vous devez effectuer deux opérations :</span><span class="sxs-lookup"><span data-stu-id="5902a-125">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="5902a-126">spécifier MACAddress ou SerialNumber comme IdentifierType ;</span><span class="sxs-lookup"><span data-stu-id="5902a-126">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="5902a-p104">inclure l’étendue lorsque vous spécifiez l’identité du périphérique. Pour créer un périphérique au niveau global, utilisez une syntaxe telle que celle-ci :</span><span class="sxs-lookup"><span data-stu-id="5902a-p104">Include the scope when specifying the device Identity. To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="5902a-129">Pour créer un périphérique de test au niveau de l’étendue Site, utilisez une syntaxe semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="5902a-129">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="5902a-130">Pour créer un périphérique de test à l’aide de l’adresse MAC</span><span class="sxs-lookup"><span data-stu-id="5902a-130">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="5902a-131">Cette commande crée un périphérique de test au niveau de l’étendue Site et utilise l’adresse MAC comme IdentifierType :</span><span class="sxs-lookup"><span data-stu-id="5902a-131">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="5902a-132">Pour créer un périphérique de test à l’aide du numéro de série</span><span class="sxs-lookup"><span data-stu-id="5902a-132">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="5902a-133">Cette commande crée un périphérique de test au niveau de l’étendue Site (pour le site Redmond) et utilise le numéro de série comme IdentifierType :</span><span class="sxs-lookup"><span data-stu-id="5902a-133">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="5902a-134">Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .</span><span class="sxs-lookup"><span data-stu-id="5902a-134">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

