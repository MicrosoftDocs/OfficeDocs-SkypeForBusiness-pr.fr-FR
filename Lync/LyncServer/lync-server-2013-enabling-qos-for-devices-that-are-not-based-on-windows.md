---
title: 'Lync Server 2013: activation de la qualité de service (QoS) pour les appareils qui ne sont pas basés sur Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d993a6905dfad9f5f2eda10a48553f2ae29b58ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="60bcc-102">Activation de la qualité de service (QoS) dans Lync Server 2013 pour les appareils qui ne sont pas basés sur Windows</span><span class="sxs-lookup"><span data-stu-id="60bcc-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60bcc-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="60bcc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="60bcc-104">Lorsque vous installez Microsoft Lync Server 2013, la qualité de service (QoS) n’est pas activée pour les appareils utilisés dans votre organisation qui utilisent un système d’exploitation autre que Windows.</span><span class="sxs-lookup"><span data-stu-id="60bcc-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="60bcc-105">Vous pouvez vérifier ceci en exécutant la commande suivante à partir de Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="60bcc-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="60bcc-106">Si vous avez apporté des modifications à vos paramètres de configuration de média, vous devez obtenir des informations similaires à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="60bcc-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="60bcc-107">Si la propriété EnableQoS est définie sur false (comme dans la sortie précédente), cela signifie que la qualité de service n’est pas activée pour les ordinateurs et appareils utilisant un système d’exploitation autre que Windows.</span><span class="sxs-lookup"><span data-stu-id="60bcc-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="60bcc-108">La QoS est activée par défaut pour les appareils Lync Phone Edition; Néanmoins, il est possible de désactiver la qualité de service pour Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="60bcc-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="60bcc-109">Pour activer la qualité de service sur l’étendue globale, exécutez la commande suivante à partir de Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="60bcc-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="60bcc-110">La commande précédente autorise la qualité de service (QoS) au niveau de l’étendue globale. Néanmoins, il est important de noter que les paramètres de configuration de média peuvent également être appliqués à l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="60bcc-110">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="60bcc-111">Si vous devez activer la qualité de service pour un site, vous devez inclure l’identité des paramètres de configuration lors de l’appel de Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="60bcc-111">If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="60bcc-112">Par exemple, cette commande active QoS pour le site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="60bcc-112">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="60bcc-113">Avez-vous besoin d’activer la qualité de service (QoS) sur l’étendue du site?</span><span class="sxs-lookup"><span data-stu-id="60bcc-113">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="60bcc-114">Cela dépend.</span><span class="sxs-lookup"><span data-stu-id="60bcc-114">That depends.</span></span> <span data-ttu-id="60bcc-115">Les paramètres assignés à l’étendue du site sont prioritaires sur les paramètres attribués à l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="60bcc-115">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="60bcc-116">Supposez que la qualité de service (QoS) soit activée sur l’étendue globale mais désactivée sur l’étendue du site (pour le site de Redmond). Dans ce cas, la qualité de service sera désactivée pour le site de Redmond; ce n’est pas parce que les paramètres du site sont prioritaires.</span><span class="sxs-lookup"><span data-stu-id="60bcc-116">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="60bcc-117">Pour activer la qualité de service (QoS) pour le site de Redmond, vous devez utiliser les paramètres de configuration de média appliqués au site.</span><span class="sxs-lookup"><span data-stu-id="60bcc-117">To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="60bcc-118">Si vous souhaitez activer simultanément la qualité de service (QoS) pour tous les paramètres de configuration de média (quelle que soit l’étendue), exécutez cette commande à partir de Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="60bcc-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="60bcc-119">Vous pouvez désactiver la qualité de service (QoS) pour les appareils qui utilisent un système d’exploitation différent de Windows en définissant la valeur de la propriété EnableQoS sur false.</span><span class="sxs-lookup"><span data-stu-id="60bcc-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="60bcc-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="60bcc-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="60bcc-121">Cette fonctionnalité vous permet d’implémenter la qualité de service (QoS) sur certaines parties de votre réseau (par exemple, sur le site de Redmond) tout en laissant la qualité de service désactivée sur d’autres parties de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="60bcc-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="60bcc-122">La qualité de service (QoS) peut uniquement être activée et désactivée à l’aide de Windows PowerShell ces options ne sont pas disponibles dans le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="60bcc-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

