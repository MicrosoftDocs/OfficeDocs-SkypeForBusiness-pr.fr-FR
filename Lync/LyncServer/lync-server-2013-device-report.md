---
title: 'Lync Server 2013 : rapport d’appareil'
description: 'Lync Server 2013 : rapport d’appareil.'
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
ms.openlocfilehash: a8bff8e973d5c3e2d96c18992a2a2d917d4deb1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575120"
---
# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="b86a1-103">Rapport de périphérique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b86a1-103">Device Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b86a1-104">_**Dernière modification de la rubrique :** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="b86a1-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="b86a1-105">Le Rapport de périphérique devrait plutôt s’appeler le Rapport de microphone et de haut-parleurs : en effet, le Rapport de périphérique récupère toutes les mesures de l’appel (comme le pourcentage d’appels médiocres, les échos et la durée du basculement vocal) regroupées par les microphones et les haut-parleurs utilisés pendant l’appel.</span><span class="sxs-lookup"><span data-stu-id="b86a1-105">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="b86a1-106">Si vous êtes intéressé par les téléphones IP (également appelés « périphériques »), utilisez plutôt le [rapport d’inventaire de téléphonie IP dans Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .</span><span class="sxs-lookup"><span data-stu-id="b86a1-106">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="b86a1-p102">Le rapport de périphérique est très utile pour les administrateurs souhaitant déterminer si un type d’appareil spécifique rencontre un plus grand nombre d’appels médiocres que d’autres appareils. Ce rapport pourrait, à son tour, influencer les décisions que vous devez prendre au moment de l’achat de nouveaux périphériques ou du remplacement des périphériques existants.</span><span class="sxs-lookup"><span data-stu-id="b86a1-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="b86a1-p103">Par défaut, les informations affichées dans le rapport de périphérique sont également basées sur le microphone (le périphérique de capture) et les haut-parleurs/casques (le périphérique de sortie) utilisés pour l’appel. Par exemple, supposons que vous ayez différents utilisateurs utilisant les périphériques de capture et de sortie suivants :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="b86a1-112">Périphérique de capture : microphone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="b86a1-112">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="b86a1-113">Périphérique de rendu : casque pour téléphone (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="b86a1-113">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="b86a1-114">Si ces utilisateurs passent 254 appels, une entrée semblable à celle-ci sera affichée dans le rapport :</span><span class="sxs-lookup"><span data-stu-id="b86a1-114">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b86a1-115">Périphérique de capture</span><span class="sxs-lookup"><span data-stu-id="b86a1-115">Capture device</span></span></th>
<th><span data-ttu-id="b86a1-116">Périphérique de rendu</span><span class="sxs-lookup"><span data-stu-id="b86a1-116">Render device</span></span></th>
<th><span data-ttu-id="b86a1-117">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="b86a1-117">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-118">Microphone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="b86a1-118">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="b86a1-119">Casque pour téléphone (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="b86a1-119">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="b86a1-120">254</span><span class="sxs-lookup"><span data-stu-id="b86a1-120">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b86a1-p104">À présent, supposons que vous ayez un nombre d’utilisateurs utilisant le même périphérique de capture, mais avec un autre périphérique de rendu. Dans ce cas, une deuxième entrée sera affichée dans le rapport, pour cette combinaison de périphériques de capture et de rendu :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b86a1-123">Périphérique de capture</span><span class="sxs-lookup"><span data-stu-id="b86a1-123">Capture device</span></span></th>
<th><span data-ttu-id="b86a1-124">Périphérique de rendu</span><span class="sxs-lookup"><span data-stu-id="b86a1-124">Render device</span></span></th>
<th><span data-ttu-id="b86a1-125">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="b86a1-125">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-126">Microphone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="b86a1-126">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="b86a1-127">Casque pour téléphone (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="b86a1-127">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="b86a1-128">254</span><span class="sxs-lookup"><span data-stu-id="b86a1-128">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-129">Microphone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="b86a1-129">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="b86a1-130">Haut-parleurs (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="b86a1-130">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="b86a1-131">319</span><span class="sxs-lookup"><span data-stu-id="b86a1-131">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b86a1-p105">Si vous préférez consulter les totaux combinés d’un périphérique donné (par exemple, pour le périphérique de capture SoundMAX, indépendamment du périphérique de rendu utilisé), sélectionnez l’option adéquate dans la liste déroulante Typé de périphérique (que ce soit pour le périphérique de capture ou celui de rendu). Si vous sélectionnez le périphérique de capture dans cet exemple, l’entrée sera semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b86a1-134">Périphérique de capture</span><span class="sxs-lookup"><span data-stu-id="b86a1-134">Capture device</span></span></th>
<th><span data-ttu-id="b86a1-135">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="b86a1-135">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-136">Microphone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="b86a1-136">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="b86a1-137">573</span><span class="sxs-lookup"><span data-stu-id="b86a1-137">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="b86a1-138">Accès au rapport de périphérique</span><span class="sxs-lookup"><span data-stu-id="b86a1-138">Accessing the Device Report</span></span>

<span data-ttu-id="b86a1-139">Normalement, vous pouvez accéder au rapport de périphérique à partir de la page d’accueil Rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="b86a1-139">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="b86a1-140">Toutefois, si vous affichez le [rapport détaillé des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md) , vous pouvez accéder au rapport de périphérique pour un périphérique spécifique en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="b86a1-140">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="b86a1-141">Périphérique de capture</span><span class="sxs-lookup"><span data-stu-id="b86a1-141">Capture Device</span></span>

  - <span data-ttu-id="b86a1-142">Périphérique de rendu</span><span class="sxs-lookup"><span data-stu-id="b86a1-142">Render Device</span></span>

<span data-ttu-id="b86a1-143">À partir du rapport de périphérique, vous pouvez accéder au [rapport de liste d’appels dans Lync Server 2013](lync-server-2013-call-list-report.md) en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="b86a1-143">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="b86a1-144">Volume d’appels</span><span class="sxs-lookup"><span data-stu-id="b86a1-144">Call volume</span></span>

  - <span data-ttu-id="b86a1-145">Pourcentage d’appels médiocres</span><span class="sxs-lookup"><span data-stu-id="b86a1-145">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="b86a1-146">Utilisation optimale du rapport de périphériques</span><span class="sxs-lookup"><span data-stu-id="b86a1-146">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="b86a1-147">Pour ce qui est des noms de périphériques, le rapport de périphérique est extrêmement détaillé : par exemple, supposons que vous ayez les périphériques de capture suivants :</span><span class="sxs-lookup"><span data-stu-id="b86a1-147">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="b86a1-148">Microphone Aastra 3002 (2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="b86a1-148">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="b86a1-149">Microphone Aastra 3002 (3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="b86a1-149">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="b86a1-150">Microphone Aastra 3002 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="b86a1-150">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="b86a1-151">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="b86a1-151">Aastra 6725ip</span></span>

  - <span data-ttu-id="b86a1-152">Microphone Aastra 6725ip (10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="b86a1-152">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="b86a1-153">Microphone Aastra 6725ip (10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="b86a1-153">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="b86a1-154">Microphone Aastra 6725ip (2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="b86a1-154">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="b86a1-155">Microphone Aastra 6725ip (3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="b86a1-155">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="b86a1-156">Microphone Aastra 6725ip (4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="b86a1-156">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="b86a1-157">Microphone Aastra 6725ip (5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="b86a1-157">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="b86a1-158">Microphone Aastra 6725ip (6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="b86a1-158">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="b86a1-159">Microphone Aastra 6725ip (7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="b86a1-159">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="b86a1-160">Microphone Aastra 6725ip (9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="b86a1-160">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="b86a1-161">Microphone Aastra 6725ip (9- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="b86a1-161">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="b86a1-162">Microphone Aastra 6725ip (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="b86a1-162">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="b86a1-163">Microphone Aastra 6725ip (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="b86a1-163">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="b86a1-164">Microphone Aastra 6725ip (périphérique audio USB)</span><span class="sxs-lookup"><span data-stu-id="b86a1-164">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="b86a1-165">Microphone Aastra 6725ip (périphérique audio USB)-V0</span><span class="sxs-lookup"><span data-stu-id="b86a1-165">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b86a1-166">N’oubliez pas que les noms des appareils de capture ne peuvent pas être les mêmes si vous exécutez des versions localisées de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b86a1-166">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="b86a1-167">Un périphérique nommé Microphone Aastra 6725ip (Aastra 6725ip)-V0 en FR français peut être nommé différemment en français ou en espagnol.</span><span class="sxs-lookup"><span data-stu-id="b86a1-167">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="b86a1-168">Il est possible que vous souhaitiez ce niveau de détail à plusieurs reprises ; cependant, la plupart du temps, vous serez probablement uniquement intéressé par le nombre d’appels utilisant n’importe quel microphone Aastra, indépendamment du numéro du modèle.</span><span class="sxs-lookup"><span data-stu-id="b86a1-168">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="b86a1-169">Une méthode pour obtenir des informations de ce type consiste à exporter les données du rapport de périphérique vers Microsoft Excel, puis à enregistrer ces données dans un fichier de valeurs séparées par des virgules (par exemple, C : \\ périphériques de données \\ \_Report.csv).</span><span class="sxs-lookup"><span data-stu-id="b86a1-169">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="b86a1-170">Vous pouvez ensuite utiliser un ensemble de commandes similaires à celles-ci pour importer le fichier .CSV dans Windows PowerShell et renvoyer le nombre d’appels effectués en utilisant un périphérique de capture Aastra :</span><span class="sxs-lookup"><span data-stu-id="b86a1-170">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="b86a1-p109">Ceci va renvoyer une valeur unique représentant le nombre d’appels effectués en utilisant un périphérique de capture Aastra. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p109">That will return a single value representing the total number of calls made using an Aastra capture device. For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b86a1-173">Filtres</span><span class="sxs-lookup"><span data-stu-id="b86a1-173">Filters</span></span>

<span data-ttu-id="b86a1-p110">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de périphérique vous permet de filtrer des éléments comme le type d’appel, c’est-à-dire s’il s’agissait d’un appel client, d’une téléconférence ou d’un appel du réseau téléphonique commuté (RTC). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les périphériques sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="b86a1-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call. You can also choose how data should be grouped. In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="b86a1-178">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de périphérique.</span><span class="sxs-lookup"><span data-stu-id="b86a1-178">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="b86a1-179">Filtres du rapport de périphérique</span><span class="sxs-lookup"><span data-stu-id="b86a1-179">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b86a1-180">Nom</span><span class="sxs-lookup"><span data-stu-id="b86a1-180">Name</span></span></th>
<th><span data-ttu-id="b86a1-181">Description</span><span class="sxs-lookup"><span data-stu-id="b86a1-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-182"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-182"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-p111">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b86a1-185">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b86a1-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b86a1-p112">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b86a1-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b86a1-188">7/7/2012</span></span></p>
<p><span data-ttu-id="b86a1-189">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="b86a1-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b86a1-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b86a1-190">7/3/2012</span></span></p>
<p><span data-ttu-id="b86a1-191">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="b86a1-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-192"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-192"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-p113">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b86a1-195">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b86a1-195">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b86a1-p114">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b86a1-198">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b86a1-198">7/7/2012</span></span></p>
<p><span data-ttu-id="b86a1-199">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="b86a1-199">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b86a1-200">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b86a1-200">7/3/2012</span></span></p>
<p><span data-ttu-id="b86a1-201">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="b86a1-201">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-202"><strong>Cause du basculement vocal</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-202"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-p115">Raison pour laquelle un appel a dû être émis en mode semi-duplex afin d’empêcher l’écho. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p115">Reason why a call had to be placed into half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-206">Tous les</span><span class="sxs-lookup"><span data-stu-id="b86a1-206">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-207">Aucune</span><span class="sxs-lookup"><span data-stu-id="b86a1-207">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-208">Horodateur incorrect</span><span class="sxs-lookup"><span data-stu-id="b86a1-208">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-209">Écho</span><span class="sxs-lookup"><span data-stu-id="b86a1-209">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-210">DNLP (Dynamic Nonlinear Processor, processeur non linéaire dynamique)</span><span class="sxs-lookup"><span data-stu-id="b86a1-210">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-211">Faible complexité</span><span class="sxs-lookup"><span data-stu-id="b86a1-211">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-212">État de périphérique incorrect</span><span class="sxs-lookup"><span data-stu-id="b86a1-212">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-213">Écho post-AEC (Acoustic Echo Cancellation, annulation de l’écho acoustique)</span><span class="sxs-lookup"><span data-stu-id="b86a1-213">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-214"><strong>Cause de l’écho</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-214"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-p116">Raison pour laquelle un écho au-dessus du niveau acceptable a été détecté dans un appel. (Dans le domaine des télécommunications, un écho est la réflexion d’un son, il s’agit du même phénomène que vous entendez lorsque vous hélez en direction du fond d’un puits.) Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p116">Reason why echo above the accepted level was detected in a call. (In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-217">Tous les</span><span class="sxs-lookup"><span data-stu-id="b86a1-217">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-218">Aucune</span><span class="sxs-lookup"><span data-stu-id="b86a1-218">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-219">Horodateur incorrect</span><span class="sxs-lookup"><span data-stu-id="b86a1-219">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-220">Écho post-AEC (Acoustic Echo Cancellation, annulation de l’écho acoustique)</span><span class="sxs-lookup"><span data-stu-id="b86a1-220">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-221">ANLP (Adaptive Nonlinear Processor, processeur non linéaire adaptatif)</span><span class="sxs-lookup"><span data-stu-id="b86a1-221">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-222">DNLP (Dynamic Nonlinear Processor, processeur non linéaire dynamique)</span><span class="sxs-lookup"><span data-stu-id="b86a1-222">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-223">Écrêtage du microphone</span><span class="sxs-lookup"><span data-stu-id="b86a1-223">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-224"><strong>Type d’appel</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-224"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-p117">Indique le type d’appel émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p117">Indicates the type of call that was made. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-227">Tous les</span><span class="sxs-lookup"><span data-stu-id="b86a1-227">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-228">Appel client</span><span class="sxs-lookup"><span data-stu-id="b86a1-228">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-229">Appel PSTN</span><span class="sxs-lookup"><span data-stu-id="b86a1-229">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-230">Téléconférence</span><span class="sxs-lookup"><span data-stu-id="b86a1-230">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-231"><strong>Type d’accès</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-231"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-p118">Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-234">Tous les</span><span class="sxs-lookup"><span data-stu-id="b86a1-234">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-235">Interne</span><span class="sxs-lookup"><span data-stu-id="b86a1-235">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-236">Externe</span><span class="sxs-lookup"><span data-stu-id="b86a1-236">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-237"><strong>Type de réseau</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-237"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-p119">Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-240">Tous les</span><span class="sxs-lookup"><span data-stu-id="b86a1-240">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-241">Circuit</span><span class="sxs-lookup"><span data-stu-id="b86a1-241">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-242">Fil</span><span class="sxs-lookup"><span data-stu-id="b86a1-242">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-243"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-243"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-p120">Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-246">Tous les</span><span class="sxs-lookup"><span data-stu-id="b86a1-246">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-247">VPN</span><span class="sxs-lookup"><span data-stu-id="b86a1-247">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-248">Non VPN</span><span class="sxs-lookup"><span data-stu-id="b86a1-248">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-249"><strong>Type de périphérique</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-249"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-p121">Indique le type du périphérique. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p121">Indicates the type of device. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-252">Périphérique de capture</span><span class="sxs-lookup"><span data-stu-id="b86a1-252">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-253">Périphérique de rendu</span><span class="sxs-lookup"><span data-stu-id="b86a1-253">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b86a1-254">Périphérique de capture/périphérique de rendu</span><span class="sxs-lookup"><span data-stu-id="b86a1-254">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-255"><strong>Nom du périphérique</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-255"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-p122">Nom du périphérique de capture ou de rendu. Vous pouvez entrez le nom complet du périphérique ou seulement une partie. Par exemple, pour trouver le périphérique Microphone (Microsoft LifeCam VX-1000), vous pouvez entrer la totalité du nom du périphérique comme suit :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p122">Name of the capture or render device. You can enter the complete device name or any portion of the device name. For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="b86a1-259">Microphone (Microsoft LifeCam VX-1000)</span><span class="sxs-lookup"><span data-stu-id="b86a1-259">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="b86a1-p123">Ou, vous pouvez entrer uniquement une partie du nom. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b86a1-p123">Or, you can enter just a portion of the name. For example:</span></span></p>
<p><span data-ttu-id="b86a1-262">LifeCam</span><span class="sxs-lookup"><span data-stu-id="b86a1-262">LifeCam</span></span></p>
<p><span data-ttu-id="b86a1-263">Notez que le filtre précédent renvoie tout périphérique qui contient la chaîne &quot; LifeCam &quot; n’importe où dans son nom.</span><span class="sxs-lookup"><span data-stu-id="b86a1-263">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b86a1-264">Mesures</span><span class="sxs-lookup"><span data-stu-id="b86a1-264">Metrics</span></span>

<span data-ttu-id="b86a1-265">Le tableau qui suit répertorie les informations fournies dans le rapport de périphérique.</span><span class="sxs-lookup"><span data-stu-id="b86a1-265">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="b86a1-266">Mesures du rapport de périphérique</span><span class="sxs-lookup"><span data-stu-id="b86a1-266">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b86a1-267">Nom</span><span class="sxs-lookup"><span data-stu-id="b86a1-267">Name</span></span></th>
<th><span data-ttu-id="b86a1-268">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="b86a1-268">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b86a1-269">Description</span><span class="sxs-lookup"><span data-stu-id="b86a1-269">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-270"><strong>Périphérique de capture</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-270"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-271">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-271">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-272">Périphérique (par exemple, un microphone ou une webcam) utilisé pour transmettre de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b86a1-272">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-273"><strong>Périphérique de rendu</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-273"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-274">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-274">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-275">Périphérique (par exemple, un casque ou des haut-parleurs) utilisé pour recevoir de l’audio.</span><span class="sxs-lookup"><span data-stu-id="b86a1-275">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-276"><strong>Volume d’appels</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-276"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-277">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-277">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-278">Nombre total d’appels émis.</span><span class="sxs-lookup"><span data-stu-id="b86a1-278">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-279"><strong>Pourcentage d’appels médiocres</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-279"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-280">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-280">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-281">Pourcentage d’appels classés comme étant &quot; médiocres. &quot; Un appel médiocre est un appel dont au moins l’une des mesures mesurées a dépassé la valeur autorisée (par exemple, un appel ayant subi une gigue excessive).</span><span class="sxs-lookup"><span data-stu-id="b86a1-281">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-282"><strong>Utilisateurs uniques</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-282"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-283">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-p124">Utilisateurs uniques qui ont utilisé le périphérique. Si un utilisateur a utilisé le périphérique 13 fois, il compte comme un seul utilisateur, à l’instar d’un utilisateur qui l’a utilisé une seule fois.</span><span class="sxs-lookup"><span data-stu-id="b86a1-p124">Unique users who used the device. If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-286"><strong>Ratio de la durée du basculement vocal</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-286"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-287">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-p125">Pourcentage de l’appel qui a dû être effectué en mode semi-duplex afin d’empêcher l’écho. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie.</span><span class="sxs-lookup"><span data-stu-id="b86a1-p125">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-290"><strong>Ratio du microphone ne fonctionnant pas</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-290"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-291">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-p126">Pourcentage de l’appel pendant lequel le périphérique de capture ne fonctionnait pas à un niveau acceptable. Une valeur élevée suggère que les problèmes de qualité de l’appel étaient principalement dus au fonctionnement incorrect du périphérique de capture.</span><span class="sxs-lookup"><span data-stu-id="b86a1-p126">Percentage of the call in which the capture device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-294"><strong>Ratio du haut-parleur ne fonctionnant pas</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-294"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-295">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-p127">Pourcentage de l’appel pendant lequel le périphérique de rendu ne fonctionnait pas à un niveau acceptable. Une valeur élevée suggère que les problèmes de qualité de l’appel étaient principalement dus au fonctionnement incorrect du périphérique de rendu.</span><span class="sxs-lookup"><span data-stu-id="b86a1-p127">Percentage of the call in which the render device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-298"><strong>Appels avec basculement vocal (%)</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-298"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-299">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-p128">Pourcentage du nombre total d’appels qui ont dû être émis en mode semi-duplex. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie.</span><span class="sxs-lookup"><span data-stu-id="b86a1-p128">Percentage of the total calls which had to be placed into half duplex mode. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-302"><strong>Écho en entrée du microphone (%)</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-302"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-303">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-304">Pourcentage de temps pendant lequel l’écho a été détecté dans le flux de capture du microphone.</span><span class="sxs-lookup"><span data-stu-id="b86a1-304">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="b86a1-305">En règle générale, les valeurs sont faibles pour les casques ou les combinés, et supérieures pour les téléphones de haut-parleur ou les haut-parleurs autonomes.</span><span class="sxs-lookup"><span data-stu-id="b86a1-305">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="b86a1-306">Pour les appareils qui prennent en charge l’annulation de l’écho acoustique intégré, des valeurs élevées indiquent une fuite d’écho.</span><span class="sxs-lookup"><span data-stu-id="b86a1-306">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="b86a1-307">Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b86a1-307">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b86a1-308"><strong>Source-réverbération (%)</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-308"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-309">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-310">Pourcentage d’écho transmis à d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b86a1-310">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b86a1-311"><strong>Appels avec écho (%)</strong></span><span class="sxs-lookup"><span data-stu-id="b86a1-311"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="b86a1-312">Oui</span><span class="sxs-lookup"><span data-stu-id="b86a1-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="b86a1-313">Pourcentage du nombre total d’appels dont l’écho a dépassé le niveau acceptable.</span><span class="sxs-lookup"><span data-stu-id="b86a1-313">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

