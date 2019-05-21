---
title: Supprimer les paramètres de configuration de qualité de l’interface dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Résumé: Découvrez comment supprimer des paramètres de qualité de l’utilisation (QoE) dans Skype entreprise Server.'
ms.openlocfilehash: 4b521afd85a97550b27f320b9e49c5439e431681
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305800"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c21bf-103">Supprimer les paramètres de configuration de qualité de l’interface dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="c21bf-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c21bf-104">**Résumé:** Découvrez comment supprimer des paramètres de qualité de l’utilisation (QoE) dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c21bf-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="c21bf-p101">Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.</span><span class="sxs-lookup"><span data-stu-id="c21bf-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="c21bf-107">Lorsque vous installez Skype entreprise Server, une collection globale unique de paramètres de configuration QoE est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="c21bf-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="c21bf-108">Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels.</span><span class="sxs-lookup"><span data-stu-id="c21bf-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="c21bf-109">Par conception, les paramètres configurés sur l’étendue Site sont prioritaires sur les paramètres configurés sur l’étendue Global.</span><span class="sxs-lookup"><span data-stu-id="c21bf-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="c21bf-110">Si vous supprimez les paramètres sur l’étendue Site, la QoE sera gérée dans ce site en utilisant les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="c21bf-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="c21bf-111">Notez que vous pouvez également «supprimer» les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="c21bf-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="c21bf-112">Cependant, les paramètres globaux ne seront pas réellement supprimés.</span><span class="sxs-lookup"><span data-stu-id="c21bf-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="c21bf-113">Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="c21bf-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="c21bf-114">Par exemple, la purge est activée par défaut dans une collection de paramètres de configuration QoE.</span><span class="sxs-lookup"><span data-stu-id="c21bf-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="c21bf-115">Supposons que vous modifiez la collection globale pour que la purge soit désactivée.</span><span class="sxs-lookup"><span data-stu-id="c21bf-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="c21bf-116">Si vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="c21bf-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="c21bf-117">Dans ce cas, cela signifie que la purge sera de nouveau activée.</span><span class="sxs-lookup"><span data-stu-id="c21bf-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="c21bf-118">Vous pouvez supprimer les paramètres de configuration QoE en utilisant le panneau de configuration Skype entreprise Server ou en utilisant l’applet de commande [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c21bf-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c21bf-119">Pour supprimer les paramètres de configuration QoE en utilisant le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="c21bf-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c21bf-120">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c21bf-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c21bf-121">Pour plus d’informations, consultez **autorisations de configuration de délégué**.</span><span class="sxs-lookup"><span data-stu-id="c21bf-121">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="c21bf-122">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c21bf-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c21bf-123">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="c21bf-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="c21bf-124">Sur la page **Données QoE**, cliquez sur la stratégie de votre choix, puis sur **Modifier**, et enfin sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="c21bf-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="c21bf-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c21bf-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c21bf-126">Suppression des paramètres de configuration QoE à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c21bf-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c21bf-127">Vous pouvez supprimer des paramètres de configuration QoE à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c21bf-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="c21bf-128">Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c21bf-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c21bf-129">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [«démarrage rapide: gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="c21bf-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c21bf-130">Le processus est le même dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c21bf-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="c21bf-131">Pour supprimer une collection spécifiée de paramètres de configuration QoE</span><span class="sxs-lookup"><span data-stu-id="c21bf-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="c21bf-132">Cette commande supprime les paramètres de configuration QoE appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="c21bf-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="c21bf-133">Pour supprimer tous les paramètres de configuration QoE appliqués à l’étendue Site</span><span class="sxs-lookup"><span data-stu-id="c21bf-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="c21bf-134">Cette commande supprime tous les paramètres de configuration QoE appliqués à l’étendue Site :</span><span class="sxs-lookup"><span data-stu-id="c21bf-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="c21bf-135">Pour supprimer tous les paramètres de configuration QoE lorsque le suivi QoE est désactivé</span><span class="sxs-lookup"><span data-stu-id="c21bf-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="c21bf-136">Cette commande supprime tous les paramètres de configuration QoE lorsque le suivi QoE est désactivé :</span><span class="sxs-lookup"><span data-stu-id="c21bf-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="c21bf-137">Pour plus d’informations, consultez la rubrique [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c21bf-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c21bf-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c21bf-138">See also</span></span>

[<span data-ttu-id="c21bf-139">Effacement manuel des bases de données de l’enregistrement des détails des appels et de la qualité de l’activité dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="c21bf-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

