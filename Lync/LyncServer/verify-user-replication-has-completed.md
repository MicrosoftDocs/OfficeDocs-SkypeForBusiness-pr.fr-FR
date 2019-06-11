---
title: Vérifier que la réplication utilisateur est terminée
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e96d3231fbbfe9ce9062e948e6b60de6521720e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="6dabb-102">Vérifier que la réplication utilisateur est terminée</span><span class="sxs-lookup"><span data-stu-id="6dabb-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dabb-103">_**Dernière modification de la rubrique:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="6dabb-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="6dabb-104">Lorsque vous exécutez l’applet de contrôle **Move-Csuser** , il est possible que vous constatiez un échec en raison du fait que les informations utilisateur entre les services de domaine Active Directory (AD DS) et celles de Lync Server 2013 ne sont pas synchronisées, car la réplication initiale est incomplète.</span><span class="sxs-lookup"><span data-stu-id="6dabb-104">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="6dabb-105">Le temps nécessaire à la réussite de la synchronisation initiale du service Réplicateur d’utilisateurs de Lync Server 2013 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le pool 2013 Server.</span><span class="sxs-lookup"><span data-stu-id="6dabb-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="6dabb-106">Le processus de synchronisation initiale du service Réplicateur d’utilisateurs de Lync Server 2013 se produit lorsque le serveur frontal de Lync Server 2013 est démarré pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="6dabb-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="6dabb-107">Après cela, la synchronisation est alors basée sur l’intervalle du réplicateur d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6dabb-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="6dabb-108">Suivez les étapes ci-dessous pour vérifier que la réplication des utilisateurs a abouti avant d’exécuter l’applet **de commande Move-Csuser** .</span><span class="sxs-lookup"><span data-stu-id="6dabb-108">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="6dabb-109">Pour vérifier la fin de la réplication des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6dabb-109">To verify user replication has completed</span></span>

1.  <span data-ttu-id="6dabb-110">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6dabb-110">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="6dabb-111">Cliquez sur le menu **Démarrer** , puis sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6dabb-111">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="6dabb-112">Entrez **eventvwr. exe** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dabb-112">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="6dabb-113">Dans l’observateur d’événements, cliquez sur **journaux des applications et des services** pour le développer, puis sélectionnez Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6dabb-113">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="6dabb-114">Dans le volet **actions** , cliquez sur **filtrer le journal actuel**.</span><span class="sxs-lookup"><span data-stu-id="6dabb-114">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="6dabb-115">Dans la liste **sources d’événements** , cliquez sur réplicateur d' **utilisateurs LS**.</span><span class="sxs-lookup"><span data-stu-id="6dabb-115">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="6dabb-116">Dans \*\* \<tous les ID\> d’événement\*\* entrez **30024** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dabb-116">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="6dabb-117">Dans la liste des événements filtrés, sous l’onglet **général** , recherchez une entrée qui indique que la réplication des utilisateurs s’est déroulée correctement.</span><span class="sxs-lookup"><span data-stu-id="6dabb-117">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

