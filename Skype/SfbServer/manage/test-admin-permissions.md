---
title: Test des autorisations d’administrateur dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Comment tester les autorisations d’administrateur dans Skype Entreprise Server
ms.openlocfilehash: 535911c26bac5e3f1dadb2c8d59cffe82dc20c7a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122398"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="ab5b2-103">Test des autorisations d’administrateur dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ab5b2-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="ab5b2-104">Planification de vérification</span><span class="sxs-lookup"><span data-stu-id="ab5b2-104">Verification schedule</span></span>|<span data-ttu-id="ab5b2-105">Après le déploiement initial de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="ab5b2-106">Si nécessaire si des problèmes liés aux autorisations surviennent.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="ab5b2-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="ab5b2-107">Testing tool</span></span>|<span data-ttu-id="ab5b2-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab5b2-108">Windows PowerShell</span></span>|
|<span data-ttu-id="ab5b2-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="ab5b2-109">Permissions required</span></span>|<span data-ttu-id="ab5b2-110">Lorsqu’ils sont exécutés localement à l’aide de Skype Entreprise Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="ab5b2-111">Lorsqu’il est exécuté à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui disposent de l’autorisation d’exécuter la cmdlet Test-CsOUPermission commande.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="ab5b2-112">Pour voir la liste de tous les rôles RBAC qui peuvent utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="ab5b2-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="ab5b2-113">Get-CsAdminRole Where-Object \| {$_. Cmdlets -match « Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="ab5b2-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="ab5b2-114">Description</span><span class="sxs-lookup"><span data-stu-id="ab5b2-114">Description</span></span>

<span data-ttu-id="ab5b2-115">Lorsque vous installez Skype Entreprise Server, l’une des tâches effectuées par le programme d’installation donne au groupe RTCUniversalUserAdmins les autorisations Active Directory nécessaires pour gérer les utilisateurs, les ordinateurs, les contacts, les contacts d’application et les personnes InetOrg.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="ab5b2-116">Si vous avez désactivé l’héritage des autorisations dans Active Directory, le programme d’installation ne pourra pas attribuer ces autorisations.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="ab5b2-117">Par conséquent, les membres du groupe RTCUniversalUserAdmins ne pourront pas gérer les entités Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="ab5b2-118">Ces privilèges de gestion seront uniquement disponibles pour les administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="ab5b2-119">LTest-CsOUPermission cmdlet vérifie que les autorisations requises pour gérer les utilisateurs, les ordinateurs et d’autres objets sont définies sur un conteneur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="ab5b2-120">Si ces autorisations ne sont pas définies, vous pouvez résoudre ce problème en exécutant [l’cmdlet Grant-CsOUPermission](/powershell/module/skype/Grant-CsOUPermission).</span><span class="sxs-lookup"><span data-stu-id="ab5b2-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="ab5b2-121">Notez Grant-CsOUPermission pouvez uniquement attribuer des autorisations aux membres du groupe RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="ab5b2-122">Vous ne pouvez pas utiliser cette cmdlet pour accorder des autorisations à un utilisateur ou un groupe arbitraire.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="ab5b2-123">Si vous souhaitez qu’un autre utilisateur ou groupe soit autorisé à gérer les utilisateurs, vous devez ajouter cet utilisateur (ou groupe) au groupe RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="ab5b2-124">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="ab5b2-124">Running the test</span></span>

<span data-ttu-id="ab5b2-125">Pour vérifier que les autorisations de gestion sont définies sur un conteneur, exécutez la cmdlet Test-CsOUPermission suivie du nom du conteneur et du type d’autorisations que vous vérifiez.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="ab5b2-126">Par exemple, cette commande vérifie si les autorisations utilisateur sont définies sur l’UO ou=Redmond,dc=litwareinc,dc=com :</span><span class="sxs-lookup"><span data-stu-id="ab5b2-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="ab5b2-127">Pour vérifier plusieurs autorisations à l’aide d’une seule commande, insérez chaque type d’autorisation entre guillemets, puis séparez ces types par des virgules.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="ab5b2-128">Par exemple, cette commande vérifie les autorisations des utilisateurs, des ordinateurs et des contacts :</span><span class="sxs-lookup"><span data-stu-id="ab5b2-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="ab5b2-129">Pour plus d’informations, voir la [rubrique d’aide Test-CsOUPermission cmdlet .](/powershell/module/skype/test-csoupermission)</span><span class="sxs-lookup"><span data-stu-id="ab5b2-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ab5b2-130">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="ab5b2-130">Determining success or failure</span></span>

<span data-ttu-id="ab5b2-131">Si les autorisations requises ont déjà été définies, Test-CsOUPermission renvoyer une réponse en un mot :</span><span class="sxs-lookup"><span data-stu-id="ab5b2-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="ab5b2-132">Vrai</span><span class="sxs-lookup"><span data-stu-id="ab5b2-132">True</span></span>

<span data-ttu-id="ab5b2-133">Si les autorisations requises ne sont pas définies, Test-CsOUPermission renvoyer la valeur False.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="ab5b2-134">Vous de devez peut-être rechercher un moment pour trouver cette valeur.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="ab5b2-135">Il est généralement incorporé dans plusieurs avertissements qui l’accompagnent.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="ab5b2-136">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ab5b2-136">For example:</span></span>

<span data-ttu-id="ab5b2-137">AVERTISSEMENT : entrée de contrôle d’accès (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendants ; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="ab5b2-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="ab5b2-138">AVERTISSEMENT : les entrées de contrôle d’accès sur l’objet « OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com » ne sont pas prêtes.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="ab5b2-139">False</span><span class="sxs-lookup"><span data-stu-id="ab5b2-139">False</span></span> 

<span data-ttu-id="ab5b2-140">AVERTISSEMENT : le traitement « Test-CsOUPermission » s’est terminé avec des avertissements.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="ab5b2-141">« 2 » avertissements ont été enregistrés au cours de cette run.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="ab5b2-142">AVERTISSEMENT : des résultats détaillés sont à l'C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ab5b2-143">Raisons pour lesquelles le test a peut-être échoué</span><span class="sxs-lookup"><span data-stu-id="ab5b2-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="ab5b2-144">Si Test-CsOUPermission échoue, cela signifie généralement que l’autorisation spécifiée n’a pas été attribuée au groupe RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="ab5b2-145">Vous pouvez résoudre ce problème et attribuer les autorisations requises à l’aide Grant-CsOUPermission cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ab5b2-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="ab5b2-146">Par exemple, cette commande accorde des autorisations d’unité d’unité d’utilisateur pour les utilisateurs, les contacts et inetOrgPersons au groupe RTCUniversalUserAdmins :</span><span class="sxs-lookup"><span data-stu-id="ab5b2-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="ab5b2-147">Pour plus d’informations, voir la [rubrique d’aide Test-CsOUPermission cmdlet .](/powershell/module/skype/test-csoupermission)</span><span class="sxs-lookup"><span data-stu-id="ab5b2-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](/powershell/module/skype/test-csoupermission).</span></span>