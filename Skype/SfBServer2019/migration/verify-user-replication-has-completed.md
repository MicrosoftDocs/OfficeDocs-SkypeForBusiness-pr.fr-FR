---
title: Vérifier que la réplication utilisateur est terminée
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Lors de l’exécution de l’cmdlet Move-CsUser, vous pouvez être en panne car les informations utilisateur entre les services de domaine Active Directory (AD DS) et les bases de données Skype Entreprise Server 2019 ne sont pas synchronisées, car la réplication initiale est incomplète. Le temps nécessaire à la réussite de la synchronisation initiale du service du réplicateur d’utilisateurs Skype Entreprise Server 2019 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le pool Skype Entreprise Server 2019. Le processus de synchronisation initiale du service réplicateur d’utilisateurs de Skype Entreprise Server 2019 se produit lors du premier démarré du serveur frontal Skype Entreprise Server 2019. Par la suite, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs. Exécutez les étapes suivantes pour vérifier que la réplication utilisateur est terminée avant d'Move-CsUser cmdlet.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751646"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="0d75c-107">Vérifier que la réplication utilisateur est terminée</span><span class="sxs-lookup"><span data-stu-id="0d75c-107">Verify user replication has completed</span></span>

<span data-ttu-id="0d75c-108">Lors de l’exécution de l’cmdlet **Move-CsUser,** vous pouvez être en panne si les informations utilisateur entre les services de domaine Active Directory (AD DS) et les bases de données Skype Entreprise Server 2019 ne sont pas synchronisées car la réplication initiale est incomplète.</span><span class="sxs-lookup"><span data-stu-id="0d75c-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="0d75c-109">Le temps nécessaire à la réussite de la synchronisation initiale du service du réplicateur d’utilisateurs Skype Entreprise Server 2019 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0d75c-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="0d75c-110">Le processus de synchronisation initiale du service réplicateur d’utilisateurs de Skype Entreprise Server 2019 se produit lors du premier démarré du serveur frontal Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0d75c-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="0d75c-111">Après cela, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0d75c-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="0d75c-112">Exécutez les étapes suivantes pour vérifier que la réplication utilisateur est terminée avant d’exécutez l’cmdlet **Move-CsUser.**</span><span class="sxs-lookup"><span data-stu-id="0d75c-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="0d75c-113">Pour vérifier que la réplication utilisateur est terminée</span><span class="sxs-lookup"><span data-stu-id="0d75c-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="0d75c-114">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0d75c-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="0d75c-115">Cliquez sur le menu **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="0d75c-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="0d75c-116">Entrez **eventvwr.exe**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d75c-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="0d75c-117">Dans l’Observateur d’événements, cliquez sur **les journaux Applications et services** pour le développer, puis sélectionnez Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0d75c-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="0d75c-118">Dans le volet **Actions**, cliquez sur **Filtrer le journal actuel**.</span><span class="sxs-lookup"><span data-stu-id="0d75c-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="0d75c-119">Dans la liste **Sources de l’événement**, cliquez sur **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="0d75c-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="0d75c-120">Dans **\<All Event IDs\>** , entrez **30024,** puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d75c-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="0d75c-121">Dans la liste des événements filtrés, sous l’onglet **Général,** recherchez une entrée qui indique que la réplication utilisateur s’est correctement terminée.</span><span class="sxs-lookup"><span data-stu-id="0d75c-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

