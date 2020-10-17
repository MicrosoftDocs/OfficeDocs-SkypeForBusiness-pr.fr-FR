---
title: 'Lync Server 2013 : modifier les paramètres des fichiers journaux de mise à jour des périphériques'
description: 'Lync Server 2013 : modifier les paramètres des fichiers journaux de mise à jour des périphériques.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c2086e11a67207a00ca99773cc818106b16d05c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566970"
---
# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="64252-103">Modifier les paramètres des fichiers journaux de mise à jour des périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64252-103">Modify settings for Device Update log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64252-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="64252-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="64252-105">Vous pouvez modifier les paramètres relatifs à la journalisation des informations de mise à jour des périphériques dans votre organisation à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="64252-105">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="64252-106">Le tableau suivant indique les paramètres modifiables et les outils que vous utilisez pour modifier les paramètres.</span><span class="sxs-lookup"><span data-stu-id="64252-106">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="64252-107">Les paramètres de journal peuvent être modifiés et appliqués globalement, ou par site.</span><span class="sxs-lookup"><span data-stu-id="64252-107">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64252-108">Pour modifier</span><span class="sxs-lookup"><span data-stu-id="64252-108">To change</span></span></th>
<th><span data-ttu-id="64252-109">Utilisation</span><span class="sxs-lookup"><span data-stu-id="64252-109">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64252-110">Taille maximale (en octets) d’un fichier journal</span><span class="sxs-lookup"><span data-stu-id="64252-110">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="64252-111">Panneau de commande Lync Server</span><span class="sxs-lookup"><span data-stu-id="64252-111">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="64252-112">-ou-</span><span class="sxs-lookup"><span data-stu-id="64252-112">-or-</span></span></p>
<p><span data-ttu-id="64252-113">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="64252-113">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64252-114">Quantité maximale d’informations (en octets) pouvant être conservées dans le cache</span><span class="sxs-lookup"><span data-stu-id="64252-114">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="64252-115">Panneau de commande Lync Server</span><span class="sxs-lookup"><span data-stu-id="64252-115">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="64252-116">-ou-</span><span class="sxs-lookup"><span data-stu-id="64252-116">-or-</span></span></p>
<p><span data-ttu-id="64252-117">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="64252-117">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64252-118">Fréquence (en minutes) d’écriture des informations mises en cache dans le fichier journal</span><span class="sxs-lookup"><span data-stu-id="64252-118">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="64252-119">Panneau de commande Lync Server</span><span class="sxs-lookup"><span data-stu-id="64252-119">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="64252-120">-ou-</span><span class="sxs-lookup"><span data-stu-id="64252-120">-or-</span></span></p>
<p><span data-ttu-id="64252-121">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="64252-121">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64252-122">Durée (en jours) pendant laquelle les fichiers journaux sont conservés</span><span class="sxs-lookup"><span data-stu-id="64252-122">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="64252-123">Panneau de commande Lync Server</span><span class="sxs-lookup"><span data-stu-id="64252-123">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="64252-124">-ou-</span><span class="sxs-lookup"><span data-stu-id="64252-124">-or-</span></span></p>
<p><span data-ttu-id="64252-125">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="64252-125">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64252-126">Lorsque (heure de la journée) pour vérifier les fichiers expirés qui doivent être supprimés</span><span class="sxs-lookup"><span data-stu-id="64252-126">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="64252-127">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="64252-127">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64252-128">Les extensions de fichiers journaux à autoriser</span><span class="sxs-lookup"><span data-stu-id="64252-128">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="64252-129">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="64252-129">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64252-130">Types de fichiers journaux à conserver</span><span class="sxs-lookup"><span data-stu-id="64252-130">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="64252-131">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="64252-131">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="64252-132">Pour modifier les paramètres de journalisation à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="64252-132">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="64252-133">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64252-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="64252-134">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="64252-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="64252-135">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur **configuration du journal du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="64252-135">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="64252-136">Sur la page **configuration du journal du périphérique** , double-cliquez sur la configuration que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="64252-136">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="64252-137">Dans la boîte de dialogue **modifier le paramètre du journal** , modifiez l’un des paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="64252-137">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="64252-138">**Taille maximale des fichiers (octets)**     Indique la taille maximale qu’un fichier journal peut prendre avant d’être purgé.</span><span class="sxs-lookup"><span data-stu-id="64252-138">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="64252-139">La valeur par défaut est 1 024 000 octets (1 Mo).</span><span class="sxs-lookup"><span data-stu-id="64252-139">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="64252-140">**Taille maximale du cache (octets)**     Spécifie la quantité maximale d’informations (en octets) pouvant être conservées dans le cache du fichier journal avant que ce cache ne soit effacé et que les données soient écrites dans un fichier journal.</span><span class="sxs-lookup"><span data-stu-id="64252-140">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="64252-141">La valeur par défaut est 512 000 octets (0,5 Mo).</span><span class="sxs-lookup"><span data-stu-id="64252-141">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="64252-142">**Nombre de minutes de vidage du cache (1-60)**     Indique la fréquence à laquelle les informations stockées dans le cache du fichier journal sont écrites dans le fichier journal réel.</span><span class="sxs-lookup"><span data-stu-id="64252-142">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="64252-143">Une fois que les données sont journalisées, le cache est effacé.</span><span class="sxs-lookup"><span data-stu-id="64252-143">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="64252-144">La valeur par défaut est de cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="64252-144">The default is five minutes.</span></span>
    
      - <span data-ttu-id="64252-145">**Nombre de jours pendant lesquels les fichiers journaux sont conservés (1-365)**     Indique le nombre de jours pendant lesquels les fichiers journaux sont conservés avant d’être purgés.</span><span class="sxs-lookup"><span data-stu-id="64252-145">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="64252-146">La valeur par défaut est 10 jours.</span><span class="sxs-lookup"><span data-stu-id="64252-146">The default is 10 days.</span></span>

5.  <span data-ttu-id="64252-147">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="64252-147">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="64252-148">Modification des paramètres de journalisation à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="64252-148">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="64252-149">Les paramètres du fichier journal de mise à jour des appareils peuvent être modifiés à l’aide de Windows PowerShell et de l’applet de commande **Set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="64252-149">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="64252-150">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64252-150">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64252-151">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="64252-151">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="64252-152">Les exemples suivants illustrent deux façons d’utiliser **Set-CsDeviceUpdateConfiguration** pour modifier les paramètres.</span><span class="sxs-lookup"><span data-stu-id="64252-152">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="64252-153">Pour modifier la taille maximale du fichier journal et l’intervalle de nettoyage des journaux</span><span class="sxs-lookup"><span data-stu-id="64252-153">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="64252-154">La commande suivante modifie les paramètres du journal de mise à jour des appareils appliqués au site Redmond.</span><span class="sxs-lookup"><span data-stu-id="64252-154">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="64252-155">Dans cet exemple, la taille maximale du fichier journal est fixée à 204800 octets et l’intervalle de nettoyage du journal est de 14 jours.</span><span class="sxs-lookup"><span data-stu-id="64252-155">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="64252-156">Pour modifier l’heure de nettoyage du journal de jour</span><span class="sxs-lookup"><span data-stu-id="64252-156">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="64252-157">Cette commande définit le temps de nettoyage du journal pour le site de Redmond sur 3:00 AM.</span><span class="sxs-lookup"><span data-stu-id="64252-157">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="64252-158">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="64252-158">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

