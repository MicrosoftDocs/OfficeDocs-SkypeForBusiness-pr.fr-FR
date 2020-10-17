---
title: 'Lync Server 2013 : suppression d’une collection de paramètres de configuration de mise à jour des périphériques'
description: 'Lync Server 2013 : suppression d’une collection de paramètres de configuration de mise à jour des périphériques.'
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
ms.openlocfilehash: b3a03227869f68a52a30ea94db33bfb954b7e122
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566650"
---
# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="38e17-103">Supprimer une collection de paramètres de configuration de mise à jour des périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38e17-103">Delete a collection of Device Update configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38e17-104">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="38e17-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="38e17-105">Les paramètres de configuration de mise à jour des périphériques peuvent également être supprimés à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsdeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="38e17-105">Device update configuration settings can also be deleted by using Windows PowerShell and the **Remove-CsdeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="38e17-106">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38e17-106">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="38e17-107">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="38e17-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a><span data-ttu-id="38e17-108">Pour supprimer une collection spécifique de paramètres de configuration de mise à jour de périphériques</span><span class="sxs-lookup"><span data-stu-id="38e17-108">To remove a specific collection of device update configuration settings</span></span>

  - <span data-ttu-id="38e17-109">Cette commande supprime les paramètres de configuration de mise à jour des périphériques appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="38e17-109">This command deletes the device update configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="38e17-110">Pour supprimer tous les paramètres de configuration de mise à jour des périphériques appliqués à l’étendue site</span><span class="sxs-lookup"><span data-stu-id="38e17-110">To remove all the device update configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="38e17-111">Cette commande supprime tous les paramètres de configuration de mise à jour des périphériques appliqués à l’étendue du site :</span><span class="sxs-lookup"><span data-stu-id="38e17-111">This command deletes all the device update configuration settings applied to the site scope:</span></span>
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a><span data-ttu-id="38e17-112">Pour supprimer les paramètres de configuration de mise à jour des périphériques en fonction de la valeur de la propriété LogCleanUpInterval</span><span class="sxs-lookup"><span data-stu-id="38e17-112">To remove device update configuration settings based on the value of the LogCleanUpInterval property</span></span>

  - <span data-ttu-id="38e17-113">La commande suivante supprime tous les paramètres de configuration de mise à jour des périphériques dont l’intervalle de nettoyage des journaux est supérieur à 10 jours (10,00:00:00) :</span><span class="sxs-lookup"><span data-stu-id="38e17-113">The following command deletes all the device update configuration settings where the log cleanup interval is greater than 10 days (10.00:00:00):</span></span>
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

<span data-ttu-id="38e17-114">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="38e17-114">For details, see the Help topic for the [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

