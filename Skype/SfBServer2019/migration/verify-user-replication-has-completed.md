---
title: Vérifier que la réplication utilisateur est terminée
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Lorsque vous exécutez l’applet de contrôle Move-CsUser, il est possible que vous constatiez un échec en raison du fait que les informations utilisateur entre les services de domaine Active Directory (AD DS) et celles de Skype entreprise Server 2019 ne sont pas synchronisées, car la réplication initiale est incomplète. Le temps nécessaire à la réussite de la synchronisation initiale du service de réplicateur d’utilisateurs Skype entreprise Server 2019 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le Skype entreprise. Pool serveur 2019. Le processus de synchronisation initiale du service Réplicateur d’utilisateurs de Skype entreprise Server 2019 se produit lorsque le serveur frontal de Skype entreprise Server 2019 est démarré pour la première fois. Après cela, la synchronisation est alors basée sur l’intervalle du réplicateur d’utilisateurs. Suivez les étapes ci-dessous pour vérifier que la réplication des utilisateurs a abouti avant d’exécuter l’applet de commande Move-CsUser.
ms.openlocfilehash: 31f4f9f1045367e376d4536df54c32be14580312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812652"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="fc255-107">Vérifier que la réplication utilisateur est terminée</span><span class="sxs-lookup"><span data-stu-id="fc255-107">Verify user replication has completed</span></span>

<span data-ttu-id="fc255-108">Lorsque vous exécutez l’applet de contrôle **Move-Csuser** , il est possible que vous soyez en panne si les informations utilisateur entre les services de domaine Active Directory (AD DS) et les bases de données Skype entreprise Server 2019 ne sont pas synchronisées, car la réplication initiale est incomplète.</span><span class="sxs-lookup"><span data-stu-id="fc255-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="fc255-109">Le temps nécessaire à la réussite de la synchronisation initiale du service de réplicateur d’utilisateurs Skype entreprise Server 2019 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le Skype entreprise. Pool serveur 2019.</span><span class="sxs-lookup"><span data-stu-id="fc255-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="fc255-110">Le processus de synchronisation initiale du service Réplicateur d’utilisateurs de Skype entreprise Server 2019 se produit lorsque le serveur frontal de Skype entreprise Server 2019 est démarré pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="fc255-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="fc255-111">Après cela, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fc255-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="fc255-112">Suivez les étapes ci-dessous pour vérifier que la réplication des utilisateurs a abouti avant d’exécuter l’applet **de commande Move-Csuser** .</span><span class="sxs-lookup"><span data-stu-id="fc255-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="fc255-113">Pour vérifier que la réplication des utilisateurs est terminée</span><span class="sxs-lookup"><span data-stu-id="fc255-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="fc255-114">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fc255-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="fc255-115">Cliquez sur le menu **Démarrer** , puis sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="fc255-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="fc255-116">Entrez **eventvwr. exe**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc255-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="fc255-117">Dans l’observateur d’événements, cliquez sur **journaux des applications et des services** pour le développer, puis sélectionnez Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="fc255-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="fc255-118">Dans le volet **actions** , cliquez sur **filtrer le journal actuel**.</span><span class="sxs-lookup"><span data-stu-id="fc255-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="fc255-119">Dans la liste **sources d’événements** , cliquez sur réplicateur d' **utilisateurs LS**.</span><span class="sxs-lookup"><span data-stu-id="fc255-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="fc255-120">Dans \*\* \<tous les ID\>d’événement\*\*, entrez **30024**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc255-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="fc255-121">Dans la liste des événements filtrés, sous l’onglet **général** , recherchez une entrée indiquant que la réplication des utilisateurs s’est déroulée correctement.</span><span class="sxs-lookup"><span data-stu-id="fc255-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

