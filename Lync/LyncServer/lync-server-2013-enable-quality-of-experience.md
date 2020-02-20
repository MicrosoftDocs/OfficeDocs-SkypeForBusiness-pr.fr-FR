---
title: 'Lync Server 2013 : activation de la qualité de l’expérience'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5d3dcdc918469488b6cb0a555cb90e42fe68785
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="4302f-102">Activer la qualité de l’expérience dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4302f-102">Enable Quality of Experience in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4302f-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4302f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4302f-104">La qualité de l’expérience (QoE) enregistre des données numériques qui indiquent la qualité du média, ainsi que les informations sur les participants, les noms des appareils, les pilotes, les adresses IP et les types de point de terminaison impliqués dans les appels et les sessions.</span><span class="sxs-lookup"><span data-stu-id="4302f-104">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="4302f-105">Pour plus d’informations, reportez-vous à la rubrique [Planning for Monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="4302f-105">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="4302f-106">Procédez comme suit pour activer la QoE dans toute l’entreprise ou dans chacun de ses sites.</span><span class="sxs-lookup"><span data-stu-id="4302f-106">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4302f-107">Pour activer la qualité de l’expérience, vous devez commencer par configurer la surveillance et une base de données principale de surveillance.</span><span class="sxs-lookup"><span data-stu-id="4302f-107">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="4302f-108">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4302f-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="4302f-109">Pour activer la qualité de l’utilisation à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="4302f-109">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4302f-110">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4302f-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="4302f-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4302f-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4302f-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4302f-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4302f-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="4302f-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="4302f-114">Dans la page **Données de qualité de l’expérience**, cliquez sur la collection appropriée dans le tableau, sur **Action**, puis sur **Activer QoE**.</span><span class="sxs-lookup"><span data-stu-id="4302f-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4302f-115">Activation du QoE à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4302f-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4302f-116">Vous pouvez activer la qualité de l’utilisation à l’aide de Windows PowerShell et de l’applet de commande **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4302f-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="4302f-117">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4302f-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4302f-118">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="4302f-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="4302f-119">Pour activer la qualité de l’expérience pour un emplacement</span><span class="sxs-lookup"><span data-stu-id="4302f-119">To enable QoE for a single location</span></span>

  - <span data-ttu-id="4302f-120">Pour activer la qualité de l’expérience, définissez le paramètre EnableQoE sur True ($True).</span><span class="sxs-lookup"><span data-stu-id="4302f-120">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="4302f-121">Pour désactiver la qualité de l’expérience pour un emplacement</span><span class="sxs-lookup"><span data-stu-id="4302f-121">To disable QoE for a single location</span></span>

  - <span data-ttu-id="4302f-p105">Pour désactiver la qualité de l’expérience, définissez le paramètre EnableQoE sur False ($False). Ceci ne désinstalle pas la surveillance, mais suspend la collecte et le stockage des données de qualité de l’expérience.</span><span class="sxs-lookup"><span data-stu-id="4302f-p105">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="4302f-125">Pour utiliser une commande pour activer la qualité de l’expérience dans plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="4302f-125">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="4302f-126">Cette commande active la qualité de l’expérience pour tous les paramètres de configuration QoE actuellement utilisés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4302f-126">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="4302f-127">Pour plus d’informations, consultez la rubrique [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="4302f-127">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4302f-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4302f-128">See Also</span></span>


[<span data-ttu-id="4302f-129">Planification de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4302f-129">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="4302f-130">Déploiement de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4302f-130">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

