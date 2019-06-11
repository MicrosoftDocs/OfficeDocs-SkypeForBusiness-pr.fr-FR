---
title: 'Lync Server 2013: configuration de la prise en charge de la Fédération pour un client Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e3b1e7a325a078d4769116697f957815f02487
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="74d99-102">Configuration de la prise en charge de la Fédération pour un client Lync Online dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74d99-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74d99-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="74d99-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="74d99-104">Vous pouvez fournir des services de communication aux utilisateurs de votre organisation de l’une des façons suivantes:</span><span class="sxs-lookup"><span data-stu-id="74d99-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="74d99-105">Déploiement de Lync Server 2013 au sein de votre organisation (connu sous le nom de *services locaux*) et configuration de comptes d’utilisateur Lync 2013 au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="74d99-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="74d99-106">Configurer un compte client Microsoft Lync Online 2010 auprès d’un fournisseur d’hébergement et configurer des comptes d’utilisateurs avec le fournisseur d’hébergement (appelé *services en ligne*).</span><span class="sxs-lookup"><span data-stu-id="74d99-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="74d99-107">Si vous déployez Lync 2013 au sein de votre organisation, vous pouvez fédérer avec les domaines d’un ou de plusieurs clients Microsoft Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="74d99-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="74d99-108">Pour permettre la Fédération entre les utilisateurs de votre déploiement local Lync 2013 et des utilisateurs d’un client 2010 Online, vous devez configurer la prise en charge du domaine et des utilisateurs du client Lync Online.</span><span class="sxs-lookup"><span data-stu-id="74d99-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74d99-109">Cette documentation décrit uniquement les procédures de configuration de votre organisation pour la prise en charge de la Fédération avec un client 2010 Lync Online.</span><span class="sxs-lookup"><span data-stu-id="74d99-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="74d99-110">Cette documentation ne décrit pas les procédures de configuration du client 2010 Lync Online pour la prise en charge de la Fédération.</span><span class="sxs-lookup"><span data-stu-id="74d99-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="74d99-111">Pour plus d’informations sur Lync Online Services, consultez Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>Online à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="74d99-111">For details about Lync Online services, see Lync Online at <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="74d99-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="74d99-112">In This Section</span></span>

  - [<span data-ttu-id="74d99-113">Conditions préalables à la Fédération avec un client Lync Online dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74d99-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="74d99-114">Configurer la prise en charge de la Fédération pour un domaine Lync Online dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74d99-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="74d99-115">Configurer l’accès utilisateur pour la Fédération avec un client Lync Online dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74d99-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="74d99-116">Vérifier les communications avec un client Lync Online dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74d99-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

