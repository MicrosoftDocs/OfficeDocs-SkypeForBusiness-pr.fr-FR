---
title: 'Lync Server 2013 : préparation de votre environnement pour VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1797dfb3388b4f443b505eb0a82c75f887e1759c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a><span data-ttu-id="51bc7-102">Préparation de votre environnement Lync Server 2013 pour VDI</span><span class="sxs-lookup"><span data-stu-id="51bc7-102">Preparing your Lync Server 2013 environment for VDI</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51bc7-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="51bc7-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="51bc7-104">Pour préparer l’environnement pour le plug-in Lync VDI, l’administrateur doit effectuer les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="51bc7-104">To prepare the environment for the Lync VDI plug-in, the administrator must perform the following steps.</span></span>

1.  <span data-ttu-id="51bc7-105">Dans Lync Server 2013, vérifiez que EnableMediaRedirection est défini sur TRUE pour tous les utilisateurs VDI.</span><span class="sxs-lookup"><span data-stu-id="51bc7-105">In Lync Server 2013, ensure that EnableMediaRedirection is set to TRUE for all VDI users.</span></span> <span data-ttu-id="51bc7-106">Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) et la cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .</span><span class="sxs-lookup"><span data-stu-id="51bc7-106">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

2.  <span data-ttu-id="51bc7-107">Sur l’ordinateur du centre de données, installez le client Lync 2013 sur toutes les machines virtuelles.</span><span class="sxs-lookup"><span data-stu-id="51bc7-107">On the data center computer, install the Lync 2013 client on all virtual machines.</span></span>

3.  <span data-ttu-id="51bc7-108">Sur les ordinateurs locaux, installez le plug-in Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="51bc7-108">On the local computers, install the Lync VDI plug-in.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

