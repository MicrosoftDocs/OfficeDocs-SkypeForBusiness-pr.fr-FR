---
title: 'Lync Server 2013 : modifier les paramètres de qualité de l’expérience'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da75a0be0e2f6aadd6cca95b19134f0653b3c9c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534345"
---
# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="e073c-102">Modifier les paramètres de qualité de l’expérience dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e073c-102">Modify Quality of Experience settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e073c-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e073c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e073c-p101">Par défaut, les données de qualité de l’expérience (QoE) sont vidées au bout de 60 jours. Vous pouvez utiliser les paramètres de la page **Données de qualité de l’expérience** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez QoE, les données capturées avant que l’activation de QoE seront également purgées.</span><span class="sxs-lookup"><span data-stu-id="e073c-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e073c-p102">Vous devez configurer l’enregistrement des détails des appels (CDR) et QoE pour conserver des données pendant le même nombre de jours. Chaque appel des enregistrements des détails des appels disponible à partir de la page d’accueil des rapports de surveillance inclut des informations sur l’enregistrement des détails des appels et sur la qualité de l’expérience. Si la durée du vidage est différente pour les enregistrements des détails des appels (CDR) et la qualité de l’expérience (QoE), certains appels pourront inclure uniquement des données CDR, tandis que d’autres contiendront uniquement des données QoE.</span><span class="sxs-lookup"><span data-stu-id="e073c-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="e073c-110">La procédure suivante décrit comment configurer des paramètres de vidage pour des données de qualité de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="e073c-110">The following procedure describes how to configure purge settings for QoE data.</span></span>

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a><span data-ttu-id="e073c-111">Pour spécifier la conservation des données QoE à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="e073c-111">To specify retention of QoE data by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e073c-112">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e073c-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e073c-113">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e073c-113">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e073c-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e073c-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e073c-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e073c-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e073c-116">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="e073c-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="e073c-117">A la page **Données de qualité de l’expérience**, cliquez sur le site approprié dans le tableau, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e073c-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="e073c-118">Pour activer le vidage, sélectionnez **Activer le vidage des données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="e073c-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6.  <span data-ttu-id="e073c-119">Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximal de jours pendant lesquels les données de qualité de l’expérience doivent être conservées.</span><span class="sxs-lookup"><span data-stu-id="e073c-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="e073c-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="e073c-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e073c-121">Spécification de la rétention QoE à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e073c-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e073c-122">Vous pouvez créer des paramètres de rétention QoE à l’aide de Windows PowerShell et de la cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e073c-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="e073c-123">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e073c-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e073c-124">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="e073c-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="e073c-125">Pour spécifier la conservation des données QoE pour un emplacement spécifique</span><span class="sxs-lookup"><span data-stu-id="e073c-125">To specify QoE retention for a specific location</span></span>

  - <span data-ttu-id="e073c-126">Cette commande active le vidage des données QoE pour le site Redmond et configure le site de façon à conserver les données QoE pendant 20 jours.</span><span class="sxs-lookup"><span data-stu-id="e073c-126">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="e073c-127">Pour spécifier la conservation des données QoE pour plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="e073c-127">To specify QoE retention for multiple locations</span></span>

  - <span data-ttu-id="e073c-128">Cette commande configure la conservation des données QoE pour tous les paramètres de configuration QoE utilisés dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="e073c-128">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

<span data-ttu-id="e073c-129">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="e073c-129">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e073c-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e073c-130">See Also</span></span>


[<span data-ttu-id="e073c-131">Déploiement de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e073c-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

