---
title: Créer ou modifier un ensemble de paramètres de configuration de la mise à jour de l’appareil
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
ms.openlocfilehash: 80e550f48e37ab9c225e5a4919cbc65a13fe09e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5c67e-102">Créer ou modifier un ensemble de paramètres de configuration de la mise à jour de périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c67e-102">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c67e-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5c67e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5c67e-104">Les paramètres de configuration de la mise à jour de l’appareil peuvent être créés (uniquement à l’étendue du site) à l’aide de Windows PowerShell et de l’applet **de nouvelle** cmdlet **Set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="5c67e-104">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="5c67e-105">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c67e-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5c67e-106">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="5c67e-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="5c67e-107">Pour créer des paramètres de configuration de mise à jour d’appareils qui utilisent les valeurs par défaut</span><span class="sxs-lookup"><span data-stu-id="5c67e-107">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="5c67e-108">Cette commande crée un ensemble de paramètres de configuration de la mise à jour de l’appareil pour le site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="5c67e-108">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="5c67e-109">Aucun paramètre différent du paramètre d’identité obligatoire n’ayant été spécifié dans la commande précédente, la nouvelle collection de paramètres de configuration utilisera les valeurs par défaut pour toutes ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="5c67e-109">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="5c67e-110">Pour modifier une valeur de propriété unique lors de la création des paramètres de configuration de la mise à jour de l’appareil</span><span class="sxs-lookup"><span data-stu-id="5c67e-110">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="5c67e-111">Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur.</span><span class="sxs-lookup"><span data-stu-id="5c67e-111">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="5c67e-112">Par exemple, pour créer un ensemble de paramètres de configuration de la mise à jour de l’appareil qui, par défaut, supprime les anciens fichiers journaux tous les 21 jours, utilisez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="5c67e-112">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="5c67e-113">Pour modifier plusieurs valeurs de propriétés lors de la création des paramètres de configuration de la mise à jour de l’appareil</span><span class="sxs-lookup"><span data-stu-id="5c67e-113">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="5c67e-114">Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="5c67e-114">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="5c67e-115">Par exemple, cette commande définit l’intervalle de nettoyage du journal sur 21 jours et l’intervalle de vidage du journal sur 30 minutes :</span><span class="sxs-lookup"><span data-stu-id="5c67e-115">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="5c67e-116">Pour plus d’informations sur la modification des paramètres de configuration des appareils existants, consultez la rubrique d’aide de l’applet de connexion [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="5c67e-116">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="5c67e-117">Pour plus d’informations sur la création de collections de paramètres de configuration, consultez la rubrique d’aide de l’applet de [nouvelle-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="5c67e-117">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

