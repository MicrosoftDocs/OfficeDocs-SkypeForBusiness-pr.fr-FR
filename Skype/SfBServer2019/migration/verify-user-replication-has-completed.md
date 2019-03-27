---
title: Vérifier que la réplication utilisateur est terminée
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Lorsque vous exécutez l’applet de commande Move-CsUser, vous pouvez rencontrer une défaillance, car les informations utilisateur entre les Services de domaine Active Directory (AD DS) et le Skype pour les bases de données métiers Server 2019 ne sont pas synchronisés, car la réplication initiale est incomplète. Le temps que nécessaire à la réussite de la Skype pour la synchronisation initiale du service Business Server 2019 User Replicator varie selon le nombre de contrôleurs de domaine qui sont hébergées dans la forêt Active Directory qui héberge le Skype pour les entreprises Pool de serveur 2019. Le Skype pour le processus de synchronisation initiale du service Business Server 2019 réplicateur se produit lorsque le Skype pour Business Server 2019 serveur frontal est démarré pour la première fois. Après cela, la synchronisation puis repose sur l’intervalle du réplicateur d’utilisateurs. Effectuez les étapes suivantes pour vérifier la réplication utilisateur est terminée avant d’exécuter l’applet de commande Move-CsUser.
ms.openlocfilehash: bab54e91ebda7a10804980e368e05bb58ff911ff
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889507"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="ea338-107">Vérifier que la réplication utilisateur est terminée</span><span class="sxs-lookup"><span data-stu-id="ea338-107">Verify user replication has completed</span></span>

<span data-ttu-id="ea338-108">Lorsque vous exécutez l’applet de commande **Move-CsUser** , vous pouvez rencontrer une défaillance si les informations utilisateur entre les Services de domaine Active Directory (AD DS) et le Skype pour les bases de données métiers Server 2019 ne sont pas synchronisées, car la réplication initiale est incomplète.</span><span class="sxs-lookup"><span data-stu-id="ea338-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="ea338-109">Le temps que nécessaire à la réussite de la Skype pour la synchronisation initiale du service Business Server 2019 User Replicator varie selon le nombre de contrôleurs de domaine qui sont hébergées dans la forêt Active Directory qui héberge le Skype pour les entreprises Pool de serveur 2019.</span><span class="sxs-lookup"><span data-stu-id="ea338-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ea338-110">Le Skype pour le processus de synchronisation initiale du service Business Server 2019 réplicateur se produit lorsque le Skype pour Business Server 2019 serveur frontal est démarré pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="ea338-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="ea338-111">Après cela, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ea338-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="ea338-112">Effectuez les étapes suivantes pour vérifier que la réplication utilisateur est terminée avant d’exécuter l’applet de commande **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="ea338-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="ea338-113">Pour vérifier que la réplication utilisateur est terminée</span><span class="sxs-lookup"><span data-stu-id="ea338-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="ea338-114">Ouvrez une session l’ordinateur où le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ea338-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="ea338-115">Cliquez sur le menu **Démarrer** , puis cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ea338-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="ea338-116">Entrez **eventvwr.exe**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea338-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="ea338-117">Dans l’Observateur d’événements, cliquez sur **journaux des Applications et des Services** pour le développer, puis sélectionnez Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ea338-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="ea338-118">Dans le volet **Actions** , cliquez sur **Filtrer le journal actuel**.</span><span class="sxs-lookup"><span data-stu-id="ea338-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="ea338-119">Dans la liste de **sources d’événements** , cliquez sur **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="ea338-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="ea338-120">Dans \*\* \<tous les ID d’événement\>\*\*, entrez **30024**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea338-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="ea338-121">Dans la liste des événements filtrés, sous l’onglet **Général** , recherchez une entrée qui indique que la réplication utilisateur a réussi.</span><span class="sxs-lookup"><span data-stu-id="ea338-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

