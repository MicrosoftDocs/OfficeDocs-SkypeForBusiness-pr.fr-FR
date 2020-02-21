---
title: 'Lync Server 2013 : gestion de la qualité de service (QoS)'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13d96132357e1981214961f136cf5365cf74907a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="51b40-102">Gestion de la qualité de service (QoS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51b40-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51b40-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="51b40-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="51b40-p101">La Qualité de service (QoS) est une technologie réseau utilisée dans certaines organisations afin de fournir des performances optimales à l’utilisateur final pour les communications audio et vidéo. QoS est le plus souvent utilisée sur les réseaux où la bande passante est limitée : avec un grand nombre de paquets réseau simultanés pour une quantité de bande passante disponible relativement faible, la Qualité de service permet aux administrateurs d’affecter une priorité supérieure aux paquets transportant des données audio ou vidéo. Le fait d’affecter une priorité supérieure à ces paquets permet aux communications audio et vidéo de s’effectuer plus rapidement, et avec moins d’interruption, que les sessions réseau impliquant des opérations telles que des transferts de fichiers, de la navigation web ou des sauvegardes de bases de données. C’est la raison pour laquelle la priorité « Meilleur effort » est affectée aux paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données.</span><span class="sxs-lookup"><span data-stu-id="51b40-p101">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications. QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data. By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups. That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51b40-p102">En règle générale, la Qualité de service s’applique uniquement aux sessions de communication sur votre réseau interne. Lorsque vous implémentez QoS, vous configurez vos serveurs et routeurs afin de prendre en charge le marquage de paquets ; toutefois, vous configurez ces périphériques pour que cette prise en charge s’effectue d’une manière particulière. Vous ne pouvez pas considérer que la Qualité de service sera prise en charge sur Internet ou sur d’autres réseaux. Même si c’est le cas, il n’est pas garanti que la configuration de QoS sera identique à celle que vous avez faite de ce service sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="51b40-p102">As a general rule, Quality of Service applies only to communication sessions on your internal network. When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner. You cannot assume that Quality of Service will be supported on the Internet or on other networks. Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="51b40-112">Microsoft Lync Server 2013 n’exige pas la qualité de service ; Si vous n’utilisez pas actuellement QoS, il n’est pas nécessaire d’installer le service avant d’installer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51b40-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="51b40-113">Si vous rencontrez une perte considérable de paquets sur votre réseau, il est recommandé d’ajouter de la bande passante supplémentaire afin de résoudre ce problème.</span><span class="sxs-lookup"><span data-stu-id="51b40-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="51b40-114">Si ce n’est pas possible, vous pouvez alors implémenter la Qualité de service à la place.</span><span class="sxs-lookup"><span data-stu-id="51b40-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="51b40-115">Lync Server 2013 offre une prise en charge complète de la qualité de service : cela signifie que les organisations qui utilisent déjà QoS peuvent facilement intégrer Lync Server dans leur infrastructure réseau existante.</span><span class="sxs-lookup"><span data-stu-id="51b40-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="51b40-116">Pour cela, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="51b40-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="51b40-117">[Activation de la qualité de service dans Lync Server 2013 pour les appareils qui ne sont pas basés sur Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span><span class="sxs-lookup"><span data-stu-id="51b40-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="51b40-118">Par défaut, QoS est désactivée pour les ordinateurs et autres périphériques (tels que les iPhones) qui exécutent d’autres systèmes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="51b40-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="51b40-119">Bien que vous puissiez utiliser Lync Server pour activer et désactiver la qualité de service pour les appareils, vous ne pouvez généralement pas utiliser le produit pour modifier les codes DSCP utilisés par ces appareils.</span><span class="sxs-lookup"><span data-stu-id="51b40-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="51b40-120">[Configuration des plages de ports dans Lync Server 2013 pour vos serveurs de conférence, d’application et de médiation](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="51b40-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="51b40-121">Vous devez réserver un ensemble unique de ports pour différents types de paquets, tels que les paquets audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="51b40-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="51b40-122">Avec Lync Server 2013, vous n’activez pas ou ne désactivez pas la qualité de service, par exemple, en définissant une valeur de propriété sur true ou sur false.</span><span class="sxs-lookup"><span data-stu-id="51b40-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="51b40-123">Au lieu de cela, vous activez la Qualité de service en configurant des plages de ports, puis en créant et en appliquant une stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="51b40-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="51b40-124">Si vous décidez par la suite de ne pas utiliser QoS, vous pouvez simplement « désactiver » ce service en supprimant les objets de stratégie de groupe appropriés.</span><span class="sxs-lookup"><span data-stu-id="51b40-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="51b40-125">[Configuration des plages de ports pour vos serveurs Edge dans Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="51b40-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="51b40-126">Bien que cela ne soit pas requis, vous pouvez configurer vos serveurs Edge de façon à utiliser les mêmes plages de ports que vos autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="51b40-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="51b40-127">[Configuration des plages de ports pour vos clients Microsoft Lync dans Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="51b40-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="51b40-128">Ces plages de ports s’appliquent uniquement aux ordinateurs clients et ne sont généralement pas les mêmes que les plages de ports configurées sur vos serveurs.</span><span class="sxs-lookup"><span data-stu-id="51b40-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="51b40-129">[Configuration d’une stratégie de qualité de service dans Lync Server 2013 pour vos serveurs de conférence, d’application et de médiation](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="51b40-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="51b40-130">Ces stratégies déterminent les codes DSCP appliqués aux différents types de paquets.</span><span class="sxs-lookup"><span data-stu-id="51b40-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="51b40-131">[Configuration d’une stratégie de qualité de service pour vos serveurs Edge a/V dans Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="51b40-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="51b40-132">Cette opération ne doit être effectuée que pour le côté interne de vos serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="51b40-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="51b40-133">En effet, la Qualité de service est conçue pour être utilisée sur votre réseau interne, et non sur Internet.</span><span class="sxs-lookup"><span data-stu-id="51b40-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="51b40-134">[Configuration des stratégies de qualité de service dans Lync Server 2013 pour les clients s’exécutant sur Windows 7 ou Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span><span class="sxs-lookup"><span data-stu-id="51b40-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="51b40-135">Notez que Microsoft Lync Server 2013 ne prend pas en charge QoS pour d’autres systèmes d’exploitation Windows, tels que Windows Vista ou Windows XP.</span><span class="sxs-lookup"><span data-stu-id="51b40-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="51b40-136">[Configuration de la qualité de service sur les appareils Microsoft Lync Phone Edition dans Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span><span class="sxs-lookup"><span data-stu-id="51b40-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="51b40-137">Par défaut, la qualité de service est activée pour les appareils Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="51b40-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="51b40-138">Vous pouvez toutefois modifier la valeur DSCP par défaut afin de garantir que tous les paquets audio de votre organisation utilisent le même code DSCP.</span><span class="sxs-lookup"><span data-stu-id="51b40-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51b40-139">Si vous utilisez Microsoft Windows Server 2012 ou Windows Server 2012 R2, le nouvel ensemble d’applets de commande Windows PowerShell disponible pour la gestion de la qualité de service sur cette plateforme est susceptible de vous intéresser.</span><span class="sxs-lookup"><span data-stu-id="51b40-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="51b40-140">Pour plus d’informations, reportez-vous à Network Quality of service [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)cmdlets in Windows PowerShell à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="51b40-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

