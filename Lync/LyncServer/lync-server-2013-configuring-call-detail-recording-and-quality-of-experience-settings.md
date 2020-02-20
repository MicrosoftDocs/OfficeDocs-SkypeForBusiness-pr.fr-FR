---
title: Configuration des paramètres d’enregistrement des détails des appels et de qualité de l’expérience
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0a7d6eb309c8afd13e671a12c98623c486b220d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="372ce-102">Configuration des paramètres d’enregistrement des détails des appels et de qualité de l’expérience dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="372ce-102">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="372ce-103">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="372ce-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="372ce-104">Une fois que vous avez associé un magasin de surveillance à un pool frontal, configurez le magasin de surveillance, puis installez et configurez SQL Server Reporting Services et configurez les rapports de surveillance pour gérer les enregistrements des détails des appels et la qualité de l’expérience (QoE). surveillance à l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="372ce-104">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Lync Server Management Shell.</span></span> <span data-ttu-id="372ce-105">Les applets de commande Lync Server Management Shell vous permettent d’activer et de désactiver la surveillance des enregistrements des détails des appels et/ou QoE pour un site particulier ou pour l’ensemble de votre déploiement Lync Server ; Cela peut être réalisé à l’aide d’une commande simple, comme suit :</span><span class="sxs-lookup"><span data-stu-id="372ce-105">Lync Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Lync Server deployment; that can be done with a command as simple as this:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

<span data-ttu-id="372ce-106">Lorsque vous installez Microsoft Lync Server 2013, vous installez également une collection prédéfinie de paramètres de configuration globaux pour les enregistrements des détails des appels et QoE.</span><span class="sxs-lookup"><span data-stu-id="372ce-106">When you install Microsoft Lync Server 2013, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="372ce-107">Les valeurs par défaut de certains des paramètres les plus couramment utilisés par l’enregistrement des détails des appels sont indiquées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="372ce-107">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="372ce-108">Propriété</span><span class="sxs-lookup"><span data-stu-id="372ce-108">Property</span></span></th>
<th><span data-ttu-id="372ce-109">Description</span><span class="sxs-lookup"><span data-stu-id="372ce-109">Description</span></span></th>
<th><span data-ttu-id="372ce-110">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="372ce-110">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="372ce-111">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="372ce-111">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="372ce-p103">Indique si l’enregistrement des détails des appels est activé ou non. Si la valeur est True, tous les enregistrements CDR sont collectés et enregistrés dans la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="372ce-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="372ce-114">Vrai</span><span class="sxs-lookup"><span data-stu-id="372ce-114">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="372ce-115">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="372ce-115">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="372ce-p104">Indique si les enregistrements des détails des appels doivent être périodiquement supprimés de la base de données. Si la valeur est définie sur True, les enregistrements sont supprimés après la période spécifiée par les propriétés KeepCallDetailForDays (pour les enregistrements CDR) et KeepErrorReportForDays (pour les erreurs CDR). Si la valeur est définie sur False, les enregistrements CDR sont conservés indéfiniment.</span><span class="sxs-lookup"><span data-stu-id="372ce-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="372ce-119">Vrai</span><span class="sxs-lookup"><span data-stu-id="372ce-119">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="372ce-120">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="372ce-120">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="372ce-p105">Indique le nombre de jours durant lesquels les enregistrements CDR sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. Mais pour cela, la purge doit être activée.</span><span class="sxs-lookup"><span data-stu-id="372ce-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="372ce-123">Vous pouvez définir la propriété KeepCallDetailForDays sur n’importe quelle valeur entière comprise entre 1 et 2562 jours (environ 7 ans).</span><span class="sxs-lookup"><span data-stu-id="372ce-123">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span></p></td>
<td><p><span data-ttu-id="372ce-124">60 jours</span><span class="sxs-lookup"><span data-stu-id="372ce-124">60 days</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="372ce-125">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="372ce-125">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="372ce-126">Indique le nombre de jours pendant lesquels les rapports d’erreurs CDR sont conservés ; tous les rapports plus anciens que le nombre spécifié de jours sont automatiquement supprimés.</span><span class="sxs-lookup"><span data-stu-id="372ce-126">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="372ce-127">Les rapports d’erreurs CDR sont des rapports de diagnostic téléchargés par des applications clientes telles que Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="372ce-127">CDR error reports are diagnostic reports uploaded by client applications such as Microsoft Lync 2013.</span></span></p>
<p><span data-ttu-id="372ce-128">Vous pouvez définir cette propriété sur n’importe quelle valeur entière comprise entre 1 et 2562.</span><span class="sxs-lookup"><span data-stu-id="372ce-128">You can set this property to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="372ce-129">60 jours</span><span class="sxs-lookup"><span data-stu-id="372ce-129">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="372ce-130">De même, les valeurs par défaut pour les paramètres de la qualité de l’expérience (QoE) sélectionnés sont indiquées dans ce tableau :</span><span class="sxs-lookup"><span data-stu-id="372ce-130">Similarly, default values for selected QoE settings are shown in this table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="372ce-131">Propriété</span><span class="sxs-lookup"><span data-stu-id="372ce-131">Property</span></span></th>
<th><span data-ttu-id="372ce-132">Description</span><span class="sxs-lookup"><span data-stu-id="372ce-132">Description</span></span></th>
<th><span data-ttu-id="372ce-133">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="372ce-133">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="372ce-134">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="372ce-134">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="372ce-p107">Indique si la surveillance QoE est activée ou non. Si la valeur est True, tous les enregistrements QoE sont collectés et enregistrés dans la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="372ce-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="372ce-137">Vrai</span><span class="sxs-lookup"><span data-stu-id="372ce-137">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="372ce-138">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="372ce-138">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="372ce-p108">Indique si les enregistrements QoE doivent être périodiquement supprimés de la base de données. Si la valeur est True, les enregistrements sont supprimés après la période spécifiée par la propriété KeepQoEDataForDays. Si la valeur est False, les enregistrements QoE sont conservés indéfiniment.</span><span class="sxs-lookup"><span data-stu-id="372ce-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="372ce-142">Vrai</span><span class="sxs-lookup"><span data-stu-id="372ce-142">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="372ce-143">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="372ce-143">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="372ce-p109">Indique le nombre de jours durant lesquels les enregistrements QoE sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. Mais pour cela, la purge doit être activée.</span><span class="sxs-lookup"><span data-stu-id="372ce-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="372ce-146">KeepCallDetailForDays peut être défini sur n’importe quelle valeur entière comprise entre 1 et 2562 jours.</span><span class="sxs-lookup"><span data-stu-id="372ce-146">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="372ce-147">60 jours</span><span class="sxs-lookup"><span data-stu-id="372ce-147">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="372ce-p110">Si vous devez modifier ces paramètres globaux, vous pouvez pour cela utiliser les applets de commande Set-CsCdrConfiguration et Set-CsQoEConfiguration. Par exemple, cette commande (qui s’exécute depuis Lync Server Management Shell) désactive la surveillance CDR au niveau global ; il suffit pour cela de définir la propriété EnableCDR sur False ($False):</span><span class="sxs-lookup"><span data-stu-id="372ce-p110">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets. For example, this command (run from within the Lync Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

<span data-ttu-id="372ce-150">Notez que le fait de désactiver la surveillance ne dissocie pas le magasin d’analyse du pool frontal, ni ne désinstalle et n’a un impact sur la base de données de surveillance principale.</span><span class="sxs-lookup"><span data-stu-id="372ce-150">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="372ce-151">Lorsque vous utilisez Lync Server Management Shell pour désactiver la surveillance des enregistrements des détails des appels ou des données QoE, vous empêchez temporairement Lync Server de collecter et d’archiver les données d’analyse.</span><span class="sxs-lookup"><span data-stu-id="372ce-151">When you use Lync Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Lync Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="372ce-152">Pour reprendre la collecte et l’archivage des données de l’enregistrement CDR, il vous suffit de redéfinir la propriété EnableCDR sur True ($True):</span><span class="sxs-lookup"><span data-stu-id="372ce-152">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="372ce-153">De même, cette commande désactive la purge des enregistrements QoE globaux :</span><span class="sxs-lookup"><span data-stu-id="372ce-153">Similarly, this command disables the purging of QoE records at the global scope:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

<span data-ttu-id="372ce-p112">Outre les paramètres globaux, les paramètres de configuration CDR et QoE peuvent être assignés pour un site. Cela offre plus de flexibilité pour la gestion de la surveillance ; par exemple, un administrateur peut activer la surveillance CDR pour le site de Redmond et la désactiver pour le site de Dublin. Pour créer de nouveaux paramètres de configuration CDR pour un site, utilisez une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="372ce-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

<span data-ttu-id="372ce-p113">Gardez à l’esprit que les paramètres configurés pour un site prévalent sur les paramètres globaux configurés. Supposons, par exemple, que la surveillance CDR soit activée globalement, mais désactivée pour un site (le site de Redmond). Dans ce cas, les informations de l’enregistrement des détails des appels ne seront pas archivées pour les utilisateurs du site de Redmond mais elles le seront pour les utilisateurs des autres sites (c’est-à-dire, les utilisateurs gérés par les paramètres globaux et non par les paramètres du site de Redmond).</span><span class="sxs-lookup"><span data-stu-id="372ce-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>

<span data-ttu-id="372ce-161">Pour créer de nouveaux paramètres QoE pour un site, il suffit d’utiliser une commande similaire à la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="372ce-161">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

<span data-ttu-id="372ce-162">Pour plus d’informations, tapez les commandes suivantes dans Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="372ce-162">For more information, type the following commands from within the Lync Server Management Shell:</span></span>

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

