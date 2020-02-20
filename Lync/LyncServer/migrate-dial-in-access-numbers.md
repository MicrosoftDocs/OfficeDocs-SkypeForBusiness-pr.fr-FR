---
title: Faire migrer les numéros d’accès entrant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eaef027180304fca2a64294177faffcc0811e565
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="84df1-102">Faire migrer les numéros d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="84df1-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84df1-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="84df1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="84df1-104">La migration des numéros d’accès entrant de Lync Server 2010 vers Lync Server 2013 nécessite l’exécution de la cmdlet **Move-CsApplicationEndpoint** pour migrer les objets contact.</span><span class="sxs-lookup"><span data-stu-id="84df1-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="84df1-105">Pendant la période de coexistence Lync Server 2010 et Lync Server 2013, les numéros d’accès entrant que vous avez créés dans Lync Server 2013 se comportent de la même manière que les numéros d’accès entrant que vous créez dans Lync Server 2010, comme décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="84df1-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="84df1-106">Les numéros d’accès entrant que vous avez créés dans Lync Server 2010, mais déplacés vers Lync Server 2013 ou créés dans Lync Server 2013 avant, pendant ou après la migration, ont les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="84df1-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="84df1-107">N’apparaissent pas sur les invitations aux réunions Office Communications Server 2007 R2 et la page numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="84df1-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="84df1-108">Apparaissent sur les invitations aux réunions Lync Server 2010 et la page numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="84df1-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="84df1-109">Apparaissent sur les invitations aux réunions Lync Server 2013 et la page numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="84df1-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="84df1-110">Ne peuvent pas être affichés ni modifiés dans l’outil d’administration Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="84df1-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="84df1-111">Peuvent être affichés et modifiés dans le panneau de configuration Lync Server 2010 et dans Lync Server 2010 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="84df1-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="84df1-112">Peuvent être affichés et modifiés dans le panneau de configuration Lync Server 2013 et dans Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="84df1-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="84df1-113">ils peuvent être réordonnés dans la région à l’aide de l’applet de commande Set-CsDialinConferencingAccessNumber avec le paramètre Priority.</span><span class="sxs-lookup"><span data-stu-id="84df1-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="84df1-114">Vous devez terminer la migration des numéros d’accès entrant qui pointent vers un pool Lync Server 2010 avant de mettre hors service le pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="84df1-114">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="84df1-115">Si vous ne terminez pas la migration des numéros d’accès entrant tel que décrit dans la procédure suivante, les appels entrants vers les numéros d’accès échoueront.</span><span class="sxs-lookup"><span data-stu-id="84df1-115">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="84df1-116">Vous devez effectuer cette procédure avant de désactiver le pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="84df1-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="84df1-117">Nous vous recommandons de déplacer les numéros d’accès entrant lorsque l’utilisation du réseau est faible, au cas où il y aurait une courte période d’interruption de service.</span><span class="sxs-lookup"><span data-stu-id="84df1-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="84df1-118">**Pour identifier et déplacer les numéros d’accès entrant**</span><span class="sxs-lookup"><span data-stu-id="84df1-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="84df1-119">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="84df1-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="84df1-120">Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Lync Server 2013, exécutez la commande suivante à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="84df1-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="84df1-121">Ouvrez le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="84df1-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="84df1-122">Dans la barre de navigation de gauche, cliquez sur **Conférence**.</span><span class="sxs-lookup"><span data-stu-id="84df1-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="84df1-123">Cliquez sur l’onglet **numéro d’accès entrant** .</span><span class="sxs-lookup"><span data-stu-id="84df1-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="84df1-124">Vérifiez qu’il ne reste aucun numéro d’accès entrant pour le pool Lync Server 2010 à partir duquel vous effectuez la migration.</span><span class="sxs-lookup"><span data-stu-id="84df1-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84df1-125">Lorsque tous les numéros d’accès entrants pointent vers le pool Lync Server 2013, vous pouvez mettre hors service le pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="84df1-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="84df1-126">**Vérifier la migration des numéros d’accès entrant à l’aide du panneau de configuration Lync Server**</span><span class="sxs-lookup"><span data-stu-id="84df1-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="84df1-127">À partir d’un compte d’utilisateur affecté au rôle **CsUserAdministrator** ou **CsAdministrator** , ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="84df1-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="84df1-128">Ouvrez le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="84df1-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="84df1-129">Dans la barre de navigation de gauche, cliquez sur **Conférence**.</span><span class="sxs-lookup"><span data-stu-id="84df1-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="84df1-130">Cliquez sur l’onglet **numéro d’accès entrant** .</span><span class="sxs-lookup"><span data-stu-id="84df1-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="84df1-131">Vérifiez que tous les numéros d’accès entrant sont migrés vers le pool hébergé sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84df1-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="84df1-132">**Vérifier la migration des numéros d’accès entrant à l’aide de Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="84df1-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="84df1-133">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="84df1-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="84df1-134">Pour renvoyer tous les numéros d’accès de conférence rendez-vous migrés, exécutez la commande suivante à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="84df1-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="84df1-135">Vérifiez que tous les numéros d’accès entrant sont migrés vers le pool hébergé sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84df1-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

