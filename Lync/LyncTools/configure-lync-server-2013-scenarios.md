---
title: Configurer des scénarios Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93ad7a3be8b69c956b1cca0f1d1554a5fa288f17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="bf252-102">Configurer des scénarios Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf252-102">Configure Lync Server 2013 Scenarios</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf252-103">_**Dernière modification de la rubrique:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="bf252-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="bf252-104">Pour exécuter l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool), la topologie Lync Server 2013 doit d’abord être configurée pour les scénarios qui seront exécutés.</span><span class="sxs-lookup"><span data-stu-id="bf252-104">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="bf252-105">Si Lync Server 2013 n’est pas configuré ou a été configuré de manière incorrecte, la simulation de charge ne fonctionnera pas dans la plupart des cas.</span><span class="sxs-lookup"><span data-stu-id="bf252-105">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="bf252-106">Grâce à l’outil de stress et de performances de Lync Server 2013, nous avons fourni des exemples de fichiers de ressources de base et de scripts Lync Server Management Shell qui peuvent servir de point de départ pour la configuration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf252-106">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="bf252-107">Cette rubrique décrit les exemples Windows PowerShell proposés.</span><span class="sxs-lookup"><span data-stu-id="bf252-107">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="bf252-108">Notez qu’il ne s’agit pas de la rubrique permettant de décrire la configuration de Lync Server 2013 en général.</span><span class="sxs-lookup"><span data-stu-id="bf252-108">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="bf252-109">Pour plus d’informations sur l’utilisation de Windows PowerShell dans Lync Server 2013, consultez la documentation Lync Server <https://technet.microsoft.com/en-us/library/gg398474.aspx>Management Shell à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="bf252-109">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/en-us/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="bf252-110">À propos de l’exécution de scripts Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="bf252-110">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="bf252-111">Nous avons fourni des exemples de scripts Lync Server Management Shell qui peuvent être utilisés en préparation pour exécuter la simulation de charge.</span><span class="sxs-lookup"><span data-stu-id="bf252-111">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="bf252-112">Étant donné que les scripts sont destinés à une simulation de charge, ils sont simples et permissif, et par conséquent, peuvent ne pas être appropriés pour la production.</span><span class="sxs-lookup"><span data-stu-id="bf252-112">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="bf252-113">Tous les scripts sont des exemples qui doivent être examinés et, dans certains cas, modifiés pour refléter votre topologie.</span><span class="sxs-lookup"><span data-stu-id="bf252-113">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="bf252-114">Au minimum, nous pensons que le scénario de service de Response Group (RGS) doit être modifié pour spécifier les agents affectés aux groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="bf252-114">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="bf252-115">Toutefois, vous avez la possibilité de ne pas simuler ce chargement.</span><span class="sxs-lookup"><span data-stu-id="bf252-115">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="bf252-116">Prenez soin de revoir et de comprendre les exemples fournis.</span><span class="sxs-lookup"><span data-stu-id="bf252-116">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="bf252-117">Les scripts écrasent les paramètres existants dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="bf252-117">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bf252-118">Pour plus d’informations sur l’utilisation de Windows PowerShell et de Lync Server Management Shell, voir le blog Lync Server <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>2013 Windows PowerShell à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="bf252-118">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="bf252-119">Monikers de la version du client d’outils de stress et de performance</span><span class="sxs-lookup"><span data-stu-id="bf252-119">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="bf252-120">Il est possible que vous deviez configurer la stratégie de vérification de la version du client si vous avez modifié les paramètres des valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="bf252-120">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="bf252-121">Pour plus d’informations, consultez la section «Configuration des versions <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>clientes prises en charge» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="bf252-121">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="bf252-122">L’outil contraintes et performances de Lync Server 2013 utilise les versions d’agent utilisateur suivantes par défaut lors de la communication avec Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="bf252-122">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="bf252-123">LSPT/15.0.0.0 (outil de stress et de performance de Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="bf252-123">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="bf252-124">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="bf252-124">OCPHONE/.0.522</span></span>

<span data-ttu-id="bf252-125">Celles-ci sont destinées au client Mobility (UCWA) dans LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="bf252-125">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="bf252-126">Outil de performance/conférence Web Ucwa</span><span class="sxs-lookup"><span data-stu-id="bf252-126">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="bf252-127">Outil perf Ucwa/mobile</span><span class="sxs-lookup"><span data-stu-id="bf252-127">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

