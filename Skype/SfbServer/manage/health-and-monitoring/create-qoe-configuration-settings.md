---
title: Créer des paramètres de configuration de la qualité de l’expérience dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Résumé : Découvrez les paramètres de qualité de l’expérience (QoE) dans Skype Entreprise Server.'
ms.openlocfilehash: d1d0b299b5cf0bbaf3627b7c90f90e7e1d958d10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816994"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9beb1-103">Créer des paramètres de configuration de la qualité de l’expérience dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9beb1-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9beb1-104">**Résumé :** Découvrez les paramètres de qualité de l’expérience (QoE) dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9beb1-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9beb1-p101">Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.</span><span class="sxs-lookup"><span data-stu-id="9beb1-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="9beb1-107">Lorsque vous installez Skype Entreprise Server, une collection globale et unique de paramètres de configuration QoE est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="9beb1-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="9beb1-108">Les administrateurs peuvent aussi créer des paramètres personnalisés sur l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="9beb1-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="9beb1-109">Chaque fois que ces paramètres étendus aux sites sont utilisés, ils ont priorité sur les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="9beb1-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="9beb1-110">Par exemple, si vous créez des paramètres étendus au site pour le site Redmond, ceux-ci (et non les paramètres globaux) sont utilisés pour gérer la qualité de l’expérience à Redmond.</span><span class="sxs-lookup"><span data-stu-id="9beb1-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="9beb1-111">Les paramètres de configuration QoE peuvent être créés à l’aide du Panneau de configuration De Skype Entreprise Server ou de l’cmdlet [New-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9beb1-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="9beb1-112">Si vous utilisez le Panneau de configuration De Skype Entreprise Server pour créer de nouveaux paramètres, les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="9beb1-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="9beb1-113">**Paramètre de l’interface utilisateur**</span><span class="sxs-lookup"><span data-stu-id="9beb1-113">**UI setting**</span></span>|<span data-ttu-id="9beb1-114">**Paramètre PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9beb1-114">**PowerShell parameter**</span></span>|<span data-ttu-id="9beb1-115">**Description**</span><span class="sxs-lookup"><span data-stu-id="9beb1-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9beb1-116">Nom</span><span class="sxs-lookup"><span data-stu-id="9beb1-116">Name</span></span>  <br/> |<span data-ttu-id="9beb1-117">Identité</span><span class="sxs-lookup"><span data-stu-id="9beb1-117">Identity</span></span>  <br/> |<span data-ttu-id="9beb1-p104">Identificateur unique des paramètres à créer. Les paramètres de configuration QoE peuvent uniquement être créés au niveau de l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="9beb1-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="9beb1-120">Activer la surveillance des données de QoE</span><span class="sxs-lookup"><span data-stu-id="9beb1-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="9beb1-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="9beb1-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="9beb1-122">Spécifie si les enregistrements QoE seront collectés et enregistrés dans la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="9beb1-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="9beb1-123">Activer le vidage des données de QoE</span><span class="sxs-lookup"><span data-stu-id="9beb1-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="9beb1-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="9beb1-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="9beb1-125">Spécifie si les rapports sont vidés une fois la durée définie dans la propriété **Conserver les données QoE pendant la durée maximale (jours)** écoulée.</span><span class="sxs-lookup"><span data-stu-id="9beb1-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="9beb1-126">Conserver les données QoE pendant la durée maximale (jours)</span><span class="sxs-lookup"><span data-stu-id="9beb1-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="9beb1-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="9beb1-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="9beb1-p105">Nombre de jours pendant lesquels les données QoE sont enregistrées avant d’être vidées de la base de données. Cette valeur est ignorée si le vidage est désactivé.</span><span class="sxs-lookup"><span data-stu-id="9beb1-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="9beb1-130">La cmdlet New-CsQoEConfiguration inclut des options supplémentaires qui ne sont pas disponibles dans le Panneau de commande Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9beb1-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="9beb1-131">Pour plus d’informations, voir la rubrique [d’aide New-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9beb1-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9beb1-132">Pour créer des paramètres de configuration QoE à l’aide du Panneau de configuration de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9beb1-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9beb1-p107">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus de détails, voir **Déléguer des autorisations de configuration**.</span><span class="sxs-lookup"><span data-stu-id="9beb1-p107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="9beb1-135">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9beb1-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9beb1-136">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="9beb1-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="9beb1-137">Dans la page **Données de qualité de l’expérience**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9beb1-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="9beb1-138">Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit être appliquée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9beb1-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="9beb1-139">Dans **Nouveau paramètre de qualité de l’expérience**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9beb1-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="9beb1-140">Sélectionnez **Activer la surveillance des données de QoE** pour activer la surveillance.</span><span class="sxs-lookup"><span data-stu-id="9beb1-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="9beb1-141">Sélectionnez **Activer le vidage des données de QoE** pour activer le vidage.</span><span class="sxs-lookup"><span data-stu-id="9beb1-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="9beb1-142">Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximum de jours de rétention des enregistrements QoE.</span><span class="sxs-lookup"><span data-stu-id="9beb1-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="9beb1-143">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="9beb1-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9beb1-144">Création de paramètres de configuration QoE à l’aide Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="9beb1-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9beb1-145">Vous pouvez créer des paramètres de configuration QoE à l’Windows PowerShell l'New-CsQoEConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9beb1-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="9beb1-146">Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9beb1-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9beb1-147">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="9beb1-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9beb1-148">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9beb1-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="9beb1-149">Pour créer une collection de paramètres de configuration QoE</span><span class="sxs-lookup"><span data-stu-id="9beb1-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="9beb1-150">Cette commande crée une collection de paramètres de configuration QoE qui sont appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="9beb1-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="9beb1-151">Pour créer une collection de paramètres de configuration QoE dans laquelle la surveillance QoE est désactivée</span><span class="sxs-lookup"><span data-stu-id="9beb1-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="9beb1-p109">Étant donné qu’aucun paramètre (à l’exception du paramètre Identity obligatoire) n’a été spécifié dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui utilisent des valeurs de propriété différentes, incluez simplement le paramètre approprié et la valeur du paramètre. Par exemple, pour créer une collection de paramètres de configuration de qualité de l’expérience qui, par défaut, permet de désactiver enregistrement de données QoE, utilisez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="9beb1-p109">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="9beb1-155">Pour spécifier plusieurs valeurs de propriété lors de création d’une collection de paramètres de configuration QoE</span><span class="sxs-lookup"><span data-stu-id="9beb1-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="9beb1-p110">Vous pouvez spécifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres de manière à conserver les données QoE pendant 30 jours et à vider les anciennes données à 03:00 :</span><span class="sxs-lookup"><span data-stu-id="9beb1-p110">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="9beb1-158">Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [New-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9beb1-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

