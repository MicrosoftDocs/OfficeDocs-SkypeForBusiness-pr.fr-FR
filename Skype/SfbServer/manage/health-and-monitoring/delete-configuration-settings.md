---
title: Supprimer une collection existante de paramètres de configuration cdR dans Skype Entreprise Server
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Résumé : Découvrez comment supprimer les paramètres de configuration de l’cdr dans Skype Entreprise Server.'
ms.openlocfilehash: ca6691d6a1a19e0d9219a256986b683b719da885
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816964"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9c5ea-103">Supprimer une collection existante de paramètres de configuration cdR dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9c5ea-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9c5ea-104">**Résumé :** Découvrez comment supprimer les paramètres de configuration de l’cdr dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9c5ea-p101">L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="9c5ea-107">Lorsque vous installez Skype Entreprise Server, une collection unique et globale de paramètres de configuration d’cdr est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="9c5ea-108">Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="9c5ea-109">Par défaut, les paramètres configurés au niveau du site ont priorité sur les paramètres configurés au niveau global.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="9c5ea-110">Si vous supprimez les paramètres au niveau du site, l’enregistrement des détails des appels sera géré dans ce site à l’aide des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="9c5ea-111">Notez que vous pouvez également « supprimer » les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="9c5ea-112">Cependant, les paramètres globaux ne seront pas réellement supprimés.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="9c5ea-113">Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="9c5ea-114">Par exemple, la purge par défaut est activée dans une collection de paramètres de configuration d’cdr.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="9c5ea-115">Supposons que vous modifiez la collection globale pour que la purge soit désactivée.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="9c5ea-116">Si vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="9c5ea-117">Dans ce cas, cela signifie que la purge sera de nouveau activée.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="9c5ea-118">Vous pouvez supprimer les paramètres de configuration de l’cdr à l’aide du Panneau de configuration skype entreprise server ou de l';cmdlet [Remove-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9c5ea-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="9c5ea-119">Pour supprimer les paramètres de configuration de l’cdr avec le Panneau de configuration de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9c5ea-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9c5ea-120">Dans le Panneau de contrôle Skype Entreprise Server, cliquez **sur Surveillance et archivage.**</span><span class="sxs-lookup"><span data-stu-id="9c5ea-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="9c5ea-p104">Sous l’onglet **Enregistrement des détails des appels**, sélectionnez la collection (ou les collections) de paramètres CDR à supprimer. Pour sélectionner plusieurs collections, cliquez sur la première collection, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="9c5ea-123">Cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="9c5ea-124">Dans la boîte de dialogue Panneau de contrôle Skype Entreprise Server, cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="9c5ea-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9c5ea-125">Suppression des paramètres de configuration d’un cdr à l’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="9c5ea-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9c5ea-126">Vous pouvez supprimer les paramètres de configuration de l’enregistrement des détails des appels à l’Windows PowerShell et à l’aide de **l';remove-cscdrconfiguration.aspx.**</span><span class="sxs-lookup"><span data-stu-id="9c5ea-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="9c5ea-127">Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9c5ea-128">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="9c5ea-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9c5ea-129">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9c5ea-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="9c5ea-130">Pour supprimer une collection spécifique de paramètres de configuration CDR</span><span class="sxs-lookup"><span data-stu-id="9c5ea-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="9c5ea-131">Cette commande supprime les paramètres de configuration CDR appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="9c5ea-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="9c5ea-132">Pour supprimer tous les paramètres de configuration d’cdr appliqués à l’étendue Site</span><span class="sxs-lookup"><span data-stu-id="9c5ea-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="9c5ea-133">Cette commande supprime tous les paramètres de configuration CDR appliqués au niveau du site :</span><span class="sxs-lookup"><span data-stu-id="9c5ea-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="9c5ea-134">Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Remove-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9c5ea-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9c5ea-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c5ea-135">See also</span></span>

[<span data-ttu-id="9c5ea-136">Vider manuellement les bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9c5ea-136">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

