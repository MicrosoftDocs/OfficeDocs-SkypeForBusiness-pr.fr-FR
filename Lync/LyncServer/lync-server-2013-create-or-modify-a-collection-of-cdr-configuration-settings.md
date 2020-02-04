---
title: 'Lync Server 2013 : création ou modification d’un ensemble de paramètres de configuration de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37ed8be52827f56b14c52f1bddd950ab39883cdf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="dfbdf-102">Créer ou modifier un ensemble de paramètres de configuration de CDR dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfbdf-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfbdf-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="dfbdf-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="dfbdf-p101">L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de l’entretien.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="dfbdf-106">Lorsque vous installez Microsoft Lync Server 2013, une collection globale unique de paramètres de configuration CDR est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="dfbdf-107">Les administrateurs peuvent aussi créer des paramètres personnalisés sur l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="dfbdf-108">Chaque fois que ces paramètres d’étendue de site sont utilisés, ils prennent la priorité sur les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="dfbdf-109">Par exemple, si vous créez des paramètres pour l’étendue du site de Redmond, ces paramètres (au lieu des paramètres globaux) servent alors à gérer l’enregistrement des détails des appels à Redmond.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="dfbdf-110">Vous pouvez créer des paramètres de configuration de CDR à l’aide du panneau de configuration de Lync Server ou de l’applet [de commande New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="dfbdf-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="dfbdf-111">Vous pouvez utiliser le panneau de configuration de Lync Server ou l’applet de commande [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) pour modifier les paramètres existants.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="dfbdf-112">Si vous utilisez le panneau de configuration de Lync Server pour créer ou modifier des paramètres, les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="dfbdf-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfbdf-113">Paramètre de l’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="dfbdf-113">UI Setting</span></span></th>
<th><span data-ttu-id="dfbdf-114">Paramètre PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfbdf-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="dfbdf-115">Description</span><span class="sxs-lookup"><span data-stu-id="dfbdf-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfbdf-116">Nom</span><span class="sxs-lookup"><span data-stu-id="dfbdf-116">Name</span></span></p></td>
<td><p><span data-ttu-id="dfbdf-117">Identity</span><span class="sxs-lookup"><span data-stu-id="dfbdf-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="dfbdf-p104">Identificateur unique pour les paramètres de configuration d’enregistrement des détails des appels créés. Ces paramètres peuvent uniquement être créés au niveau de l’étendue Site.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfbdf-120">Activer la surveillance des enregistrements des détails des appels</span><span class="sxs-lookup"><span data-stu-id="dfbdf-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="dfbdf-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="dfbdf-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="dfbdf-122">Indique si l’enregistrement des détails des appels est activé ou non.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfbdf-123">Activer le vidage des enregistrements des détails des appels</span><span class="sxs-lookup"><span data-stu-id="dfbdf-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="dfbdf-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="dfbdf-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="dfbdf-125">Indique si les enregistrements des détails des appels doivent être périodiquement supprimés de la base de données d’enregistrements des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfbdf-126">Conserver les enregistrements des détails des appels pendant la durée maximale (jours)</span><span class="sxs-lookup"><span data-stu-id="dfbdf-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="dfbdf-127">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="dfbdf-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="dfbdf-p105">Indique le nombre de jours pendant lesquels les enregistrements des détails des appels sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. (Notez que le vidage ne se produit que s’il est activé.)</span><span class="sxs-lookup"><span data-stu-id="dfbdf-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfbdf-131">Conserver les données de signalement d’erreurs pendant la durée maximale (jours)</span><span class="sxs-lookup"><span data-stu-id="dfbdf-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="dfbdf-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="dfbdf-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="dfbdf-p106">Indique le nombre de jours pendant lesquels les rapports d’erreur des détails des appels sont conservés. Tout rapport plus ancien que le nombre de jours spécifié est automatiquement supprimé. Les rapports d’erreur des détails des appels sont des rapports de diagnostic téléchargés par les applications clientes.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="dfbdf-136">Les applets de commande New-CsCdrConfiguration et Set-CsCdrConfiguration incluent des options supplémentaires qui ne sont pas disponibles dans le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="dfbdf-137">Pour plus d’informations, reportez-vous à la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">nouvelle-CsCdrConfiguration</A> et aux rubriques d’aide de <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="dfbdf-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="dfbdf-138">Pour créer des paramètres de configuration de CDR en utilisant le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="dfbdf-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="dfbdf-139">Dans le panneau de configuration de Lync Server, cliquez sur **surveillance et archivage**.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="dfbdf-140">Dans l’onglet **enregistrement des détails des appels** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="dfbdf-p108">Dans la boîte de dialogue **Sélectionner un site**, indiquez le site où les nouveaux paramètres de configuration doivent être créés. Si la boîte de dialogue est vide, cela indique qu’une collection de paramètres de configuration d’enregistrement des détails des appels a déjà été affectée à tous vos sites. Chaque site ne peut recevoir qu’une seule collection. Vous pouvez dans ce cas supprimer puis recréer les paramètres ou modifier simplement les paramètres existants.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="dfbdf-145">Dans la boîte de dialogue **Nouveau paramètre d’enregistrement des détails des appels (CDR)**, sélectionnez les options voulues, puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="dfbdf-146">Pour modifier les paramètres de configuration de CDR existants en utilisant le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="dfbdf-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="dfbdf-147">Dans le panneau de configuration de Lync Server, cliquez sur **surveillance et archivage**.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="dfbdf-148">Double-cliquez sur la collection de paramètres à modifier, ou sélectionnez la collection, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="dfbdf-149">Sachez que vous ne pouvez modifier qu’une seule collection à la fois.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="dfbdf-150">Pour modifier plusieurs collections, utilisez plutôt Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="dfbdf-151">Dans la boîte de dialogue **Modifier le paramètre de l’enregistrement des détails des appels**, sélectionnez les options voulues, puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dfbdf-152">Création de paramètres de configuration de CDR à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfbdf-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dfbdf-153">Vous pouvez créer des paramètres de configuration de CDR en utilisant Windows PowerShell et l’applet **de nouvelle applet de nouveau-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="dfbdf-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="dfbdf-154">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfbdf-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dfbdf-155">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="dfbdf-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="dfbdf-156">Pour créer une collection de paramètres de configuration d’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="dfbdf-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="dfbdf-157">La commande crée une collection de paramètres de configuration pour l’enregistrement des détails des appels qui s’applique au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="dfbdf-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="dfbdf-158">Pour créer une collection de paramètres de configuration d’enregistrement des détails des appels qui désactivent l’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="dfbdf-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="dfbdf-p111">Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur. Par exemple, pour créer une collection de paramètres de configuration des détails des appels, l’autorisation de la désactivation de l’enregistrement des détails des appels fait appel par défaut à une commande comme celle-ci :</span><span class="sxs-lookup"><span data-stu-id="dfbdf-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="dfbdf-162">Pour spécifier plusieurs valeurs de propriétés pendant la création d’une collection de paramètres de configuration d’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="dfbdf-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="dfbdf-p112">Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres pour conserver les enregistrements des détails des appels pendant 30 jours et les rapports d’erreur 90 jours :</span><span class="sxs-lookup"><span data-stu-id="dfbdf-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="dfbdf-165">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de [nouvelle-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="dfbdf-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

