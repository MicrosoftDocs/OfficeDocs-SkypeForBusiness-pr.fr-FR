---
title: Migrer les numéros d’accès entrant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La migration des numéros d’accès rendez-vous dans Skype entreprise Server 2019 nécessite l’exécution de l’applet de connexion Move-CsApplicationEndpoint pour migrer les objets de contact. Lors de l’installation héritée et de la période de coexistence 2019 de Skype entreprise Server, les numéros d’accès rendez-vous créés dans Skype entreprise Server 2019 se comportent de la même manière que les numéros d’accès entrants que vous créez dans l’installation héritée, comme décrit dans cet zone.
ms.openlocfilehash: 35c1e665f8affdbf84628f9a7d532405779648f0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991139"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="0d62b-104">Migrer les numéros d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="0d62b-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="0d62b-105">La migration des numéros d’accès rendez-vous dans Skype entreprise Server 2019 nécessite l’exécution de l’applet de connexion **Move-CsApplicationEndpoint** pour migrer les objets de contact.</span><span class="sxs-lookup"><span data-stu-id="0d62b-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="0d62b-106">Lors de l’installation héritée et de la période de coexistence 2019 de Skype entreprise Server, les numéros d’accès rendez-vous créés dans Skype entreprise Server 2019 se comportent de la même manière que les numéros d’accès entrants que vous créez dans l’installation héritée, comme décrit dans cet zone.</span><span class="sxs-lookup"><span data-stu-id="0d62b-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="0d62b-107">Les numéros d’accès rendez-vous créés lors de l’installation de Skype entreprise Server 2019 ou que vous avez créés dans Skype entreprise Server 2019 avant, pendant ou après la migration, présentent les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d62b-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="0d62b-108">N’apparaissent pas dans les invitations aux réunions Office Communications Server 2007 R2 et la page numéro d’accès rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="0d62b-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="0d62b-109">Apparaissent sur les invitations à la réunion d’installation héritée et sur la page numéro d’accès rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="0d62b-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="0d62b-110">S’affichent dans les invitations aux réunions 2019 de Skype entreprise Server et la page des numéros d’accès rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="0d62b-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="0d62b-111">Ne peut pas être affiché ou modifié dans l’outil d’administration d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="0d62b-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="0d62b-112">Peut être affiché et modifié dans le panneau de configuration de l’installation légué et dans l’environnement d’administration de l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="0d62b-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="0d62b-113">Peut être affiché et modifié dans le panneau de configuration Skype entreprise Server 2019 et dans Skype entreprise Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0d62b-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="0d62b-114">Peuvent être réécrits au sein de la région à l’aide de l’applet de requête Set-CsDialinConferencingAccessNumber avec le paramètre Priority.</span><span class="sxs-lookup"><span data-stu-id="0d62b-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="0d62b-115">Vous devez mettre fin à la migration des numéros d’accès rendez-vous qui pointent vers le pool d’installation hérité avant de désactiver le pool d’installation hérité.</span><span class="sxs-lookup"><span data-stu-id="0d62b-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="0d62b-116">Si vous n’avez pas terminé la migration des numéros d’accès rendez-vous, comme indiqué dans la procédure suivante, les appels entrants vers les numéros d’accès échoueront.</span><span class="sxs-lookup"><span data-stu-id="0d62b-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d62b-117">Vous devez effectuer cette procédure avant de désaffecter le pool d’installation hérité.</span><span class="sxs-lookup"><span data-stu-id="0d62b-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="0d62b-118">Nous vous recommandons de déplacer les numéros d’accès rendez-vous lorsque le niveau d’utilisation du réseau est faible, en cas de panne de service de courte durée.</span><span class="sxs-lookup"><span data-stu-id="0d62b-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="0d62b-119">Pour identifier et déplacer les numéros d’accès rendez-vous</span><span class="sxs-lookup"><span data-stu-id="0d62b-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="0d62b-120">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0d62b-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="0d62b-121">Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Skype entreprise Server 2019, à partir de la ligne de commande exécutée :</span><span class="sxs-lookup"><span data-stu-id="0d62b-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="0d62b-122">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0d62b-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="0d62b-123">Dans la barre de navigation de gauche, cliquez sur **Conférences**.</span><span class="sxs-lookup"><span data-stu-id="0d62b-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="0d62b-124">Cliquez sur l’onglet **numéro d’accès** rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="0d62b-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="0d62b-125">Vérifiez qu’il n’y a pas de numéros d’accès rendez-vous pour le pool d’installation hérité à partir duquel vous effectuez la migration.</span><span class="sxs-lookup"><span data-stu-id="0d62b-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d62b-126">Lorsque tous les numéros d’accès entrant pointent vers le pool Skype entreprise Server 2019, vous pouvez désactiver le pool d’installation hérité.</span><span class="sxs-lookup"><span data-stu-id="0d62b-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0d62b-127">Vérifier la migration des numéros d’accès rendez-vous à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0d62b-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0d62b-128">À partir d’un compte d’utilisateur affecté au rôle **CsUserAdministrator** ou au rôle **CsAdministrator** , connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0d62b-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="0d62b-129">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0d62b-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="0d62b-130">Dans la barre de navigation de gauche, cliquez sur **Conférences**.</span><span class="sxs-lookup"><span data-stu-id="0d62b-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="0d62b-131">Cliquez sur l’onglet **numéro d’accès** rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="0d62b-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="0d62b-132">Vérifiez que tous les numéros d’accès rendez-vous sont déplacés vers le pool hébergé sur Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0d62b-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0d62b-133">Vérifier la migration des numéros d’accès entrants à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="0d62b-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="0d62b-134">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0d62b-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="0d62b-135">Pour rétablir tous les numéros d’accès pour les conférences rendez-vous transférés, à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="0d62b-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="0d62b-136">Vérifiez que tous les numéros d’accès rendez-vous sont déplacés vers le pool hébergé sur Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0d62b-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


