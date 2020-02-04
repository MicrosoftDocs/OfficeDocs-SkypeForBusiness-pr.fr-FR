---
title: Configuration de la qualité de service sur les appareils Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8068b69afa3e02a5634041c61be6f7711e8f30
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="a6b2d-102">Configuration de la qualité de service sur les appareils Microsoft Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6b2d-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6b2d-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a6b2d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a6b2d-104">Même si la qualité de service (QoS) n’est pas activée par défaut pour les appareils tels que les iPhone, la qualité de service (QoS) est activée par défaut pour les appareils exécutant Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="a6b2d-105">(Ces appareils sont généralement désignés sous le nom de téléphones de communications unifiées ou unifiées.) Pour vérifier cela, exécutez la commande Windows PowerShell suivante à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a6b2d-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="a6b2d-106">Si vous n’avez apporté aucune modification aux paramètres de configuration de votre téléphone UC, vous obtiendrez des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a6b2d-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="a6b2d-107">Pour des raisons de qualité de service, une seule de ces propriétés est particulièrement intéressante : VoiceDiffServTag.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="a6b2d-108">Le VoiceDiffServTag représente la valeur DSCP affectée au trafic vocal émis à partir d’un appareil Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a6b2d-109">Le paramètre Voice8021p n’est plus pris en charge dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="a6b2d-110">Le paramètre reste valide pour la compatibilité descendante avec Microsoft Lync Server 2010 ; Néanmoins, il n’a aucun effet sur les appareils utilisés avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="a6b2d-111">Dans la plupart des réseaux, le marquage de paquets Lync Phone Edition avec un VoiceDiffServTag de 40 ne doit pas provoquer de problèmes.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="a6b2d-112">À la place, le trafic audio est presque toujours marqué avec le le code DSCP 46.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="a6b2d-113">Pour garantir la cohérence de votre réseau, il peut être préférable de changer la propriété VoiceDiffServTag de vos téléphones UC vers 46.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="a6b2d-114">Pour ce faire, vous pouvez utiliser Windows PowerShell ou le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="a6b2d-115">Pour modifier la valeur VoiceDiffServTag à l’aide de Windows PowerShell, exécutez la commande suivante à partir de Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a6b2d-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="a6b2d-116">La commande précédente modifie la collection globale des paramètres de configuration de téléphone UC.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-116">The preceding command modifies the global collection of UC phone configuration settings.</span></span> <span data-ttu-id="a6b2d-117">Notez, toutefois, que les paramètres de téléphone monouc peuvent également être attribués à l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-117">Note, however, that UC phone settings can also be assigned to the site scope.</span></span> <span data-ttu-id="a6b2d-118">Pour modifier les paramètres de configuration de téléphone UC sur l’étendue du site, vous devez spécifier l’identité du site.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-118">To modify UC phone configuration settings at the site scope, you must specify the site Identity.</span></span> <span data-ttu-id="a6b2d-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a6b2d-119">For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="a6b2d-120">Vous pouvez également utiliser la commande suivante pour modifier simultanément l’ensemble des paramètres de configuration du téléphone de communications unifiées :</span><span class="sxs-lookup"><span data-stu-id="a6b2d-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="a6b2d-121">Si vous préférez apporter cette modification à l’aide du panneau de configuration de Lync Server, démarrez le panneau de configuration, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a6b2d-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="a6b2d-122">Cliquez sur **clients** , puis sur Configuration de l' **appareil**.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="a6b2d-123">Dans l’onglet Configuration de l' **appareil** , double-cliquez sur l’ensemble de paramètres que vous souhaitez modifier (par exemple, **Global**).</span><span class="sxs-lookup"><span data-stu-id="a6b2d-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="a6b2d-124">Dans la boîte de dialogue **modifier la configuration** de l’appareil, définissez la valeur de la zone **qualité de service (QoS)** sur **46** , puis cliquez sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="a6b2d-125">Si vous avez plusieurs collections, vous devrez répéter ce processus pour chaque ensemble de paramètres de téléphone de communications unifiées.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="a6b2d-126">Le panneau de configuration de Lync Server ne vous permet pas de modifier simultanément plusieurs collections de paramètres.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="a6b2d-127">Si vous disposez de périphériques qui ne sont pas basés sur le système d’exploitation Windows (par exemple, iPhone) au sein de votre organisation, ces appareils ne sont pas touchés par le changement du paramètre VoiceDiffServTag.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-127">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting.</span></span> <span data-ttu-id="a6b2d-128">Pour modifier les valeurs DSCP sur ces appareils, vous devez vous référer au manuel d’administration de chaque type d’appareil.</span><span class="sxs-lookup"><span data-stu-id="a6b2d-128">If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

