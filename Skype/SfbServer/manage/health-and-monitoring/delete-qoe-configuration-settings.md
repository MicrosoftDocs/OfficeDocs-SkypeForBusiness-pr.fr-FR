---
title: Suppression des paramètres de configuration de la qualité de l’expérience dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Résumé : Découvrez comment supprimer les paramètres de qualité d’expérience (QoE) dans Skype pour Business Server 2015.'
ms.openlocfilehash: 52008e14ca7a7b2a7a26726a2749f6d4dd083bbb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="fc99f-103">Suppression des paramètres de configuration de la qualité de l’expérience dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="fc99f-103">Delete Quality of Experience configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fc99f-104">**Résumé :** Découvrez comment supprimer les paramètres de qualité d’expérience (QoE) dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="fc99f-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="fc99f-p101">Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.</span><span class="sxs-lookup"><span data-stu-id="fc99f-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="fc99f-107">Lorsque vous installez Skype pour Business Server 2015, une seule collection globale QoE de paramètres de configuration est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="fc99f-107">When you install Skype for Business Server 2015, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="fc99f-108">Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels.</span><span class="sxs-lookup"><span data-stu-id="fc99f-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="fc99f-109">Par conception, les paramètres configurés sur l’étendue Site sont prioritaires sur les paramètres configurés sur l’étendue Global.</span><span class="sxs-lookup"><span data-stu-id="fc99f-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="fc99f-110">Si vous supprimez les paramètres sur l’étendue Site, la QoE sera gérée dans ce site en utilisant les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="fc99f-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="fc99f-111">Notez que vous pouvez également « supprimer » les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="fc99f-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="fc99f-112">Cependant, les paramètres globaux ne seront pas réellement supprimés.</span><span class="sxs-lookup"><span data-stu-id="fc99f-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="fc99f-113">Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="fc99f-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="fc99f-114">Par exemple, la purge est activée par défaut dans une collection de paramètres de configuration QoE.</span><span class="sxs-lookup"><span data-stu-id="fc99f-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="fc99f-115">Supposons que vous modifiez la collection globale pour que la purge soit désactivée.</span><span class="sxs-lookup"><span data-stu-id="fc99f-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="fc99f-116">Si vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="fc99f-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="fc99f-117">Dans ce cas, cela signifie que la purge sera de nouveau activée.</span><span class="sxs-lookup"><span data-stu-id="fc99f-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="fc99f-118">Vous pouvez supprimer les paramètres de configuration QoE à l’aide de la Skype pour le panneau de configuration de Business Server ou à l’aide de l’applet de commande [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="fc99f-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="fc99f-119">Pour supprimer les paramètres de configuration QoE pour le panneau de configuration de Business Server à l’aide de Skype</span><span class="sxs-lookup"><span data-stu-id="fc99f-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="fc99f-120">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fc99f-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="fc99f-121">Pour plus d’informations, consultez **Déléguer les autorisations de configuration**.</span><span class="sxs-lookup"><span data-stu-id="fc99f-121">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="fc99f-122">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc99f-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="fc99f-123">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="fc99f-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="fc99f-124">Sur la page **Données QoE**, cliquez sur la stratégie de votre choix, puis sur **Modifier**, et enfin sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="fc99f-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="fc99f-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc99f-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fc99f-126">Suppression des paramètres de Configuration QoE à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc99f-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fc99f-127">Vous pouvez supprimer les paramètres de configuration QoE à l’aide de Windows PowerShell et l’applet de commande **Remove-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="fc99f-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="fc99f-128">Vous pouvez exécuter cette applet de commande depuis le Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc99f-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fc99f-129">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="fc99f-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="fc99f-130">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc99f-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="fc99f-131">Pour supprimer une collection spécifiée de paramètres de configuration QoE</span><span class="sxs-lookup"><span data-stu-id="fc99f-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="fc99f-132">Cette commande supprime les paramètres de configuration QoE appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="fc99f-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="fc99f-133">Pour supprimer tous les paramètres de configuration QoE appliqués à l’étendue Site</span><span class="sxs-lookup"><span data-stu-id="fc99f-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="fc99f-134">Cette commande supprime tous les paramètres de configuration QoE appliqués à l’étendue Site :</span><span class="sxs-lookup"><span data-stu-id="fc99f-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="fc99f-135">Pour supprimer tous les paramètres de configuration QoE lorsque le suivi QoE est désactivé</span><span class="sxs-lookup"><span data-stu-id="fc99f-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="fc99f-136">Cette commande supprime tous les paramètres de configuration QoE lorsque le suivi QoE est désactivé :</span><span class="sxs-lookup"><span data-stu-id="fc99f-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="fc99f-137">Pour plus d’informations, consultez [Supprimer-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fc99f-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc99f-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fc99f-138">See also</span></span>

[<span data-ttu-id="fc99f-139">Purge manuelle de la d’enregistrement des données et les bases de données de qualité dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fc99f-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

