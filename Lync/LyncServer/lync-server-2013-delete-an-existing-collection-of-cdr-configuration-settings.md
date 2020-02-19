---
title: 'Lync Server 2013 : suppression d’une collection existante de paramètres de configuration CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77abb8ff4d50ec19b5d689193f909b0ddc4a475e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="2b3ae-102">Supprimer une collection existante de paramètres de configuration CDR dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b3ae-102">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b3ae-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2b3ae-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2b3ae-p101">L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="2b3ae-106">Lorsque vous installez Microsoft Lync Server 2013, une seule collection globale de paramètres de configuration CDR est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="2b3ae-107">Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="2b3ae-108">Par défaut, les paramètres configurés au niveau du site ont priorité sur les paramètres configurés au niveau global.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="2b3ae-109">Si vous supprimez les paramètres au niveau du site, l’enregistrement des détails des appels sera géré dans ce site à l’aide des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-109">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="2b3ae-p103">Notez que vous pouvez également « supprimer » les paramètres globaux. Cependant, les paramètres globaux ne seront pas réellement supprimés. Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut. Par exemple, le vidage est, par défaut, activé dans une collection de paramètres de configuration CDR. Si vous modifiez la collection globale afin que le vidage soit désactivé, et que vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut. Dans ce cas, cela signifie que le vidage sera de nouveau activé.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of CDR configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="2b3ae-117">Vous pouvez supprimer les paramètres de configuration CDR à l’aide du panneau de configuration Lync Server ou de la cmdlet [Remove-applet cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="2b3ae-117">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="2b3ae-118">Pour supprimer les paramètres de configuration CDR avec le panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="2b3ae-118">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2b3ae-119">Dans le panneau de configuration Lync Server, cliquez sur **surveillance et archivage**.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-119">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="2b3ae-p104">Sous l’onglet **Enregistrement des détails des appels**, sélectionnez la collection (ou les collections) de paramètres CDR à supprimer. Pour sélectionner plusieurs collections, cliquez sur la première collection, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="2b3ae-122">Cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-122">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="2b3ae-123">Dans la boîte de dialogue Lync Server, panneau de configuration, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-123">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2b3ae-124">Suppression des paramètres de configuration CDR à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b3ae-124">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2b3ae-125">Vous pouvez supprimer les paramètres de configuration de l’enregistrement des détails des appels à l’aide de Windows PowerShell et de l’applet de commande **Remove-applet cscdrconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2b3ae-125">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="2b3ae-126">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2b3ae-127">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="2b3ae-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="2b3ae-128">Pour supprimer une collection spécifique de paramètres de configuration CDR</span><span class="sxs-lookup"><span data-stu-id="2b3ae-128">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="2b3ae-129">Cette commande supprime les paramètres de configuration CDR appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="2b3ae-129">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="2b3ae-130">Pour supprimer tous les paramètres de configuration CDR appliqués à l’étendue site</span><span class="sxs-lookup"><span data-stu-id="2b3ae-130">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="2b3ae-131">Cette commande supprime tous les paramètres de configuration CDR appliqués au niveau du site :</span><span class="sxs-lookup"><span data-stu-id="2b3ae-131">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="2b3ae-132">Pour supprimer tous les paramètres de configuration CDR qui désactivent l’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="2b3ae-132">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="2b3ae-133">Cette commande supprime tous les paramètres de configuration CDR pour lesquels l’enregistrement des détails des appels a été désactivé :</span><span class="sxs-lookup"><span data-stu-id="2b3ae-133">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="2b3ae-134">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-applet cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="2b3ae-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

