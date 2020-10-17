---
title: Activer Exchange 2013 Outlook Web App et l’intégration de la messagerie instantanée
description: Activez Exchange 2013 Outlook Web App et l’intégration de la messagerie instantanée.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7fd6e8600f255d6ac4dde52487776cdb5fe1a51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551120"
---
# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="72b1d-103">Activer Exchange 2013 Outlook Web App et l’intégration de la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="72b1d-103">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72b1d-104">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="72b1d-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="72b1d-105">Pour activer l’intégration d’Exchange 2013 Outlook Web Access (OWA) et de la messagerie instantanée avec Lync Server 2013, vous devez ajouter le serveur de serveur d’accès au client (CAS) Exchange 2013 à la topologie Lync Server 2013 en tant que serveur d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="72b1d-105">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="72b1d-106">Pour créer un pool d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="72b1d-106">To create a trusted application pool</span></span>

1.  <span data-ttu-id="72b1d-107">Démarrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72b1d-107">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="72b1d-108">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="72b1d-108">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="72b1d-109">Celle-ci renvoie la valeur siteID correspondant à la valeur siteName dans laquelle vous créez le pool.</span><span class="sxs-lookup"><span data-stu-id="72b1d-109">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="72b1d-110">Pour plus d’informations, reportez-vous à [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) dans la documentation de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72b1d-110">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="72b1d-111">Exécutez la l’applet commande suivant :</span><span class="sxs-lookup"><span data-stu-id="72b1d-111">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="72b1d-112">Pour plus d’informations, reportez-vous à la rubrique [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) dans la documentation de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72b1d-112">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="72b1d-113">Le nom de domaine complet du serveur Exchange Server doit être configuré en tant que nom d’objet du certificat Exchange OWA ou en tant qu’autre nom de l’objet.</span><span class="sxs-lookup"><span data-stu-id="72b1d-113">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="72b1d-114">Dans Exchange OWA, assurez-vous que le nom de domaine complet du pool est également approuvé.</span><span class="sxs-lookup"><span data-stu-id="72b1d-114">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="72b1d-115">Si votre serveur CAS n’est <EM>pas</EM> colocalisé sur le même serveur qui exécute la messagerie unifiée Exchange 2013, ignorez les étapes restantes de cette procédure et exécutez la procédure « créer une application approuvée pour le serveur CAS Exchange 2013 » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="72b1d-115">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="72b1d-116">Si votre serveur CAS est colocalisé sur le même serveur qui exécute la messagerie unifiée Exchange 2013, effectuez les étapes de cette procédure et n’effectuez pas la procédure « créer une application approuvée pour le serveur CAS Exchange 2013 » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="72b1d-116">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="72b1d-117">Exécutez **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="72b1d-117">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="72b1d-118">Ouvrez le Générateur de topologie et téléchargez la topologie existante.</span><span class="sxs-lookup"><span data-stu-id="72b1d-118">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="72b1d-119">Dans le volet gauche, développez l’arborescence jusqu’à ce que vous atteigniez **Serveurs d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="72b1d-119">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="72b1d-120">Développez le nœud **Serveurs d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="72b1d-120">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="72b1d-121">Vous devez maintenant voir le serveur CAS Exchange 2013 mentionné en tant que serveur d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="72b1d-121">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="72b1d-122">Pour créer une application approuvée pour le serveur CAS Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="72b1d-122">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="72b1d-123">Démarrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72b1d-123">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="72b1d-124">Si votre serveur CAS n’est *pas* colocalisé sur le même serveur qui exécute la messagerie unifiée Exchange 2013, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="72b1d-124">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="72b1d-125">Pour plus d’informations, reportez-vous à la rubrique [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) dans la documentation de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72b1d-125">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="72b1d-126">Exécutez **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="72b1d-126">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="72b1d-127">Dans le Générateur de topologie, dans le volet gauche, développez l’arborescence jusqu’à ce que vous atteigniez **Serveurs d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="72b1d-127">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="72b1d-128">Développez le nœud **Serveurs d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="72b1d-128">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="72b1d-129">Vous devez maintenant voir le serveur CAS Exchange 2013 mentionné en tant que serveur d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="72b1d-129">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

