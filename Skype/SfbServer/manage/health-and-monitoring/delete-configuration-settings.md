---
title: Suppression d’une collection existante de paramètres de configuration de l’enregistrement des détails des appels dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Résumé : Découvrez comment supprimer les paramètres de configuration de CD-r dans Skype pour Business Server 2015.'
ms.openlocfilehash: d7379817b808ac800694c01014469fe0d159d68f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="965ae-103">Suppression d’une collection existante de paramètres de configuration de l’enregistrement des détails des appels dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="965ae-103">Delete an existing collection of CDR configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="965ae-104">**Résumé :** Découvrez comment supprimer les paramètres de configuration de CD-r dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="965ae-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="965ae-p101">L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.</span><span class="sxs-lookup"><span data-stu-id="965ae-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="965ae-107">Lorsque vous installez Skype pour Business Server 2015, une seule collection globale CDR de paramètres de configuration est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="965ae-107">When you install Skype for Business Server 2015, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="965ae-108">Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels.</span><span class="sxs-lookup"><span data-stu-id="965ae-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="965ae-109">Par conception, les paramètres configurés sur l’étendue Site sont prioritaires sur les paramètres configurés sur l’étendue Global.</span><span class="sxs-lookup"><span data-stu-id="965ae-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="965ae-110">Si vous supprimez les paramètres sur l’étendue Site, les enregistrements des détails des appels seront gérés dans ce site en utilisant les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="965ae-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="965ae-111">Notez que vous pouvez également « supprimer » les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="965ae-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="965ae-112">Cependant, les paramètres globaux ne seront pas réellement supprimés.</span><span class="sxs-lookup"><span data-stu-id="965ae-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="965ae-113">Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="965ae-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="965ae-114">Par exemple, par défaut purge est activée dans une collection de paramètres de configuration de CD-r.</span><span class="sxs-lookup"><span data-stu-id="965ae-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="965ae-115">Supposons que vous modifiez la collection globale pour que la purge soit désactivée.</span><span class="sxs-lookup"><span data-stu-id="965ae-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="965ae-116">Si vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="965ae-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="965ae-117">Dans ce cas, cela signifie que la purge sera de nouveau activée.</span><span class="sxs-lookup"><span data-stu-id="965ae-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="965ae-118">Vous pouvez supprimer les paramètres de configuration de CD-r à l’aide de la Skype pour Business Server du Panneau de configuration ou l’applet de commande [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="965ae-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="965ae-119">Pour supprimer les paramètres de configuration de CD-r avec Skype pour le panneau de configuration de Business Server</span><span class="sxs-lookup"><span data-stu-id="965ae-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="965ae-120">Dans Skype pour le panneau de configuration de Business Server, cliquez sur **surveillance et archivage**.</span><span class="sxs-lookup"><span data-stu-id="965ae-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="965ae-p104">Sous l’onglet **Enregistrement des détails des appels**, sélectionnez la collection (ou les collections) de paramètres CDR à supprimer. Pour sélectionner plusieurs collections, cliquez sur la première collection, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres.</span><span class="sxs-lookup"><span data-stu-id="965ae-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="965ae-123">Cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="965ae-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="965ae-124">Dans la boîte de dialogue Panneau de configuration de Business Server Skype, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="965ae-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="965ae-125">Suppression des paramètres de configuration de CD-r à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="965ae-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="965ae-126">Vous pouvez supprimer les détails de l’appel d’enregistrement des paramètres de configuration à l’aide de Windows PowerShell et l’applet de commande **Remove-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="965ae-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="965ae-127">Vous pouvez exécuter cette applet de commande depuis le Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="965ae-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="965ae-128">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="965ae-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="965ae-129">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="965ae-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="965ae-130">Pour supprimer une collection spécifique de paramètres de configuration CDR</span><span class="sxs-lookup"><span data-stu-id="965ae-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="965ae-131">Cette commande supprime les paramètres de configuration CDR appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="965ae-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="965ae-132">Pour supprimer tous les paramètres de configuration CDR appliqués au niveau du site</span><span class="sxs-lookup"><span data-stu-id="965ae-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="965ae-133">Cette commande supprime tous les paramètres de configuration CDR appliqués au niveau du site :</span><span class="sxs-lookup"><span data-stu-id="965ae-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="965ae-134">Pour supprimer tous les paramètres de configuration CDR qui désactivent l’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="965ae-134">To remove all the CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="965ae-135">Cette commande supprime tous les paramètres de configuration CDR pour lesquels l’enregistrement des détails des appels a été désactivé :</span><span class="sxs-lookup"><span data-stu-id="965ae-135">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="965ae-136">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="965ae-136">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="965ae-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="965ae-137">See also</span></span>

[<span data-ttu-id="965ae-138">Purge manuelle de la d’enregistrement des données et les bases de données de qualité dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="965ae-138">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

