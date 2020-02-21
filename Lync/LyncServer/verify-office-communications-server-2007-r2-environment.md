---
title: Vérifier l’environnement Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 885b1b08ef2d02c6a3cb3a77b83ca832e70281a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="2f318-102">Vérifier l’environnement Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2f318-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f318-103">_**Dernière modification de la rubrique :** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="2f318-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="2f318-104">Avant de déployer Lync Server 2013 dans un état de coexistence avec Office Communications Server 2007 R2, vous devez vérifier que les services Office Communications Server 2007 R2 sont configurés et démarrés.</span><span class="sxs-lookup"><span data-stu-id="2f318-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="2f318-105">**Vérifier que le pool est démarré à l’aide de l’outil d’administration Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="2f318-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="2f318-106">Ouvrez l’outil d’administration Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2f318-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="2f318-107">Développez le nœud **Forêt**, développez le nœud **Serveurs Standard Edition Servers** ou **pools d’entreprise**, puis développez le nom du pool ou du serveur.</span><span class="sxs-lookup"><span data-stu-id="2f318-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="2f318-108">Vérifiez que les services sont exécutés sur le serveur Standard Edition ou le pool d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="2f318-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="2f318-109">![Office Communications Server 2007 R2, console d’administration](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2, console d’administration")</span><span class="sxs-lookup"><span data-stu-id="2f318-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="2f318-110">**Passez en revue les utilisateurs configurés pour le serveur Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="2f318-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="2f318-111">Ouvrez l’outil d’administration Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2f318-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="2f318-112">Développez le nœud **Forêt**, développez le nœud **serveur Standard Edition Servers** ou **pools d’entreprise**, puis développez le nom du pool ou du serveur.</span><span class="sxs-lookup"><span data-stu-id="2f318-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="2f318-113">Cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="2f318-113">Click **Users**.</span></span>

4.  <span data-ttu-id="2f318-114">Vérifiez la liste des utilisateurs d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2f318-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="2f318-115">![Répertorier les utilisateurs dans l’outil d’administration OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Répertorier les utilisateurs dans l’outil d’administration OCS")</span><span class="sxs-lookup"><span data-stu-id="2f318-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="2f318-116">**Vérifiez la configuration de partenaire fédéré XMPP héritée**</span><span class="sxs-lookup"><span data-stu-id="2f318-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="2f318-117">À partir du serveur XMPP hérité, accédez à l’application\\outils d’administration Services.</span><span class="sxs-lookup"><span data-stu-id="2f318-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="2f318-118">Vérifiez que le service de passerelle XMPP Office Communications Server est démarré.</span><span class="sxs-lookup"><span data-stu-id="2f318-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="2f318-119">![Service de passerelle XMPP Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Service de passerelle XMPP Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="2f318-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

