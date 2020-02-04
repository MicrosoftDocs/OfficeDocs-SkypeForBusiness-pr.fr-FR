---
title: 'Lync Server 2013 : modifier les paramètres de qualité de l’expertise'
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
ms.openlocfilehash: a2cf4745f76fa4667d14c9da5ca2b4e5309767b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="44c8a-102">Modifier les paramètres de qualité d’expérimentation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44c8a-102">Modify Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44c8a-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="44c8a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="44c8a-p101">Par défaut, les données de qualité de l’expérience (QoE) sont vidées au bout de 60 jours. Vous pouvez utiliser les paramètres de la page **Données de qualité de l’expérience** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez QoE, les données capturées avant que l’activation de QoE seront également purgées.</span><span class="sxs-lookup"><span data-stu-id="44c8a-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44c8a-p102">Vous devez configurer l’enregistrement des détails des appels (CDR) et QoE pour conserver des données pendant le même nombre de jours. Chaque appel des enregistrements des détails des appels disponible à partir de la page d’accueil des rapports de surveillance inclut des informations sur l’enregistrement des détails des appels et sur la qualité de l’expérience. Si la durée du vidage est différente pour les enregistrements des détails des appels (CDR) et la qualité de l’expérience (QoE), certains appels pourront inclure uniquement des données CDR, tandis que d’autres contiendront uniquement des données QoE.</span><span class="sxs-lookup"><span data-stu-id="44c8a-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="44c8a-110">La procédure suivante décrit comment configurer des paramètres de vidage pour des données de qualité de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="44c8a-110">The following procedure describes how to configure purge settings for QoE data.</span></span>

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a><span data-ttu-id="44c8a-111">Pour spécifier la conservation des données QoE en utilisant le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="44c8a-111">To specify retention of QoE data by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="44c8a-112">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="44c8a-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="44c8a-113">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="44c8a-113">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="44c8a-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44c8a-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="44c8a-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="44c8a-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="44c8a-116">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="44c8a-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="44c8a-117">Dans la page **Données de qualité de l’expérience**, cliquez sur le site approprié dans le tableau, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="44c8a-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="44c8a-118">Pour activer le vidage, sélectionnez **Activer le vidage des données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="44c8a-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6.  <span data-ttu-id="44c8a-119">Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximal de jours pendant lesquels les données de qualité de l’expérience doivent être conservées.</span><span class="sxs-lookup"><span data-stu-id="44c8a-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="44c8a-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="44c8a-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="44c8a-121">Spécification de la rétention QoE en utilisant des applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44c8a-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="44c8a-122">Vous pouvez créer des paramètres de rétention QoE à l’aide de Windows PowerShell et de l’applet **de cmdlet Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="44c8a-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="44c8a-123">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44c8a-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="44c8a-124">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="44c8a-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="44c8a-125">Pour spécifier la conservation des données QoE pour un emplacement spécifique</span><span class="sxs-lookup"><span data-stu-id="44c8a-125">To specify QoE retention for a specific location</span></span>

  - <span data-ttu-id="44c8a-126">Cette commande active le vidage des données QoE pour le site Redmond et configure le site de façon à conserver les données QoE pendant 20 jours.</span><span class="sxs-lookup"><span data-stu-id="44c8a-126">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="44c8a-127">Pour spécifier la conservation des données QoE pour plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="44c8a-127">To specify QoE retention for multiple locations</span></span>

  - <span data-ttu-id="44c8a-128">Cette commande configure la conservation des données QoE pour tous les paramètres de configuration QoE utilisés dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="44c8a-128">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

<span data-ttu-id="44c8a-129">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="44c8a-129">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="44c8a-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="44c8a-130">See Also</span></span>


[<span data-ttu-id="44c8a-131">Déploiement de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44c8a-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

