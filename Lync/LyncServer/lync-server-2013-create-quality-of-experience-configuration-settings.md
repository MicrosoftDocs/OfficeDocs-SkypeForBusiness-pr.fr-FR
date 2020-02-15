---
title: 'Lync Server 2013 : création des paramètres de configuration de la qualité de l’expérience'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e2d81f62bb35710d14450aa26f3100ea53021ca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="cf600-102">Créer des paramètres de configuration de qualité de l’expérience dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf600-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf600-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cf600-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cf600-p101">Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.</span><span class="sxs-lookup"><span data-stu-id="cf600-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="cf600-106">Lorsque vous installez Microsoft Lync Server 2013, une seule collection globale de paramètres de configuration QoE est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="cf600-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="cf600-107">Les administrateurs peuvent aussi créer des paramètres personnalisés sur l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="cf600-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="cf600-108">Chaque fois que ces paramètres étendus aux sites sont utilisés, ils ont priorité sur les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="cf600-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="cf600-109">Par exemple, si vous créez des paramètres étendus au site pour le site Redmond, ceux-ci (et non les paramètres globaux) sont utilisés pour gérer la qualité de l’expérience à Redmond.</span><span class="sxs-lookup"><span data-stu-id="cf600-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="cf600-110">Les paramètres de configuration QoE peuvent être créés à l’aide du panneau de configuration Lync Server ou de la cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="cf600-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="cf600-111">Si vous utilisez le panneau de configuration Lync Server pour créer de nouveaux paramètres, les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="cf600-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf600-112">Paramètre de l’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="cf600-112">UI Setting</span></span></th>
<th><span data-ttu-id="cf600-113">Paramètre PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf600-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="cf600-114">Description</span><span class="sxs-lookup"><span data-stu-id="cf600-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf600-115">Nom</span><span class="sxs-lookup"><span data-stu-id="cf600-115">Name</span></span></p></td>
<td><p><span data-ttu-id="cf600-116">Identité</span><span class="sxs-lookup"><span data-stu-id="cf600-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="cf600-p104">Identificateur unique des paramètres à créer. Les paramètres de configuration QoE peuvent uniquement être créés au niveau de l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="cf600-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf600-119">Activer la surveillance des données de QoE</span><span class="sxs-lookup"><span data-stu-id="cf600-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="cf600-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="cf600-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="cf600-121">Spécifie si les enregistrements QoE seront collectés et enregistrés dans la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="cf600-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf600-122">Activer le vidage des données de QoE</span><span class="sxs-lookup"><span data-stu-id="cf600-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="cf600-123">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="cf600-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="cf600-124">Spécifie si les rapports sont vidés une fois la durée définie dans la propriété <strong>Conserver les données QoE pendant la durée maximale (jours)</strong> écoulée.</span><span class="sxs-lookup"><span data-stu-id="cf600-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf600-125">Conserver les données QoE pendant la durée maximale (jours)</span><span class="sxs-lookup"><span data-stu-id="cf600-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="cf600-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="cf600-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="cf600-p105">Nombre de jours pendant lesquels les données QoE sont enregistrées avant d’être vidées de la base de données. Cette valeur est ignorée si le vidage est désactivé.</span><span class="sxs-lookup"><span data-stu-id="cf600-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="cf600-129">La cmdlet New-CsQoEConfiguration inclut des options supplémentaires qui ne sont pas disponibles dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf600-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="cf600-130">Pour plus d’informations, consultez la rubrique d’aide <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="cf600-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="cf600-131">Pour créer des paramètres de configuration QoE à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="cf600-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="cf600-132">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cf600-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="cf600-133">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cf600-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="cf600-134">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf600-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cf600-135">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cf600-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cf600-136">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="cf600-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="cf600-137">Dans la page **Données de qualité de l’expérience**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cf600-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="cf600-138">Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit être appliquée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf600-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="cf600-139">Dans **Nouveau paramètre de qualité de l’expérience**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cf600-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="cf600-140">Sélectionnez **Activer la surveillance des données de QoE** pour activer la surveillance.</span><span class="sxs-lookup"><span data-stu-id="cf600-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="cf600-141">Sélectionnez **Activer le vidage des données de QoE** pour activer le vidage.</span><span class="sxs-lookup"><span data-stu-id="cf600-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="cf600-142">Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximum de jours de rétention des enregistrements QoE.</span><span class="sxs-lookup"><span data-stu-id="cf600-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="cf600-143">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="cf600-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cf600-144">Création de paramètres de configuration QoE à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf600-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cf600-145">Vous pouvez créer des paramètres de configuration QoE à l’aide de Windows PowerShell et de la cmdlet New-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cf600-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="cf600-146">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf600-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cf600-147">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="cf600-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="cf600-148">Pour créer une collection de paramètres de configuration QoE</span><span class="sxs-lookup"><span data-stu-id="cf600-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="cf600-149">Cette commande crée une collection de paramètres de configuration QoE qui sont appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="cf600-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="cf600-150">Pour créer une collection de paramètres de configuration QoE dans laquelle la surveillance QoE est désactivée</span><span class="sxs-lookup"><span data-stu-id="cf600-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="cf600-p110">Étant donné qu’aucun paramètre (à l’exception du paramètre Identity obligatoire) n’a été spécifié dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui utilisent des valeurs de propriété différentes, incluez simplement le paramètre approprié et la valeur du paramètre. Par exemple, pour créer une collection de paramètres de configuration de qualité de l’expérience qui, par défaut, permet de désactiver enregistrement de données QoE, utilisez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="cf600-p110">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="cf600-154">Pour spécifier plusieurs valeurs de propriété lors de création d’une collection de paramètres de configuration QoE</span><span class="sxs-lookup"><span data-stu-id="cf600-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="cf600-p111">Vous pouvez spécifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres de manière à conserver les données QoE pendant 30 jours et à vider les anciennes données à 03:00 :</span><span class="sxs-lookup"><span data-stu-id="cf600-p111">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="cf600-157">Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="cf600-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

