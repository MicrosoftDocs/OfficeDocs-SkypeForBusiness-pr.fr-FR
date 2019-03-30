---
title: Gérer l’application Shifts pour votre organisation dans Microsoft Teams
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment configurer et gérer l’application des déplacements dans les équipes pour les travailleurs Firstline dans votre organisation.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b1ef7ee44b1d6318b85461b5d6b9d4173cc8552
ms.sourcegitcommit: 89b866a3c383555f6f89dc77bebd74cddf9e40fb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013208"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="9faf8-103">Gérer l’application Shifts pour votre organisation dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9faf8-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9faf8-104">Effet 2019, octobre 1, Microsoft StaffHub sera être retirée.</span><span class="sxs-lookup"><span data-stu-id="9faf8-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="9faf8-105">Nous créons StaffHub fonctionnalités dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9faf8-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="9faf8-106">Aujourd'hui, les équipes inclut l’application des équipes de gestion de la planification et des fonctionnalités supplémentaires seront intégrées au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="9faf8-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="9faf8-107">StaffHub cessera de fonctionner pour tous les utilisateurs sur le 1 octobre 2019.</span><span class="sxs-lookup"><span data-stu-id="9faf8-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="9faf8-108">Toute personne qui essaie d’ouvrir StaffHub s’affichera un message pronom pour télécharger les équipes.</span><span class="sxs-lookup"><span data-stu-id="9faf8-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="9faf8-109">Pour plus d’informations, voir [Microsoft StaffHub à retirer](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="9faf8-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="9faf8-110">Vue d’ensemble des équipes</span><span class="sxs-lookup"><span data-stu-id="9faf8-110">Overview of Shifts</span></span>
<span data-ttu-id="9faf8-111">L’application d’équipes dans Microsoft Teams conserve Firstline employés connectés et synchronisés. Il est mobile d’abord généré pour la gestion du temps efficace et rapide et de communication pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="9faf8-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="9faf8-112">Déplacements permet aux travailleurs Firstline et leurs responsables utilisent leurs appareils mobiles pour gérer les planifications et garder le contact.</span><span class="sxs-lookup"><span data-stu-id="9faf8-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="9faf8-113">Responsables de créer, mettre à jour et gérer les planifications de travail d’équipe pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="9faf8-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="9faf8-114">Ils peuvent envoyer des messages à une personne (« il existe un fractionnement sur le plancher ») ou l’ensemble de l’équipe (« les familles régionaux arrive dans 20 minutes »).</span><span class="sxs-lookup"><span data-stu-id="9faf8-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="9faf8-115">Ils peuvent également envoyer des documents de stratégie, des bulletins d’informations et des vidéos.</span><span class="sxs-lookup"><span data-stu-id="9faf8-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="9faf8-116">Employés afficher leurs équipes à venir, peuvent voir qui d’autre est prévue pour le jour, demande d’échange ou de proposer une équipe et durée hors de la demande.</span><span class="sxs-lookup"><span data-stu-id="9faf8-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="9faf8-117">Il est important de savoir qu’équipes actuellement ne prennent en charge les utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="9faf8-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="9faf8-118">Cela signifie que les invités d’une équipe ne peut pas être ajoutées à ou utilisent planifications MAJ lors de l’accès invité est activé dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="9faf8-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="9faf8-119">Disponibilité des équipes</span><span class="sxs-lookup"><span data-stu-id="9faf8-119">Availability of Shifts</span></span>

<span data-ttu-id="9faf8-120">Déplacements est disponible dans tous les abonnements Office 365 qui incluent des équipes, avec quelques exceptions.</span><span class="sxs-lookup"><span data-stu-id="9faf8-120">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="9faf8-121">Les exceptions sont nous gouvernement nuage communautaire (GCC) et les équipes libres.</span><span class="sxs-lookup"><span data-stu-id="9faf8-121">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="9faf8-122">Équipes n’est pas disponible dans Office 365 américains ou équipes libre offres.</span><span class="sxs-lookup"><span data-stu-id="9faf8-122">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="9faf8-123">Pour plus d’informations sur la gestion des licences pour les équipes, notamment la liste des abonnements Office 365 qui inclut des équipes, voir [Gestion des licences Office 365 pour les équipes](../../Office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="9faf8-123">To learn more about licensing for Teams, including a list of Office 365 subscriptions that includes Teams, see [Office 365 licensing for Teams](../../Office-365-licensing.md).</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="9faf8-124">Emplacement des données d’équipes</span><span class="sxs-lookup"><span data-stu-id="9faf8-124">Location of Shifts data</span></span>

<span data-ttu-id="9faf8-125">Équipes données sont actuellement stockées dans Azure dans les centres de données en Amérique du Nord et Europe occidentale Asie-Pacifique.</span><span class="sxs-lookup"><span data-stu-id="9faf8-125">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="9faf8-126">Pour plus d’informations sur le stockage des données, voir [où se trouvent mes données](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="9faf8-126">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="9faf8-127">Configurer des équipes</span><span class="sxs-lookup"><span data-stu-id="9faf8-127">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="9faf8-128">Activer ou désactiver des équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9faf8-128">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="9faf8-129">Équipes est activée par défaut pour tous les utilisateurs d’équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9faf8-129">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="9faf8-130">Vous pouvez désactiver ou activer l’application pour votre organisation dans le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9faf8-130">You can turn off or turn on the app for your organization in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="9faf8-131">Connectez-vous au centre d’administration Microsoft 365 avec votre compte d’administration d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="9faf8-131">Sign in to the Microsoft 365 admin center with your Office 365 admin account.</span></span>
2. <span data-ttu-id="9faf8-132">Accédez à **paramètres** > **compléments Services &** > **Équipes Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="9faf8-132">Go to **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> 
3. <span data-ttu-id="9faf8-133">Sous **paramètres au niveau du client**, sélectionnez **applications**, puis sous **Applications par défaut**, désactivez ou sélectionnez la case à cocher **équipes** pour activer ou désactiver l’application.</span><span class="sxs-lookup"><span data-stu-id="9faf8-133">Under **Tenant-wide settings**, select **Apps**, and then under **Default Apps**, clear or select the **Shifts** check box to turn off or turn on the app.</span></span> 

    <span data-ttu-id="9faf8-134">![Capture d’écran de la section applications par défaut] (../../media/firstline-worker-enable-disable-shifts.png "Capture d’écran de la section par défaut des applications dans le centre d’administration Microsoft 365, affichant la liste des applications, notamment les déplacements des applications")</span><span class="sxs-lookup"><span data-stu-id="9faf8-134">![Screen shot of the Default Apps section](../../media/firstline-worker-enable-disable-shifts.png "Screen shot of the Default Apps section in the Microsoft 365 admin center, showing the list of apps, including the Shifts app")</span></span>

### <a name="use-the-firstline-worker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="9faf8-135">Utilisent la stratégie du programme d’installation Firstline travailleur de l’application à des équipes de code confidentiel pour les équipes</span><span class="sxs-lookup"><span data-stu-id="9faf8-135">Use the Firstline Worker app setup policy to pin Shifts to Teams</span></span>

> [!INCLUDE [Preview customer token](../../includes/preview-feature.md)]

<span data-ttu-id="9faf8-136">Stratégies d’application du programme d’installation vous permettent de personnaliser des équipes pour mettre en surbrillance les applications qui sont plus importantes pour les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9faf8-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="9faf8-137">La liste des applications dans une stratégie sont épinglées sur la barre d’application&mdash;la barre sur le côté du client de bureau équipes et en bas des clients mobiles équipes&mdash;où les utilisateurs peuvent rapidement et facilement y accéder.</span><span class="sxs-lookup"><span data-stu-id="9faf8-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="9faf8-138">Les équipes inclut une stratégie du programme d’installation d’une application de travail Firstline intégrée que vous pouvez attribuer aux travailleurs Firstline dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9faf8-138">Teams includes a built-in Firstline Worker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="9faf8-139">Par défaut, la stratégie inclut les applications de l’activité, équipes, la conversation et appeler.</span><span class="sxs-lookup"><span data-stu-id="9faf8-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="9faf8-140">Pour afficher la stratégie de travail Firstline, dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **l’application des équipes** > **stratégies du programme d’installation des applications**.</span><span class="sxs-lookup"><span data-stu-id="9faf8-140">To view the Firstline Worker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="9faf8-141">![Capture d’écran de la stratégie du programme d’installation Firstline travailleur de l’application dans le centre d’administration Microsoft équipes] (../../media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie du programme d’installation Firstline travailleur de l’application dans le centre d’administration Microsoft équipes")</span><span class="sxs-lookup"><span data-stu-id="9faf8-141">![Screen shot of the Firstline Worker app setup policy in the Microsoft Teams admin center](../../media/firstline-worker-app-setup-policy.png "Screen shot of the Firstline Worker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstline-worker-policy-to-individual-users"></a><span data-ttu-id="9faf8-142">Attribuer la stratégie de travail Firstline à des utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="9faf8-142">Assign the Firstline Worker policy to individual users</span></span>

1. <span data-ttu-id="9faf8-143">Dans la navigation de gauche du centre d’administration Microsoft Teams, accédez à des **utilisateurs**, puis cliquez sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9faf8-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="9faf8-144">En regard de **stratégies attribuées**, cliquez **sur Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9faf8-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="9faf8-145">Sous **stratégie de l’installation des applications d’équipes**, sélectionnez **FirstlineWorker**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9faf8-145">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstline-worker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="9faf8-146">Affecter le travailleur Firstline stratégie d’application du programme d’installation aux utilisateurs dans un groupe</span><span class="sxs-lookup"><span data-stu-id="9faf8-146">Assign the Firstline Worker app setup policy to users in a group</span></span>

<span data-ttu-id="9faf8-147">Vous pouvez affecter le travailleur Firstline stratégie d’application du programme d’installation aux utilisateurs dans un groupe, par exemple un groupe de sécurité, en vous connectant à Azure Active Directory PowerShell pour le module graphique et le Skype pour le module PowerShell Business.</span><span class="sxs-lookup"><span data-stu-id="9faf8-147">You can assign the Firstline Worker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="9faf8-148">Pour plus d’informations sur l’utilisation de PowerShell pour gérer les équipes, voir [Vue d’ensemble de PowerShell équipes](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9faf8-148">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="9faf8-149">Dans cet exemple, nous affectons le processus de travail Firstline stratégie du programme d’installation d’application à tous les utilisateurs dans le groupe équipe Firstline de Contoso.</span><span class="sxs-lookup"><span data-stu-id="9faf8-149">In this example, we assign the Firstline Worker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="9faf8-150">Assurez-vous que votre première connexion à Azure Active Directory PowerShell pour le module graphique et Skype pour le module PowerShell Business en suivant les étapes de [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="9faf8-150">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="9faf8-151">Obtenir le GroupObjectId du groupe particulier.</span><span class="sxs-lookup"><span data-stu-id="9faf8-151">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="9faf8-152">Obtenir les membres du groupe spécifié.</span><span class="sxs-lookup"><span data-stu-id="9faf8-152">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="9faf8-153">Affecter tous les utilisateurs dans le groupe à la stratégie du programme d’installation d’application FirstlineWorker.</span><span class="sxs-lookup"><span data-stu-id="9faf8-153">Assign all users in the group to the FirstlineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="9faf8-154">Selon le nombre de membres dans le groupe, cette commande peut prendre plusieurs minutes à exécuter.</span><span class="sxs-lookup"><span data-stu-id="9faf8-154">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9faf8-155">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="9faf8-155">Related topics</span></span>
- [<span data-ttu-id="9faf8-156">Déplace l’aide pour les travailleurs Firstline</span><span class="sxs-lookup"><span data-stu-id="9faf8-156">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
