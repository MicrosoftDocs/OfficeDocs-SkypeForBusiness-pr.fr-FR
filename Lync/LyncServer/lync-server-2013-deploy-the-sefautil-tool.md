---
title: 'Lync Server 2013 : déploiement de l’outil SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ff23a228710ecc934e2984f27c63351ccf6d32
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="058a0-102">Déployer l’outil SEFAUtil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="058a0-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="058a0-103">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="058a0-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="058a0-104">Pour déployer et gérer la prise d’appel de groupe, vous devez utiliser l’outil Kit de ressources de SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="058a0-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="058a0-105">L’outil fait partie des outils du kit de ressources Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="058a0-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="058a0-106">Avant de pouvoir installer SEFAUtil, vous devez disposer d’un pool d’applications approuvées dans votre topologie, spécifier SEFAUtil comme application approuvée et activer la topologie.</span><span class="sxs-lookup"><span data-stu-id="058a0-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="058a0-107">Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK doit être installé sur tout ordinateur sur lequel vous envisagez d’exécuter l’outil SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="058a0-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="058a0-108">Vous pouvez exécuter l’SEFAUtil dans n’importe quel pool frontal de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="058a0-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="058a0-109">Pour plus d’informations sur l’exécution d’SEFAUtil, consultez l’article du blog TechNet « How to get SEFAutil Running ? »</span><span class="sxs-lookup"><span data-stu-id="058a0-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="058a0-110">à <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>l’adresse.</span><span class="sxs-lookup"><span data-stu-id="058a0-110">at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="058a0-111">Pour déployer SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="058a0-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="058a0-112">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="058a0-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="058a0-113">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="058a0-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="058a0-114">L’outil SEFAUtil peut être exécuté uniquement sur un ordinateur qui fait partie d’un pool d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="058a0-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="058a0-115">Si nécessaire, définissez un pool d’applications approuvées pour le pool frontal dans lequel vous prévoyez d’exécuter SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="058a0-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="058a0-116">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="058a0-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="058a0-117">Définissez l’outil SEFAUtil en tant qu’application approuvée.</span><span class="sxs-lookup"><span data-stu-id="058a0-117">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="058a0-118">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="058a0-118">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="058a0-119">Vous pouvez utiliser un autre port si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="058a0-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="058a0-120">Activez la topologie avec vos modifications.</span><span class="sxs-lookup"><span data-stu-id="058a0-120">Enable the topology with your changes.</span></span> <span data-ttu-id="058a0-121">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="058a0-121">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="058a0-122">Installez les outils du kit de ressources Lync Server 2013 sur un serveur frontal qui se trouve dans le pool d’applications approuvées que vous avez créé à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="058a0-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="058a0-123">Vérifiez que l’outil SEFAUtil s’exécute correctement, comme suit :</span><span class="sxs-lookup"><span data-stu-id="058a0-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="058a0-124">Exécutez l’outil à partir de l’invite de commandes Windows avec les privilèges d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="058a0-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="058a0-125">L’outil se trouve à l’emplacement \Program Files\Microsoft Lync Server 2013 \ reskit.</span><span class="sxs-lookup"><span data-stu-id="058a0-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="058a0-126">Afficher les paramètres de transfert d’appel d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="058a0-126">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="058a0-127">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="058a0-127">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="058a0-128">Les paramètres de transfert d’appel de l’utilisateur seront affichés.</span><span class="sxs-lookup"><span data-stu-id="058a0-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

