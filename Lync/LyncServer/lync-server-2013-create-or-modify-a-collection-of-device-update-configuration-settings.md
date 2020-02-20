---
title: Créer ou modifier une collection de paramètres de configuration de mise à jour des périphériques
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 125b8c1f0db938d8870bc1eb5dca67554fffa16a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="eb7d1-102">Créer ou modifier une collection de paramètres de configuration de mise à jour des périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb7d1-102">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb7d1-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="eb7d1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="eb7d1-104">Les paramètres de configuration de mise à jour des périphériques peuvent être créés (au niveau de l’étendue du site uniquement) à l’aide de Windows PowerShell et de la cmdlet **New-CsDeviceUpdateConfiguration** et modifiés à l’aide de la cmdlet **Set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="eb7d1-104">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="eb7d1-105">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb7d1-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="eb7d1-106">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="eb7d1-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="eb7d1-107">Pour créer des paramètres de configuration de mise à jour de périphérique qui utilisent les valeurs par défaut</span><span class="sxs-lookup"><span data-stu-id="eb7d1-107">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="eb7d1-108">Cette commande crée un nouvel ensemble de paramètres de configuration de mise à jour de périphérique pour le site Redmond :</span><span class="sxs-lookup"><span data-stu-id="eb7d1-108">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="eb7d1-109">Étant donné qu’aucun paramètre autre que le paramètre Identity obligatoire n’a été spécifié dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="eb7d1-109">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="eb7d1-110">Pour modifier une seule valeur de propriété lors de la création des paramètres de configuration de mise à jour des périphériques</span><span class="sxs-lookup"><span data-stu-id="eb7d1-110">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="eb7d1-111">Pour créer des paramètres qui utilisent différentes valeurs de propriété, incluez simplement le paramètre et la valeur de paramètre appropriés.</span><span class="sxs-lookup"><span data-stu-id="eb7d1-111">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="eb7d1-112">Par exemple, pour créer une collection de paramètres de configuration de mise à jour des périphériques qui, par défaut, supprime les anciens fichiers journaux tous les 21 jours, utilisez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="eb7d1-112">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="eb7d1-113">Pour modifier plusieurs valeurs de propriété lors de la création des paramètres de configuration de mise à jour des périphériques</span><span class="sxs-lookup"><span data-stu-id="eb7d1-113">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="eb7d1-114">Plusieurs valeurs de propriété peuvent être modifiées en incluant plusieurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="eb7d1-114">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="eb7d1-115">Par exemple, cette commande définit l’intervalle de nettoyage du journal sur 21 jours et l’intervalle de vidage du journal sur 30 minutes :</span><span class="sxs-lookup"><span data-stu-id="eb7d1-115">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="eb7d1-116">Pour plus d’informations sur la modification des paramètres de configuration d’appareil existants, voir la rubrique d’aide relative à l’applet de commande [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="eb7d1-116">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="eb7d1-117">Pour plus d’informations sur la création de collections de paramètres de configuration, voir la rubrique d’aide relative à la cmdlet [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="eb7d1-117">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

