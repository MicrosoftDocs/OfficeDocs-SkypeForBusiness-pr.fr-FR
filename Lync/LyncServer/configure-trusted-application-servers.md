---
title: Configuration des serveurs d’applications approuvées
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cab126429fc5ec77a2308fdc1e1f8965fdfccb5b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="3db50-102">Configuration des serveurs d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="3db50-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3db50-103">_**Dernière modification de la rubrique:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="3db50-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="3db50-104">Dans un environnement mixte, si vous créez un nouveau serveur d’applications de confiance, vous devez définir le pool de sauts suivant comme pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3db50-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="3db50-105">Dans un environnement mixte, le pool Lync Server 2010 hérité et le pool 2013 du serveur Lync apparaissent dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3db50-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="3db50-106">La sélection du pool hérité n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="3db50-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="3db50-107">**Sélectionner Lync Server 2013 comme tronçon suivant lors de la création d’un serveur d’applications de confiance**</span><span class="sxs-lookup"><span data-stu-id="3db50-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="3db50-108">Ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="3db50-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="3db50-109">Dans le volet de gauche, cliquez avec le bouton droit sur **serveurs d’applications de confiance** , puis cliquez sur **nouveau pool d’applications de confiance**.</span><span class="sxs-lookup"><span data-stu-id="3db50-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="3db50-110">Entrez le **nom de domaine complet (FQDN)** du pool d’applications de confiance et sélectionnez s’il s’agit d’un serveur unique ou d’un serveur multiple.</span><span class="sxs-lookup"><span data-stu-id="3db50-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="3db50-111">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3db50-111">Click **Next**.</span></span>

5.  <span data-ttu-id="3db50-112">Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3db50-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="3db50-113">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="3db50-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="3db50-114">Sélectionnez le nœud supérieur **serveur Lync** et dans le menu **action** , sélectionnez **publier**.</span><span class="sxs-lookup"><span data-stu-id="3db50-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="3db50-115">Vérifiez que le **pool d’applications approuvé** a été créé avec succès et est associé au pool frontal approprié.</span><span class="sxs-lookup"><span data-stu-id="3db50-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

