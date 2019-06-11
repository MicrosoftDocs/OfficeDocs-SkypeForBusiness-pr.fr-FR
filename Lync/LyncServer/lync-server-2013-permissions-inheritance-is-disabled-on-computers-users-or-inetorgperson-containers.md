---
title: 'Lync Server 2013 : Désactivation de l’héritage des autorisations sur les conteneurs des objets Ordinateur, Utilisateur ou InetOrgPerson'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73692539fb5dda38446ffddccbe35c8d366e2d67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="045d2-102">Désactivation de l’héritage des autorisations sur les conteneurs des objets Ordinateur, Utilisateur ou InetOrgPerson dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="045d2-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="045d2-103">_**Dernière modification de la rubrique:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="045d2-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="045d2-104">Dans les services de domaine Active Directory (AD DS) verrouillés, les utilisateurs et les objets d’ordinateur sont souvent placés dans des unités d’organisation spécifiques (UO) avec l’héritage des autorisations désactivé pour sécuriser la délégation d’administration et permettre l’utilisation des objets de stratégie de groupe (GPO). pour appliquer les stratégies de sécurité.</span><span class="sxs-lookup"><span data-stu-id="045d2-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="045d2-105">Préparation du domaine et activation du serveur définissez les entrées de contrôle d’accès (ACE) requises par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="045d2-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="045d2-106">Lorsque l’héritage des autorisations est désactivé, les groupes de sécurité du serveur Lync ne peuvent pas hériter de ces ACE.</span><span class="sxs-lookup"><span data-stu-id="045d2-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="045d2-107">Lorsque ces autorisations ne sont pas héritées, les groupes de sécurité du serveur Lync ne peuvent pas accéder aux paramètres, et les deux problèmes suivants peuvent se produire:</span><span class="sxs-lookup"><span data-stu-id="045d2-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="045d2-108">Pour gérer les utilisateurs, les InetOrgPersons, les contacts et les serveurs, les groupes de sécurité du serveur Lync requièrent des entrées ACE définies par la procédure de préparation du domaine sur les jeux de propriétés de chaque utilisateur, de communication en temps réel (RTC), de recherche d’utilisateurs RTC et d’informations publiques. .</span><span class="sxs-lookup"><span data-stu-id="045d2-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="045d2-109">Lorsque l’héritage des autorisations est désactivé, les groupes de sécurité n’héritent pas de ces ACE et ne peuvent pas gérer les serveurs ou les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="045d2-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="045d2-110">Pour détecter les serveurs et les pools, les serveurs exécutant Lync Server dépendent des ACE définies par l’activation sur les objets liés aux ordinateurs, dont le conteneur et l’objet serveur Microsoft.</span><span class="sxs-lookup"><span data-stu-id="045d2-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="045d2-111">Lorsque l’héritage des autorisations est désactivé, les groupes de sécurité, les serveurs et les pools n’héritent pas de ces ACE et ne peuvent pas bénéficier de ces ACE.</span><span class="sxs-lookup"><span data-stu-id="045d2-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="045d2-112">Pour résoudre ces problèmes, Lync Server fournit l’applet **de passe Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="045d2-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="045d2-113">Ce cmdlet définit les ACE serveur Lync requis directement sur un conteneur et des unités d’organisation et des objets au sein du conteneur ou de l’unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="045d2-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="045d2-114">Définir des autorisations pour les objets utilisateur, InetOrgPerson et contact après l’exécution de la préparation du domaine</span><span class="sxs-lookup"><span data-stu-id="045d2-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="045d2-115">Dans un environnement Active Directory verrouillé dans lequel l’héritage des autorisations est désactivé, la préparation du domaine ne définit pas les ACE nécessaires sur les conteneurs ou les unités d’organisation qui contiennent des utilisateurs ou des objets InetOrgPerson au sein du domaine.</span><span class="sxs-lookup"><span data-stu-id="045d2-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="045d2-116">Dans ce cas, vous devez exécuter l’applet de passe **Grant-CsOuPermission** sur chaque conteneur ou unité d’organisation qui comporte des objets utilisateur ou InetOrgPerson pour lesquels l’héritage des autorisations est désactivé.</span><span class="sxs-lookup"><span data-stu-id="045d2-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="045d2-117">Si vous disposez d’une topologie de forêt centrale, vous devez également effectuer cette procédure sur les conteneurs ou les unités d’organisation qui contiennent des objets de contact.</span><span class="sxs-lookup"><span data-stu-id="045d2-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="045d2-118">Pour plus d’informations sur les topologies de forêt centralisées, voir [topologies Active Directory prises en charge dans Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="045d2-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="045d2-119">Le paramètre typeobjet spécifie le type d’objet.</span><span class="sxs-lookup"><span data-stu-id="045d2-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="045d2-120">Le paramètre UO spécifie l’unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="045d2-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="045d2-121">Cette applet de demande ajoute les entrées ACE requises directement dans les conteneurs ou UO spécifiques et dans le conteneur.</span><span class="sxs-lookup"><span data-stu-id="045d2-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="045d2-122">Si l’unité d’organisation sur laquelle cette commande est exécutée possède des unités d’organisation enfants avec des objets utilisateur ou InetOrgPerson, les autorisations ne sont pas appliquées sur celles-ci.</span><span class="sxs-lookup"><span data-stu-id="045d2-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="045d2-123">Vous devez exécuter la commande sur chaque UO enfant individuellement.</span><span class="sxs-lookup"><span data-stu-id="045d2-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="045d2-124">Il s’agit d’un scénario courant avec des déploiements d’hébergement Lync, par exemple, des UO parentes, DC = CONTOSO, DC = LOCAL et Child UO = premier client, UO = clients OCS, DC = CONTOSO, DC = LOCAL.</span><span class="sxs-lookup"><span data-stu-id="045d2-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="045d2-125">Pour exécuter cette cmdlet, vous devez disposer des droits d’utilisateur pour l’appartenance au groupe administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="045d2-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="045d2-126">Si les entrées ACE de l’utilisateur authentifié ont également été supprimées de l’environnement verrouillé, vous devez accorder à ce compte des ACE d’accès en lecture sur les conteneurs appropriés ou les UO dans le domaine racine de la forêt, comme décrit dans la section [les autorisations des utilisateurs authentifiés sont supprimées dans Lync. Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou utiliser un compte membre du groupe administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="045d2-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="045d2-127">**Pour définir les entrées ACE requises pour les objets utilisateur, InetOrgPerson et contact**</span><span class="sxs-lookup"><span data-stu-id="045d2-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="045d2-128">Connectez-vous à un ordinateur joint au domaine avec un compte membre du groupe administrateurs de domaine ou qui dispose de droits d’utilisateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="045d2-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="045d2-129">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="045d2-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="045d2-130">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="045d2-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="045d2-131">Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.</span><span class="sxs-lookup"><span data-stu-id="045d2-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="045d2-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="045d2-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="045d2-133">Dans le fichier journal, recherchez le résultat d’exécution \*\* \<réussie\> \*\* à la fin de chaque tâche pour vérifier que les autorisations ont été définies, puis fermez la fenêtre du journal.</span><span class="sxs-lookup"><span data-stu-id="045d2-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="045d2-134">Vous pouvez utiliser la commande suivante pour déterminer si les autorisations ont été définies:</span><span class="sxs-lookup"><span data-stu-id="045d2-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="045d2-135">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="045d2-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="045d2-136">Définir des autorisations pour les objets ordinateur après l’exécution de la préparation du domaine</span><span class="sxs-lookup"><span data-stu-id="045d2-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="045d2-137">Dans un environnement Active Directory verrouillé dans lequel l’héritage des autorisations est désactivé, la préparation du domaine ne définit pas les ACE nécessaires sur les conteneurs ou les unités d’organisation qui contiennent des objets d’ordinateur au sein du domaine.</span><span class="sxs-lookup"><span data-stu-id="045d2-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="045d2-138">Dans ce cas, vous devez exécuter l’applet de passe **Grant-CsOuPermission** sur chaque conteneur ou unité d’organisation qui comporte des ordinateurs exécutant Lync Server et sur lequel l’héritage des autorisations est désactivé.</span><span class="sxs-lookup"><span data-stu-id="045d2-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="045d2-139">Le paramètre typeobjet spécifie le type d’objet.</span><span class="sxs-lookup"><span data-stu-id="045d2-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="045d2-140">Cette procédure ajoute les entrées ACE requises directement sur les conteneurs spécifiés.</span><span class="sxs-lookup"><span data-stu-id="045d2-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="045d2-141">Pour exécuter cette cmdlet, vous devez disposer des droits d’utilisateur pour l’appartenance au groupe administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="045d2-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="045d2-142">Si les ACE des utilisateurs authentifiés ont été supprimées, vous devez accorder ce compte aux entrées ACE d’accès en lecture sur les conteneurs pertinents dans le domaine racine de la forêt, comme décrit dans la section [les autorisations des utilisateurs authentifiés sont supprimées dans Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) ou utiliser un compte qui est a membre du groupe administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="045d2-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="045d2-143">**Pour définir les entrées ACE requises pour les objets ordinateur**</span><span class="sxs-lookup"><span data-stu-id="045d2-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="045d2-144">Connectez-vous à l’ordinateur du domaine avec un compte membre du groupe administrateurs de domaine ou qui dispose de droits d’utilisateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="045d2-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="045d2-145">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="045d2-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="045d2-146">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="045d2-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="045d2-147">Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.</span><span class="sxs-lookup"><span data-stu-id="045d2-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="045d2-148">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="045d2-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="045d2-149">Dans l’exemple de fichier journal C\\:\\enregistre OUPermissions. xml, vous devez chercher \*\* \<le\> \*\* résultat d’exécution réussie à la fin de chaque tâche et vérifier qu’il n’y a aucune erreur, puis fermer le journal.</span><span class="sxs-lookup"><span data-stu-id="045d2-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="045d2-150">Vous pouvez exécuter l’applet de commande suivante pour tester les autorisations:</span><span class="sxs-lookup"><span data-stu-id="045d2-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="045d2-151">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="045d2-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="045d2-152">Si vous exécutez une préparation de domaine sur le domaine racine de la forêt dans un environnement Active Directory verrouillé, sachez que Lync Server doit avoir accès au schéma Active Directory et aux conteneurs de configuration.</span><span class="sxs-lookup"><span data-stu-id="045d2-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="045d2-153">Si l’autorisation utilisateur authentifié par défaut est supprimée du schéma ou des conteneurs de configuration dans&nbsp;AD DS, seuls les membres du groupe administrateurs de schéma (pour le conteneur de schéma) ou des administrateurs d’entreprise (pour le conteneur de configuration) sont autorisés à Accédez au conteneur donné.</span><span class="sxs-lookup"><span data-stu-id="045d2-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="045d2-154">Dans la mesure où les applets de commande Setup. exe, Lync Server Management Shell et le panneau de configuration de Lync Server requièrent l’accès à ces conteneurs, la configuration et l’installation des outils d’administration échouent sauf si l’utilisateur qui exécute l’installation dispose de droits d’utilisateur équivalents au schéma Appartenance au groupe administrateurs et administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="045d2-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="045d2-155">Pour remédier à ce problème, vous devez accorder au groupe RTCUniversalGlobalWriteGroup l’accès en lecture, en écriture au schéma et aux conteneurs de configuration.</span><span class="sxs-lookup"><span data-stu-id="045d2-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

