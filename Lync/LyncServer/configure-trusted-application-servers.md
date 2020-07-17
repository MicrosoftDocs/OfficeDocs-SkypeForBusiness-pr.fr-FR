---
title: Configurer les serveurs d’applications approuvées
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb71833e782378f0d959fcbfcf5647235252e594
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="5d12d-102">Configurer les serveurs d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="5d12d-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d12d-103">_**Dernière modification de la rubrique :** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="5d12d-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="5d12d-104">Dans un environnement mixte, si vous créez un nouveau serveur d’applications approuvées, vous devez définir le pool de tronçon suivant comme pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d12d-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="5d12d-105">Dans un environnement mixte, le pool Lync Server 2010 hérité et le pool Lync Server 2013 apparaissent dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="5d12d-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="5d12d-106">La sélection du pool hérité n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="5d12d-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="5d12d-107">**Sélectionnez Lync Server 2013 comme tronçon suivant lors de la création d’un serveur d’applications approuvées**</span><span class="sxs-lookup"><span data-stu-id="5d12d-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="5d12d-108">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="5d12d-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="5d12d-109">Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications approuvées**, puis cliquez sur **Nouveau pool d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="5d12d-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="5d12d-110">Entrez le **Nom de domaine complet du pool** de l’application approuvée et indiquez s’il s’agira d’un serveur unique ou d’un serveur multiple.</span><span class="sxs-lookup"><span data-stu-id="5d12d-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="5d12d-111">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5d12d-111">Click **Next**.</span></span>

5.  <span data-ttu-id="5d12d-112">Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d12d-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="5d12d-113">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="5d12d-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="5d12d-114">Sélectionnez le nœud supérieur **Lync Server** et dans le menu **Action**, sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="5d12d-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="5d12d-115">Le **Pool d’applications approuvées** doit avoir été créé avec succès et être associé au pool frontal correct.</span><span class="sxs-lookup"><span data-stu-id="5d12d-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

