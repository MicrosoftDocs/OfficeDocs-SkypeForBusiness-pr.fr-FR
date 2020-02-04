---
title: 'Lync Server 2013 : Technologies de virtualisation prises en charge et limites connues'
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
ms.openlocfilehash: cf513e9dee4e6a27708c8882519099c825f903f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="75661-102">Technologies de virtualisation prises en charge et limites connues dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75661-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75661-103">_**Dernière modification de la rubrique :** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="75661-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="75661-104">Le plug-in Lync VDI autorise les appels audio et vidéo pour les technologies de virtualisation prises en charge.</span><span class="sxs-lookup"><span data-stu-id="75661-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="75661-105">Cette opération étend les fonctionnalités de Microsoft Lync Server 2010 dans le livre blanc [sur la virtualisation du client dans Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) .</span><span class="sxs-lookup"><span data-stu-id="75661-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="75661-106">Conformément aux réglementations téléphoniques standard, la prise en charge pour E911 est également incluse.</span><span class="sxs-lookup"><span data-stu-id="75661-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="75661-107">Les sections suivantes décrivent les technologies de virtualisation prises en charge par le plug-in Lync VDI et les limitations de fonctionnalités connues.</span><span class="sxs-lookup"><span data-stu-id="75661-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="75661-108">Prise en charge des technologies de virtualisation</span><span class="sxs-lookup"><span data-stu-id="75661-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="75661-109">Le plug-in Lync VDI prend en charge l’accès complet au bureau virtuel dans le scénario de bureau virtuel personnel, mais pas dans le scénario de session Bureau à distance.</span><span class="sxs-lookup"><span data-stu-id="75661-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="75661-110">Ces scénarios peuvent être décrits comme suit :</span><span class="sxs-lookup"><span data-stu-id="75661-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="75661-111">**Pris en charge : les bureaux virtuels personnalisés ou l’infrastructure de bureau virtuelle.**    Dans ce scénario, chaque utilisateur se connecte à un bureau virtuel personnalisable et est en mesure d’enregistrer des fichiers sur le bureau qui persistent dans toutes les sessions.</span><span class="sxs-lookup"><span data-stu-id="75661-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="75661-112">Les services Bureau à distance de Microsoft, le mode d’affichage horizontal de VMware et Citrix XenDesktop sont des implémentations qui ont été testées pour Lync.</span><span class="sxs-lookup"><span data-stu-id="75661-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="75661-113">Pour plus d’informations sur les environnements VDI spécifiques aux fournisseurs et sur le matériel client testés par Microsoft, voir [infrastructure Qualified pour Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="75661-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="75661-114">**Non pris en charge : sessions de bureau à distance.**    Dans ce scénario, chaque utilisateur se connecte à une session de bureau virtuel générique qui ne peut pas être personnalisée.</span><span class="sxs-lookup"><span data-stu-id="75661-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="75661-115">Les exemples d’implémentations incluent les sessions Bureau à distance de Microsoft (RDSH) et Citrix XenApp combiné à Citrix Receiver.</span><span class="sxs-lookup"><span data-stu-id="75661-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="75661-116">Le plug-in Lync VDI ne prend pas en charge les autres technologies de virtualisation, telles que la virtualisation de l’application, qui permet d’utiliser une application sans avoir besoin d’installer entièrement l’application en local.</span><span class="sxs-lookup"><span data-stu-id="75661-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="75661-117">Les exemples d’implémentations incluent Citrix XenApp et Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="75661-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="75661-118">Les modes de diffusion en continu d’application, de mise à distance d’application et de virtualisation mixte (par exemple, mise à distance d’application dans une mise à distance de bureau complet) ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="75661-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="75661-119">Pour autoriser l’extensibilité, le plug-in Lync VDI a été conçu pour utiliser des API indépendantes de la plateforme appelées canaux virtuels dynamiques (DVCs).</span><span class="sxs-lookup"><span data-stu-id="75661-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="75661-120">Dans le cas de scénarios non pris en charge de manière explicite par Lync, voir instructions d’assistance du fournisseur de solutions VDI.</span><span class="sxs-lookup"><span data-stu-id="75661-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="75661-121">Limitations de fonctionnalité connues</span><span class="sxs-lookup"><span data-stu-id="75661-121">Known Feature Limitations</span></span>

<span data-ttu-id="75661-122">Vous trouverez ci-après des limitations connues lorsque vous utilisez Lync 2013 dans un environnement VDI :</span><span class="sxs-lookup"><span data-stu-id="75661-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="75661-123">La prise en charge des fonctionnalités de délégation d’appel et d’anonymisation de l’agent de Response Group est limitée.</span><span class="sxs-lookup"><span data-stu-id="75661-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="75661-124">Il n’existe pas de prise en charge pour les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="75661-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="75661-125">pages de réglage des périphériques audio et vidéo intégrés ;</span><span class="sxs-lookup"><span data-stu-id="75661-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="75661-126">vidéo à vues multiples ;</span><span class="sxs-lookup"><span data-stu-id="75661-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="75661-127">enregistrement des conversations ;</span><span class="sxs-lookup"><span data-stu-id="75661-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="75661-128">Services Bureau à distance.</span><span class="sxs-lookup"><span data-stu-id="75661-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="75661-129">La participation anonyme aux réunions (c’est-à-dire, la participation à des réunions Lync hébergées par une organisation non fédérée avec votre organisation).</span><span class="sxs-lookup"><span data-stu-id="75661-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="75661-130">Utiliser le plug-in Lync VDI avec un appareil Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="75661-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="75661-131">continuité des appels en cas de panne du réseau ;</span><span class="sxs-lookup"><span data-stu-id="75661-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="75661-132">sonneries personnalisées et fonctionnalités d’attente musicale.</span><span class="sxs-lookup"><span data-stu-id="75661-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="75661-133">Le plug-in Lync VDI n’est pas pris en charge dans un environnement Office 365.</span><span class="sxs-lookup"><span data-stu-id="75661-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

