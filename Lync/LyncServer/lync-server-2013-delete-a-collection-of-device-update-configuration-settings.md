---
title: 'Lync Server 2013 : suppression d’une collection de paramètres de configuration de mise à jour des périphériques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345e1ad4c621ce6330b1b1a34c97664d080d6575
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="fa9f6-102">Supprimer une collection de paramètres de configuration de mise à jour des périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa9f6-102">Delete a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa9f6-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="fa9f6-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="fa9f6-104">Les paramètres de configuration de mise à jour des périphériques peuvent également être supprimés à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsdeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="fa9f6-104">Device update configuration settings can also be deleted by using Windows PowerShell and the **Remove-CsdeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="fa9f6-105">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa9f6-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fa9f6-106">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="fa9f6-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a><span data-ttu-id="fa9f6-107">Pour supprimer une collection spécifique de paramètres de configuration de mise à jour de périphériques</span><span class="sxs-lookup"><span data-stu-id="fa9f6-107">To remove a specific collection of device update configuration settings</span></span>

  - <span data-ttu-id="fa9f6-108">Cette commande supprime les paramètres de configuration de mise à jour des périphériques appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="fa9f6-108">This command deletes the device update configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="fa9f6-109">Pour supprimer tous les paramètres de configuration de mise à jour des périphériques appliqués à l’étendue site</span><span class="sxs-lookup"><span data-stu-id="fa9f6-109">To remove all the device update configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="fa9f6-110">Cette commande supprime tous les paramètres de configuration de mise à jour des périphériques appliqués à l’étendue du site :</span><span class="sxs-lookup"><span data-stu-id="fa9f6-110">This command deletes all the device update configuration settings applied to the site scope:</span></span>
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a><span data-ttu-id="fa9f6-111">Pour supprimer les paramètres de configuration de mise à jour des périphériques en fonction de la valeur de la propriété LogCleanUpInterval</span><span class="sxs-lookup"><span data-stu-id="fa9f6-111">To remove device update configuration settings based on the value of the LogCleanUpInterval property</span></span>

  - <span data-ttu-id="fa9f6-112">La commande suivante supprime tous les paramètres de configuration de mise à jour des périphériques dont l’intervalle de nettoyage des journaux est supérieur à 10 jours (10,00:00:00) :</span><span class="sxs-lookup"><span data-stu-id="fa9f6-112">The following command deletes all the device update configuration settings where the log cleanup interval is greater than 10 days (10.00:00:00):</span></span>
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

<span data-ttu-id="fa9f6-113">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="fa9f6-113">For details, see the Help topic for the [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

