---
title: 'Lync Server 2013 : l’héritage des autorisations est désactivé sur les conteneurs des ordinateurs, des utilisateurs ou des InetOrgPerson'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd6e20c510c1a26b3fc367c853d08469798ff765
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524321"
---
# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="1aa02-102">L’héritage des autorisations est désactivé sur les conteneurs ordinateurs, utilisateurs ou InetOrgPerson dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa02-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1aa02-103">_**Dernière modification de la rubrique :** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="1aa02-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="1aa02-104">Dans les services de domaine Active Directory verrouillés, les utilisateurs et les objets ordinateur sont souvent placés dans des unités d’organisation (UO) spécifiques dont l’héritage des autorisations est désactivé pour aider à sécuriser la délégation administrative et pour permettre l’utilisation des objets de stratégie de groupe (GPO) pour appliquer des stratégies de sécurité.</span><span class="sxs-lookup"><span data-stu-id="1aa02-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="1aa02-105">Préparation de domaine et activation de serveur définissez les entrées de contrôle d’accès (ACE) requises par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1aa02-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="1aa02-106">Lorsque l’héritage des autorisations est désactivé, les groupes de sécurité Lync Server ne peuvent pas hériter de ces ACE.</span><span class="sxs-lookup"><span data-stu-id="1aa02-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="1aa02-107">Lorsque ces autorisations ne sont pas héritées, les groupes de sécurité Lync Server ne peuvent pas accéder aux paramètres et les deux problèmes suivants se produisent :</span><span class="sxs-lookup"><span data-stu-id="1aa02-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="1aa02-108">Pour administrer les utilisateurs, les InetOrgPersons et les contacts, et pour exploiter les serveurs, les groupes de sécurité Lync Server nécessitent des ACE définies par la procédure de préparation du domaine sur les jeux de propriétés de chaque utilisateur, les communications en temps réel (RTC), la recherche de l’utilisateur RTC et les informations publiques.</span><span class="sxs-lookup"><span data-stu-id="1aa02-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="1aa02-109">Quand l’héritage des autorisations est désactivé, les groupes de sécurité n’héritent pas ces entrées de contrôle d’accès et ne peuvent pas gérer les serveurs ou les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1aa02-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="1aa02-110">Pour détecter les serveurs et les pools, les serveurs exécutant Lync Server s’appuient sur les ACE définies par l’activation sur les objets liés à l’ordinateur, y compris le conteneur Microsoft et l’objet serveur.</span><span class="sxs-lookup"><span data-stu-id="1aa02-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="1aa02-111">Quand l’héritage des autorisations est désactivé, les groupes de sécurité, les serveurs et les pools n’héritent pas de ces entrées de contrôle d’accès et ne peuvent pas les exploiter.</span><span class="sxs-lookup"><span data-stu-id="1aa02-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="1aa02-112">Pour résoudre ces problèmes, Lync Server fournit l’applet **de commande Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="1aa02-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="1aa02-113">Cette applet de commande définit les ACE Lync Server requises directement sur un conteneur et des unités d’organisation spécifiés, ainsi que sur les objets dans le conteneur ou l’unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="1aa02-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="1aa02-114">Définir des autorisations sur les objets Utilisateur, InetOrgPerson et Contact après exécution de la préparation du domaine</span><span class="sxs-lookup"><span data-stu-id="1aa02-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="1aa02-115">Dans un environnement Active Directory verrouillé dans lequel l’héritage des autorisations est désactivé, la préparation du domaine ne définit pas les entrées de contrôle d’accès nécessaires sur les conteneurs ou les unités d’organisation abritant des objets Utilisateur ou InetOrgPerson à l’intérieur du domaine.</span><span class="sxs-lookup"><span data-stu-id="1aa02-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="1aa02-116">Dans ce cas, vous devez exécuter l’applet de commande **Grant-CsOuPermission** sur chaque conteneur ou unité d’organisation contenant les objets Utilisateur ou InetOrgPerson pour lesquels l’héritage des autorisations est désactivé.</span><span class="sxs-lookup"><span data-stu-id="1aa02-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="1aa02-117">Si vous avez déployé une topologie de forêt centrale, vous devez également exécuter cette procédure sur les conteneurs ou les unités d’organisation qui détiennent des objets Contact.</span><span class="sxs-lookup"><span data-stu-id="1aa02-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="1aa02-118">Pour plus d’informations sur les topologies de forêt centrale, voir [topologies Active Directory prises en charge dans Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="1aa02-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="1aa02-119">Le paramètre ObjectType précise le type d’objet.</span><span class="sxs-lookup"><span data-stu-id="1aa02-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="1aa02-120">Le paramètre OU spécifie l’unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="1aa02-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="1aa02-121">Cette applet de commande ajoute directement les entrées de contrôle d’accès requises sur les conteneurs ou les unités d’organisation spécifiées et les objets Utilisateur et InetOrgPerson qu’ils contiennent.</span><span class="sxs-lookup"><span data-stu-id="1aa02-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="1aa02-122">Si l’unité d’organisation sur laquelle cette commande est exécutée comporte des unités d’organisation enfants avec des objets utilisateur ou InetOrgPerson, les autorisations ne sont pas appliquées sur ces unités.</span><span class="sxs-lookup"><span data-stu-id="1aa02-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="1aa02-123">Vous devrez exécuter la commande sur chaque unité d’organisation enfant individuellement.</span><span class="sxs-lookup"><span data-stu-id="1aa02-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="1aa02-124">Il s’agit d’un scénario courant avec les déploiements d’hébergement Lync, par exemple l’unité d’organisation parente, les clients OCS, DC = CONTOSO, DC = LOCAL et Child OU = Tenant1, OU = OCS clients, DC = CONTOSO, DC = LOCAL.</span><span class="sxs-lookup"><span data-stu-id="1aa02-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="1aa02-125">Pour exécuter cette applet de commande, vous devez bénéficier de droits d’utilisateur identiques à ceux utilisés en tant que membre du groupe Administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="1aa02-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="1aa02-126">Si les ACE de l’utilisateur authentifié ont également été supprimées dans l’environnement verrouillé, vous devez accorder à ce compte les ACE accès en lecture sur les conteneurs ou unités d’organisation appropriés dans le domaine racine de la forêt, comme décrit dans la rubrique les [autorisations des utilisateurs authentifiés sont supprimées dans Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou utilisez un compte membre du groupe administrateurs de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1aa02-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="1aa02-127">**Pour définir les entrées de contrôle d’accès requises pour les objets Utilisateur, InetOrgPerson et Contact**</span><span class="sxs-lookup"><span data-stu-id="1aa02-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="1aa02-128">Ouvrez une session sur un ordinateur lié au domaine en utilisant un compte qui est membre du groupe Administrateurs de domaine ou doté de droits d’utilisateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="1aa02-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="1aa02-129">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1aa02-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1aa02-130">Générer</span><span class="sxs-lookup"><span data-stu-id="1aa02-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="1aa02-131">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="1aa02-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="1aa02-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1aa02-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="1aa02-133">Dans le fichier journal, recherchez résultat de l' **\<Success\>** exécution à la fin de chaque tâche pour vérifier que les autorisations ont été définies, puis fermez la fenêtre du journal.</span><span class="sxs-lookup"><span data-stu-id="1aa02-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="1aa02-134">Vous pouvez également exécuter la commande suivante pour déterminer si les autorisations ont été définies :</span><span class="sxs-lookup"><span data-stu-id="1aa02-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="1aa02-135">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1aa02-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="1aa02-136">Définir des autorisations sur les objets Ordinateur après exécution de la préparation du domaine</span><span class="sxs-lookup"><span data-stu-id="1aa02-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="1aa02-137">Dans un environnement Active Directory verrouillé dans lequel l’héritage des autorisations est désactivé, la préparation du domaine ne définit pas les entrées de contrôle d’accès nécessaires sur les conteneurs ou les unités d’organisation abritant des objets Ordinateur à l’intérieur du domaine.</span><span class="sxs-lookup"><span data-stu-id="1aa02-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="1aa02-138">Dans ce cas, vous devez exécuter l’applet de commande **Grant-CsOuPermission** sur chaque conteneur ou unité d’organisation dont les ordinateurs exécutent Lync Server et où l’héritage des autorisations est désactivé.</span><span class="sxs-lookup"><span data-stu-id="1aa02-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="1aa02-139">Le paramètre ObjectType précise le type d’objet.</span><span class="sxs-lookup"><span data-stu-id="1aa02-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="1aa02-140">Cette procédure ajoute directement les entrées de contrôle d’accès requises sur les conteneurs spécifiés.</span><span class="sxs-lookup"><span data-stu-id="1aa02-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="1aa02-141">Pour exécuter cette applet de commande, vous devez bénéficier de droits d’utilisateur identiques à ceux utilisés en tant que membre du groupe Administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="1aa02-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="1aa02-142">Si les ACE de l’utilisateur authentifié ont également été supprimées, vous devez accorder à ce compte les ACE accès en lecture-écriture sur les conteneurs appropriés dans le domaine racine de la forêt, comme décrit dans la rubrique les [autorisations des utilisateurs authentifiés sont supprimées dans Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou utilisez un compte membre du groupe administrateurs de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1aa02-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="1aa02-143">**Pour configurer les entrées de contrôle d’accès requises pour les objets Ordinateur**</span><span class="sxs-lookup"><span data-stu-id="1aa02-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="1aa02-144">Ouvrez une session sur l’ordinateur du domaine en utilisant un compte qui est membre du groupe Administrateurs de domaine ou doté de droits d’utilisateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="1aa02-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="1aa02-145">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1aa02-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1aa02-146">Générer</span><span class="sxs-lookup"><span data-stu-id="1aa02-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="1aa02-147">Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="1aa02-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="1aa02-148">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1aa02-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="1aa02-149">Dans l’exemple de fichier journal C : \\ Logs \\OUPermissions.xml, recherchez **\<Success\>** le résultat de l’exécution à la fin de chaque tâche et vérifiez qu’il n’y a pas d’erreurs, puis fermez le journal.</span><span class="sxs-lookup"><span data-stu-id="1aa02-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="1aa02-150">Vous pouvez exécuter l’applet de commande suivante pour tester les autorisations :</span><span class="sxs-lookup"><span data-stu-id="1aa02-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="1aa02-151">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1aa02-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1aa02-152">Si vous exécutez une préparation de domaine sur le domaine racine de la forêt dans un environnement Active Directory verrouillé, sachez que Lync Server doit avoir accès aux conteneurs de schéma et de configuration Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1aa02-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="1aa02-153">Si l’autorisation utilisateur authentifié par défaut est supprimée du schéma ou des conteneurs de configuration dans AD &nbsp; DS, seuls les membres du groupe administrateurs du schéma (pour le conteneur de schéma) ou du groupe administrateurs de l’entreprise (pour le conteneur de configuration) sont autorisés à accéder au conteneur donné.</span><span class="sxs-lookup"><span data-stu-id="1aa02-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="1aa02-154">Étant donné que les Setup.exe, les cmdlets Lync Server Management Shell et le panneau de configuration Lync Server nécessitent un accès à ces conteneurs, la configuration et l’installation des outils d’administration échouent, sauf si l’utilisateur qui exécute l’installation dispose de droits d’utilisateur équivalents à ceux des administrateurs du schéma et des groupes Administrateurs de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1aa02-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="1aa02-155">Pour remédier à cette situation, vous devez octroyer au groupe RTCUniversalGlobalWriteGroup un accès en lecture et en écriture aux conteneurs Schéma et Configuration.</span><span class="sxs-lookup"><span data-stu-id="1aa02-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

