---
title: 'Lync Server 2013 : (facultatif) Verify Response Group Deployment'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Response Group deployment
ms:assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687989(v=OCS.15)
ms:contentKeyID: 49733579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00373df840e46e6a0c849f2974b83b858c9fed70
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="0252b-102">Module Vérifier le déploiement de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0252b-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0252b-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="0252b-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="0252b-104">Après avoir configuré Response Group, vous devez vérifier la configuration pour vous assurer que les groupes Response Group fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="0252b-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="0252b-105">Au minimum, vérifiez les scénarios suivants en vous basant sur les types d’utilisateur indiqués ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="0252b-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="0252b-106">**Utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="0252b-106">**Users**</span></span>

  - <span data-ttu-id="0252b-107">Un utilisateur hébergé sur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0252b-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="0252b-108">Utilisateur externe qui utilise le réseau téléphonique commuté (PSTN) public</span><span class="sxs-lookup"><span data-stu-id="0252b-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="0252b-109">Agent hébergé sur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0252b-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="0252b-110">**Scenarios**</span><span class="sxs-lookup"><span data-stu-id="0252b-110">**Scenarios**</span></span>

  - <span data-ttu-id="0252b-111">L’utilisateur de Lync Server 2013 appelle le groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="0252b-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="0252b-112">L’utilisateur externe appelle le service Response Group.</span><span class="sxs-lookup"><span data-stu-id="0252b-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="0252b-113">Un utilisateur appelle le service Response Group alors que l’agent traite un autre appel. L’appel de l’utilisateur est alors transmis à la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="0252b-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

