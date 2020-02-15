---
title: Vérifier que la réplication utilisateur est terminée
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6433c1e88edf69b957047b9dc405df392e5ec104
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="8d80e-102">Vérifier que la réplication utilisateur est terminée</span><span class="sxs-lookup"><span data-stu-id="8d80e-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d80e-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8d80e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8d80e-104">Lors de l’exécution de la cmdlet **Move-CsLegacyUser** , vous pouvez être confronté à un échec dû à des informations utilisateur entre les services de domaine Active Directory (AD DS) et les bases de données Lync Server 2013 désynchronisées car la réplication initiale est incomplète.</span><span class="sxs-lookup"><span data-stu-id="8d80e-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="8d80e-105">Le temps nécessaire à la synchronisation initiale de Lync Server 2013 le service Réplicateur d’utilisateurs dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory hébergeant le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d80e-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="8d80e-106">Le processus de synchronisation initiale du service Réplicateur d’utilisateurs Lync Server 2013 se produit lorsque le serveur frontal Lync Server 2013 est démarré pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="8d80e-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="8d80e-107">Par la suite, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8d80e-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="8d80e-108">Procédez comme suit pour vérifier que la réplication utilisateur est terminée avant d’exécuter la cmdlet **Move-CsLegacyUser** .</span><span class="sxs-lookup"><span data-stu-id="8d80e-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="8d80e-109">Pour vérifier que la réplication utilisateur est terminée</span><span class="sxs-lookup"><span data-stu-id="8d80e-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="8d80e-110">À partir du serveur frontal Lync Server 2013, cliquez sur le menu **Démarrer** , puis sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8d80e-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="8d80e-111">Entrez **eventvwr.exe**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d80e-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="8d80e-112">Dans l’observateur d’événements, cliquez sur **journaux des applications et des services** pour le développer, puis sélectionnez Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d80e-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="8d80e-113">Dans le volet **Actions**, cliquez sur **Filtrer le journal actuel**.</span><span class="sxs-lookup"><span data-stu-id="8d80e-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="8d80e-114">Dans la liste **Sources de l’événement**, cliquez sur **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="8d80e-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="8d80e-115">Dans \*\* \<tous les ID\> d’événement\*\* , entrez **30024** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d80e-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="8d80e-116">Dans la liste des événements filtrés, dans l’onglet **Général**, recherchez une entrée qui stipule que la réplication utilisateur s’est achevée avec succès.</span><span class="sxs-lookup"><span data-stu-id="8d80e-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

