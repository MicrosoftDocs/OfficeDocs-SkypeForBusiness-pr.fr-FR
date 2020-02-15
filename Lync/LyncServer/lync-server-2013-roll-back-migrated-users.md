---
title: 'Lync Server 2013 : restauration des utilisateurs migrés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7398e69e5a02924025d63fc48096244d67c49aeb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="4de99-102">Restaurer les utilisateurs migrés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4de99-102">Roll back migrated users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4de99-103">_**Dernière modification de la rubrique :** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="4de99-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="4de99-104">Si vous devez restaurer la fonctionnalité magasin de contacts unifié, annulez les contacts uniquement si vous redéplacez l’utilisateur vers Exchange 2010 ou Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4de99-104">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="4de99-105">Pour effectuer la restauration, désactivez la stratégie définie pour l’utilisateur, puis exécutez l’applet de commande **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="4de99-105">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="4de99-106">Le fait de simplement exécuter **Invoke-CsUcsRollback** ne suffit pas à garantir une restauration permanente ; en effet, si la stratégie n’est pas désactivée, le magasin de contacts unifié continuera d’être transféré.</span><span class="sxs-lookup"><span data-stu-id="4de99-106">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="4de99-107">Par exemple, si un utilisateur est annulé car Exchange 2013 est restauré vers Exchange 2010, puis la boîte aux lettres de l’utilisateur est déplacée vers Exchange 2013, la migration du magasin de contacts unifié est lancée à nouveau sept jours après la restauration, aussi longtemps que le magasin de contacts unifié est toujours activé pour l’utilisateur dans la stratégie de services d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4de99-107">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4de99-108">L’applet de commande <STRONG>Move-Csuser</STRONG> restaure automatiquement le magasin de contacts de l’utilisateur à partir d’Exchange 2013 vers Lync Server 2013 dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4de99-108">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="4de99-109">Lorsque les utilisateurs sont déplacés de Lync Server 2013 vers Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4de99-109">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="4de99-110">Lorsque les utilisateurs sont migrés sur des sites distants, par exemple lorsqu’un utilisateur est déplacé de Lync Online vers Lync Server 2013 local, ou vice versa.</span><span class="sxs-lookup"><span data-stu-id="4de99-110">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4de99-p102">L’importation des données d’un magasin de contacts unifié à partir d’une base de données de sauvegarde peut endommager les données du magasin de contacts unifié et les données utilisateur si le mode de magasin de contacts unifié a été modifié entre l’exportation et l’importation. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4de99-p102">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="4de99-113">Si vous exportez des listes de contacts avant la migration des contacts des utilisateurs vers Exchange 2013 puis, après la migration, importez les mêmes données, les données du magasin de contacts unifié et les listes de contacts sont endommagées.</span><span class="sxs-lookup"><span data-stu-id="4de99-113">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="4de99-114">Si vous exportez les données UserData après avoir migré les utilisateurs vers Exchange 2013, restaurez la migration, puis, pour une raison quelconque, vous importez les données à partir de après la migration, les données du magasin de contacts unifié et les listes de contacts sont endommagées.</span><span class="sxs-lookup"><span data-stu-id="4de99-114">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4de99-115">Avant de déplacer une boîte aux lettres Exchange d’Exchange 2013 vers Exchange 2010, l’administrateur Exchange doit s’assurer que l’administrateur de Lync Server a d’abord restauré les contacts de l’utilisateur Lync Server d’Exchange 2013 vers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4de99-115">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="4de99-116">Pour restaurer les contacts du magasin de contacts unifié vers Lync Server, voir procédure « pour restaurer les contacts de magasin de contacts unifiés à partir d’Exchange 2013 vers Lync Server 2013 », plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="4de99-116">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="4de99-117">La procédure suivante explique comment restaurer les contacts des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4de99-117">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="4de99-118">Si vous utilisez l’applet de commande **Move-Csuser** pour déplacer des utilisateurs entre lync Server 2013 et lync Server 2010, vous pouvez ignorer ces étapes car l’applet de commande **Move-Csuser** annule automatiquement Unifed magasin de contacts lorsqu’il déplace les utilisateurs de Lync Server 2013 vers Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4de99-118">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="4de99-119">**Move-Csuser** ne désactive pas la stratégie de magasin de contacts unifiée, de sorte que la migration vers le magasin de contacts unifié se répétera si l’utilisateur est ramené à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4de99-119">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="4de99-120">Pour restaurer les contacts utilisateur de Lync Server 2013 vers Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4de99-120">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="4de99-121">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4de99-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4de99-p105">Désactivez le magasin de contacts unifié des utilisateurs à restaurer afin que ces derniers ne soient pas de nouveau transférés après la restauration. (Effectuez cette étape uniquement si vous souhaitez empêcher tout transfert ultérieure des utilisateurs.) Pour désactiver le magasin de contacts unifié d’utilisateurs spécifiques, sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="4de99-p105">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. (Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="4de99-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4de99-124">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="4de99-125">Avant de transférer un utilisateur de Lync Server 2013 vers Lync Server 2010, restaurez la liste de contacts pour les utilisateurs spécifiés sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4de99-125">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4de99-126">Si cette étape est omise, la liste de contacts sera perdue.</span><span class="sxs-lookup"><span data-stu-id="4de99-126">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="4de99-p106">Restaurez les utilisateurs spécifiés. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="4de99-p106">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="4de99-129">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4de99-129">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4de99-p107">Nous vous recommandons de ne pas utiliser l’option –Force pour forcer la restauration. Si vous le faites, les contacts des utilisateurs seront perdus.</span><span class="sxs-lookup"><span data-stu-id="4de99-p107">We do not recommend using the –Force option to force the rollback. If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="4de99-132">Pour restaurer les contacts du magasin de contacts unifié de Microsoft Exchange 2013 vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4de99-132">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="4de99-133">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4de99-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4de99-p108">Désactivez le magasin de contacts unifié des utilisateurs à restaurer afin que ces derniers ne soient pas de nouveau transférés après la restauration. Pour désactiver le magasin de contacts unifié d’utilisateurs spécifiques, sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="4de99-p108">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="4de99-136">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4de99-136">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="4de99-p109">Restaurez les utilisateurs spécifiés. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="4de99-p109">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="4de99-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4de99-139">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4de99-140">Vous devez d’abord restaurer l’utilisateur Lync Server, puis déplacer la boîte aux lettres Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="4de99-140">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="4de99-141">L’administrateur Exchange ne peut pas restaurer Exchange tant que la restauration de Lync Server n’est pas terminée.</span><span class="sxs-lookup"><span data-stu-id="4de99-141">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="4de99-142">Nous vous recommandons de ne pas utiliser l’option –Force pour forcer la restauration.</span><span class="sxs-lookup"><span data-stu-id="4de99-142">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="4de99-143">Si vous le faites, les contacts des utilisateurs seront perdus.</span><span class="sxs-lookup"><span data-stu-id="4de99-143">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="4de99-144">Une fois que vous avez restauré l’utilisateur sur Lync Server, l’administrateur Exchange peut restaurer l’utilisateur Exchange à partir d’Exchange 2013 vers Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="4de99-144">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

