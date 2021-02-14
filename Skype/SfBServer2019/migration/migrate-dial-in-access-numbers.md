---
title: Migration des numéros d’accès entrant
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
description: La migration des numéros d’accès à des appels vers Skype Entreprise Server 2019 nécessite l’exécution Move-CsApplicationEndpoint cmdlet pour migrer les objets contact. Pendant la période d’installation héritée et de coexistence de Skype Entreprise Server 2019, les numéros d’accès à la connexion que vous avez créés dans Skype Entreprise Server 2019 se comportent de la même manière que les numéros d’accès à la connexion que vous créez dans l’installation héritée, comme décrit dans cette section.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752696"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="937a3-104">Migration des numéros d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="937a3-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="937a3-105">La migration des numéros d’accès à des appels vers Skype Entreprise Server 2019 nécessite l’exécution de l’cmdlet **Move-CsApplicationEndpoint** pour migrer les objets contact.</span><span class="sxs-lookup"><span data-stu-id="937a3-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="937a3-106">Pendant la période d’installation héritée et de coexistence de Skype Entreprise Server 2019, les numéros d’accès à la connexion que vous avez créés dans Skype Entreprise Server 2019 se comportent de la même manière que les numéros d’accès à la connexion que vous créez dans l’installation héritée, comme décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="937a3-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="937a3-107">Les numéros d’accès à la connexion que vous avez créés dans l’installation héritée, mais que vous avez déplacés vers Skype Entreprise Server 2019, ou que vous avez créés dans Skype Entreprise Server 2019 avant, pendant ou après la migration, ont les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="937a3-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="937a3-108">N’apparaissent pas sur les invitations aux réunions Office Communications Server 2007 R2 et la page des numéros d’accès rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="937a3-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="937a3-109">Apparaissent sur les invitations aux réunions d’installation héritées et la page des numéros d’accès rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="937a3-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="937a3-110">Apparaissent sur les invitations aux réunions Skype Entreprise Server 2019 et la page des numéros d’accès rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="937a3-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="937a3-111">Ne peut pas être vu ou modifié dans l’outil d’administration Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="937a3-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="937a3-112">Peut être vue et modifiée dans le Panneau de contrôle d’installation hérité et dans l’installation héritée de Management Shell.</span><span class="sxs-lookup"><span data-stu-id="937a3-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="937a3-113">Peut être visionnable et modifié dans le Panneau de commande Skype Entreprise Server 2019 et dans Skype Entreprise Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="937a3-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="937a3-114">ils peuvent être réordonnés dans la région à l’aide de l’applet de commande Set-CsDialinConferencingAccessNumber avec le paramètre Priority.</span><span class="sxs-lookup"><span data-stu-id="937a3-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="937a3-115">Vous devez terminer la migration des numéros d’accès à la connexion qui pointent vers le pool d’installation hérité avant de désaffecter le pool d’installation hérité.</span><span class="sxs-lookup"><span data-stu-id="937a3-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="937a3-116">Si vous ne terminez pas la migration des numéros d’accès entrant tel que décrit dans la procédure suivante, les appels entrants vers les numéros d’accès échoueront.</span><span class="sxs-lookup"><span data-stu-id="937a3-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="937a3-117">Vous devez effectuer cette procédure avant de désaffecter le pool d’installation hérité.</span><span class="sxs-lookup"><span data-stu-id="937a3-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="937a3-118">Nous vous recommandons de déplacer les numéros d’accès entrant lorsque l’utilisation du réseau est faible, au cas où il y aurait une courte période d’interruption de service.</span><span class="sxs-lookup"><span data-stu-id="937a3-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="937a3-119">Pour identifier et déplacer les numéros d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="937a3-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="937a3-120">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Microsoft Skype Entreprise **Server 2019,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="937a3-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="937a3-121">Pour déplacer chaque numéro d’accès à un pool hébergé sur Skype Entreprise Server 2019, à partir de la ligne de commande, exécutez :</span><span class="sxs-lookup"><span data-stu-id="937a3-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="937a3-122">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="937a3-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="937a3-123">Dans la barre de navigation de gauche, cliquez sur **Conférence**.</span><span class="sxs-lookup"><span data-stu-id="937a3-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="937a3-124">Cliquez sur **l’onglet Numéro d’accès** à la connexion.</span><span class="sxs-lookup"><span data-stu-id="937a3-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="937a3-125">Vérifiez qu’il ne reste aucun numéro d’accès pour le pool d’installation hérité à partir duquel vous migrez.</span><span class="sxs-lookup"><span data-stu-id="937a3-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="937a3-126">Lorsque tous les numéros d’accès à la connexion pointent vers le pool Skype Entreprise Server 2019, vous pouvez ensuite désaffecter le pool d’installation hérité.</span><span class="sxs-lookup"><span data-stu-id="937a3-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="937a3-127">Vérifier la migration des numéros d’accès à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="937a3-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="937a3-128">À partir d’un compte d’utilisateur affecté au rôle **CsUserAdministrator** ou **CsAdministrator,** connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="937a3-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="937a3-129">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="937a3-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="937a3-130">Dans la barre de navigation de gauche, cliquez sur **Conférence**.</span><span class="sxs-lookup"><span data-stu-id="937a3-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="937a3-131">Cliquez sur **l’onglet Numéro d’accès** à la connexion.</span><span class="sxs-lookup"><span data-stu-id="937a3-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="937a3-132">Vérifiez que tous les numéros d’accès sont migrés vers le pool hébergé sur Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="937a3-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="937a3-133">Vérifier la migration des numéros d’accès à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="937a3-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="937a3-134">Ouvrez Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="937a3-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="937a3-135">Pour retourner tous les numéros d’accès aux conférences dial-in migrés, à partir de la ligne de commande, exécutez :</span><span class="sxs-lookup"><span data-stu-id="937a3-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="937a3-136">Vérifiez que tous les numéros d’accès sont migrés vers le pool hébergé sur Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="937a3-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


