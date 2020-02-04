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
ms.openlocfilehash: bc6d8100a7bd0d348c3414da627584bae8697a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="18c28-102">Vérifier que la réplication utilisateur est terminée</span><span class="sxs-lookup"><span data-stu-id="18c28-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18c28-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="18c28-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="18c28-104">Lors de l’exécution de l’applet de contrôle **Move-CsLegacyUser** , il est possible que vous constatiez un échec en raison d’informations utilisateur entre les services de domaine Active Directory (AD DS) et les bases de données Lync Server 2013 en dehors de la synchronisation, car la réplication initiale est incomplète.</span><span class="sxs-lookup"><span data-stu-id="18c28-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="18c28-105">Le temps nécessaire à la réussite de la synchronisation initiale du service Réplicateur d’utilisateurs de Lync Server 2013 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le pool 2013 Server.</span><span class="sxs-lookup"><span data-stu-id="18c28-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="18c28-106">Le processus de synchronisation initiale du service Réplicateur d’utilisateurs de Lync Server 2013 se produit lorsque le serveur frontal de Lync Server 2013 est démarré pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="18c28-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="18c28-107">Après cela, la synchronisation est alors basée sur l’intervalle du réplicateur d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="18c28-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="18c28-108">Suivez les étapes ci-dessous pour vérifier que la réplication des utilisateurs a abouti avant d’exécuter l’applet **de commande Move-CsLegacyUser** .</span><span class="sxs-lookup"><span data-stu-id="18c28-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="18c28-109">Pour vérifier que la réplication des utilisateurs est terminée</span><span class="sxs-lookup"><span data-stu-id="18c28-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="18c28-110">À partir du serveur frontal Lync Server 2013, cliquez sur le menu **Démarrer** , puis sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="18c28-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="18c28-111">Entrez **eventvwr. exe** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="18c28-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="18c28-112">Dans l’observateur d’événements, cliquez sur **journaux des applications et des services** pour le développer, puis sélectionnez Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18c28-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="18c28-113">Dans le volet **actions** , cliquez sur **filtrer le journal actuel**.</span><span class="sxs-lookup"><span data-stu-id="18c28-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="18c28-114">Dans la liste **sources d’événements** , cliquez sur réplicateur d' **utilisateurs LS**.</span><span class="sxs-lookup"><span data-stu-id="18c28-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="18c28-115">Dans \*\* \<tous les ID\> d’événement\*\* entrez **30024** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="18c28-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="18c28-116">Dans la liste des événements filtrés, sous l’onglet **général** , recherchez une entrée qui indique que la réplication des utilisateurs s’est déroulée correctement.</span><span class="sxs-lookup"><span data-stu-id="18c28-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

