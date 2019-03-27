---
title: 'Déployer le magasin de contacts unifié dans Skype pour Business Server '
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Résumé : Activer le magasin de contacts unifié dans Skype pour Business Server.'
ms.openlocfilehash: 5e7fb34d03459be5066d154e89fa8e27dc060757
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882564"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="85210-103">Déployer le magasin de contacts unifié dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="85210-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="85210-104">**Résumé :** Activer le magasin de contacts unifié dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="85210-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="85210-105">Activation du magasin de contacts unifié dans Skype pour Business Server ne nécessite pas les paramètres de la topologie.</span><span class="sxs-lookup"><span data-stu-id="85210-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="85210-106">Pour activer le magasin de contacts unifié pour les utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="85210-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="85210-107">La stratégie du magasin de contacts unifié est activée (par défaut).</span><span class="sxs-lookup"><span data-stu-id="85210-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="85210-108">Les utilisateurs se connectent avec Skype pour les entreprises au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="85210-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="85210-109">Une fois que les contacts d’un utilisateur ont été migrés, ce qui se produit automatiquement lorsqu’un utilisateur se connecte avec Skype pour les entreprises, l’utilisateur peut accéder et gérer leur Skype de contacts professionnels à partir de Skype pour les professionnels, Outlook 2013 ou Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="85210-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="85210-110">L’utilisateur n’a pas à être connecté à Skype pour les entreprises à gérer leurs contacts dans Outlook ou Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="85210-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="85210-111">Si un utilisateur se connecte en Skype pour les entreprises après la migration, les contacts et les groupes sont disponibles et à jour, mais l’utilisateur ne peut pas gérer (qui est, ajouter, supprimer, déplacer, tag, baliser ou modifier) ces contacts.</span><span class="sxs-lookup"><span data-stu-id="85210-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="85210-112">Activation des utilisateurs pour le magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="85210-112">Enable users for unified contact store</span></span>

<span data-ttu-id="85210-113">Lorsque vous déployez Skype pour Business Server et que vous publiez la topologie, le magasin de contacts unifié est activé pour tous les utilisateurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="85210-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="85210-114">Il est inutile d’aucune action supplémentaire pour activer le magasin de contacts unifié après avoir déployé Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="85210-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="85210-115">Cependant, vous pouvez utiliser l’applet de commande **Set-CsUserServicesPolicy** pour personnaliser les utilisateurs pour lesquels le magasin de contact unifié est disponible.</span><span class="sxs-lookup"><span data-stu-id="85210-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="85210-116">Vous pouvez activer cette fonctionnalité globalement, par site, par locataire, par personne ou par groupes de personnes.</span><span class="sxs-lookup"><span data-stu-id="85210-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="85210-117">Pour activer les utilisateurs pour le magasin de contact unifié</span><span class="sxs-lookup"><span data-stu-id="85210-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="85210-118">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour les entreprises**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="85210-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="85210-119">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="85210-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="85210-120">Pour activer le magasin de contacts unifié globalement pour tous les Skype pour les utilisateurs Business Server, notamment l’applet de commande suivante à l’interface de ligne de commande Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="85210-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="85210-121">Pour activer le magasin de contact unifié pour tous les utilisateurs d’un site spécifique, à l’invite, tapez :</span><span class="sxs-lookup"><span data-stu-id="85210-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="85210-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="85210-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="85210-123">Pour activer le magasin de contact unifié par locataire, à l’invite, tapez :</span><span class="sxs-lookup"><span data-stu-id="85210-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="85210-124">Exemple :</span><span class="sxs-lookup"><span data-stu-id="85210-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="85210-125">Pour activer le magasin de contact unifié pour des utilisateurs spécifiques, à l’invite, tapez :</span><span class="sxs-lookup"><span data-stu-id="85210-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="85210-126">Vous pouvez également utiliser un alias utilisateur ou un URI SIP à la place du nom d’affichage de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="85210-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="85210-127">Exemple :</span><span class="sxs-lookup"><span data-stu-id="85210-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="85210-128">Dans l’exemple précédant, la première commande crée une nouvelle stratégie par utilisateur appelée Utilisateurs UCS activés avec l’indicateur UcsAllowed défini à True.</span><span class="sxs-lookup"><span data-stu-id="85210-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="85210-129">La seconde commande affecte la stratégie à l’utilisateur avec le nom complet Ken Myer, ce qui signifie que Ken Myer est désormais activé pour le magasin de contact unifié.</span><span class="sxs-lookup"><span data-stu-id="85210-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="85210-130">Migration des utilisateurs vers le magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="85210-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="85210-131">Contacts d’un utilisateur sont transférés automatiquement vers le serveur Exchange 2013 lorsque l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="85210-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="85210-132">une stratégie de services utilisateur dont le paramètre UcsAllowed a la valeur True a été attribuée à l’utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="85210-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="85210-133">A été mis en service avec une boîte aux lettres Exchange 2013 et s’est connecté à la boîte aux lettres au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="85210-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="85210-134">Journaux dans à l’aide d’un Skype pour le client riche Business.</span><span class="sxs-lookup"><span data-stu-id="85210-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="85210-135">Si l’utilisateur se connecte avec un client antérieure ou de Lync, ou si l’utilisateur n’est pas connecté à un serveur Exchange 2013, la stratégie de services utilisateur est ignorée et les contacts de l’utilisateur restent dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="85210-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="85210-136">Déterminez si les contacts d’un utilisateur ont été transférés en utilisant l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="85210-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="85210-137">Vérifiez la clé de Registre suivante sur l’ordinateur client :</span><span class="sxs-lookup"><span data-stu-id="85210-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="85210-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span><span class="sxs-lookup"><span data-stu-id="85210-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="85210-139">Si les contacts de l’utilisateur sont stockés dans Exchange 2013, cette clé contient une valeur inucsmode dont la valeur est 2165.</span><span class="sxs-lookup"><span data-stu-id="85210-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="85210-140">Exécutez l’applet de commande **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="85210-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="85210-141">À Skype pour la ligne de commande Business Server Management Shell, tapez :</span><span class="sxs-lookup"><span data-stu-id="85210-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="85210-142">Si l’exécution de la commande **Test-CsUnifiedContactStore** s’est déroulée correctement, les contacts de l’utilisateur ont été migrés vers le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="85210-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="85210-143">Restauration des utilisateurs migrés</span><span class="sxs-lookup"><span data-stu-id="85210-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="85210-144">Si vous avez besoin restaurer le contact unifié magasin fonctionnalité, annuler les contacts uniquement si vous déplacez l’utilisateur vers Exchange 2010 ou Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="85210-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="85210-145">Pour effectuer la restauration, désactivez la stratégie définie pour l’utilisateur, puis exécutez l’applet de commande **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="85210-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="85210-146">La simple exécution de **Invoke-CsUcsRollback** ne suffit pas à garantir une restauration permanente ; en effet, si la stratégie n’est pas désactivée, le magasin de contacts unifié continue d’être transféré.</span><span class="sxs-lookup"><span data-stu-id="85210-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="85210-147">Par exemple, si un utilisateur est annulé, car Exchange 2013 est restaurée vers Exchange 2010, puis la boîte aux lettres est déplacée vers Exchange 2013, la migration de magasin de contacts unifié sera effectuée à nouveau sept jours après la restauration, dans la mesure où stocker de contact unifié est toujours activé pour l’utilisateur dans la stratégie de services utilisateur.</span><span class="sxs-lookup"><span data-stu-id="85210-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="85210-148">L’applet de commande **Move-CsUser** restaure automatiquement magasin de contacts de l’utilisateur à partir d’Exchange 2013 à Skype pour Business Server dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="85210-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="85210-149">Lorsque les utilisateurs sont déplacés de Skype pour Business Server vers Lync Server 2010 ou de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85210-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="85210-150">Lorsque les utilisateurs sont transférés local, par exemple lorsqu’un utilisateur est déplacé de Skype pour Business Online à Skype pour Business Server local, ou vice versa.</span><span class="sxs-lookup"><span data-stu-id="85210-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="85210-p107">L’importation des données d’un magasin de contacts unifié à partir d’une base de données de sauvegarde peut endommager les données du magasin de contacts unifié et les données utilisateur si le mode de magasin de contacts unifié a été modifié entre l’exportation et l’importation. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="85210-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="85210-153">Si vous exportez des listes de contacts avant de contacts des utilisateurs sont migrés vers Exchange 2013 et, après la migration, vous importerez les mêmes données, les données de magasin de contacts unifié et les listes de contacts seront endommagées.</span><span class="sxs-lookup"><span data-stu-id="85210-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="85210-154">Si vous exportez des données utilisateur après la migration des utilisateurs vers Exchange 2013, annuler la migration, puis pour une raison quelconque, vous importez les données d’après la migration, le contact unifié stockent des données et listes de contacts seront endommagées.</span><span class="sxs-lookup"><span data-stu-id="85210-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="85210-155">Avant de déplacer une boîte aux lettres Exchange vers Exchange 2010 à partir d’Exchange 2013, l’administrateur Exchange devez vous assurer que le Skype pour l’administrateur du serveur d’entreprise a tout d’abord restaurée la Skype pour les contacts des utilisateurs Business Server à partir d’Exchange 2013 à Skype pour Serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="85210-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="85210-156">Pour restaurer les contacts de magasin de contacts unifié Skype pour Business Server, consultez la procédure « pour restaurer les contacts du magasin de contacts unifié de Exchange 2013 à Skype pour Business Server » plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="85210-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="85210-157">**Comment restaurer les contacts de l’utilisateur :** Si vous utilisez l’applet de commande **Move-CsUser** pour déplacer des utilisateurs entre Skype pour Business Server 2015 et Lync Server 2010, vous pouvez ignorer ces étapes, car l’applet de commande **Move-CsUser** restaure automatiquement magasin de contacts unifié lorsqu’il déplace les utilisateurs de Skype pour Entreprise 2015 serveur Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="85210-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="85210-158">**Move-CsUser** ne désactive pas la stratégie du magasin de contacts unifié, afin que la migration vers le magasin de contacts unifié se reproduit si l’utilisateur est déplacé vers Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="85210-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

