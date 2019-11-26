---
title: Migrer de Slack vers Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.custom: ''
description: Suivez les instructions pour la migration de Slack vers Microsoft Teams.
ms.openlocfilehash: 56278359062bb7f154b5e3248c343f98c62cb916
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793470"
---
# <a name="migrate-from-slack-to-microsoft-teams"></a><span data-ttu-id="860d4-103">Migrer de Slack vers Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="860d4-103">Migrate from Slack to Teams</span></span>

<span data-ttu-id="860d4-104">Cet article vous guide dans la transition vers Microsoft Teams à partir de Slack.</span><span class="sxs-lookup"><span data-stu-id="860d4-104">This article walks you through the journey of moving to Microsoft Teams from Slack.</span></span>

<span data-ttu-id="860d4-105">Lorsque vous planifiez la migration de votre organisation de Slack vers Teams, il est important de déterminer ce que vous devez conserver (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="860d4-105">When planning your organization’s move to Teams from Slack, it's important to decide what you need to keep (if anything).</span></span> <span data-ttu-id="860d4-106">Nous allons commencer par décrire les types de données pouvant être migrés, puis vous guider dans la façon d’évaluer vos besoins, planifier la migration et effectuer ensuite la migration.</span><span class="sxs-lookup"><span data-stu-id="860d4-106">We'll start off by describing what types of data can be migrated and then walk you through how to assess your needs, plan your move, and then make the move.</span></span>

<span data-ttu-id="860d4-107">Le diagramme ci-dessous montre l’architecture de Slack à un haut niveau.</span><span class="sxs-lookup"><span data-stu-id="860d4-107">The diagram below shows the Slack architecture at a high level.</span></span>

![Image qui montre l’architecture de Slack à haut niveau](media/migrate-slack-to-teams-image1.png)

## <a name="plan-your-migration-from-slack"></a><span data-ttu-id="860d4-109">Planifiez votre migration de Slack</span><span class="sxs-lookup"><span data-stu-id="860d4-109">Plan your migration from Slack</span></span>
### <a name="what-you-can-and-cant-migrate"></a><span data-ttu-id="860d4-110">Ce qui peut et ne peut être migré</span><span class="sxs-lookup"><span data-stu-id="860d4-110">What you can and can’t migrate</span></span>
<span data-ttu-id="860d4-111">Votre plan de service Slack détermine ce que vous pouvez et ne pouvez pas migrer.</span><span class="sxs-lookup"><span data-stu-id="860d4-111">Your Slack service plan will determine what you can and can’t migrate.</span></span> <span data-ttu-id="860d4-112">Par exemple, certains plans de service de Slack vous permettent uniquement d’exporter des fichiers et historiques de canaux publics, d’autres nécessitent une demande DocuSign pour inclure les canaux privés et les messages directs.</span><span class="sxs-lookup"><span data-stu-id="860d4-112">For example, some Slack service plans only let you export public channels history and files, other require a DocuSign request to include Private Channels and Direct Messages.</span></span> 

<span data-ttu-id="860d4-113">Pour déterminer le niveau de service de votre espace de travail de Slack, connectez-vous à Slack et notez le type de votre plan sur la page **À propos de cet espace de travail**.</span><span class="sxs-lookup"><span data-stu-id="860d4-113">To determine your Slack Workspace service level, log into Slack and note your plan type on the **About this Workspace** page.</span></span>

<span data-ttu-id="860d4-114">Pour en savoir plus sur les options d’exportation de Slack, accédez au site Web Slack : https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="860d4-114">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

<span data-ttu-id="860d4-115">Le diagramme ci-dessous donne une vue d’ensemble du paysage de la migration de Slack que nous allons aborder dans cet article.</span><span class="sxs-lookup"><span data-stu-id="860d4-115">The diagram below gives you a high-level look at the Slack migration landscape that we’ll cover in this article.</span></span> 

<span data-ttu-id="860d4-116">:::image type="content" source="media/migrate-slack-to-teams-image2.png" alt-text="Diagramme montrant le paysage d’exportation Slack.":::</span><span class="sxs-lookup"><span data-stu-id="860d4-116">:::image type="content" source="media/migrate-slack-to-teams-image2.png" alt-text="Diagram that shows the Slack export landscape.":::</span></span>

<span data-ttu-id="860d4-117">Après avoir lu cette section, vous devriez être en mesure de comprendre les concepts suivants :</span><span class="sxs-lookup"><span data-stu-id="860d4-117">When you're done with this section, you should understand:</span></span>
- <span data-ttu-id="860d4-118">Niveau de service de vos espaces de travail Slack</span><span class="sxs-lookup"><span data-stu-id="860d4-118">The service level of your Slack Workspaces</span></span>
- <span data-ttu-id="860d4-119">Ce qui peut et ne peut être exporté</span><span class="sxs-lookup"><span data-stu-id="860d4-119">What can and can't be exported</span></span>
- <span data-ttu-id="860d4-120">Approches courantes d’exportation</span><span class="sxs-lookup"><span data-stu-id="860d4-120">Common approaches to exporting</span></span>

### <a name="assess-your-slack-workspaces"></a><span data-ttu-id="860d4-121">Évaluer vos espaces de travail Slack</span><span class="sxs-lookup"><span data-stu-id="860d4-121">Assess your Slack workspaces</span></span>
<span data-ttu-id="860d4-122">Avant de planifier le plan de migration de votre organisation, vous devez rassembler des informations sur les espaces de travail Slack.</span><span class="sxs-lookup"><span data-stu-id="860d4-122">Before you can plan your organization’s migration plan, you need to pull together some information about your Slack workspaces.</span></span> <span data-ttu-id="860d4-123">La compréhension de l’utilisation de vos espaces de travail Slack vous permet de déterminer l’étendue de votre migration.</span><span class="sxs-lookup"><span data-stu-id="860d4-123">Understanding how your Slack workspaces are being used helps you determine the scope of your migration.</span></span> <span data-ttu-id="860d4-124">Par exemple, combien d’espaces de travail sont migrés ?</span><span class="sxs-lookup"><span data-stu-id="860d4-124">For example, how many workspaces are being moved?</span></span> <span data-ttu-id="860d4-125">Sont-ils utilisés par un service spécifique, plusieurs ou utilisés par une organisation entière ?</span><span class="sxs-lookup"><span data-stu-id="860d4-125">Are they used by a specific department, many, or in use by an entire organization?</span></span>

<span data-ttu-id="860d4-126">Si vous êtes membre des espaces de travail de Slack que vous voulez déplacer, vous pouvez analyser l’utilisation vous-même en accédant à *<your Slack workspace>. slack.com/stats*. Consultez les onglets canaux et membres pour rechercher des modèles d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="860d4-126">If you’re a member of the Slack Workspaces you want to migrate, you can analyze the usage yourself by going to *<your Slack workspace>.slack.com/stats*. Review the Channels and Members tabs to look for usage patterns.</span></span> <span data-ttu-id="860d4-127">Choisissez les espaces de travail que vous voulez migrer (et ceux que vous voulez laisser).</span><span class="sxs-lookup"><span data-stu-id="860d4-127">Decide which workspaces you want to migrate (and which ones you want to leave behind).</span></span> 

> [!NOTE]
> <span data-ttu-id="860d4-128">Si vous n’avez pas accès à la page statistiques, vous n’êtes pas un administrateur ou un propriétaire.</span><span class="sxs-lookup"><span data-stu-id="860d4-128">If you don’t have access to the stats page, you’re not an admin or owner.</span></span> 

### <a name="export-channels"></a><span data-ttu-id="860d4-129">Exporter des canaux</span><span class="sxs-lookup"><span data-stu-id="860d4-129">Export Channels</span></span>

<span data-ttu-id="860d4-130">Dans Slack, les utilisateurs rejoignent un canal qui fait partie d’un espace de travail Slack, tandis que les utilisateurs de Teams rejoignent une équipe qui est une collection de canaux.</span><span class="sxs-lookup"><span data-stu-id="860d4-130">In Slack, users join a channel which is part of a Slack Workspace, whereas in Teams users join a team which is a collection of channels.</span></span> <span data-ttu-id="860d4-131">Nous vous recommandons d’utiliser l’analyse de Slack pour déterminer la quantité d’activité qui se produit dans chaque canal afin de vous aider à décider des canaux à déplacer.</span><span class="sxs-lookup"><span data-stu-id="860d4-131">We recommend that you use Slack analytics to see how much activity happens in each channel to help you decide which channels to move.</span></span> <span data-ttu-id="860d4-132">Vous utiliserez la liste résultante pour déterminer comment regrouper vos canaux de Slack en équipes dans Teams, ainsi que les membres de chaque équipe.</span><span class="sxs-lookup"><span data-stu-id="860d4-132">You’ll use the resulting list to figure out how to group your Slack channels into teams in Teams as well as who should be members of each team.</span></span>

<span data-ttu-id="860d4-133">Si vous avez une offre de service de Slack payante (autre que Free), vous pouvez utiliser la fonction d’analyse de Slack (<your Slack workspace>. slack.com/admin/stats#channels) pour voir l’état d’un canal, sa date de dernière utilisation et le nombre de personnes qui en sont membres.</span><span class="sxs-lookup"><span data-stu-id="860d4-133">If you have a paid Slack service plan (anything other than Free), you can use Slack’s analytics (<your Slack workspace>.slack.com/admin/stats#channels) to see how active a channel is, when it was last used, and how many people are members.</span></span> <span data-ttu-id="860d4-134">Cela peut vous aider à décider si vous voulez migrer le canal.</span><span class="sxs-lookup"><span data-stu-id="860d4-134">This can help you decide whether to migrate the channel.</span></span> <span data-ttu-id="860d4-135">Par défaut, le contenu des canaux publics (messages et fichiers) peut être exporté.</span><span class="sxs-lookup"><span data-stu-id="860d4-135">By default, public channels content (messages and files) can be exported.</span></span> <span data-ttu-id="860d4-136">Selon votre offre de service de Slack et si vous avez demandé des canaux privés et des messages directs de Slack, vous pouvez les exporter.</span><span class="sxs-lookup"><span data-stu-id="860d4-136">Depending on your Slack service plan and whether you’ve requested Private Channels and Direct Messages from Slack, those can be exported.</span></span>

<span data-ttu-id="860d4-137">Pour en savoir plus sur les options d’exportation de Slack, accédez au site Web Slack : https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="860d4-137">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="860d4-138">Vérifiez les conditions de confidentialité et de conformité de votre organisation concernant les données de canal.</span><span class="sxs-lookup"><span data-stu-id="860d4-138">Check your organization’s privacy and compliance requirements around channel data.</span></span> <span data-ttu-id="860d4-139">Votre organisation peut respecter les exigences de conformité relatives à la manipulation, au stockage et au traitement de ces données, ainsi qu’au cycle de vie du contenu identifiable par l’utilisateur final (EUII).</span><span class="sxs-lookup"><span data-stu-id="860d4-139">Your organization may have compliance requirements around the handling, storage, and processing of this data, in addition to complying with the lifecycle of end-user identifiable content (EUII).</span></span>

### <a name="export-direct-messages"></a><span data-ttu-id="860d4-140">Exporter des messages directs</span><span class="sxs-lookup"><span data-stu-id="860d4-140">Export Direct Messages</span></span>
<span data-ttu-id="860d4-141">Les messages directs sont identiques aux conversations dans Teams, qui sont 1:1 ou 1-à-plusieurs conversations non-canal.</span><span class="sxs-lookup"><span data-stu-id="860d4-141">Direct Messages are the same as chats in Teams, which are 1:1 or 1-to-many non-channel conversations.</span></span> <span data-ttu-id="860d4-142">La fonctionnalité d’exportation dépend de votre offre de service Slack et si vous avez demandé que les messages directs soient inclus dans votre exportation de Slack.</span><span class="sxs-lookup"><span data-stu-id="860d4-142">Export-ability depends on your Slack service plan and if you’ve requested Direct Messages to be included in your Slack Export.</span></span> <span data-ttu-id="860d4-143">Teams ne prend pas en charge l’importation de messages directs pour le moment.</span><span class="sxs-lookup"><span data-stu-id="860d4-143">Teams doesn’t support importing Direct messages currently.</span></span> <span data-ttu-id="860d4-144">Consultez un partenaire Microsoft pour en savoir plus sur les solutions tierces que vous pouvez explorer afin d’intégrer du contenu direct dans Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-144">Consult a Microsoft partner to learn about third-party solutions you can explore that bring Direct Messages content into Teams.</span></span>

<span data-ttu-id="860d4-145">Pour l’exportation de messages directs, voir les outils, tels que Exporter, dans le Store App Store.</span><span class="sxs-lookup"><span data-stu-id="860d4-145">For exporting Direct Messages, check out tools, such as Export, in the Slack App Store.</span></span>

### <a name="apps-and-custom-integrations"></a><span data-ttu-id="860d4-146">Applications et intégrations personnalisées</span><span class="sxs-lookup"><span data-stu-id="860d4-146">Apps and custom integrations</span></span>

<span data-ttu-id="860d4-147">Les applications dans Slack sont comme les applications dans Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-147">Apps in Slack are like apps in Teams.</span></span> <span data-ttu-id="860d4-148">Une fois que vous disposez d’une liste d’applications et de leurs configurations dans l’espace de travail, vous pouvez effectuer une recherche dans l’App Store Teams pour voir si elles sont disponibles pour Teams \*.</span><span class="sxs-lookup"><span data-stu-id="860d4-148">Once you have a list of apps and their configurations in the Workspace, you can search in the Teams App store to see if they’re available for Teams\*.</span></span> 

<span data-ttu-id="860d4-149">Accédez à <your Slack workspace>. slack.com/apps/manage pour obtenir la liste des applications et les intégrations personnalisées.</span><span class="sxs-lookup"><span data-stu-id="860d4-149">Go to <your Slack workspace>.slack.com/apps/manage to get a list of Apps and Custom Integrations.</span></span> <span data-ttu-id="860d4-150">Cette page indique également le nombre de configurations où chaque application est en cours d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="860d4-150">This page also shows you the number of configurations where each app is in use.</span></span> <span data-ttu-id="860d4-151">L’intégration personnalisée peut varier en fonction de la « capacité de migration ».</span><span class="sxs-lookup"><span data-stu-id="860d4-151">Custom Integrations vary in their “migrate-ability.”</span></span> <span data-ttu-id="860d4-152">S’il s’agit d’un hook Web, vous pouvez généralement l’envoyer à un connecteur Office 365 pour déplacer le flux de travail dans Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-152">If it’s a Web Hook, you can usually send it to an Office 365 Connector to shift the workflow into Teams.</span></span> <span data-ttu-id="860d4-153">Évaluez les robots et les autres applications au cas par cas pour planifier leur migration vers Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-153">Assess bots and other apps on a case-by-case basis to plan for moving them to Teams.</span></span>

<span data-ttu-id="860d4-154">\* Si votre administrateur a utilisé des applications restreintes, il est possible que vous ne consultiez pas la liste complète des applications disponibles.</span><span class="sxs-lookup"><span data-stu-id="860d4-154">\*If your administrator has restricted apps usage, you may not be looking at the full list of available apps.</span></span>

### <a name="users"></a><span data-ttu-id="860d4-155">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="860d4-155">Users</span></span>
<span data-ttu-id="860d4-156">Il se peut que les schémas d’identité que vous avez utilisés dans Slack ne s’intègrent pas directement à Office 365.</span><span class="sxs-lookup"><span data-stu-id="860d4-156">The identity schemes you used in Slack might not map directly to Office 365.</span></span> <span data-ttu-id="860d4-157">Par exemple, il est possible que les adresses de messagerie de Slack ne correspondent pas aux comptes Office 365 professionnels ou scolaires.</span><span class="sxs-lookup"><span data-stu-id="860d4-157">For example, the email addresses of your Slack users may not map to Office 365 work or school accounts.</span></span> <span data-ttu-id="860d4-158">Vous devez créer un mappage ID utilisateur avant de commencer à planifier le déploiement de Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-158">You should create a user-ID map before you start planning your Teams rollout.</span></span>

<span data-ttu-id="860d4-159">Si vous utilisez une offre de service Slack payante, vous pouvez accéder à *<your Slack workspace>. slack.com/admin/stats#members* pour obtenir des informations sur les membres, telles que l’adresse de messagerie et le type de compte pour chaque utilisateur (par exemple, un invité à un ou plusieurs canaux).</span><span class="sxs-lookup"><span data-stu-id="860d4-159">If you’re on a paid Slack service plan, you can go to *<your Slack workspace>.slack.com/admin/stats#members* to get member details such as email address and account type for each user (for example, single vs. multi-channel guest).</span></span>

<span data-ttu-id="860d4-160">Voici un script que vous pouvez utiliser pour comparer les adresses de courrier d’une exportation Slack par rapport à Azure AD afin de résoudre l’ambiguïté de noms.</span><span class="sxs-lookup"><span data-stu-id="860d4-160">Here’s a script you can use to compare email addresses from a Slack export against Azure AD to help solve for name ambiguity.</span></span> <span data-ttu-id="860d4-161">Il signale également si l’utilisateur est activé pour Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-161">It’ll also report if the user is enabled for Teams.</span></span> <span data-ttu-id="860d4-162">Si vous avez besoin d’aide sur PowerShell, consultez [Prise en main d’Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="860d4-162">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>

```azurepowershell
Connect-AzureAD
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class User {
    [ValidateNotNullOrEmpty()] $ID
    [ValidateNotNullOrEmpty()] $FullName
    [string] $Email
    [string] $UPN
    [ValidateNotNullOrEmpty()][bool] $ExistsAzureAD
    [ValidateNotNullOrEmpty()][bool] $TeamsEnabled
}

$output = New-Object -type System.Collections.ObjectModel.Collection["User"]

$users = Get-Content -Raw -Path .\slackHistory\users.json | ConvertFrom-Json

Write-Host -ForegroundColor Green "$(Get-Timestamp) User Count: " $users.Count

$i=1
Write-Host "$(Get-Timestamp) Attempting direct email match.. `n"
foreach ($slackUser in $users) {
    $user = New-Object User
    $user.id = $slackUser.id
    $user.FullName = $slackUser.name
    try {
        if ($null -ne $slackUser.profile.email) {
            $user.email = $slackUser.profile.email
            $emailSplit = $slackUser.profile.email.Split('@')
            $mailNickName = $emailSplit[0]
            $result = Get-AzureADUser -Filter "MailNickName eq '$($mailNickName)' or UserPrincipalName eq '$($slackUser.profile.email)' or proxyAddresses/any(c:c eq 'smtp:$($slackUser.profile.email)')"
            if ($null -ne $result) {
                $user.ExistsAzureAD = $true
                $user.UPN = $result.UserPrincipalName
                $assignedPlans = $result.assignedPlans
                foreach ($plan in $assignedPlans) {
                    if ($plan.ServicePlanId -eq "57ff2da0-773e-42df-b2af-ffb7a2317929") {
                        if ($plan.CapabilityStatus -eq "Enabled") {
                            $user.TeamsEnabled = $true
                        }
                        else {
                            $user.TeamsEnabled = $false
                        }
                    }
                }
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - AzureAD object found:" $result.MailNickName
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - Teams Enabled:" $user.TeamsEnabled
            }
            else {
                $user.ExistsAzureAD = $false
                Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: " $slackUser.profile.email
            }
        }
        $i++
    }   
    catch
    {
        $user.ExistsAzureAD = $false
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: $($i)" $user.profile.email
        $i++
    }
    $output.Add($user)
}

$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
```

<span data-ttu-id="860d4-163">Après avoir lu cette section, vous devriez disposer de :</span><span class="sxs-lookup"><span data-stu-id="860d4-163">When you’re done with this section, you should have:</span></span>
- <span data-ttu-id="860d4-164">Liste de canaux par espace de travail avec les statistiques d’utilisation</span><span class="sxs-lookup"><span data-stu-id="860d4-164">A list of Channels per Workspace with usage stats</span></span>
- <span data-ttu-id="860d4-165">Liste des applications Slack avec des configurations par canal</span><span class="sxs-lookup"><span data-stu-id="860d4-165">A list of Slack Apps with configurations per channel</span></span>
- <span data-ttu-id="860d4-166">Déterminez le type d’historique de message Slack que vous voulez exporter (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="860d4-166">Determined what type of Slack message history you want to export (if any)</span></span>
- <span data-ttu-id="860d4-167">Liste d’utilisateurs dont les comptes Slack sont mappés avec les comptes professionnels ou scolaires de Microsoft et quelle licence Teams leur est associée</span><span class="sxs-lookup"><span data-stu-id="860d4-167">A list of users whose Slack accounts map to Microsoft work or school accounts and which Teams license they have</span></span>

## <a name="plan-your-teams-deployment"></a><span data-ttu-id="860d4-168">Planifier le déploiement de Teams</span><span class="sxs-lookup"><span data-stu-id="860d4-168">Plan your deployment</span></span>
<span data-ttu-id="860d4-169">Vous avez exporté les éléments dont vous avez besoin de Slack (et laissés les éléments dont vous n’avez pas besoin).</span><span class="sxs-lookup"><span data-stu-id="860d4-169">You’ve exported what you need from Slack (and left behind anything you don’t need).</span></span> <span data-ttu-id="860d4-170">À présent, il est temps de planifier le déploiement de Teams et l’importation de vos données Slack.</span><span class="sxs-lookup"><span data-stu-id="860d4-170">Now it’s time to plan how you’ll roll out Teams and import your Slack data.</span></span> <span data-ttu-id="860d4-171">Il s’agit d’une excellente opportunité pour évaluer ce qui est bien adapté à l’équipe en fonction de l’utilisation et inclure les éléments de votre plan de déploiement Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-171">This is a great opportunity to assess what's worked well for the team based on usage and include those elements in your Teams deployment plan.</span></span> <span data-ttu-id="860d4-172">À la fin de cette section, vous aurez un plan pour les utilisateurs, les canaux et les applications Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-172">At the end of this section, you’ll have a blueprint for your Teams users, channels, and apps.</span></span> 

<span data-ttu-id="860d4-173">Le diagramme ci-dessous donne une vue d’ensemble des éléments que vous allez gérer dans le cadre de votre déploiement Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-173">The diagram below gives you a high-level outline of the things you’ll address in your Teams deployment.</span></span>

<span data-ttu-id="860d4-174">:::image type="content" source="media/migrate-slack-to-teams-image3.png" alt-text="Plan général de planification du déploiement de Teams à partir de Slack.":::</span><span class="sxs-lookup"><span data-stu-id="860d4-174">:::image type="content" source="media/migrate-slack-to-teams-image3.png" alt-text="High-level outline of planning a Teams deployment from Slack.":::</span></span>

### <a name="team-and-channel-structure"></a><span data-ttu-id="860d4-175">Structure des équipes et des canaux</span><span class="sxs-lookup"><span data-stu-id="860d4-175">Team and channel structure</span></span>

<span data-ttu-id="860d4-176">Un espace de travail Slack peut représenter une équipe individuelle, plusieurs équipes ou toute une organisation.</span><span class="sxs-lookup"><span data-stu-id="860d4-176">A Slack Workspace may represent a single team, multiple teams or an entire organization.</span></span> <span data-ttu-id="860d4-177">Il est important de comprendre l’étendue des espaces de travail au fur et à mesure que vous déterminez la structure.</span><span class="sxs-lookup"><span data-stu-id="860d4-177">It’s important to understand the scope of the Workspaces as you determine the structure.</span></span> <span data-ttu-id="860d4-178">La relation la plus proche avec une équipe de Teams dans Slack est l’espace de travail, qui contient un ensemble de canaux.</span><span class="sxs-lookup"><span data-stu-id="860d4-178">The closest relationship to a Teams team in Slack is the Workspace, which contains a collection of channels.</span></span> <span data-ttu-id="860d4-179">Le diagramme ci-dessous montre trois mappages de Slack à Teams et des instructions pour la sélection du bon pour chaque espace de travail.</span><span class="sxs-lookup"><span data-stu-id="860d4-179">The diagram below demonstrates 3 different Slack-to-Teams mappings, and guidance for picking the right one for each Workspace.</span></span>


|<span data-ttu-id="860d4-180">Mise en correspondance Slack à Teams</span><span class="sxs-lookup"><span data-stu-id="860d4-180">Slack-to-Teams mapping</span></span> |  |
|---------|---------|
|<span data-ttu-id="860d4-181">1 espace de travail Slack : arrow_right : 1 équipe</span><span class="sxs-lookup"><span data-stu-id="860d4-181">1 Slack Workspace :arrow_right: 1 team</span></span>   | <span data-ttu-id="860d4-182">Pour les espaces de travail Slack de plus petite taille nécessitant moins de 200 canaux</span><span class="sxs-lookup"><span data-stu-id="860d4-182">For smaller Slack workspaces that need fewer than 200 channels</span></span><br><span data-ttu-id="860d4-183">Inclure un tampon pour la croissance et la planification des canaux privés</span><span class="sxs-lookup"><span data-stu-id="860d4-183">Include a buffer for growth and private channel planning</span></span>  |
|<span data-ttu-id="860d4-184">1 espace de travail Slack : arrow_right : plusieurs équipes</span><span class="sxs-lookup"><span data-stu-id="860d4-184">1 Slack Workspace :arrow_right: multiple teams</span></span>     | <span data-ttu-id="860d4-185">Utilisez les données d’analyse de votre espace de travail Slack pour créer des regroupements de canaux logiques, qui deviendront la base de vos équipes</span><span class="sxs-lookup"><span data-stu-id="860d4-185">Use your Slack Workspace analytics data to create logical channel groupings, which become the basis of your teams</span></span>        |
|<span data-ttu-id="860d4-186">2+ espaces de travail Slack : arrow_right : plusieurs équipes</span><span class="sxs-lookup"><span data-stu-id="860d4-186">2+ Slack Workspaces :arrow_right: multiple teams</span></span>     | <span data-ttu-id="860d4-187">Utilisez les données d’analyse de votre espace de travail Slack pour créer des regroupements de canaux et d’équipes logiques, qui deviendront la base de vos équipes</span><span class="sxs-lookup"><span data-stu-id="860d4-187">Use your Slack Workspace analytics data to create logical team and channel groupings, which become the basis of your teams</span></span>        |

<span data-ttu-id="860d4-188">Les solutions tierces comportent des statistiques d’utilisation pour vous aider à évaluer la façon dont le canal est actif et le nombre de publications qu’il contient.</span><span class="sxs-lookup"><span data-stu-id="860d4-188">Third-party solutions have usage statistics to help you assess how active the channel is and how many posts there are.</span></span> <span data-ttu-id="860d4-189">En règle générale, les canaux fréquemment utilisés peuvent être inclus dans la planification de votre équipe.</span><span class="sxs-lookup"><span data-stu-id="860d4-189">Typically, channels that are frequently used would be candidates to include in your team planning.</span></span>

> [!TIP]
> <span data-ttu-id="860d4-190">Conservez uniquement les éléments requis dans votre approche pour déterminer les canaux à recréer dans Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-190">Retain only what is required in your approach to determine which channels to recreate in Teams.</span></span> <span data-ttu-id="860d4-191">Pour en savoir plus, voir [Vue d’ensemble des équipes et canaux](teams-channels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="860d4-191">To learn more, read [Overview of teams and channels](teams-channels-overview.md).</span></span> 

#### <a name="team-planning"></a><span data-ttu-id="860d4-192">Planification d’équipe</span><span class="sxs-lookup"><span data-stu-id="860d4-192">Team Planning</span></span>
<span data-ttu-id="860d4-193">À l’aide de l’inventaire des canaux que vous avez compilé dans la section de Planification ci-dessus, travaillez avec vos propriétaires et administrateurs Slack pour déterminer les canaux qui deviendront les équipes et ceux qui doivent devenir des canaux au sein d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="860d4-193">Using the Channel inventory you compiled in the Planning section above, work with your Slack owners and admins to figure out which channels should become teams and which ones should become channels in a team.</span></span> <span data-ttu-id="860d4-194">Utiliser Excel ou PowerBI pour vous aider dans cette analyse : les deux peuvent fournir des informations supplémentaires pour vous aider à piloter ces discussions sur les canaux à conserver.</span><span class="sxs-lookup"><span data-stu-id="860d4-194">Use either Excel or PowerBI to help with this analysis - both can provide additional insights to help drive these discussions on which channels to retain.</span></span>

> [!TIP]
> <span data-ttu-id="860d4-195">Teams a actuellement une limite de 200 canaux par équipe.</span><span class="sxs-lookup"><span data-stu-id="860d4-195">Teams currently has a 200-channel limit per team.</span></span> <span data-ttu-id="860d4-196">Si votre liste de canaux approche de cette limite, vous devez déterminer un moyen de les diviser en deux équipes distinctes.</span><span class="sxs-lookup"><span data-stu-id="860d4-196">If your list of channels is getting close to that limit, you should figure out a way to split them into two separate teams.</span></span>

### <a name="channel-history"></a><span data-ttu-id="860d4-197">Historique des canaux</span><span class="sxs-lookup"><span data-stu-id="860d4-197">Channel History</span></span>

<span data-ttu-id="860d4-198">Vous pouvez utiliser des solutions gratuites et des solutions payantes sur GitHub, en fonction des besoins de votre organisation pour conserver l’historique des canaux publics et privés.</span><span class="sxs-lookup"><span data-stu-id="860d4-198">There are both free solutions on GitHub and paid solutions you can use, depending on your organization’s requirements to retain Channel History of Public and Private channels.</span></span> <span data-ttu-id="860d4-199">De plus, cela peut être scripté dans Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-199">Additionally, this could be scripted into Teams.</span></span>

<span data-ttu-id="860d4-200">Une fois que vous avez configuré votre nouvelle structure d’équipe et de canal dans Teams, vous pouvez copier les fichiers exportés dans les bibliothèques de documents appropriées dans les canaux Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-200">Once you’ve set up your new team and channel structure in Teams, you can copy the exported files into the appropriate document libraries in your Teams channels.</span></span>

<span data-ttu-id="860d4-201">Pour automatiser l’importation de votre contenu, plusieurs approches peuvent être considérées.</span><span class="sxs-lookup"><span data-stu-id="860d4-201">To automate the importing of your content, there are several approaches you can consider.</span></span> <span data-ttu-id="860d4-202">Il existe des solutions gratuites sur GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) ou [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) et des solutions de partenaires.</span><span class="sxs-lookup"><span data-stu-id="860d4-202">There are  free solutions on GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) or [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) and partner solutions.</span></span> <span data-ttu-id="860d4-203">Choisissez une solution en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="860d4-203">Choose a solution based on your organization’s needs.</span></span> 

### <a name="channel-files"></a><span data-ttu-id="860d4-204">Fichiers de canaux</span><span class="sxs-lookup"><span data-stu-id="860d4-204">Channel Files</span></span>

<span data-ttu-id="860d4-205">La plupart des solutions exportent des fichiers.</span><span class="sxs-lookup"><span data-stu-id="860d4-205">Most solutions will export files.</span></span> <span data-ttu-id="860d4-206">Toutefois, ils sont généralement fournis sous forme de liens dans l’historique des canaux qui nécessitent une clé API pour récupérer par programme.</span><span class="sxs-lookup"><span data-stu-id="860d4-206">However, they’re typically provided as links in the Channel History that require an API key to programmatically retrieve.</span></span>

<span data-ttu-id="860d4-207">Pour les fichiers stockés dans Slack, une fois que vous avez configuré vos équipes et canaux dans Teams, vous pouvez les copier par programme de Slack dans le canal cible de Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-207">For files stored in Slack, once you’ve set up your teams and channels in Teams, you can programmatically copy them from Slack into the target Teams channel.</span></span>

<span data-ttu-id="860d4-208">Le script suivant extrait des fichiers de Slack.</span><span class="sxs-lookup"><span data-stu-id="860d4-208">The following script retrieves files from Slack.</span></span> <span data-ttu-id="860d4-209">Il recherche l’exportation de Slack spécifiée sur votre ordinateur, crée un dossier dans chaque canal cible et télécharge tous les fichiers vers cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="860d4-209">It searches the specified Slack export on your computer, creates a folder in each target channel, and downloads all of the files to that location.</span></span> <span data-ttu-id="860d4-210">Des solutions tierces peuvent extraire des données.</span><span class="sxs-lookup"><span data-stu-id="860d4-210">Third-party solutions exist that can extract data.</span></span> <span data-ttu-id="860d4-211">Si vous avez besoin d’aide sur PowerShell, consultez [Prise en main d’Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="860d4-211">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>



```azurepowershell
$ExportPath = ".\slackHistory"
$ExportContents = Get-ChildItem -path $ExportPath -Recurse
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class File {
    [string] $Name
    [string] $Title
    [string] $Channel
    [string] $DownloadURL
    [string] $MimeType
    [double] $Size
    [string] $ParentPath
    [string] $Time
}

$channelList = Get-Content -Raw -Path .\slackHistory\channels.json | ConvertFrom-Json
$Files = New-Object -TypeName System.Collections.ObjectModel.Collection["File"]

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting Step 1 (processing channel export for files) of 2. Total Channel Count: $($channelList.Count)"
#Iterate through each Channel listed in the Archive
foreach ($channel in $channelList) {
    #Iterate through Channel folders from the Export
    foreach ($folder in $ExportContents)
    {
        #If Channel Name matches..
        if ($channel.name -eq $folder){
            $channelJsons = Get-ChildItem -Path $folder.FullName -File
            Write-Host -ForegroundColor White "$(Get-TimeStamp) Info: Starting to process $($channelJsons.Count) days of content for #$($channel.name)."
            #Start processing the daily JSON for files
            foreach ($json in $channelJsons){
                $currentJson = Get-Content -Raw -Path $json.FullName | ConvertFrom-Json
                #Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Info: Processing $($json.Name) in #$($channel.name).."
                #Iterate through every action
                foreach ($entry in $currentJson){
                    #If the action contained file(s)..
                    if($null -ne $entry.files){
                        #Iterate through each file and add it to the List of Files to download
                        foreach ($item in $entry.Files) {
                        $file = New-Object -TypeName File
                            if ($null -ne $item.url_private_download){
                                $file.Name = $item.name
                                $file.Title = $item.Title
                                $file.Channel = $channel.name
                                $file.DownloadURL = $item.url_private_download
                                $file.MimeType = $item.mimetype
                                $file.Size = $item.size
                                $file.ParentPath = $folder.FullName
                                $file.Time = $item.created
                                $files.Add($file)
                            }
                        }
                    }
                }
            }
        }
    }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 1 of 2 complete. `n"

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting step 2 (creating folders and downloading files) of 2."
#Determine which Files folders need to be created
$FoldersToMake = New-Object System.Collections.ObjectModel.Collection["string"]
foreach ($file in $files){
    if ($FoldersToMake -notcontains $file.Channel){
        $FoldersToMake.Add($file.Channel)
    }
}

#Create Folders
foreach ($folder in $FoldersToMake){
    #$fullFolderPath = $file.ParentPath + "\Files"
    $fullFolderPath = $ExportPath +"\$($folder)"
    $fullFilesPath = $ExportPath +"\$($folder)\Files"
    if (-not (Test-Path $fullFilesPath)){
        New-Item -Path $fullFolderPath  -Name "Files" -ItemType "directory"
    }
}

#Downloading Files
foreach ($file in $files)
{
    Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Downloading $($file.Name)."
    $fullFilePath = $file.ParentPath + "\Files\" + $file.Name
        if (-not (Test-Path $fullFilePath)){
            try{
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
        else {
            try{
                $extensionPosition = $file.name.LastIndexOf('.')
                $splitFileName = $file.name.Substring(0,$extensionPosition)
                $splitFileExtention = $file.name.Substring($extensionPosition)
                $newFileName = $splitFileName + $file.Time + $splitFileExtention
                $fullFilePath = $file.ParentPath + "\Files\" + $newFileName
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 2 of 2 complete. `n"
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Exiting.."
```


### <a name="apps-and-custom-integrations"></a><span data-ttu-id="860d4-212">Applications et intégrations personnalisées</span><span class="sxs-lookup"><span data-stu-id="860d4-212">Apps and Custom Integrations</span></span>
<span data-ttu-id="860d4-213">Consultez votre liste d’applications et d’intégrations personnalisées Slack (avec les configurations) et choisissez celles que vous voulez déplacer vers Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-213">Review your list of Slack apps and custom integrations (with configurations) and decide which ones you want to move to Teams.</span></span> <span data-ttu-id="860d4-214">Consultez le Marketplace de Teams pour savoir si une application est disponible.</span><span class="sxs-lookup"><span data-stu-id="860d4-214">Check the Teams Marketplace to see if an app is available.</span></span> <span data-ttu-id="860d4-215">Si ce n’est pas le cas, il peut exister d’autres solutions.</span><span class="sxs-lookup"><span data-stu-id="860d4-215">If not, there are likely alternatives.</span></span> 

<span data-ttu-id="860d4-216">Pour déterminer les applications à ajouter à Teams, il est important de comprendre la manière dont l’application est utilisée.</span><span class="sxs-lookup"><span data-stu-id="860d4-216">To figure out which apps to add to Teams, it’s important to understand how the app is being used.</span></span> <span data-ttu-id="860d4-217">En posant la question « quelle fonctionnalité est-ce que l’application fournit à ce canal ? », vous découvrirez le but de l’application.</span><span class="sxs-lookup"><span data-stu-id="860d4-217">By asking the question "what functionality is the app providing to this channel?", you'll learn about the outcome the app is delivering.</span></span> 

<span data-ttu-id="860d4-218">Dans de nombreux cas, les applications reçoivent principalement des données pilotées par les événements d’un service externe (par exemple, le système de surveillance) et envoient un message dans Slack.</span><span class="sxs-lookup"><span data-stu-id="860d4-218">In many cases, apps primarily receive event-driven data from an external service (for example, monitoring system) and push a message into Slack.</span></span> <span data-ttu-id="860d4-219">Vous pouvez obtenir le même résultat en utilisant un connecteur Microsoft 365 qui peut envoyer les messages au sein de Teams, sur la base d’événements.</span><span class="sxs-lookup"><span data-stu-id="860d4-219">You can achieve the same outcome by using a Microsoft 365 Connector that can push messages into Teams based on events.</span></span>

<span data-ttu-id="860d4-220">Vous trouverez ci-dessous des exemples de solution Slack dans laquelle un connecteur Office 365 était utilisé dans Teams pour l’intégration.</span><span class="sxs-lookup"><span data-stu-id="860d4-220">Below are examples of Slack solutions where an Office 365 Connector was used in Teams for integration.</span></span>
- <span data-ttu-id="860d4-221">Ansible</span><span class="sxs-lookup"><span data-stu-id="860d4-221">Ansible</span></span>
  - <span data-ttu-id="860d4-222">Les alertes peuvent être envoyées à Teams via [webhook Ansible](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook)</span><span class="sxs-lookup"><span data-stu-id="860d4-222">Alerts can be sent to Teams via [Ansible webhook](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook)</span></span>
- <span data-ttu-id="860d4-223">New Relic</span><span class="sxs-lookup"><span data-stu-id="860d4-223">New Relic</span></span>
  - <span data-ttu-id="860d4-224">Consultez cette solution utilisateur pour [Envoi d’alertes New Relic à Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span><span class="sxs-lookup"><span data-stu-id="860d4-224">Check out this user solution for [sending New Relic alerts to Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span></span>
- <span data-ttu-id="860d4-225">Nagios </span><span class="sxs-lookup"><span data-stu-id="860d4-225">Nagios</span></span>
  - <span data-ttu-id="860d4-226">Les alertes peuvent être intégrées aujourd’hui via les connecteurs.</span><span class="sxs-lookup"><span data-stu-id="860d4-226">Alerts can be integrated today via Connectors.</span></span> <span data-ttu-id="860d4-227">https://github.com/isaac-galvan/nagios-teams-notify</span><span class="sxs-lookup"><span data-stu-id="860d4-227"></span></span>
- <span data-ttu-id="860d4-228">ZenDesk</span><span class="sxs-lookup"><span data-stu-id="860d4-228">ZenDesk</span></span>
  - <span data-ttu-id="860d4-229">L’application existe dans le Store Teams</span><span class="sxs-lookup"><span data-stu-id="860d4-229">App exists in Teams Store</span></span>
- <span data-ttu-id="860d4-230">Jenkins</span><span class="sxs-lookup"><span data-stu-id="860d4-230">Jenkins</span></span>
  - <span data-ttu-id="860d4-231">Les alertes peuvent être envoyées à Teams à l’aide d'un[connecteur Office 365 Jenkins](https://plugins.jenkins.io/Office-365-Connector)</span><span class="sxs-lookup"><span data-stu-id="860d4-231">Alerts can be sent to Teams using [Jenkins’s Office 365 Connector](https://plugins.jenkins.io/Office-365-Connector)</span></span>


### <a name="user-readiness-and-adoption-plan"></a><span data-ttu-id="860d4-232">Plan d’adoption et de préparation des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="860d4-232">User readiness and adoption plan</span></span>
<span data-ttu-id="860d4-233">L’une des charnières de tout déploiement de logiciel réussi repose sur la façon dont les utilisateurs ont été préparés pour la modification.</span><span class="sxs-lookup"><span data-stu-id="860d4-233">The cornerstone of any successful software deployment hinges on how prepared users are for the change.</span></span> <span data-ttu-id="860d4-234">Les utilisateurs de votre organisation qui utilisent Slack comprendront facilement les concepts de Teams, mais une formation est néanmoins nécessaire pour simplifier la transition.</span><span class="sxs-lookup"><span data-stu-id="860d4-234">Users in your organization using Slack will easily understand Teams concepts, but training is still needed to help them make a smooth transition.</span></span> <span data-ttu-id="860d4-235">Pour un ensemble complet de ressources d’adoption de Teams, accédez au [Teams adoption Hub](adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="860d4-235">For a comprehensive set of Teams adoption resources, go to the [Teams adoption hub](adopt-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="860d4-236">Par exemple, les deux produits disposent de canaux, mais ils sont utilisés différemment dans chaque produit.</span><span class="sxs-lookup"><span data-stu-id="860d4-236">For example, both products feature channels, but they’re used differently in each product.</span></span> <span data-ttu-id="860d4-237">Par exemple, un canal dans Slack est souvent utilisé comme une conversation dans Teams pour les conversations transactionnelles à court terme.</span><span class="sxs-lookup"><span data-stu-id="860d4-237">For example, often a Channel in Slack is used like a chat in Teams for short-term, transactional conversations.</span></span> <span data-ttu-id="860d4-238">Les autres différences notables concernent les conversations à thème/sans thème et le réglage des paramètres de notification.</span><span class="sxs-lookup"><span data-stu-id="860d4-238">Other notable differences are around threaded/non-threaded conversations and tuning notification settings.</span></span>

<span data-ttu-id="860d4-239">Consultez notre bibliothèque complète de [formation utilisateurs finaux Teams](enduser-training.md).</span><span class="sxs-lookup"><span data-stu-id="860d4-239">Check out our rich library of [End-user Teams training](enduser-training.md).</span></span> 

## <a name="move-to-teams"></a><span data-ttu-id="860d4-240">Migrer vers Teams</span><span class="sxs-lookup"><span data-stu-id="860d4-240">Move users from on-premises to Teams</span></span> 
<span data-ttu-id="860d4-241">À présent que votre plan de transition est défini, vous pouvez commencer à créer vos équipes et canaux dans Teams.</span><span class="sxs-lookup"><span data-stu-id="860d4-241">Now that your transition plan is defined, you can begin creating your teams and channels in Teams.</span></span> 

<span data-ttu-id="860d4-242">Une fois que vous avez créé vos équipes & canaux, commencez à copier les fichiers à partir de Slack dans Teams et à configurer vos applications.</span><span class="sxs-lookup"><span data-stu-id="860d4-242">Once you’ve created your teams & channels, begin copying files from Slack channels into Teams and configuring your apps.</span></span> <span data-ttu-id="860d4-243">Si vous utilisez une solution pour conserver l’historique, celle-ci peut également être configurée.</span><span class="sxs-lookup"><span data-stu-id="860d4-243">If you’re using a solution to retain history, that can be configured now as well.</span></span> <span data-ttu-id="860d4-244">Ensuite, vous êtes prêt à commencer à attribuer des licences aux utilisateurs (s’ils ne sont pas déjà titulaires d’une licence) et à les ajouter aux équipes appropriées.</span><span class="sxs-lookup"><span data-stu-id="860d4-244">Then you’re ready to start licensing users (if they aren’t licensed already) and adding them to the appropriate teams.</span></span> <span data-ttu-id="860d4-245">Pour réduire la nécessité d’effectuer d’autres exportations et copies de fichiers, vous pouvez supprimer l’accès à Slack à une date convenue qui coïncide avec l’ajout de chaque utilisateur à l’équipe.</span><span class="sxs-lookup"><span data-stu-id="860d4-245">To reduce the need for additional exports and file copies, consider removing Slack access at an agreed-upon date that coincides with each user’s addition to the team.</span></span> <span data-ttu-id="860d4-246">Cela évite d’avoir à réexporter et importer les modifications différentielles sur les fichiers et sur l’historique.</span><span class="sxs-lookup"><span data-stu-id="860d4-246">This avoids needing to re-export and import delta changes on files and history.</span></span>

<span data-ttu-id="860d4-247">Suivez les étapes décrites dans le diagramme ci-dessous pour déployer Teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="860d4-247">Follow the steps in the diagram below to roll out Teams in your organization.</span></span> <span data-ttu-id="860d4-248">Pour plus d’informations, voir [comment déployer Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="860d4-248">For more information, check out [How to roll out Teams](How-to-roll-out-teams.md).</span></span>


<span data-ttu-id="860d4-249">:::image type="content" source="media/migrate-slack-to-teams-image4.png" alt-text="Diagramme répertoriant les étapes de transition vers Teams à partir de Slack.":::</span><span class="sxs-lookup"><span data-stu-id="860d4-249">:::image type="content" source="media/migrate-slack-to-teams-image4.png" alt-text="Diagram listing the steps of moving to Teams from Slack.":::</span></span>
