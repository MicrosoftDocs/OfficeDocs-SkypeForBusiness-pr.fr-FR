---
title: Expanseur des paramètres du pool de serveurs Edge
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 'Les sections suivantes vous permettent de modifier les paramètres d’un pool Edge de serveur unique ou de serveurs multiples :'
ms.openlocfilehash: cc8e0094a601faaf89c6a932172d5b6cb3522f2d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822434"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="e6919-103">Expandeur des paramètres du pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="e6919-103">Edge Settings Expander</span></span>

<span data-ttu-id="e6919-104">Les sections suivantes vous permettent de modifier les paramètres d’un pool Edge de serveur unique ou de serveurs multiples :</span><span class="sxs-lookup"><span data-stu-id="e6919-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="e6919-105">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="e6919-105">General settings</span></span>

- <span data-ttu-id="e6919-106">Paramètres de sélection du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="e6919-106">Next hop selection settings</span></span>

- <span data-ttu-id="e6919-107">Configuration du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e6919-107">Edge Server configuration</span></span>


## <a name="general-settings"></a><span data-ttu-id="e6919-108">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="e6919-108">General settings</span></span>

<span data-ttu-id="e6919-p101">Nom de domaine complet (FQDN) du pool interne pour le pool de serveurs Edge. Modifiez le nom de domaine complet du pool pour changer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="e6919-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="e6919-111">Activez la case à cocher Activer la fédération pour ce **pool Edge (port 5061)** si vous allez configurer la fédération avec un serveur Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e6919-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Skype for Business Server 2015 server.</span></span>

<span data-ttu-id="e6919-112">Spécifiez le numéro de port pour **Port de réplication de configuration interne (HTTPS)**.</span><span class="sxs-lookup"><span data-stu-id="e6919-112">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="e6919-113">Paramètres de sélection du tronçon suivant</span><span class="sxs-lookup"><span data-stu-id="e6919-113">Next hop selection settings</span></span>

<span data-ttu-id="e6919-114">Pour définir ou modifier le **pool** du saut suivant que les serveurs Edge utiliseront pour communiquer avec l’infrastructure interne, sélectionnez un directeur, un pool directeur, un serveur frontal ou un pool de serveurs frontux dans la zone de liste liste.</span><span class="sxs-lookup"><span data-stu-id="e6919-114">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="e6919-115">Seuls les directeurs ou les fronts qui ont été configurés dans le Générateur de topologies s’affichent pour la sélection.</span><span class="sxs-lookup"><span data-stu-id="e6919-115">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="e6919-116">Configuration du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="e6919-116">Edge Server configuration</span></span>

<span data-ttu-id="e6919-117">Pour modifier ou spécifier des paramètres pour les **Paramètres externes** des serveurs Edge, vous devez déterminer si vous allez utiliser des adresses IP séparées pour l’accès SIP, la conférence web et le service audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="e6919-117">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="e6919-p103">Si vous envisagez d’utiliser des adresses IP distinctes à chaque fois, activez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Un enregistrement DNS A (hôte) doit avoir été créé pour chaque service.</span><span class="sxs-lookup"><span data-stu-id="e6919-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="e6919-p104">Pour chaque service externe, vous spécifiez un nom de domaine complet et un port associé. Par exemple, l’**Accès SIP** utilise sip.contoso.com avec un port associé de 5061.</span><span class="sxs-lookup"><span data-stu-id="e6919-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6919-122">Si vous sélectionnez des noms de domaine complets distincts pour chaque service côté externe, chacun de ces services devra avoir une valeur de port unique associée.</span><span class="sxs-lookup"><span data-stu-id="e6919-122">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="e6919-123">Par défaut, le SIP est sur le port 5061/TLS, le service Edge de conférence web est sur le port 444/TLS et le serveur de conférence A/V sur le port 443/TLS.</span><span class="sxs-lookup"><span data-stu-id="e6919-123">By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS.</span></span> <span data-ttu-id="e6919-124">Si vous apportez des modifications à l’un de ces paramètres, y compris l’utilisation d’un nom de domaine complet et d’adresses IP ou de ports distincts, vous devez mettre à jour tous les autres services qui s’appuient sur les valeurs initialement configurées.</span><span class="sxs-lookup"><span data-stu-id="e6919-124">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="e6919-p106">Si vous déterminez que votre organisation utilisera un nom de domaine complet et une adresse IP uniques pour les services côté externe, désactivez la case à cocher **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo**. Vous pouvez ensuite modifier les valeurs du nom de domaine complet du pool et du port **Accès SIP**, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e6919-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6919-127">Si vous apportez des modifications à l’un de ces paramètres, y compris l’utilisation d’un nom de domaine complet et d’adresses IP ou de ports distincts, vous devez mettre à jour tous les autres services qui s’appuient sur les valeurs initialement configurées.</span><span class="sxs-lookup"><span data-stu-id="e6919-127">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6919-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6919-128">See also</span></span>

<span data-ttu-id="e6919-129">Pour plus d’informations sur la définition et la configuration des paramètres des services Edge, voir [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6919-129">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


