---
title: Activation de la qualité de service pour les périphériques non basés sur Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Découvrez comment activer la qualité de service (QoS) pour les appareils utilisés au sein de votre organisation qui utilisent un système d’exploitation autre que Windows.
ms.openlocfilehash: adb879d2319c5eeeb84578907ce57a3a408d9a13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279409"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="bfc9a-103">Activation de la qualité de service (QoS) dans Skype entreprise Server pour les appareils qui ne sont pas basés sur Windows</span><span class="sxs-lookup"><span data-stu-id="bfc9a-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="bfc9a-104">Lorsque vous installez Skype entreprise Server, la qualité de service (QoS) n’est pas activée pour les appareils utilisés dans votre organisation qui utilisent un système d’exploitation autre que Windows.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="bfc9a-105">Vous pouvez vérifier ceci en exécutant la commande suivante à partir de l’interpréteur de commandes de Skype entreprise ServerManagement:</span><span class="sxs-lookup"><span data-stu-id="bfc9a-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="bfc9a-106">Si vous avez apporté des modifications à vos paramètres de configuration de média, vous devez obtenir des informations similaires à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="bfc9a-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="bfc9a-107">Si la propriété EnableQoS est définie sur false (comme dans la sortie précédente), cela signifie que la qualité de service n’est pas activée pour les ordinateurs et appareils utilisant un système d’exploitation autre que Windows.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="bfc9a-108">Pour activer la qualité de service sur l’étendue globale, exécutez la commande suivante à partir de Skype entreprise Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="bfc9a-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="bfc9a-109">La commande précédente autorise la qualité de service (QoS) au niveau de l’étendue globale. Néanmoins, il est important de noter que les paramètres de configuration de média peuvent également être appliqués à l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="bfc9a-110">Si vous devez activer la qualité de service pour un site, vous devez inclure l’identité des paramètres de configuration lors de l’appel de Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="bfc9a-111">Par exemple, cette commande active QoS pour le site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="bfc9a-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="bfc9a-112">Avez-vous besoin d’activer la qualité de service (QoS) sur l’étendue du site?</span><span class="sxs-lookup"><span data-stu-id="bfc9a-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="bfc9a-113">Cela dépend.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-113">That depends.</span></span> <span data-ttu-id="bfc9a-114">Les paramètres assignés à l’étendue du site sont prioritaires sur les paramètres attribués à l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="bfc9a-115">Supposez que la qualité de service (QoS) soit activée sur l’étendue globale mais désactivée sur l’étendue du site (pour le site de Redmond).</span><span class="sxs-lookup"><span data-stu-id="bfc9a-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="bfc9a-116">Dans ce cas, la qualité de service est désactivée pour le site de Redmond; ce n’est pas parce que les paramètres du site sont prioritaires.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="bfc9a-117">Pour activer la qualité de service (QoS) pour le site de Redmond, vous devez le faire à l’aide des paramètres de configuration de média appliqués au site.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="bfc9a-118">Si vous souhaitez activer simultanément la qualité de service (QoS) pour tous les paramètres de configuration de média (quelle que soit l’étendue), exécutez la commande suivante à partir de LSkype pour Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="bfc9a-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="bfc9a-119">Vous pouvez désactiver la qualité de service (QoS) pour les appareils qui utilisent un système d’exploitation différent de Windows en définissant la valeur de la propriété EnableQoS sur false.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="bfc9a-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="bfc9a-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="bfc9a-121">Cette fonctionnalité vous permet d’implémenter la qualité de service (QoS) sur certaines parties de votre réseau (par exemple, sur le site de Redmond) tout en laissant la qualité de service désactivée sur d’autres parties de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="bfc9a-122">La qualité de service (QoS) peut uniquement être activée et désactivée à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="bfc9a-123">Ces options ne sont pas disponibles dans le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="bfc9a-123">These options are not available in the Skype for Business Server Control Panel.</span></span>


