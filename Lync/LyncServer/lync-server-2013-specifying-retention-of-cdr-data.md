---
title: 'Lync Server 2013 : spécification de la rétention des données CDR'
description: 'Lync Server 2013 : spécification de la rétention des données CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9367721a2390ad701702818590ac14e69da0df9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563400"
---
# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a><span data-ttu-id="1be70-103">Spécification de la rétention des données CDR dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1be70-103">Specifying retention of CDR data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1be70-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1be70-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1be70-p101">Par défaut, les données d’enregistrement des détails des appels sont vidées après un délai de 60 jours. Vous pouvez utiliser les paramètres de la page **Enregistrement des détails des appels** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez la fonctionnalité d’enregistrement des détails des appels, les données capturées avant l’enregistrement seront également vidées.</span><span class="sxs-lookup"><span data-stu-id="1be70-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1be70-p102">Vous devez configurer l’enregistrement des détails des appels et la qualité de l’expérience (QoE) afin de conserver les données pendant le même nombre de jours. Chaque appel dans les rapports des détails des appels (disponibles à partir de la page web Rapports du serveur de surveillance) comprend des informations d’enregistrement des détails des appels et QoE. Si la durée de vidage pour les données d’enregistrement des détails des appels et de QoE est différente, certains appels peuvent inclure uniquement des données d’enregistrement des détails des appels et d’autres exclusivement des données QoE</span><span class="sxs-lookup"><span data-stu-id="1be70-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="1be70-111">Utilisez les procédures suivantes pour configurer les paramètres de vidage des données d’enregistrement des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="1be70-111">Use the following procedures to configure purge settings for CDR data.</span></span>

<div>

## <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="1be70-112">Pour spécifier la conservation des données d’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="1be70-112">To specify retention of CDR data</span></span>

1.  <span data-ttu-id="1be70-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1be70-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="1be70-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1be70-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1be70-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1be70-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1be70-116">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="1be70-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="1be70-117">Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans le tableau, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1be70-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="1be70-118">Pour activer le vidage, sélectionnez **Activer le vidage des enregistrements des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="1be70-118">To turn on purging, select **Enable purging of CDRs**.</span></span>

6.  <span data-ttu-id="1be70-119">Dans **Conserver les enregistrements des détails des appels pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les enregistrements des détails des appels sont à conserver.</span><span class="sxs-lookup"><span data-stu-id="1be70-119">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="1be70-120">Dans **Conserver les données de signalement d’erreurs pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les rapports d’erreurs sont à conserver.</span><span class="sxs-lookup"><span data-stu-id="1be70-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="1be70-121">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1be70-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1be70-122">Spécification de la rétention CDR à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1be70-122">Specifying CDR Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1be70-123">Vous pouvez définir les paramètres de conservation des enregistrements des détails des appels en utilisant Windows PowerShell et l’applet de commande Set-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="1be70-123">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="1be70-124">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1be70-124">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1be70-125">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="1be70-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="1be70-126">Pour spécifier la conservation des enregistrements des détails des appels pour un emplacement particulier</span><span class="sxs-lookup"><span data-stu-id="1be70-126">To specify CDR retention for a specific location</span></span>

  - <span data-ttu-id="1be70-127">Cette commande vide les enregistrements des détails des appels pour le site de Redmond, et configure ce site pour qu’il conserve les enregistrements des détails des appels et les données de signalement d’erreurs pendant 20 jours.</span><span class="sxs-lookup"><span data-stu-id="1be70-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="1be70-128">Pour spécifier la conservation des enregistrements des détails des appels pour plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="1be70-128">To specify CDR retention for multiple locations</span></span>

  - <span data-ttu-id="1be70-129">Cette commande configure la conservation des enregistrements des détails des appels pour tous les paramètres de configuration des enregistrements des détails des appels actuellement appliqués dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="1be70-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<span data-ttu-id="1be70-130">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-applet cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1be70-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1be70-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1be70-131">See Also</span></span>


[<span data-ttu-id="1be70-132">Enregistrement des détails des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1be70-132">Call detail recording (CDR) in Lync Server 2013</span></span>](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

