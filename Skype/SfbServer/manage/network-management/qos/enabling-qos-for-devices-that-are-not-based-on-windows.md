---
title: Activation de la qualité de service pour les appareils non basés sur Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Découvrez comment activer la QoS pour les appareils utilisés dans votre organisation qui utilisent un système d’exploitation autre que Windows.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814174"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="68224-103">Activation de la QoS dans Skype Entreprise Server pour les appareils qui ne sont pas basés sur Windows</span><span class="sxs-lookup"><span data-stu-id="68224-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="68224-104">Lorsque vous installez Skype Entreprise Server, la qualité de service (QoS) n’est activée pour aucun appareil utilisé dans votre organisation qui utilise un système d’exploitation autre que Windows.</span><span class="sxs-lookup"><span data-stu-id="68224-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="68224-105">Vous pouvez le vérifier en exécutant la commande suivante à partir de Skype Entreprise ServerManagement Shell :</span><span class="sxs-lookup"><span data-stu-id="68224-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="68224-106">En supposant que vous n’avez pas apporté de modifications à vos paramètres de configuration multimédia, vous devez obtenir des informations semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="68224-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="68224-107">Si la propriété EnableQoS a la valeur False (comme dans la sortie précédente), cela signifie que la qualité de service n’est pas activée pour les ordinateurs et les appareils qui utilisent un système d’exploitation autre que Windows.</span><span class="sxs-lookup"><span data-stu-id="68224-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="68224-108">Pour activer la qualité de service au niveau global, exécutez la commande suivante à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="68224-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="68224-109">La commande précédente active la QoS au niveau global, mais notez que les paramètres de configuration multimédia peuvent aussi être appliqués au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="68224-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="68224-110">Si vous devez activer la qualité de service pour un site, vous devez inclure l’identité des paramètres de configuration lors de l’appel de Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="68224-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="68224-111">Cette commande, par exemple, active la QoS pour le site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="68224-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="68224-112">Est-il nécessaire d’activer la QoS au niveau du site ?</span><span class="sxs-lookup"><span data-stu-id="68224-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="68224-113">Cela dépend.</span><span class="sxs-lookup"><span data-stu-id="68224-113">That depends.</span></span> <span data-ttu-id="68224-114">Les paramètres affectés au site sont prioritaires sur ceux affectés à l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="68224-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="68224-115">Supposons que la QoS soit activée au niveau de l’étendue globale, mais désactivée au niveau de l’étendue Site (pour le site redmond).</span><span class="sxs-lookup"><span data-stu-id="68224-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="68224-116">Dans ce cas, la qualité de service est désactivée pour le site redmond ; En raison du fait que les paramètres du site sont prioritaire.</span><span class="sxs-lookup"><span data-stu-id="68224-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="68224-117">Pour activer la QoS pour le site Redmond, vous devez utiliser les paramètres de configuration multimédia appliqués à ce site.</span><span class="sxs-lookup"><span data-stu-id="68224-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="68224-118">Si vous souhaitez activer simultanément QoS pour tous vos paramètres de configuration multimédia (quelle que soit l’étendue), exécutez cette commande à partir de LSkype for Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="68224-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="68224-119">Vous pouvez désactiver la qualité de service pour les appareils qui utilisent un système d’exploitation autre que Windows en fixant la valeur de la propriété EnableQoS sur False.</span><span class="sxs-lookup"><span data-stu-id="68224-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="68224-120">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="68224-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="68224-121">Cela vous donne la possibilité d’implémenter la QoS sur des parties de votre réseau (par exemple, sur le site de Redmond), tout en la gardant désactivée sur d’autres.</span><span class="sxs-lookup"><span data-stu-id="68224-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="68224-122">La QoS ne peut être activée et désactivée qu’à l’aide Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68224-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="68224-123">Ces options ne sont pas disponibles dans le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="68224-123">These options are not available in the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="68224-124">Les clients Skype Entreprise pour iOS version 6.17 et ultérieures utilisent désormais QoS.</span><span class="sxs-lookup"><span data-stu-id="68224-124">Skype for Business clients for iOS Version 6.17 and later now support QoS.</span></span>  <span data-ttu-id="68224-125">Cette fonctionnalité de QoS s’applique uniquement aux clients Skype Entreprise et aux périphériques téléphoniques IP qui sont enregistrés directement sur un serveur de pool Skype Entreprise ou Lync interne sur des réseaux gérés.</span><span class="sxs-lookup"><span data-stu-id="68224-125">This QoS capability is only applicable to Skype for Business clients and IP phone devices which are registered directly to an internal Skype for Business or Lync pool Server on managed networks.</span></span> <span data-ttu-id="68224-126">La QoS n’est pas applicable pour le trafic acheminé sur Internet.</span><span class="sxs-lookup"><span data-stu-id="68224-126">QoS is not applicable for traffic routed over the Internet.</span></span>



