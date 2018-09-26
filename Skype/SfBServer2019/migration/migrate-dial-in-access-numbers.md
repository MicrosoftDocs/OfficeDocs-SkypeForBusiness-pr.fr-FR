---
title: Migrer les numéros d’accès à distance
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Migration numéros d’accès à distance à Skype pour Business Server 2019 nécessitent l’exécution de l’applet de commande Move-CsApplicationEndpoint pour migrer les objets de contact. Lors de l’installation héritée et Skype pour la période de coexistence Business Server 2019, les numéros d’accès que vous avez créé dans Skype pour Business Server 2019 agissent comme les numéros d’accès que vous créez dans l’installation héritée, comme décrit dans ce section.
ms.openlocfilehash: 62d2d4f34f109c265a72a92283082601bd92b40b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027724"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="da1df-104">Migrer les numéros d’accès à distance</span><span class="sxs-lookup"><span data-stu-id="da1df-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="da1df-105">Migration numéros d’accès à distance à Skype pour Business Server 2019 nécessitent l’exécution de l’applet de commande **Move-CsApplicationEndpoint** pour migrer les objets de contact.</span><span class="sxs-lookup"><span data-stu-id="da1df-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="da1df-106">Lors de l’installation héritée et Skype pour la période de coexistence Business Server 2019, les numéros d’accès que vous avez créé dans Skype pour Business Server 2019 agissent comme les numéros d’accès que vous créez dans l’installation héritée, comme décrit dans ce section.</span><span class="sxs-lookup"><span data-stu-id="da1df-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 
  
<span data-ttu-id="da1df-107">Les numéros d’accès que vous avez créé dans hérité installent mais déplacés vers Skype pour Business Server 2019 ou que vous avez créé dans Skype for Business Server 2019 avant, pendant ou après la migration, ont les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="da1df-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>
  
- <span data-ttu-id="da1df-108">N’apparaissent pas dans la page de numéro d’accès et les invitations à une réunion Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="da1df-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>
    
- <span data-ttu-id="da1df-109">Apparaissent sur les invitations aux réunions d’install hérité et de la page de numéro d’accès à distance.</span><span class="sxs-lookup"><span data-stu-id="da1df-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>
    
- <span data-ttu-id="da1df-110">Apparaissent sur Skype pour les invitations à une réunion Business Server 2019 et la page de numéro d’accès à distance.</span><span class="sxs-lookup"><span data-stu-id="da1df-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>
    
- <span data-ttu-id="da1df-111">Ne peuvent pas être affichés ou modifiés dans l’outil d’administration Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="da1df-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>
    
- <span data-ttu-id="da1df-112">Peuvent être visualisés et modifiés dans l’installation héritée le panneau de configuration et l’installation héritée Management Shell.</span><span class="sxs-lookup"><span data-stu-id="da1df-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>
    
- <span data-ttu-id="da1df-113">Peuvent être visualisés et modifiés dans le Skype pour Business Server 2019 le panneau de configuration et Skype pour Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="da1df-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>
    
- <span data-ttu-id="da1df-114">Peuvent être séquencés à nouveau dans la zone à l’aide de l’applet de commande Set-CsDialinConferencingAccessNumber avec le paramètre Priority.</span><span class="sxs-lookup"><span data-stu-id="da1df-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>
    
<span data-ttu-id="da1df-115">Vous devez terminer la migration des numéros d’accès à distance qui pointent vers hérité installer pool avant de vous mettre hors service le pool hérité install.</span><span class="sxs-lookup"><span data-stu-id="da1df-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="da1df-116">Si vous n’effectuez pas la migration des numéros d’accès à distance comme décrit dans la procédure suivante, les appels entrants vers les numéros d’accès échoue.</span><span class="sxs-lookup"><span data-stu-id="da1df-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="da1df-117">Vous devez effectuer cette procédure avant de désactiver le pool hérité install.</span><span class="sxs-lookup"><span data-stu-id="da1df-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="da1df-118">Nous vous recommandons de déplacer les numéros d’accès entrant lorsque l’utilisation du réseau est faible, au cas où une courte période d’interruption de service.</span><span class="sxs-lookup"><span data-stu-id="da1df-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 
  
## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="da1df-119">Pour identifier et déplacer les numéros d’accès à distance</span><span class="sxs-lookup"><span data-stu-id="da1df-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="da1df-120">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="da1df-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="da1df-121">Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Skype pour Business Server 2019, à partir de la ligne de commande, exécutez :</span><span class="sxs-lookup"><span data-stu-id="da1df-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 
    
  ```
  Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
  
  ```

3. <span data-ttu-id="da1df-122">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="da1df-122">Open Skype for Business Server Control Panel.</span></span>
    
4. <span data-ttu-id="da1df-123">Dans la barre de navigation de gauche, cliquez sur **Conférences**.</span><span class="sxs-lookup"><span data-stu-id="da1df-123">In the left navigation bar, click **Conferencing**.</span></span>
    
5. <span data-ttu-id="da1df-124">Cliquez sur l’onglet **Numéro d’accès entrant** .</span><span class="sxs-lookup"><span data-stu-id="da1df-124">Click the **Dial-in Access Number** tab.</span></span> 
    
6. <span data-ttu-id="da1df-125">Vérifiez qu’il ne reste aucun numéro d’accès à distance pour le pool hérité installer à partir de laquelle vous migrez.</span><span class="sxs-lookup"><span data-stu-id="da1df-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="da1df-126">Lorsque tous les numéros d’accès à distance pointent vers le Skype pour Business Server 2019 pool, vous pouvez désactiver le pool hérité install.</span><span class="sxs-lookup"><span data-stu-id="da1df-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 
  
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="da1df-127">Vérifier la migration des numéros d’accès à distance à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="da1df-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="da1df-128">À partir d’un compte d’utilisateur auquel est affecté le rôle **CsUserAdministrator** ou **csadministrator** , ouvrez une session n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="da1df-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="da1df-129">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="da1df-129">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="da1df-130">Dans la barre de navigation de gauche, cliquez sur **Conférences**.</span><span class="sxs-lookup"><span data-stu-id="da1df-130">In the left navigation bar, click **Conferencing**.</span></span>
    
4. <span data-ttu-id="da1df-131">Cliquez sur l’onglet **Numéro d’accès entrant** .</span><span class="sxs-lookup"><span data-stu-id="da1df-131">Click the **Dial-in Access Number** tab.</span></span> 
    
5. <span data-ttu-id="da1df-132">Vérifiez que tous les numéros d’accès à distance sont migrés vers le pool hébergé sur Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="da1df-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>
    
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="da1df-133">Vérifier la migration des numéros d’accès à distance à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="da1df-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="da1df-134">Ouvrez Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="da1df-134">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="da1df-135">Pour retourner tous les numéros d’accès à la conférence rendez-vous migrés, à partir de la ligne de commande exécutée :</span><span class="sxs-lookup"><span data-stu-id="da1df-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
  ```
  Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
  ```

3. <span data-ttu-id="da1df-136">Vérifiez que tous les numéros d’accès à distance sont migrés vers le pool hébergé sur Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="da1df-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>
    

