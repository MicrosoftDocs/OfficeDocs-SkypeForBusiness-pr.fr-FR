---
title: Configurer les scénarios Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e706edf9d66e3a1e9ac76eeac32ab882365e5ab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="5a717-102">Configurer les scénarios Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a717-102">Configure Lync Server 2013 Scenarios</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a717-103">_**Dernière modification de la rubrique :** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="5a717-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="5a717-104">Pour exécuter l’outil de contrainte et performances de Lync Server 2013 (LyncPerfTool), la topologie Lync Server 2013 doit d’abord être configurée pour les scénarios qui seront exécutés.</span><span class="sxs-lookup"><span data-stu-id="5a717-104">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="5a717-105">Si Lync Server 2013 n’est pas configuré ou qu’il est configuré de manière incorrecte, la simulation de charge échoue dans la plupart des cas.</span><span class="sxs-lookup"><span data-stu-id="5a717-105">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="5a717-106">Avec l’outil de contrainte et de performances de Lync Server 2013, nous avons fourni un exemple de scripts Lync Server Management Shell et de fichiers de ressources de base qui peuvent être utilisés comme point de départ pour la configuration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a717-106">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="5a717-107">Cette rubrique décrit les exemples Windows PowerShell fournis.</span><span class="sxs-lookup"><span data-stu-id="5a717-107">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="5a717-108">Notez qu’il ne s’agit pas de l’objectif de cette rubrique, qui explique comment configurer Lync Server 2013 en général.</span><span class="sxs-lookup"><span data-stu-id="5a717-108">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="5a717-109">Pour plus d’informations sur l’utilisation de Windows PowerShell dans Lync Server 2013, reportez-vous <https://technet.microsoft.com/library/gg398474.aspx>à la documentation Lync Server Management Shell à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="5a717-109">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="5a717-110">À propos de l’exécution de scripts Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="5a717-110">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="5a717-111">Nous avons fourni des exemples de scripts Lync Server Management Shell pouvant être utilisés en préparation à l’exécution de la simulation de charge.</span><span class="sxs-lookup"><span data-stu-id="5a717-111">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="5a717-112">Étant donné que les scripts sont destinés à la simulation de charge, ils sont simples et permissants et, par conséquent, peuvent ne pas être appropriés pour la production.</span><span class="sxs-lookup"><span data-stu-id="5a717-112">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="5a717-113">Tous les scripts sont des exemples et doivent être examinés, et, dans certains cas, modifiés pour refléter votre topologie.</span><span class="sxs-lookup"><span data-stu-id="5a717-113">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="5a717-114">Au minimum, nous prévoyons que le scénario de service Response Group (RGS) doit être modifié pour spécifier les agents affectés aux groupes d’agents.</span><span class="sxs-lookup"><span data-stu-id="5a717-114">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="5a717-115">Toutefois, vous avez la possibilité de ne pas simuler cette charge.</span><span class="sxs-lookup"><span data-stu-id="5a717-115">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5a717-116">Veillez à examiner et à comprendre les exemples fournis.</span><span class="sxs-lookup"><span data-stu-id="5a717-116">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="5a717-117">Les scripts remplacent tous les paramètres existants dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="5a717-117">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5a717-118">Pour plus d’informations sur l’utilisation de Windows PowerShell et de Lync Server Management Shell, voir le blog Lync Server <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>2013 Windows PowerShell à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="5a717-118">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="5a717-119">Monikers de version du client outil de stress et de performance</span><span class="sxs-lookup"><span data-stu-id="5a717-119">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="5a717-120">Vous devrez peut-être configurer la stratégie de vérification de la version du client si vous avez modifié les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="5a717-120">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="5a717-121">Pour plus d’informations, voir « Configuration des versions de clients <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>prises en charge » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="5a717-121">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="5a717-122">L’outil de contrainte et de performances de Lync Server 2013 utilise par défaut les versions suivantes de l’agent utilisateur lors de la communication avec Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="5a717-122">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="5a717-123">LSPT/15.0.0.0 (outil de contrainte et de performances de Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="5a717-123">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="5a717-124">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="5a717-124">OCPHONE/.0.522</span></span>

<span data-ttu-id="5a717-125">Celles-ci sont destinées au client Mobility (UCWA) dans LyncPerfTool :</span><span class="sxs-lookup"><span data-stu-id="5a717-125">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="5a717-126">Outil perf Ucwa/conférence Web</span><span class="sxs-lookup"><span data-stu-id="5a717-126">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="5a717-127">Outil de performances Ucwa/mobile</span><span class="sxs-lookup"><span data-stu-id="5a717-127">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

