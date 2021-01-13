---
title: 'Déployer un magasin de contacts unifié dans Skype Entreprise Server '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Résumé : Activez le magasin de contacts unifié dans Skype Entreprise Server.'
ms.openlocfilehash: 7bf4dcb884dc9fecee15209f5acb563fce9efd43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812554"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="d0224-103">Déployer un magasin de contacts unifié dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d0224-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="d0224-104">**Résumé :** Activez le magasin de contacts unifié dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d0224-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="d0224-105">L’activation du magasin de contacts unifié dans Skype Entreprise Server ne nécessite aucun paramètre de topologie.</span><span class="sxs-lookup"><span data-stu-id="d0224-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="d0224-106">Pour activer le magasin de contacts unifié pour les utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="d0224-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="d0224-107">La stratégie du magasin de contacts unifié est activée (par défaut).</span><span class="sxs-lookup"><span data-stu-id="d0224-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="d0224-108">Les utilisateurs se connectent avec Skype Entreprise au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="d0224-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="d0224-109">Une fois les contacts d’un utilisateur migrés, ce qui se produit automatiquement lorsqu’un utilisateur se connecte avec Skype Entreprise, l’utilisateur peut accéder à ses contacts Skype Entreprise et les gérer à partir de Skype Entreprise, Outlook 2013 ou Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="d0224-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="d0224-110">L’utilisateur n’a pas besoin d’être connecté à Skype Entreprise pour gérer ses contacts à partir d’Outlook ou Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="d0224-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d0224-111">Si un utilisateur se connecte à partir de Skype Entreprise après la migration, les contacts et les groupes sont disponibles et à jour, mais l’utilisateur ne peut pas gérer (c’est-à-dire, ajouter, supprimer, déplacer, baliser, supprimer ou modifier) ces contacts.</span><span class="sxs-lookup"><span data-stu-id="d0224-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="d0224-112">Activer les utilisateurs pour le magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="d0224-112">Enable users for unified contact store</span></span>

<span data-ttu-id="d0224-113">Lorsque vous déployez Skype Entreprise Server et publiez la topologie, le magasin de contacts unifié est activé par défaut pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d0224-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="d0224-114">Vous n’avez pas besoin d’action supplémentaire pour activer le magasin de contacts unifié après avoir déployé Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d0224-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="d0224-115">Cependant, vous pouvez utiliser l’applet de commande **Set-CsUserServicesPolicy** pour personnaliser les utilisateurs pour lesquels le magasin de contact unifié est disponible.</span><span class="sxs-lookup"><span data-stu-id="d0224-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="d0224-116">Vous pouvez activer cette fonctionnalité globalement, par site, par locataire, par personne ou par groupes de personnes.</span><span class="sxs-lookup"><span data-stu-id="d0224-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="d0224-117">Pour activer les utilisateurs pour le magasin de contact unifié</span><span class="sxs-lookup"><span data-stu-id="d0224-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="d0224-118">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype** Entreprise, puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="d0224-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d0224-119">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0224-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="d0224-120">Pour activer le magasin de contacts unifié globalement pour tous les utilisateurs de Skype Entreprise Server, inter-cmdlet suivante dans l Windows PowerShell interface de ligne de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d0224-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="d0224-121">Pour activer le magasin de contacts unifié pour les utilisateurs d’un site spécifique, à l’invite, tapez :</span><span class="sxs-lookup"><span data-stu-id="d0224-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="d0224-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d0224-122">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="d0224-123">Pour activer le magasin de contacts unifié par client, à l’invite, tapez :</span><span class="sxs-lookup"><span data-stu-id="d0224-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="d0224-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d0224-124">For example:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="d0224-125">Pour activer le magasin de contacts unifié pour des utilisateurs spécifiques, à l’invite, tapez :</span><span class="sxs-lookup"><span data-stu-id="d0224-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="d0224-126">Vous pouvez également utiliser un alias utilisateur ou un URI SIP à la place du nom d’affichage de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d0224-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="d0224-127">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d0224-127">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="d0224-128">Dans l’exemple précédant, la première commande crée une nouvelle stratégie par utilisateur appelée Utilisateurs UCS activés avec l’indicateur UcsAllowed défini à True.</span><span class="sxs-lookup"><span data-stu-id="d0224-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="d0224-129">La seconde commande affecte la stratégie à l’utilisateur avec le nom complet Ken Myer, ce qui signifie que Ken Myer est désormais activé pour le magasin de contact unifié.</span><span class="sxs-lookup"><span data-stu-id="d0224-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="d0224-130">Migrer des utilisateurs vers un magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="d0224-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="d0224-131">Les contacts d’un utilisateur sont transférés automatiquement vers le serveur Exchange 2013 quand :</span><span class="sxs-lookup"><span data-stu-id="d0224-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="d0224-132">une stratégie de services utilisateur dont le paramètre UcsAllowed a la valeur True a été attribuée à l’utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="d0224-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="d0224-133">A été mis en service avec une boîte aux lettres Exchange 2013 et s’y est déjà inscrit au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="d0224-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="d0224-134">l'utilisateur se connecte à l'aide d'un client riche Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d0224-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="d0224-135">Si l’utilisateur se connecte avec un client Lync ou un client précédent, ou si l’utilisateur n’est pas connecté à un serveur Exchange 2013, la stratégie de services d’utilisateurs est ignorée et les contacts de l’utilisateur restent dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d0224-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="d0224-136">Déterminez si les contacts d’un utilisateur ont été transférés en utilisant l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0224-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="d0224-137">Vérifiez la clé de Registre suivante sur l’ordinateur client :</span><span class="sxs-lookup"><span data-stu-id="d0224-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="d0224-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ URL SIP \> \UCS</span><span class="sxs-lookup"><span data-stu-id="d0224-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="d0224-139">Si les contacts de l’utilisateur sont stockés dans Exchange 2013, cette clé contient la valeur InUCSMode avec la valeur 2165.</span><span class="sxs-lookup"><span data-stu-id="d0224-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="d0224-140">Exécutez l’applet de commande **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="d0224-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="d0224-141">Sur la ligne de commande Skype Entreprise Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="d0224-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="d0224-142">Si l’exécution de la commande **Test-CsUnifiedContactStore** s’est déroulée correctement, les contacts de l’utilisateur ont été migrés vers le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="d0224-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="d0224-143">Roll Back Migrated Users</span><span class="sxs-lookup"><span data-stu-id="d0224-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="d0224-144">Si vous avez besoin de la fonctionnalité de magasin de contacts unifié, revenir aux contacts uniquement si vous déplacez l’utilisateur vers Exchange 2010 ou Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d0224-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="d0224-145">Pour effectuer la restauration, désactivez la stratégie définie pour l’utilisateur, puis exécutez l’applet de commande **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="d0224-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="d0224-146">Le fait de simplement exécuter **Invoke-CsUcsRollback** ne suffit pas à garantir une restauration permanente ; en effet, si la stratégie n’est pas désactivée, le magasin de contacts unifié continuera d’être transféré.</span><span class="sxs-lookup"><span data-stu-id="d0224-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="d0224-147">Par exemple, si un utilisateur est retourné parce qu’Exchange 2013 est revenir à Exchange 2010, puis que la boîte aux lettres de l’utilisateur est déplacée vers Exchange 2013, la migration du magasin de contacts unifié est lancée à nouveau sept jours après la récupération, tant que le magasin de contacts unifié est toujours activé pour l’utilisateur dans la stratégie des services d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d0224-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="d0224-148">L’cmdlet **Move-CsUser** retourne automatiquement le magasin de contacts de l’utilisateur d’Exchange 2013 vers Skype Entreprise Server dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0224-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="d0224-149">Lorsque les utilisateurs sont déplacés de Skype Entreprise Server vers Microsoft Lync Server 2013 ou Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d0224-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="d0224-150">Lorsque les utilisateurs sont migrés entre les locaux, par exemple lorsqu’un utilisateur est déplacé de Skype Entreprise Online vers Skype Entreprise Server local, ou inversement.</span><span class="sxs-lookup"><span data-stu-id="d0224-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="d0224-p107">L’importation des données d’un magasin de contacts unifié à partir d’une base de données de sauvegarde peut endommager les données du magasin de contacts unifié et les données utilisateur si le mode de magasin de contacts unifié a été modifié entre l’exportation et l’importation. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d0224-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="d0224-153">Si vous exportez des listes de contacts avant la migration des contacts des utilisateurs vers Exchange 2013, puis, après la migration, importez les mêmes données, les données du magasin de contacts unifié et les listes de contacts seront endommagées.</span><span class="sxs-lookup"><span data-stu-id="d0224-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="d0224-154">Si vous exportez des données utilisateur après avoir migré des utilisateurs vers Exchange 2013, revenir à la migration, puis pour une raison quelconque vous importez les données après la migration, les données du magasin de contacts unifié et les listes de contacts seront endommagées.</span><span class="sxs-lookup"><span data-stu-id="d0224-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d0224-155">Avant de déplacer une boîte aux lettres Exchange d’Exchange 2013 vers Exchange 2010, l’administrateur Exchange doit s’assurer que l’administrateur Skype Entreprise Server a d’abord retourné les contacts utilisateur Skype Entreprise Server d’Exchange 2013 vers Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d0224-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="d0224-156">Pour revenir aux contacts du magasin de contacts unifié vers Skype Entreprise Server, consultez la procédure « Pour revenir aux contacts du magasin de contacts unifié d’Exchange 2013 vers Skype Entreprise Server », plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="d0224-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="d0224-157">**Comment récupérer les contacts utilisateur :** Si vous utilisez l';cmdlet **Move-CsUser** pour déplacer des utilisateurs entre Skype Entreprise Server 2015 et Lync Server 2010, vous pouvez ignorer ces étapes, car l';cmdlet **Move-CsUser** a automatiquement pour effet de revenir au magasin de contacts unifié lors du déplacement des utilisateurs de Skype Entreprise Server 2015 vers Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d0224-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="d0224-158">**Move-CsUser** ne désactive pas la stratégie de magasin de contacts unifié, de sorte que la migration vers le magasin de contacts unifié se reproduira si l’utilisateur est revenir à Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d0224-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

