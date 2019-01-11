---
title: Gérer l’application des équipes de votre organisation dans Microsoft Teams
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 1/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment configurer et gérer l’application des déplacements dans les équipes pour les travailleurs firstline dans votre organisation.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fdd9c47e54c9ce51e736363eb47227614824a4c
ms.sourcegitcommit: 768c7b5f0aaa4b38a0b98c7c9ff904ffedd2e9b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2019
ms.locfileid: "27893356"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="fbcfd-103">Gérer l’application des équipes de votre organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fbcfd-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fbcfd-104">Effet 2019, octobre 1, Microsoft StaffHub sera être retirée.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="fbcfd-105">Nous créons StaffHub fonctionnalités, notamment la gestion de tâches et calendrier dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-105">We're building StaffHub capabilities, including schedule and task management, into Microsoft Teams.</span></span> <span data-ttu-id="fbcfd-106">Des fonctionnalités supplémentaires pour les travailleurs firstline mettra en place pour les équipes au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-106">Additional capabilities for firstline workers will roll out to Teams over time.</span></span> <span data-ttu-id="fbcfd-107">Pour plus d’informations, voir [Microsoft StaffHub à retirer](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0).</span><span class="sxs-lookup"><span data-stu-id="fbcfd-107">To learn more, see [Microsoft StaffHub to be retired](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="fbcfd-108">Vue d’ensemble des équipes</span><span class="sxs-lookup"><span data-stu-id="fbcfd-108">Overview of Shifts</span></span>
<span data-ttu-id="fbcfd-109">L’application d’équipes dans Microsoft Teams conserve firstline employés connectés et synchronisés. Il est mobile d’abord généré pour la gestion du temps efficace et rapide et de communication pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-109">The Shifts app in Microsoft Teams keeps firstline workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="fbcfd-110">Déplacements permet aux travailleurs firstline et leurs responsables utilisent leurs appareils mobiles pour gérer les planifications et garder le contact.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-110">Shifts lets firstline workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="fbcfd-111">Responsables de créer, mettre à jour et gérer les planifications de travail d’équipe pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-111">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="fbcfd-112">Ils peuvent envoyer des messages à une personne (« il existe un fractionnement sur le plancher ») ou l’ensemble de l’équipe (« les familles régionaux arrive dans 20 minutes »).</span><span class="sxs-lookup"><span data-stu-id="fbcfd-112">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="fbcfd-113">Ils peuvent également envoyer des documents de stratégie, des bulletins d’informations et des vidéos.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-113">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="fbcfd-114">Employés afficher leurs équipes à venir, peuvent voir qui d’autre est prévue pour le jour, demande d’échange ou de proposer une équipe et durée hors de la demande.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-114">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="fbcfd-115">Il est important de savoir qu’équipes actuellement ne prennent en charge les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-115">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="fbcfd-116">Cela signifie que les invités d’une équipe ne peut pas être ajoutées à ou utilisent planifications MAJ lors de l’accès invité est activé dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-116">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="fbcfd-117">Disponibilité des équipes</span><span class="sxs-lookup"><span data-stu-id="fbcfd-117">Availability of Shifts</span></span>

<span data-ttu-id="fbcfd-118">Déplacements est disponible dans tous les abonnements Office 365 qui incluent des équipes, avec quelques exceptions.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-118">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="fbcfd-119">Les exceptions sont nous gouvernement nuage communautaire (GCC) et les équipes libres.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-119">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="fbcfd-120">Équipes n’est pas disponible dans Office 365 américains ou équipes libre offres.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-120">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="fbcfd-121">Pour en savoir plus sur la gestion des licences pour les équipes, voir [Gestion des licences Office 365 pour les équipes](Office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="fbcfd-121">To learn more about licensing for Teams, see [Office 365 licensing for Teams](Office-365-licensing.md).</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="fbcfd-122">Configurer des équipes</span><span class="sxs-lookup"><span data-stu-id="fbcfd-122">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="fbcfd-123">Activer ou désactiver des équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-123">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="fbcfd-124">Équipes est activée par défaut pour tous les utilisateurs d’équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-124">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="fbcfd-125">Vous pouvez désactiver ou activer l’application pour votre organisation dans le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-125">You can turn off or turn on the app for your organization in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="fbcfd-126">Connectez-vous au centre d’administration Microsoft 365 avec votre compte d’administration d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-126">Sign in to the Microsoft 365 admin center with your Office 365 admin account.</span></span>
2. <span data-ttu-id="fbcfd-127">Accédez à **paramètres** > **Services et compléments** > **Équipes Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-127">Go to **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> 
3. <span data-ttu-id="fbcfd-128">Sous **paramètres au niveau du client**, sélectionnez **applications**, puis sous **Applications par défaut**, désactivez ou sélectionnez la case à cocher **équipes** pour activer ou désactiver l’application.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-128">Under **Tenant-wide settings**, select **Apps**, and then under **Default Apps**, clear or select the **Shifts** check box to turn off or turn on the app.</span></span> 

    <span data-ttu-id="fbcfd-129">![Capture d’écran de la section applications par défaut] (media/firstline-worker-enable-disable-shifts.png "Capture d’écran de la section par défaut des applications dans le centre d’administration Microsoft 365, affichant la liste des applications, notamment les déplacements des applications")</span><span class="sxs-lookup"><span data-stu-id="fbcfd-129">![Screen shot of the Default Apps section](media/firstline-worker-enable-disable-shifts.png "Screen shot of the Default Apps section in the Microsoft 365 admin center, showing the list of apps, including the Shifts app")</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="fbcfd-130">Utiliser la stratégie du programme d’installation FirstLineWorker application aux équipes de code confidentiel pour les équipes</span><span class="sxs-lookup"><span data-stu-id="fbcfd-130">Use the FirstLineWorker app setup policy to pin Shifts to Teams</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="fbcfd-131">Stratégies d’application du programme d’installation vous permettent de personnaliser des équipes pour mettre en surbrillance les applications qui sont plus importantes pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-131">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="fbcfd-132">La liste des applications dans une stratégie sont épinglées sur la barre d’application&mdash;la barre sur le côté du client de bureau équipes et en bas des clients mobiles équipes&mdash;où les utilisateurs peuvent rapidement et facilement y accéder.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-132">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="fbcfd-133">Équipes inclut une stratégie de configuration d’une application de FirstLineWorker intégrée que vous pouvez attribuer aux travailleurs firstline dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-133">Teams includes a built-in FirstLineWorker app setup policy that you can assign to firstline workers in your organization.</span></span> <span data-ttu-id="fbcfd-134">Par défaut, la stratégie inclut les applications de l’activité, équipes, la conversation et appeler.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-134">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="fbcfd-135">Pour afficher la stratégie FirstLineWorker, dans le volet de navigation gauche de Microsoft Teams & Skype entreprise centre d’administration, accédez à **l’application des équipes** > **stratégies du programme d’installation des applications**.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-135">To view the FirstLineWorker policy, in the left navigation of the Microsoft Teams & Skype for Business Admin Center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="fbcfd-136">![Capture d’écran de la stratégie du programme d’installation d’application FirstLineWorker dans les équipes Microsoft & Skype entreprise centre d’administration] (media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie du programme d’installation d’application FirstLineWorker dans les équipes Microsoft & Skype entreprise centre d’administration")</span><span class="sxs-lookup"><span data-stu-id="fbcfd-136">![Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams & Skype for Business Admin Center](media/firstline-worker-app-setup-policy.png "Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams & Skype for Business Admin Center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="fbcfd-137">Affecter la stratégie FirstLineWorker à des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="fbcfd-137">Assign the FirstLineWorker policy to individual users</span></span>

1. <span data-ttu-id="fbcfd-138">Dans la navigation de gauche du Microsoft Teams & Skype entreprise centre d’administration, accédez à des **utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-138">In the left navigation of the Microsoft Teams & Skype for Business Admin Center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="fbcfd-139">En regard de **stratégies attribuées**, cliquez **sur Modifier**.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-139">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="fbcfd-140">Sous **stratégie de l’installation des applications d’équipes**, sélectionnez **FirstLineWorker**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-140">Under **Teams App Setup policy**, select **FirstLineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="fbcfd-141">Attribuez-les FirstLineWorker application du programme d’installation pour les utilisateurs dans un groupe</span><span class="sxs-lookup"><span data-stu-id="fbcfd-141">Assign the FirstLineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="fbcfd-142">Vous pouvez affecter la stratégie du programme d’installation d’application FirstLineWorker aux utilisateurs dans un groupe, par exemple un groupe de sécurité, en vous connectant à Azure Active Directory PowerShell pour le module graphique et le Skype pour le module PowerShell Business.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-142">You can assign the FirstLineWorker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="fbcfd-143">Pour plus d’informations sur l’utilisation de PowerShell pour gérer les équipes, voir [Vue d’ensemble de PowerShell équipes](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fbcfd-143">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="fbcfd-144">Dans cet exemple, nous affectons la stratégie du programme d’installation d’application FirstLineWorker à tous les utilisateurs dans le groupe équipe Firstline de Contoso.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-144">In this example, we assign the FirstLineWorker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="fbcfd-145">Assurez-vous que votre première connexion à Azure Active Directory PowerShell pour le module graphique et Skype pour le module PowerShell Business en suivant les étapes de [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="fbcfd-145">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="fbcfd-146">Obtenir le GroupObjectId du groupe particulier.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-146">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="fbcfd-147">Obtenir les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-147">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="fbcfd-148">Affecter tous les utilisateurs dans le groupe à la stratégie du programme d’installation d’application FirstLineWorker.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-148">Assign all users in the group to the FirstLineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="fbcfd-149">Selon le nombre de membres dans le groupe, cette commande peut prendre plusieurs minutes à exécuter.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-149">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fbcfd-150">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="fbcfd-150">Related topics</span></span>
- [<span data-ttu-id="fbcfd-151">Déplace l’aide pour les travailleurs firstline et responsables</span><span class="sxs-lookup"><span data-stu-id="fbcfd-151">Shifts Help for firstline workers and managers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)