---
title: 'Lync Server 2013 : activation de la qualité de service pour les appareils qui ne sont pas basés sur Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447c19b96e2189953db81db6ce4f022e4d0f6e6f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="a777e-102">Activation de la qualité de service dans Lync Server 2013 pour les appareils qui ne sont pas basés sur Windows</span><span class="sxs-lookup"><span data-stu-id="a777e-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a777e-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a777e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a777e-104">Lorsque vous installez Microsoft Lync Server 2013, la qualité de service (QoS) n’est pas activée pour les appareils utilisés dans votre organisation qui utilisent un système d’exploitation autre que Windows.</span><span class="sxs-lookup"><span data-stu-id="a777e-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="a777e-105">Vous pouvez vérifier cela en exécutant la commande suivante à partir de Lync Server 2013 Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a777e-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="a777e-106">Si vous n’avez apporté aucune modification à vos paramètres de configuration multimédia, vous devriez obtenir des informations de ce type :</span><span class="sxs-lookup"><span data-stu-id="a777e-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="a777e-107">Si la propriété EnableQoS est définie sur false (comme dans la sortie précédente), cela signifie que la qualité de service n’est pas activée pour les ordinateurs et les appareils qui utilisent un système d’exploitation autre que Windows.</span><span class="sxs-lookup"><span data-stu-id="a777e-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="a777e-108">La qualité de service est activée par défaut pour les appareils Lync Phone Edition ; Toutefois, il est possible de désactiver la qualité de service pour Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="a777e-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="a777e-109">Pour activer la qualité de service au niveau global, exécutez la commande suivante à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a777e-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="a777e-p103">La commande précédente active la QoS au niveau global, mais notez que les paramètres de configuration multimédia peuvent aussi être appliqués au niveau du site. Si vous avez besoin d’activer la qualité de service pour un site, vous devez inclure l’identité des paramètres de configuration lorsque vous appelez l’applet de commande Set-CsMediaConfiguration. Cette commande, par exemple, active la QoS pour le site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="a777e-p103">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope. If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration. For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="a777e-p104">Est-il nécessaire d’activer la QoS au niveau du site ? Cela dépend. Les paramètres affectés au site sont prioritaires sur ceux affectés à l’étendue globale. Supposons que vous avez activé la QoS au niveau global, mais qu’elle est désactivée au niveau du site (le site de Redmond). Dans ce cas, la qualité de service sera désactivée pour le site de Redmond, car le site est prioritaire. Pour activer la qualité de service sur le site de Redmond, vous devez modifier les paramètres de configuration multimédia appliqués à ce site.</span><span class="sxs-lookup"><span data-stu-id="a777e-p104">Do you need to enable QoS at the site scope? That depends. Settings assigned to the site scope take precedence over settings assigned to the global scope. Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence. To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="a777e-118">Si vous souhaitez activer simultanément QoS pour tous vos paramètres de configuration multimédia (quelle que soit l’étendue), exécutez cette commande à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a777e-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="a777e-119">Vous pouvez désactiver la qualité de service pour les appareils qui utilisent un système d’exploitation autre que Windows en définissant la valeur de la propriété EnableQoS sur false.</span><span class="sxs-lookup"><span data-stu-id="a777e-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="a777e-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a777e-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="a777e-121">Cela vous donne la possibilité d’implémenter la QoS sur des parties de votre réseau (par exemple, sur le site de Redmond), tout en la gardant désactivée sur d’autres.</span><span class="sxs-lookup"><span data-stu-id="a777e-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="a777e-122">QoS ne peut être activée et désactivée qu’à l’aide de Windows PowerShell ces options ne sont pas disponibles dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a777e-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

