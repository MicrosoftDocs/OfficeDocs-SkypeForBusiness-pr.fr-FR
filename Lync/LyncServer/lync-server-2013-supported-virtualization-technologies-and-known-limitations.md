---
title: 'Lync Server 2013 : technologies de virtualisation prises en charge et limitations connues'
description: 'Lync Server 2013 : technologies de virtualisation prises en charge et limitations connues.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745fa535462d29342f4c0a58674ee6487db42a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544610"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="f1146-103">Technologies de virtualisation prises en charge et limitations connues dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1146-103">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1146-104">_**Dernière modification de la rubrique :** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="f1146-104">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="f1146-105">Le plug-in Lync VDI autorise les appels audio et vidéo pour les technologies de virtualisation prises en charge.</span><span class="sxs-lookup"><span data-stu-id="f1146-105">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="f1146-106">Cela étend les fonctionnalités décrites pour Microsoft Lync Server 2010 dans le livre blanc sur la [virtualisation des clients dans Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) .</span><span class="sxs-lookup"><span data-stu-id="f1146-106">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="f1146-107">Conformément aux réglementations téléphoniques standard, la prise en charge de E911 est également incluse.</span><span class="sxs-lookup"><span data-stu-id="f1146-107">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="f1146-108">Les sections suivantes décrivent les technologies de virtualisation prises en charge par le plug-in Lync VDI et les limitations de fonctionnalités connues.</span><span class="sxs-lookup"><span data-stu-id="f1146-108">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="f1146-109">Prise en charge des technologies de virtualisation</span><span class="sxs-lookup"><span data-stu-id="f1146-109">Support for Virtualization Technologies</span></span>

<span data-ttu-id="f1146-110">Le plug-in Lync VDI prend en charge l’accès à distance complet au bureau dans le scénario de bureau virtuel personnel, mais pas dans le scénario de session de bureau à distance.</span><span class="sxs-lookup"><span data-stu-id="f1146-110">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="f1146-111">Ces scénarios peuvent être décrits comme suit :</span><span class="sxs-lookup"><span data-stu-id="f1146-111">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="f1146-112">**Pris en charge : bureaux virtuels personnalisés ou VDI (Virtual Desktop Infrastructure).**     Dans ce scénario, chaque utilisateur se connecte à un bureau virtuel personnalisable et peut enregistrer des fichiers sur le bureau qui persistent dans les sessions.</span><span class="sxs-lookup"><span data-stu-id="f1146-112">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="f1146-113">Les services Bureau à distance de Microsoft, l’affichage de l’horizon VMware et Citrix XenDesktop sont des implémentations testées pour une utilisation avec Lync.</span><span class="sxs-lookup"><span data-stu-id="f1146-113">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="f1146-114">Pour plus d’informations sur les environnements VDI et le matériel client spécifiques aux fournisseurs qui ont été testés par Microsoft, voir [infrastructure Qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="f1146-114">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="f1146-115">**Non pris en charge : sessions de bureau à distance.**     Dans ce scénario, chaque utilisateur se connecte à une session de bureau virtuel générique qui ne peut pas être personnalisée.</span><span class="sxs-lookup"><span data-stu-id="f1146-115">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="f1146-116">Les exemples d’implémentation incluent les sessions Bureau à distance de Microsoft et Citrix XenApp combinés avec le récepteur Citrix.</span><span class="sxs-lookup"><span data-stu-id="f1146-116">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="f1146-117">Le plug-in Lync VDI ne prend pas en charge les autres technologies de virtualisation, telles que la virtualisation d’application, qui permet l’utilisation d’une application sans avoir à installer entièrement l’application en local.</span><span class="sxs-lookup"><span data-stu-id="f1146-117">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="f1146-118">Exemples d’implémentations incluent Citrix XenApp et Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="f1146-118">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="f1146-119">La diffusion d’application, l’accès à distance aux applications et les modes de virtualisation mixte (par exemple, application Remoting dans l’accès à distance complet au bureau) ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f1146-119">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="f1146-120">Pour permettre l’extensibilité, le plug-in Lync VDI a été conçu pour utiliser les API indépendantes des plateformes appelées canaux virtuels dynamiques (DVC).</span><span class="sxs-lookup"><span data-stu-id="f1146-120">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="f1146-121">Pour les scénarios qui ne sont pas explicitement pris en charge par Lync, reportez-vous aux instructions de prise en charge du fournisseur de solution VDI.</span><span class="sxs-lookup"><span data-stu-id="f1146-121">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="f1146-122">Limitations des fonctionnalités connues</span><span class="sxs-lookup"><span data-stu-id="f1146-122">Known Feature Limitations</span></span>

<span data-ttu-id="f1146-123">Les limitations suivantes sont connues lorsque vous utilisez Lync 2013 dans un environnement VDI :</span><span class="sxs-lookup"><span data-stu-id="f1146-123">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="f1146-124">La prise en charge des fonctionnalités d’anonymisation de l’agent Response Group et de délégation d’appel est limitée.</span><span class="sxs-lookup"><span data-stu-id="f1146-124">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="f1146-125">Il n’existe pas de prise en charge pour les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="f1146-125">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="f1146-126">pages de réglage des périphériques audio et vidéo intégrés ;</span><span class="sxs-lookup"><span data-stu-id="f1146-126">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="f1146-127">Vidéo en plusieurs vues.</span><span class="sxs-lookup"><span data-stu-id="f1146-127">Multiple-view video.</span></span>
    
      - <span data-ttu-id="f1146-128">enregistrement des conversations ;</span><span class="sxs-lookup"><span data-stu-id="f1146-128">Recording of conversations.</span></span>
    
      - <span data-ttu-id="f1146-129">Services Bureau à distance (RDS).</span><span class="sxs-lookup"><span data-stu-id="f1146-129">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="f1146-130">Participation anonyme à des réunions (c’est-à-dire, rejoindre des réunions Lync hébergées par une organisation qui ne se fédérer pas avec votre organisation).</span><span class="sxs-lookup"><span data-stu-id="f1146-130">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="f1146-131">Utilisation du plug-in Lync VDI avec un appareil Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="f1146-131">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="f1146-132">continuité des appels en cas de panne du réseau ;</span><span class="sxs-lookup"><span data-stu-id="f1146-132">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="f1146-133">Sonneries personnalisées et fonctionnalités d’attente musicale.</span><span class="sxs-lookup"><span data-stu-id="f1146-133">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="f1146-134">Le plug-in Lync VDI n’est pas pris en charge dans un environnement Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="f1146-134">The Lync VDI plug-in is not supported in a Microsoft 365 or Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

