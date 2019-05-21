---
title: 'Déploiement d’un magasin de contacts unifié dans Skype entreprise Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Résumé: activez le magasin de contacts unifié dans Skype entreprise Server.'
ms.openlocfilehash: 737e9dbdd0dc9e4aae54e454cb558c59004719b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302802"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="8d03b-103">Déploiement d’un magasin de contacts unifié dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8d03b-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="8d03b-104">**Résumé:** Activez le magasin de contacts unifié dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8d03b-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="8d03b-105">L’activation d’un magasin de contacts unifié dans Skype entreprise Server n’exige aucun paramètre de topologie.</span><span class="sxs-lookup"><span data-stu-id="8d03b-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="8d03b-106">Pour activer le magasin de contacts unifié pour les utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="8d03b-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="8d03b-107">La stratégie du magasin de contacts unifié est activée (par défaut).</span><span class="sxs-lookup"><span data-stu-id="8d03b-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="8d03b-108">Les utilisateurs se connectent à Skype entreprise au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="8d03b-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="8d03b-109">Après la migration des contacts d’un utilisateur, ce qui se produit automatiquement lorsqu’un utilisateur se connecte à l’aide de Skype entreprise, l’utilisateur peut accéder à ses contacts Skype entreprise et les gérer depuis Skype entreprise, Outlook 2013 ou Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="8d03b-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="8d03b-110">Il n’est pas nécessaire de se connecter à Skype entreprise pour gérer ses contacts à partir d’Outlook ou d’Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="8d03b-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8d03b-111">Si un utilisateur se connecte à partir de Skype entreprise après la migration, les contacts et les groupes sont disponibles et à jour, mais l’utilisateur ne peut pas gérer (c’est-à-dire ajouter, supprimer, déplacer, Baliser, supprimer ou modifier) ces contacts.</span><span class="sxs-lookup"><span data-stu-id="8d03b-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="8d03b-112">Activation des utilisateurs pour le magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="8d03b-112">Enable users for unified contact store</span></span>

<span data-ttu-id="8d03b-113">Lorsque vous déployez Skype entreprise Server et que vous publiez la topologie, le magasin de contacts unifié est activé par défaut pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8d03b-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="8d03b-114">Vous n’avez pas besoin d’effectuer d’action supplémentaire pour activer le magasin de contacts unifié après le déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8d03b-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="8d03b-115">Cependant, vous pouvez utiliser l’applet de commande **Set-CsUserServicesPolicy** pour personnaliser les utilisateurs pour lesquels le magasin de contact unifié est disponible.</span><span class="sxs-lookup"><span data-stu-id="8d03b-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="8d03b-116">Vous pouvez activer cette fonctionnalité globalement, par site, par locataire, par personne ou par groupes de personnes.</span><span class="sxs-lookup"><span data-stu-id="8d03b-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="8d03b-117">Pour activer les utilisateurs pour le magasin de contact unifié</span><span class="sxs-lookup"><span data-stu-id="8d03b-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="8d03b-118">Démarrer Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8d03b-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8d03b-119">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8d03b-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="8d03b-120">Pour activer globalement le magasin de contacts unifié pour tous les utilisateurs de Skype entreprise Server, procédez de l’une des manières suivantes dans l’interface de ligne de commande Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8d03b-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="8d03b-121">Pour activer le magasin de contact unifié pour tous les utilisateurs d’un site spécifique, à l’invite, tapez :</span><span class="sxs-lookup"><span data-stu-id="8d03b-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="8d03b-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8d03b-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="8d03b-123">Pour activer le magasin de contact unifié par locataire, à l’invite, tapez :</span><span class="sxs-lookup"><span data-stu-id="8d03b-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="8d03b-124">Exemple :</span><span class="sxs-lookup"><span data-stu-id="8d03b-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="8d03b-125">Pour activer le magasin de contact unifié pour des utilisateurs spécifiques, à l’invite, tapez :</span><span class="sxs-lookup"><span data-stu-id="8d03b-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="8d03b-126">Vous pouvez également utiliser un alias utilisateur ou un URI SIP à la place du nom d’affichage de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d03b-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="8d03b-127">Exemple :</span><span class="sxs-lookup"><span data-stu-id="8d03b-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="8d03b-128">Dans l’exemple précédant, la première commande crée une nouvelle stratégie par utilisateur appelée Utilisateurs UCS activés avec l’indicateur UcsAllowed défini à True.</span><span class="sxs-lookup"><span data-stu-id="8d03b-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="8d03b-129">La seconde commande affecte la stratégie à l’utilisateur avec le nom complet Ken Myer, ce qui signifie que Ken Myer est désormais activé pour le magasin de contact unifié.</span><span class="sxs-lookup"><span data-stu-id="8d03b-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="8d03b-130">Migration des utilisateurs vers le magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="8d03b-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="8d03b-131">Les contacts d’un utilisateur sont automatiquement déplacés vers le serveur Exchange 2013 lorsque l’utilisateur:</span><span class="sxs-lookup"><span data-stu-id="8d03b-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="8d03b-132">une stratégie de services utilisateur dont le paramètre UcsAllowed a la valeur True a été attribuée à l’utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="8d03b-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="8d03b-133">A été configuré avec une boîte aux lettres Exchange 2013 et s’est connecté à la boîte aux lettres au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="8d03b-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="8d03b-134">Se connecte à l’aide d’un client enrichi Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="8d03b-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="8d03b-135">Si l’utilisateur se connecte avec un client Lync ou antérieur, ou si l’utilisateur n’est pas connecté à un serveur Exchange 2013, la stratégie de services des utilisateurs est ignorée et les contacts de l’utilisateur sont conservés dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8d03b-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="8d03b-136">Déterminez si les contacts d’un utilisateur ont été transférés en utilisant l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8d03b-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="8d03b-137">Vérifiez la clé de Registre suivante sur l’ordinateur client :</span><span class="sxs-lookup"><span data-stu-id="8d03b-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="8d03b-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span><span class="sxs-lookup"><span data-stu-id="8d03b-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="8d03b-139">Si les contacts de l’utilisateur sont stockés dans Exchange 2013, cette clé contient une valeur de InUCSMode avec une valeur de 2165.</span><span class="sxs-lookup"><span data-stu-id="8d03b-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="8d03b-140">Exécutez l’applet de commande **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="8d03b-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="8d03b-141">Dans la ligne de commande de Skype entreprise Server Management Shell, tapez:</span><span class="sxs-lookup"><span data-stu-id="8d03b-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="8d03b-142">Si l’exécution de la commande **Test-CsUnifiedContactStore** s’est déroulée correctement, les contacts de l’utilisateur ont été migrés vers le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="8d03b-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="8d03b-143">Restauration des utilisateurs migrés</span><span class="sxs-lookup"><span data-stu-id="8d03b-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="8d03b-144">Si vous avez besoin de restaurer la fonctionnalité de magasin de contacts unifiée, restaurez les contacts uniquement si vous revenez à l’utilisateur dans Exchange 2010 ou Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8d03b-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="8d03b-145">Pour effectuer la restauration, désactivez la stratégie définie pour l’utilisateur, puis exécutez l’applet de commande **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="8d03b-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="8d03b-146">La simple exécution de **Invoke-CsUcsRollback** ne suffit pas à garantir une restauration permanente ; en effet, si la stratégie n’est pas désactivée, le magasin de contacts unifié continue d’être transféré.</span><span class="sxs-lookup"><span data-stu-id="8d03b-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="8d03b-147">Par exemple, si un utilisateur est restauré, car Exchange 2013 est restauré dans Exchange 2010, puis la boîte aux lettres de l’utilisateur est déplacée vers Exchange 2013, la migration de magasin de contacts unifiée sera lancée à nouveau après le Rollback, tant que magasin de contacts unifié est toujours activée pour l’utilisateur dans la stratégie de services des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8d03b-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="8d03b-148">L’applet de commande **Move-Csuser** restaure automatiquement le magasin de contacts de l’utilisateur à partir de Exchange 2013 vers Skype entreprise Server dans les situations suivantes:</span><span class="sxs-lookup"><span data-stu-id="8d03b-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="8d03b-149">Lorsque les utilisateurs sont déplacés de Skype entreprise Server vers Microsoft Lync Server 2013 ou Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8d03b-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="8d03b-150">Lorsque les utilisateurs sont déplacés vers l’environnement croisé, par exemple lorsqu’un utilisateur est déplacé de Skype entreprise Online vers Skype entreprise Server en local, ou vice versa.</span><span class="sxs-lookup"><span data-stu-id="8d03b-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="8d03b-p107">L’importation des données d’un magasin de contacts unifié à partir d’une base de données de sauvegarde peut endommager les données du magasin de contacts unifié et les données utilisateur si le mode de magasin de contacts unifié a été modifié entre l’exportation et l’importation. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8d03b-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="8d03b-153">Si vous exportez des listes de contacts avant la migration des contacts de l’utilisateur vers Exchange 2013, puis après la migration, vous importez les mêmes données, les données et les listes de contacts du magasin de contacts unifié seront corrompues.</span><span class="sxs-lookup"><span data-stu-id="8d03b-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="8d03b-154">Si vous exportez les données des utilisateurs après avoir migré les utilisateurs vers Exchange 2013, restaurez la migration, puis, pour une raison quelconque, vous importez les données à partir de la migration, les données et les listes de contacts du magasin de contacts unifié seront endommagées.</span><span class="sxs-lookup"><span data-stu-id="8d03b-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="8d03b-155">Avant de déplacer une boîte aux lettres Exchange à partir d’Exchange 2013 vers Exchange 2010, l’administrateur Exchange doit s’assurer que l’administrateur de Skype entreprise Server a préalablement restauré les contacts de l’utilisateur de Skype entreprise à partir d’Exchange 2013 vers Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="8d03b-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="8d03b-156">Pour restaurer des contacts de magasin de contacts unifiés dans Skype entreprise Server, reportez-vous à la procédure «pour restaurer des contacts de magasin de contacts unifiés à partir d’Exchange 2013 vers Skype entreprise Server» plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="8d03b-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="8d03b-157">**Pour restaurer des contacts de l’utilisateur, procédez comme suit:** Si vous utilisez l’applet de action **Move-Csuser** pour déplacer des utilisateurs entre Skype entreprise Server 2015 et Lync Server 2010, vous pouvez ignorer ces étapes dans la mesure où l’applet de l’applet de **déplacement-Csuser** annule automatiquement le magasin de contacts unifié lors du déplacement des utilisateurs de Skype Business Server 2015 vers Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8d03b-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="8d03b-158">La migration **-Csuser** n’entraîne pas la désactivation de la stratégie de magasin de contacts unifiée, de sorte que la migration vers le magasin de contacts unifié se reproduit si l’utilisateur est reculé dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8d03b-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

