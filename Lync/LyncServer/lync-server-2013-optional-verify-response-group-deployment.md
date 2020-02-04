---
title: 'Lync Server 2013 : (facultatif) vérifier le déploiement de Response Group'
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
ms.openlocfilehash: 065a48aedf1b093358193d0c8afbd12b44653025
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="02a3a-102">Facultatif Vérifier le déploiement de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a3a-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02a3a-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="02a3a-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="02a3a-104">Après avoir configuré Response Group, vous devez vérifier la configuration pour vous assurer que les groupes de réponse fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="02a3a-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="02a3a-105">Au minimum, vérifiez les scénarios ci-dessous en vous basant sur les types d’utilisateur indiqués ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="02a3a-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="02a3a-106">**Utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="02a3a-106">**Users**</span></span>

  - <span data-ttu-id="02a3a-107">Utilisateur hébergé sur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a3a-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="02a3a-108">Utilisateur externe utilisant le réseau téléphonique commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="02a3a-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="02a3a-109">Agent hébergé sur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a3a-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="02a3a-110">**Scénarios**</span><span class="sxs-lookup"><span data-stu-id="02a3a-110">**Scenarios**</span></span>

  - <span data-ttu-id="02a3a-111">L’utilisateur de Lync Server 2013 appelle le groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="02a3a-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="02a3a-112">L’utilisateur externe appelle le service Response Group.</span><span class="sxs-lookup"><span data-stu-id="02a3a-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="02a3a-113">Un utilisateur appelle le service Response Group pendant que l’agent traite un autre appel. L’appel de l’utilisateur est alors transmis à la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="02a3a-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

