---
title: 'Lync Server 2013 : activation de l’enregistrement des détails des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 309d96d6aacd5409aa285ddeb4b95837ca98e302
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528791"
---
# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="01b1f-102">Activer l’enregistrement des détails des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01b1f-102">Enable call detail recording in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01b1f-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="01b1f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="01b1f-p101">La fonctionnalité d’enregistrement des détails des appels recense des informations d’utilisation et de diagnostic sur les activités d’égal à égal, telles que la messagerie instantanée, les appels VoIP (Voice over Internet Protocol), le partage d’application, le transfert de fichiers et les réunions. Vous pouvez utiliser les données d’utilisation pour calculer le retour sur investissement (ROI) et les données de diagnostic pour résoudre les problèmes liés aux activités d’égal à égal et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="01b1f-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="01b1f-106">Procédez comme suit pour activer l’enregistrement des détails des appels dans toute l’organisation ou dans chacun de ses sites.</span><span class="sxs-lookup"><span data-stu-id="01b1f-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01b1f-107">Pour activer l’enregistrement des détails des appels, vous devez configurer la surveillance et une base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="01b1f-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="01b1f-108">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="01b1f-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="01b1f-109">Pour activer l’enregistrement des détails des appels dans le panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="01b1f-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="01b1f-110">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01b1f-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="01b1f-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01b1f-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="01b1f-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="01b1f-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="01b1f-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="01b1f-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="01b1f-114">Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans la table, sur **Action**, puis sur **Activer l’enregistrement des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="01b1f-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="01b1f-115">Cette fonctionnalité est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="01b1f-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="01b1f-116">Activation des enregistrements des détails des appels à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="01b1f-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="01b1f-117">Vous pouvez activer les enregistrements des détails des appels à l’aide de Windows PowerShell et de l’applet de commande **Set-applet cscdrconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="01b1f-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="01b1f-118">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01b1f-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="01b1f-119">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="01b1f-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="01b1f-120">Pour activer l’enregistrement des détails des appels pour un seul site</span><span class="sxs-lookup"><span data-stu-id="01b1f-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="01b1f-121">Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur True ($True).</span><span class="sxs-lookup"><span data-stu-id="01b1f-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="01b1f-122">Pour désactiver l’enregistrement des détails des appels pour un seul site</span><span class="sxs-lookup"><span data-stu-id="01b1f-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="01b1f-123">Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur False ($False).</span><span class="sxs-lookup"><span data-stu-id="01b1f-123">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="01b1f-124">La désactivation de l’enregistrement des détails des appels ne désinstalle pas la surveillance.</span><span class="sxs-lookup"><span data-stu-id="01b1f-124">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="01b1f-125">Il suspend la collecte et le stockage des données CDR.</span><span class="sxs-lookup"><span data-stu-id="01b1f-125">It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="01b1f-126">Pour activer l’enregistrement des détails des appels sur plusieurs sites en une seule commande</span><span class="sxs-lookup"><span data-stu-id="01b1f-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="01b1f-127">Cette commande active l’enregistrement des détails des appels pour tous les paramètres de configuration de l’enregistrement des détails des appels utilisés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="01b1f-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="01b1f-128">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-applet cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="01b1f-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01b1f-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01b1f-129">See Also</span></span>


[<span data-ttu-id="01b1f-130">Planification de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01b1f-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="01b1f-131">Déploiement de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01b1f-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

