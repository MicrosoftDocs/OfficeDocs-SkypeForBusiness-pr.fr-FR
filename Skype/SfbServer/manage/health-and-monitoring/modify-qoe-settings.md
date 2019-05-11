---
title: Modifier les paramètres de qualité de l’expérience dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Résumé : Découvrez comment spécifier la conservation des données QoE dans Skype pour Business Server.'
ms.openlocfilehash: 19342bb3f24f9e93919d0f1a292153d553f4c450
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929510"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="b8870-103">Modifier les paramètres de qualité de l’expérience dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="b8870-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="b8870-104">**Résumé :** Découvrez comment spécifier la conservation des données QoE dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="b8870-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="b8870-p101">Par défaut, les données de qualité de l’expérience (QoE) sont vidées au bout de 60 jours. Vous pouvez utiliser les paramètres de la page **Données de qualité de l’expérience** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez QoE, les données capturées avant que l’activation de QoE seront également purgées.</span><span class="sxs-lookup"><span data-stu-id="b8870-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="b8870-p102">Vous devez configurer l’enregistrement des détails des appels (CDR) et QoE pour conserver des données pendant le même nombre de jours. Chaque appel des enregistrements des détails des appels disponible à partir de la page d’accueil des rapports de surveillance inclut des informations sur l’enregistrement des détails des appels et sur la qualité de l’expérience. Si la durée du vidage est différente pour les enregistrements des détails des appels (CDR) et la qualité de l’expérience (QoE), certains appels pourront inclure uniquement des données CDR, tandis que d’autres contiendront uniquement des données QoE.</span><span class="sxs-lookup"><span data-stu-id="b8870-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="b8870-111">La procédure suivante décrit comment configurer des paramètres de vidage pour des données de qualité de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="b8870-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b8870-112">Pour spécifier la conservation des données QoE à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="b8870-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="b8870-113">Ouvrez une session l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b8870-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b8870-114">Pour plus d’informations, voir **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="b8870-114">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="b8870-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="b8870-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="b8870-116">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="b8870-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="b8870-117">Dans la page **Données de qualité de l’expérience**, cliquez sur le site approprié dans le tableau, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b8870-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="b8870-118">Pour activer le vidage, sélectionnez **Activer le vidage des données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="b8870-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="b8870-119">Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximal de jours pendant lesquels les données de qualité de l’expérience doivent être conservées.</span><span class="sxs-lookup"><span data-stu-id="b8870-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="b8870-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b8870-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b8870-121">Spécification de conservation des données QoE à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8870-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b8870-122">Vous pouvez créer des paramètres de rétention QoE à l’aide de Windows PowerShell et l’applet de commande **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b8870-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="b8870-123">Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8870-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b8870-124">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="b8870-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b8870-125">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="b8870-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="b8870-126">Pour spécifier la conservation des données QoE pour un emplacement spécifique</span><span class="sxs-lookup"><span data-stu-id="b8870-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="b8870-127">Cette commande active le vidage des données QoE pour le site Redmond et configure le site de façon à conserver les données QoE pendant 20 jours.</span><span class="sxs-lookup"><span data-stu-id="b8870-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="b8870-128">Pour spécifier la conservation des données QoE pour plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="b8870-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="b8870-129">Cette commande configure la conservation des données QoE pour tous les paramètres de configuration QoE utilisés dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="b8870-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="b8870-130">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b8870-130">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8870-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8870-131">See also</span></span>

[<span data-ttu-id="b8870-132">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="b8870-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
