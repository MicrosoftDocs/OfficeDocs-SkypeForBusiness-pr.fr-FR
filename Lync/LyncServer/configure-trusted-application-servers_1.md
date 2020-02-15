---
title: Configurer les serveurs d’applications approuvées
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e74cba866a7353890bb47de745e5e525d43963
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="a4290-102">Configurer les serveurs d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="a4290-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4290-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="a4290-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="a4290-104">Dans un environnement mixte, si vous créez un nouveau serveur d’applications approuvées après avoir fusionné la topologie Office Communications Server héritée avec Lync Server 2013 et que vous définissez un nouveau serveur d’applications approuvées à l’aide du générateur de topologie, vous devez définir le pool de tronçon suivant comme étant un Pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4290-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="a4290-105">Dans un environnement fusionné, le pool Office Communications Server hérité et le pool Lync Server 2013 apparaissent dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a4290-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="a4290-106">La sélection du pool hérité *n’est pas* prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a4290-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="a4290-107">Pour sélectionner Lync Server 2013 comme tronçon suivant lors de la création d’un serveur d’applications approuvées</span><span class="sxs-lookup"><span data-stu-id="a4290-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="a4290-108">Ouvrez une topologie existante dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="a4290-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="a4290-109">Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications approuvées**, puis cliquez sur **Nouveau pool d’applications approuvées**.</span><span class="sxs-lookup"><span data-stu-id="a4290-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="a4290-110">Entrez le **Nom de domaine complet (FQDN) du pool** de l’application approuvée et indiquez s’il s’agit d’un déploiement d’un seul serveur ou de plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="a4290-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="a4290-111">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a4290-111">Click **Next**.</span></span>

5.  <span data-ttu-id="a4290-112">Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4290-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="a4290-113">![Boîte de dialogue définir un nouveau pool d’applications approuvées](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Boîte de dialogue définir un nouveau pool d’applications approuvées")</span><span class="sxs-lookup"><span data-stu-id="a4290-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="a4290-114">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="a4290-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="a4290-115">Sélectionnez le nœud supérieur **Lync Server** puis, dans le volet **Actions**, sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="a4290-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="a4290-116">Vérifiez si le **Pool d’applications approuvées** a été correctement créé et s’il est associé au pool frontal approprié.</span><span class="sxs-lookup"><span data-stu-id="a4290-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

