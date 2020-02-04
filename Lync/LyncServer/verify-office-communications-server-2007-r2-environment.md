---
title: Vérification de l’environnement Office Communications Server 2007 R2
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
ms.openlocfilehash: 0fb67868c9f7eddfe2b11b4238c5fdd1bd14d8e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="4d58d-102">Vérification de l’environnement Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4d58d-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d58d-103">_**Dernière modification de la rubrique :** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="4d58d-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="4d58d-104">Avant de déployer Lync Server 2013 dans un état de coexistence avec Office Communications Server 2007 R2, vous devez vérifier que les services Office Communications Server 2007 R2 sont configurés et démarrés.</span><span class="sxs-lookup"><span data-stu-id="4d58d-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="4d58d-105">**Vérifier que le pool est démarré à l’aide de l’outil d’administration Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="4d58d-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="4d58d-106">Ouvrez l’outil d’administration d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4d58d-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="4d58d-107">Développez le nœud de la **forêt** , développez le nœud **Standard Edition Servers** ou **pools d’entreprise** , puis développez le nom du pool ou du serveur.</span><span class="sxs-lookup"><span data-stu-id="4d58d-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="4d58d-108">Vérifiez que les services s’exécutent sur le serveur Standard Edition Server ou le pool d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4d58d-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="4d58d-109">![Console d’administration Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Console d’administration Office Communications Server 2007 R2")</span><span class="sxs-lookup"><span data-stu-id="4d58d-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="4d58d-110">**Examiner les utilisateurs configurés pour Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="4d58d-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="4d58d-111">Ouvrez l’outil d’administration d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4d58d-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="4d58d-112">Développez le nœud de la **forêt** , développez le nœud **Standard Edition Servers** ou **pools d’entreprise** , puis développez le nom du pool ou du serveur.</span><span class="sxs-lookup"><span data-stu-id="4d58d-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="4d58d-113">Cliquez sur **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="4d58d-113">Click **Users**.</span></span>

4.  <span data-ttu-id="4d58d-114">Vérifiez la liste des utilisateurs d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4d58d-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="4d58d-115">![Listing FO Users dans l’outil d’administration OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Listing FO Users dans l’outil d’administration OCS")</span><span class="sxs-lookup"><span data-stu-id="4d58d-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="4d58d-116">**Vérification de la configuration de partenaire fédéré hérité de XMPP**</span><span class="sxs-lookup"><span data-stu-id="4d58d-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="4d58d-117">À partir du serveur XMPP hérité, accédez à l’applet\\services des outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="4d58d-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="4d58d-118">Vérifiez que le service de passerelle XMPP d’Office Communications Server est démarré.</span><span class="sxs-lookup"><span data-stu-id="4d58d-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="4d58d-119">![Service de passerelle Office Communications Server XMPP](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Service de passerelle Office Communications Server XMPP")</span><span class="sxs-lookup"><span data-stu-id="4d58d-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

