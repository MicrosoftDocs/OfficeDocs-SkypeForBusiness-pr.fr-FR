---
title: Activer Exchange 2013 Outlook Web App et l’intégration de la messagerie instantanée
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
ms.openlocfilehash: a67dd3c18525d7a39678b5871d087ea79c502fce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="c25de-102">Activer Exchange 2013 Outlook Web App et l’intégration de la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="c25de-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c25de-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c25de-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c25de-104">Pour activer l’intégration d’Exchange 2013 Outlook Web Access (OWA) et de la messagerie instantanée avec Lync Server 2013, vous devez ajouter le serveur de serveur d’accès au client (CAS) Exchange 2013 à la topologie Lync Server 2013 en tant que serveur d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="c25de-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="c25de-105">Pour créer un pool d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="c25de-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="c25de-106">Démarrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c25de-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="c25de-107">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="c25de-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="c25de-108">Celle-ci renvoie la valeur siteID correspondant à la valeur siteName dans laquelle vous créez le pool.</span><span class="sxs-lookup"><span data-stu-id="c25de-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="c25de-109">Pour plus d’informations, reportez-vous à [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) dans la documentation de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c25de-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="c25de-110">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="c25de-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="c25de-111">Pour plus d’informations, reportez-vous à la rubrique [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) dans la documentation de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c25de-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="c25de-112">Le nom de domaine complet du serveur Exchange Server doit être configuré en tant que nom d’objet du certificat Exchange OWA ou en tant qu’autre nom de l’objet.</span><span class="sxs-lookup"><span data-stu-id="c25de-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="c25de-113">Dans Exchange OWA, assurez-vous que le nom de domaine complet du pool est également approuvé.</span><span class="sxs-lookup"><span data-stu-id="c25de-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c25de-114">Si votre serveur CAS n’est <EM>pas</EM> colocalisé sur le même serveur qui exécute la messagerie unifiée Exchange 2013, ignorez les étapes restantes de cette procédure et exécutez la procédure « créer une application approuvée pour le serveur CAS Exchange 2013 » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c25de-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="c25de-115">Si votre serveur CAS est colocalisé sur le même serveur qui exécute la messagerie unifiée Exchange 2013, effectuez les étapes de cette procédure et n’effectuez pas la procédure « créer une application approuvée pour le serveur CAS Exchange 2013 » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c25de-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="c25de-116">Exécutez **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="c25de-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="c25de-117">Ouvrez le Générateur de topologie et téléchargez la topologie existante.</span><span class="sxs-lookup"><span data-stu-id="c25de-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="c25de-118">Dans le volet gauche, développez l’arborescence jusqu’à ce que vous atteigniez **Serveurs d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="c25de-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="c25de-119">Développez le nœud **Serveurs d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="c25de-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="c25de-120">Vous devez maintenant voir le serveur CAS Exchange 2013 mentionné en tant que serveur d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="c25de-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="c25de-121">Pour créer une application approuvée pour le serveur CAS Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="c25de-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="c25de-122">Démarrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c25de-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="c25de-123">Si votre serveur CAS n’est *pas* colocalisé sur le même serveur qui exécute la messagerie unifiée Exchange 2013, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c25de-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="c25de-124">Pour plus d’informations, reportez-vous à la rubrique [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) dans la documentation de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c25de-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="c25de-125">Exécutez **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="c25de-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="c25de-126">Dans le Générateur de topologie, dans le volet gauche, développez l’arborescence jusqu’à ce que vous atteigniez **Serveurs d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="c25de-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="c25de-127">Développez le nœud **Serveurs d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="c25de-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="c25de-128">Vous devez maintenant voir le serveur CAS Exchange 2013 mentionné en tant que serveur d’applications approuvées.</span><span class="sxs-lookup"><span data-stu-id="c25de-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

