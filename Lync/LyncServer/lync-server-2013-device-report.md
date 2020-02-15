---
title: 'Lync Server 2013 : rapport d’appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da9ec08af933f90eaf1e941259628b38ec055d9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="db6b1-102">Rapport de périphérique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db6b1-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db6b1-103">_**Dernière modification de la rubrique :** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="db6b1-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="db6b1-104">Le Rapport de périphérique devrait plutôt s’appeler le Rapport de microphone et de haut-parleurs : en effet, le Rapport de périphérique récupère toutes les mesures de l’appel (comme le pourcentage d’appels médiocres, les échos et la durée du basculement vocal) regroupées par les microphones et les haut-parleurs utilisés pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="db6b1-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="db6b1-105">Si vous êtes intéressé par les téléphones IP (également appelés « périphériques »), utilisez plutôt le [rapport d’inventaire de téléphonie IP dans Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .</span><span class="sxs-lookup"><span data-stu-id="db6b1-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="db6b1-p102">Le rapport de périphérique est très utile pour les administrateurs souhaitant déterminer si un type d’appareil spécifique rencontre un plus grand nombre d’appels médiocres que d’autres appareils. Ce rapport pourrait, à son tour, influencer les décisions que vous devez prendre au moment de l’achat de nouveaux périphériques ou du remplacement des périphériques existants.</span><span class="sxs-lookup"><span data-stu-id="db6b1-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="db6b1-p103">Par défaut, les informations affichées dans le rapport de périphérique sont également basées sur le microphone (le périphérique de capture) et les haut-parleurs/casques (le périphérique de sortie) utilisés pour l’appel. Par exemple, supposons que vous ayez différents utilisateurs utilisant les périphériques de capture et de sortie suivants :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="db6b1-111">Périphérique de capture : microphone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="db6b1-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="db6b1-112">Périphérique de rendu : casque pour téléphone (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="db6b1-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="db6b1-113">Si ces utilisateurs passent 254 appels, une entrée semblable à celle-ci sera affichée dans le rapport :</span><span class="sxs-lookup"><span data-stu-id="db6b1-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db6b1-114">Périphérique de capture</span><span class="sxs-lookup"><span data-stu-id="db6b1-114">Capture device</span></span></th>
<th><span data-ttu-id="db6b1-115">Périphérique de rendu</span><span class="sxs-lookup"><span data-stu-id="db6b1-115">Render device</span></span></th>
<th><span data-ttu-id="db6b1-116">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="db6b1-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-117">Microphone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="db6b1-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="db6b1-118">Casque pour téléphone (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="db6b1-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="db6b1-119">254</span><span class="sxs-lookup"><span data-stu-id="db6b1-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db6b1-p104">À présent, supposons que vous ayez un nombre d’utilisateurs utilisant le même périphérique de capture, mais avec un autre périphérique de rendu. Dans ce cas, une deuxième entrée sera affichée dans le rapport, pour cette combinaison de périphériques de capture et de rendu :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db6b1-122">Périphérique de capture</span><span class="sxs-lookup"><span data-stu-id="db6b1-122">Capture device</span></span></th>
<th><span data-ttu-id="db6b1-123">Périphérique de rendu</span><span class="sxs-lookup"><span data-stu-id="db6b1-123">Render device</span></span></th>
<th><span data-ttu-id="db6b1-124">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="db6b1-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-125">Microphone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="db6b1-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="db6b1-126">Casque pour téléphone (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="db6b1-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="db6b1-127">254</span><span class="sxs-lookup"><span data-stu-id="db6b1-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-128">Microphone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="db6b1-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="db6b1-129">Haut-parleurs (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="db6b1-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="db6b1-130">319</span><span class="sxs-lookup"><span data-stu-id="db6b1-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db6b1-p105">Si vous préférez consulter les totaux combinés d’un périphérique donné (par exemple, pour le périphérique de capture SoundMAX, indépendamment du périphérique de rendu utilisé), sélectionnez l’option adéquate dans la liste déroulante Typé de périphérique (que ce soit pour le périphérique de capture ou celui de rendu). Si vous sélectionnez le périphérique de capture dans cet exemple, l’entrée sera semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db6b1-133">Périphérique de capture</span><span class="sxs-lookup"><span data-stu-id="db6b1-133">Capture device</span></span></th>
<th><span data-ttu-id="db6b1-134">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="db6b1-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-135">Microphone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="db6b1-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="db6b1-136">573</span><span class="sxs-lookup"><span data-stu-id="db6b1-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="db6b1-137">Accès au rapport de périphérique</span><span class="sxs-lookup"><span data-stu-id="db6b1-137">Accessing the Device Report</span></span>

<span data-ttu-id="db6b1-138">Normalement, vous pouvez accéder au rapport de périphérique à partir de la page d’accueil Rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="db6b1-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="db6b1-139">Toutefois, si vous affichez le [rapport détaillé des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md) , vous pouvez accéder au rapport de périphérique pour un périphérique spécifique en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="db6b1-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="db6b1-140">Périphérique de capture</span><span class="sxs-lookup"><span data-stu-id="db6b1-140">Capture Device</span></span>

  - <span data-ttu-id="db6b1-141">Périphérique de rendu</span><span class="sxs-lookup"><span data-stu-id="db6b1-141">Render Device</span></span>

<span data-ttu-id="db6b1-142">À partir du rapport de périphérique, vous pouvez accéder au [rapport de liste d’appels dans Lync Server 2013](lync-server-2013-call-list-report.md) en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="db6b1-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="db6b1-143">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="db6b1-143">Call volume</span></span>

  - <span data-ttu-id="db6b1-144">Pourcentage d’appels médiocres</span><span class="sxs-lookup"><span data-stu-id="db6b1-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="db6b1-145">Utilisation optimale du rapport de périphériques</span><span class="sxs-lookup"><span data-stu-id="db6b1-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="db6b1-146">Pour ce qui est des noms de périphériques, le rapport de périphérique est extrêmement détaillé : par exemple, supposons que vous ayez les périphériques de capture suivants :</span><span class="sxs-lookup"><span data-stu-id="db6b1-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="db6b1-147">Microphone Aastra 3002 (2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="db6b1-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="db6b1-148">Microphone Aastra 3002 (3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="db6b1-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="db6b1-149">Microphone Aastra 3002 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="db6b1-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="db6b1-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="db6b1-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="db6b1-151">Microphone Aastra 6725ip (10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="db6b1-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="db6b1-152">Microphone Aastra 6725ip (10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="db6b1-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="db6b1-153">Microphone Aastra 6725ip (2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="db6b1-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="db6b1-154">Microphone Aastra 6725ip (3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="db6b1-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="db6b1-155">Microphone Aastra 6725ip (4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="db6b1-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="db6b1-156">Microphone Aastra 6725ip (5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="db6b1-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="db6b1-157">Microphone Aastra 6725ip (6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="db6b1-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="db6b1-158">Microphone Aastra 6725ip (7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="db6b1-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="db6b1-159">Microphone Aastra 6725ip (9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="db6b1-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="db6b1-160">Microphone Aastra 6725ip (9- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="db6b1-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="db6b1-161">Microphone Aastra 6725ip (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="db6b1-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="db6b1-162">Microphone Aastra 6725ip (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="db6b1-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="db6b1-163">Microphone Aastra 6725ip (périphérique audio USB)</span><span class="sxs-lookup"><span data-stu-id="db6b1-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="db6b1-164">Microphone Aastra 6725ip (périphérique audio USB)-V0</span><span class="sxs-lookup"><span data-stu-id="db6b1-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db6b1-165">N’oubliez pas que les noms des appareils de capture ne peuvent pas être les mêmes si vous exécutez des versions localisées de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db6b1-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="db6b1-166">Un périphérique nommé Microphone Aastra 6725ip (Aastra 6725ip)-V0 en FR français peut être nommé différemment en français ou en espagnol.</span><span class="sxs-lookup"><span data-stu-id="db6b1-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="db6b1-167">Il est possible que vous souhaitiez ce niveau de détail à plusieurs reprises ; cependant, la plupart du temps, vous serez probablement uniquement intéressé par le nombre d’appels utilisant n’importe quel microphone Aastra, indépendamment du numéro du modèle.</span><span class="sxs-lookup"><span data-stu-id="db6b1-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="db6b1-168">Une méthode pour obtenir des informations de ce type consiste à exporter les données du rapport de périphérique vers Microsoft Excel, puis à enregistrer ces données dans un fichier de valeurs séparées par des\\virgules (par exemple, C : Data\\Devices\_Report. csv).</span><span class="sxs-lookup"><span data-stu-id="db6b1-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="db6b1-169">Vous pouvez ensuite utiliser un ensemble de commandes similaires à celles-ci pour importer le fichier .CSV dans Windows PowerShell et renvoyer le nombre d’appels effectués en utilisant un périphérique de capture Aastra :</span><span class="sxs-lookup"><span data-stu-id="db6b1-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="db6b1-p109">Ceci va renvoyer une valeur unique représentant le nombre d’appels effectués en utilisant un périphérique de capture Aastra. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p109">That will return a single value representing the total number of calls made using an Aastra capture device. For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="db6b1-172">Filtres</span><span class="sxs-lookup"><span data-stu-id="db6b1-172">Filters</span></span>

<span data-ttu-id="db6b1-p110">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de périphérique vous permet de filtrer des éléments comme le type d’appel, c’est-à-dire s’il s’agissait d’un appel client, d’une téléconférence ou d’un appel du réseau téléphonique commuté (RTC). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les périphériques sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="db6b1-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call. You can also choose how data should be grouped. In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="db6b1-177">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de périphérique.</span><span class="sxs-lookup"><span data-stu-id="db6b1-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="db6b1-178">Filtres du rapport de périphérique</span><span class="sxs-lookup"><span data-stu-id="db6b1-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db6b1-179">Nom</span><span class="sxs-lookup"><span data-stu-id="db6b1-179">Name</span></span></th>
<th><span data-ttu-id="db6b1-180">Description</span><span class="sxs-lookup"><span data-stu-id="db6b1-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-181"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-p111">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="db6b1-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="db6b1-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="db6b1-p112">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="db6b1-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="db6b1-187">7/7/2012</span></span></p>
<p><span data-ttu-id="db6b1-188">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="db6b1-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="db6b1-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="db6b1-189">7/3/2012</span></span></p>
<p><span data-ttu-id="db6b1-190">Les semaines commencent le dimanche et se terminent le samedi.</span><span class="sxs-lookup"><span data-stu-id="db6b1-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-191"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-p113">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="db6b1-194">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="db6b1-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="db6b1-p114">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="db6b1-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="db6b1-197">7/7/2012</span></span></p>
<p><span data-ttu-id="db6b1-198">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="db6b1-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="db6b1-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="db6b1-199">7/3/2012</span></span></p>
<p><span data-ttu-id="db6b1-200">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="db6b1-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-201"><strong>Cause du basculement vocal</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-p115">Raison pour laquelle un appel a dû être émis en mode semi-duplex afin d’empêcher l’écho. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p115">Reason why a call had to be placed into half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-205">Tous les</span><span class="sxs-lookup"><span data-stu-id="db6b1-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-206">Aucun</span><span class="sxs-lookup"><span data-stu-id="db6b1-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-207">Horodateur incorrect</span><span class="sxs-lookup"><span data-stu-id="db6b1-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-208">Écho</span><span class="sxs-lookup"><span data-stu-id="db6b1-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-209">DNLP (Dynamic Nonlinear Processor, processeur non linéaire dynamique)</span><span class="sxs-lookup"><span data-stu-id="db6b1-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-210">Faible complexité</span><span class="sxs-lookup"><span data-stu-id="db6b1-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-211">État de périphérique incorrect</span><span class="sxs-lookup"><span data-stu-id="db6b1-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-212">Écho post-AEC (Acoustic Echo Cancellation, annulation de l’écho acoustique)</span><span class="sxs-lookup"><span data-stu-id="db6b1-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-213"><strong>Cause de l’écho</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-p116">Raison pour laquelle un écho au-dessus du niveau acceptable a été détecté dans un appel. (Dans le domaine des télécommunications, un écho est la réflexion d’un son, il s’agit du même phénomène que vous entendez lorsque vous hélez en direction du fond d’un puits.) Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p116">Reason why echo above the accepted level was detected in a call. (In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-216">Tous les</span><span class="sxs-lookup"><span data-stu-id="db6b1-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-217">Aucun</span><span class="sxs-lookup"><span data-stu-id="db6b1-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-218">Horodateur incorrect</span><span class="sxs-lookup"><span data-stu-id="db6b1-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-219">Écho post-AEC (Acoustic Echo Cancellation, annulation de l’écho acoustique)</span><span class="sxs-lookup"><span data-stu-id="db6b1-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-220">ANLP (Adaptive Nonlinear Processor, processeur non linéaire adaptatif)</span><span class="sxs-lookup"><span data-stu-id="db6b1-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-221">DNLP (Dynamic Nonlinear Processor, processeur non linéaire dynamique)</span><span class="sxs-lookup"><span data-stu-id="db6b1-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-222">Écrêtage du microphone</span><span class="sxs-lookup"><span data-stu-id="db6b1-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-223"><strong>Type d’appel</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-p117">Indique le type d’appel émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p117">Indicates the type of call that was made. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-226">Tous les</span><span class="sxs-lookup"><span data-stu-id="db6b1-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-227">Appel client</span><span class="sxs-lookup"><span data-stu-id="db6b1-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-228">Appel PSTN</span><span class="sxs-lookup"><span data-stu-id="db6b1-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-229">Téléconférence</span><span class="sxs-lookup"><span data-stu-id="db6b1-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-230"><strong>Type d’accès</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-p118">Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-233">Tous les</span><span class="sxs-lookup"><span data-stu-id="db6b1-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-234">Interne</span><span class="sxs-lookup"><span data-stu-id="db6b1-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-235">Externe</span><span class="sxs-lookup"><span data-stu-id="db6b1-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-236"><strong>Type de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-p119">Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-239">Tous les</span><span class="sxs-lookup"><span data-stu-id="db6b1-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-240">Circuit</span><span class="sxs-lookup"><span data-stu-id="db6b1-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-241">Fil</span><span class="sxs-lookup"><span data-stu-id="db6b1-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-p120">Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-245">Tous les</span><span class="sxs-lookup"><span data-stu-id="db6b1-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-246">VPN</span><span class="sxs-lookup"><span data-stu-id="db6b1-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-247">Non VPN</span><span class="sxs-lookup"><span data-stu-id="db6b1-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-248"><strong>Type de périphérique</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-p121">Indique le type du périphérique. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p121">Indicates the type of device. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-251">Périphérique de capture</span><span class="sxs-lookup"><span data-stu-id="db6b1-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-252">Périphérique de rendu</span><span class="sxs-lookup"><span data-stu-id="db6b1-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="db6b1-253">Périphérique de capture/périphérique de rendu</span><span class="sxs-lookup"><span data-stu-id="db6b1-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-254"><strong>Nom du périphérique</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-p122">Nom du périphérique de capture ou de rendu. Vous pouvez entrez le nom complet du périphérique ou seulement une partie. Par exemple, pour trouver le périphérique Microphone (Microsoft LifeCam VX-1000), vous pouvez entrer la totalité du nom du périphérique comme suit :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p122">Name of the capture or render device. You can enter the complete device name or any portion of the device name. For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="db6b1-258">Microphone (Microsoft LifeCam VX-1000)</span><span class="sxs-lookup"><span data-stu-id="db6b1-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="db6b1-p123">Ou, vous pouvez entrer uniquement une partie du nom. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="db6b1-p123">Or, you can enter just a portion of the name. For example:</span></span></p>
<p><span data-ttu-id="db6b1-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="db6b1-261">LifeCam</span></span></p>
<p><span data-ttu-id="db6b1-262">Notez que le filtre précédent renvoie tout périphérique qui contient la chaîne &quot;LifeCam&quot; n’importe où dans son nom.</span><span class="sxs-lookup"><span data-stu-id="db6b1-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="db6b1-263">Mesures</span><span class="sxs-lookup"><span data-stu-id="db6b1-263">Metrics</span></span>

<span data-ttu-id="db6b1-264">Le tableau qui suit répertorie les informations fournies dans le rapport de périphérique.</span><span class="sxs-lookup"><span data-stu-id="db6b1-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="db6b1-265">Mesures du rapport de périphérique</span><span class="sxs-lookup"><span data-stu-id="db6b1-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db6b1-266">Nom</span><span class="sxs-lookup"><span data-stu-id="db6b1-266">Name</span></span></th>
<th><span data-ttu-id="db6b1-267">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="db6b1-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="db6b1-268">Description</span><span class="sxs-lookup"><span data-stu-id="db6b1-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-269"><strong>Périphérique de capture</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-270">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-271">Périphérique (par exemple, un microphone ou une webcam) utilisé pour transmettre de l’audio.</span><span class="sxs-lookup"><span data-stu-id="db6b1-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-272"><strong>Périphérique de rendu</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-273">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-274">Périphérique (par exemple, un casque ou des haut-parleurs) utilisé pour recevoir de l’audio.</span><span class="sxs-lookup"><span data-stu-id="db6b1-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-275"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-276">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-277">Nombre total d’appels émis.</span><span class="sxs-lookup"><span data-stu-id="db6b1-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-278"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-279">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-280">Pourcentage d’appels classés comme étant &quot;médiocres. &quot; Un appel médiocre est un appel dont au moins l’une des mesures mesurées a dépassé la valeur autorisée (par exemple, un appel ayant subi une gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="db6b1-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-281"><strong>Utilisateurs uniques</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-282">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-p124">Utilisateurs uniques qui ont utilisé le périphérique. Si un utilisateur a utilisé le périphérique 13 fois, il compte comme un seul utilisateur, à l’instar d’un utilisateur qui l’a utilisé une seule fois.</span><span class="sxs-lookup"><span data-stu-id="db6b1-p124">Unique users who used the device. If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-285"><strong>Ratio de la durée du basculement vocal</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-286">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-p125">Pourcentage de l’appel qui a dû être effectué en mode semi-duplex afin d’empêcher l’écho. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie.</span><span class="sxs-lookup"><span data-stu-id="db6b1-p125">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-289"><strong>Ratio du microphone ne fonctionnant pas</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-290">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-p126">Pourcentage de l’appel pendant lequel le périphérique de capture ne fonctionnait pas à un niveau acceptable. Une valeur élevée suggère que les problèmes de qualité de l’appel étaient principalement dus au fonctionnement incorrect du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="db6b1-p126">Percentage of the call in which the capture device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-293"><strong>Ratio du haut-parleur ne fonctionnant pas</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-294">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-p127">Pourcentage de l’appel pendant lequel le périphérique de rendu ne fonctionnait pas à un niveau acceptable. Une valeur élevée suggère que les problèmes de qualité de l’appel étaient principalement dus au fonctionnement incorrect du périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="db6b1-p127">Percentage of the call in which the render device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-297"><strong>Appels avec basculement vocal (%)</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-298">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-p128">Pourcentage du nombre total d’appels qui ont dû être émis en mode semi-duplex. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie.</span><span class="sxs-lookup"><span data-stu-id="db6b1-p128">Percentage of the total calls which had to be placed into half duplex mode. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-301"><strong>Écho en entrée du microphone (%)</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-302">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-303">Pourcentage de temps pendant lequel l’écho a été détecté dans le flux de capture du microphone.</span><span class="sxs-lookup"><span data-stu-id="db6b1-303">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="db6b1-304">En règle générale, les valeurs sont faibles pour les casques ou les combinés, et supérieures pour les téléphones de haut-parleur ou les haut-parleurs autonomes.</span><span class="sxs-lookup"><span data-stu-id="db6b1-304">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="db6b1-305">Pour les appareils qui prennent en charge l’annulation de l’écho acoustique intégré, des valeurs élevées indiquent une fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="db6b1-305">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="db6b1-306">Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="db6b1-306">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db6b1-307"><strong>Source-réverbération (%)</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-308">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-309">Pourcentage d’écho transmis à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="db6b1-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db6b1-310"><strong>Appels avec écho (%)</strong></span><span class="sxs-lookup"><span data-stu-id="db6b1-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="db6b1-311">Oui</span><span class="sxs-lookup"><span data-stu-id="db6b1-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="db6b1-312">Pourcentage du nombre total d’appels dont l’écho a dépassé le niveau acceptable.</span><span class="sxs-lookup"><span data-stu-id="db6b1-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

