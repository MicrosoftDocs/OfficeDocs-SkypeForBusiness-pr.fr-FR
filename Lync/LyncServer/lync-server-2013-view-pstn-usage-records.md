---
title: 'Lync Server 2013 : affichage des enregistrements d’utilisation RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84ba8e2091a88238caee188f3542b76f652129c4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="b4824-102">Afficher les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4824-102">View PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4824-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="b4824-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="b4824-104">Un enregistrement d’utilisation du réseau téléphonique commuté (PSTN) spécifie une classe d’appel (interne, local ou longue distance) réalisable par différents utilisateurs, ou groupes d’utilisateurs, dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="b4824-104">A public switched telephone network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="b4824-105">Pour plus d’informations, reportez-vous à la rubrique [RTC usage Records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="b4824-105">For details, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) in the Planning documentation.</span></span>

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a><span data-ttu-id="b4824-106">Pour afficher un enregistrement d’utilisation PSTN à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="b4824-106">To view a PSTN usage record by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b4824-107">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b4824-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b4824-108">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b4824-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b4824-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4824-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b4824-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b4824-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b4824-111">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Utilisation PSTN**.</span><span class="sxs-lookup"><span data-stu-id="b4824-111">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

4.  <span data-ttu-id="b4824-112">Dans la page **Utilisation PSTN**, sélectionnez l’enregistrement d’utilisation PSTN que vous souhaitez afficher, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b4824-112">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4824-113">Une page en lecture seule de l’enregistrement d’utilisation PSTN sélectionné affiche les itinéraires associés et les stratégies de voix associées.</span><span class="sxs-lookup"><span data-stu-id="b4824-113">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b4824-114">Affichage des informations d’utilisation PSTN à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4824-114">Viewing PSTN Usage Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b4824-115">Vous pouvez également afficher les utilisations PSTN à l’aide de Windows PowerShell et de la cmdlet **Get-CsPstnUsage** .</span><span class="sxs-lookup"><span data-stu-id="b4824-115">You can also view PSTN usages by using Windows PowerShell and the **Get-CsPstnUsage** cmdlet.</span></span> <span data-ttu-id="b4824-116">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4824-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b4824-117">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="b4824-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b4824-118">Pour afficher les informations d’utilisation PSTN à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4824-118">To view PSTN usage information by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="b4824-119">Pour afficher des informations sur toutes vos utilisations RTC, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="b4824-119">To view information about all of your PSTN usages, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsPstnUsage
    
    <span data-ttu-id="b4824-120">Cette commande renvoie le type d’information suivant :</span><span class="sxs-lookup"><span data-stu-id="b4824-120">This command returns information similar to the following:</span></span>
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

<span data-ttu-id="b4824-121">Pour plus d’informations, voir [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span><span class="sxs-lookup"><span data-stu-id="b4824-121">For details, see [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4824-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4824-122">See Also</span></span>


[<span data-ttu-id="b4824-123">Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4824-123">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="b4824-124">Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4824-124">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

