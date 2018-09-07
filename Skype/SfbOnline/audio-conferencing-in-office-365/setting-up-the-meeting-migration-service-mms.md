---
title: Configuration de Meeting Migration Service (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) est un service Skype Entreprise qui s'exécute en arrière-plan et met automatiquement à jour les réunions Skype Entreprise et Microsoft Teams pour les utilisateurs. MMS est conçu pour que les utilisateurs n'aient plus besoin d'exécuter l'outil de migration des réunions pour mettre à jour leurs réunions Skype Entreprise et Microsoft Teams.
ms.openlocfilehash: 562cc616af59ee2fb87b5a2a023c9efe6c3093c3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854314"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="334d3-104">Configuration de Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="334d3-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="334d3-105">Meeting Migration Service (MMS) est un service Skype Entreprise qui s'exécute en arrière-plan et met automatiquement à jour les réunions Skype Entreprise et Microsoft Teams pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="334d3-105">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype meetings for users.</span></span> <span data-ttu-id="334d3-106">MMS est conçu pour que les utilisateurs n'aient plus besoin d'exécuter l'outil de migration des réunions pour mettre à jour leurs réunions Skype Entreprise et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="334d3-106">MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype meetings.</span></span>  <span data-ttu-id="334d3-107">Cet outil ne migre pas les réunions Skype Entreprise vers les réunions Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="334d3-107">This tool does not migrate Skype for Business meetings into Microsoft Teams meetings.</span></span>  
  
 <span data-ttu-id="334d3-108">**Configuration requise**</span><span class="sxs-lookup"><span data-stu-id="334d3-108">**Requirements**</span></span>
  
<span data-ttu-id="334d3-109">Pour que MMS fonctionne, les boîtes aux lettres des organisateurs de réunion doivent être sur Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="334d3-109">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="334d3-110">**Principaux scénarios**</span><span class="sxs-lookup"><span data-stu-id="334d3-110">**Primary scenarios**</span></span>
  
<span data-ttu-id="334d3-111">MMS met à jour les réunions Skype d'un utilisateur pour les deux situations suivants :</span><span class="sxs-lookup"><span data-stu-id="334d3-111">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="334d3-112">Lorsque l'utilisateur migre localement de Skype Entreprise Server vers Skype Entreprise Online.
</span><span class="sxs-lookup"><span data-stu-id="334d3-112">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online</span></span>
    
- <span data-ttu-id="334d3-113">Lorsqu'un administrateur apporte une modification aux paramètres d'audioconférence de l'utilisateur qui nécessiterait la mise à jour des informations d'audioconférence dans les réunions de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="334d3-113">When an admin makes a change to the user's dial-in conferencing settings that would require updating the dial-in conferencing information in that user's meetings</span></span>
    
 <span data-ttu-id="334d3-114">**Scénarios courants pour lesquels vous ne pouvez pas utiliser MMS**</span><span class="sxs-lookup"><span data-stu-id="334d3-114">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="334d3-p103">Voici quelques scénarios courants qui peuvent s'appliquer. Tous ces scénarios prennent en charge la migration. Toutefois, MMS ne fonctionne pas pour ces scénarios ; vous devez utiliser [l'outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="334d3-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="334d3-118">L'emplacement des boîtes aux lettres de l'utilisateur se trouve sur une version locale de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="334d3-118">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="334d3-119">Utilisation d'un fournisseur d'audioconférence tiers</span><span class="sxs-lookup"><span data-stu-id="334d3-119">Using a third-party dial-in conferencing provider</span></span>
    
- <span data-ttu-id="334d3-120">Migration des utilisateurs de Skype Entreprise Online vers Skype Server local</span><span class="sxs-lookup"><span data-stu-id="334d3-120">Migrating users from Skype for Business online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="334d3-121">Mise à jour des réunions lorsqu'un utilisateur local est migré vers Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="334d3-121">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="334d3-122">C'est le scénario le plus courant où MMS peut aider à créer une transition plus fluide pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="334d3-122">This is the most common scenario where MMS can help create a smoother transition for your users.</span></span> <span data-ttu-id="334d3-123">Lorsqu'un utilisateur migre d'un Skype Entreprise Server local vers Skype Entreprise Online, MMS détectera le nouvel utilisateur et analysera le calendrier de cet utilisateur pour les réunions Skype Entreprise et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="334d3-123">When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype meetings.</span></span> <span data-ttu-id="334d3-124">Toute réunion future sera mise à jour avec les nouvelles informations pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="334d3-124">Any future Skype meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="334d3-125">Si vous utilisez actuellement Skype Server 2015 pour l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="334d3-125">If you're currently using Skype Server 2015 for dial-in conferencing</span></span>

<span data-ttu-id="334d3-126">Nous vous recommandons de suivre les meilleures pratiques suivantes afin d'exploiter pleinement MMS pour ce scénario :</span><span class="sxs-lookup"><span data-stu-id="334d3-126">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="334d3-127">Puisque, pour que MMS fonctionne, la boîte aux lettres de l'utilisateur doit être sur Exchange Online, si vous effectuez une migration depuis Exchange Server sur site, déplacez d'abord la boîte aux lettres de l'utilisateur vers Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="334d3-127">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="334d3-128">Attribuez la licence d' **audioconférence** à l'utilisateur avant d'exécuter le `Move-CSUser` cmdlet pour effectuer une migration de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="334d3-128">Assign the PSTN Conferencing license to the user before you run the   cmdlet to migrate the user.</span></span> <span data-ttu-id="334d3-129">En effet, MMS met également à jour les réunions lorsque les paramètres d'audioconférence sont modifiés pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="334d3-129">This is because MMS also updates meetings when dial-in conferencing settings are changed for a user.</span></span> <span data-ttu-id="334d3-130">Si vous n'attribuez pas d'abord la licence, MMS mettra à jour toutes les réunions, à nouveau, lorsque vous attribuerez la licence.</span><span class="sxs-lookup"><span data-stu-id="334d3-130">If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="334d3-131">Si vous utilisez actuellement un fournisseur de services d'audioconférence (ACP) tiers</span><span class="sxs-lookup"><span data-stu-id="334d3-131">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="334d3-132">Avec un ACP tiers, le fait que MMS s'exécute ou pas dépend des paramètres d'audioconférence de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="334d3-132">With a third-party ACP, whether or not MMS runs depends on your organization's dial-in conferencing settings.</span></span> <span data-ttu-id="334d3-133">Vous pouvez choisir de remplacer automatiquement les numéros d'appel à partir de votre ACP, lorsque vous attribuez une licence d' **audioconférence** à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="334d3-133">You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a PSTN Conferencing license.</span></span> <span data-ttu-id="334d3-134">Toutefois, vous pouvez également choisir d'éviter un tel remplacement et de conserver les numéros d'appel à partir de votre ACP.</span><span class="sxs-lookup"><span data-stu-id="334d3-134">On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP.</span></span> <span data-ttu-id="334d3-135">Pour voir les paramètres de votre organisation, exécutez la commande Windows PowerShell suivante et vérifiez la valeur du paramètre `AutomaticallyReplaceAcpProvider`.</span><span class="sxs-lookup"><span data-stu-id="334d3-135">To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter  `AutomaticallyReplaceAcpProvider`.</span></span> <span data-ttu-id="334d3-136">Si vous avez besoin d'aide pour utiliser PowerShell, consultez la section [Utilisation de PowerShell pour gérer votre entreprise dans Skype Entreprise](setting-up-the-meeting-migration-service-mms.md#WPSInfo) à la fin de cet article.</span><span class="sxs-lookup"><span data-stu-id="334d3-136">If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="334d3-137">Si la valeur de ce paramètre est $true, alors MMS s'exécutera quand un utilisateur se verra attribuer une licence d' **audioconférence** et mettra à jour leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="334d3-137">If the value of this parameter is $true, then MMS will run when a user is assigned a PSTN Conferencing license and update their meetings.</span></span> <span data-ttu-id="334d3-138">Les numéros d'appel de votre ACP sont conservés jusqu'à l'attribution de la licence d' **audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="334d3-138">The dial-in numbers from your ACP are retained until the PSTN Conferencing license is assigned.</span></span>
    
- <span data-ttu-id="334d3-139">Si la valeur de ce paramètre est $false, alors MMS ne mettra pas à jour les réunions, même si un utilisateur se voit attribuer une licence **d'audioconférence** .</span><span class="sxs-lookup"><span data-stu-id="334d3-139">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a PSTN Conferencing licence.</span></span> <span data-ttu-id="334d3-140">Les numéros d'appel de votre ACP sont conservés, jusqu'à ce que l'utilisateur soit manuellement configuré pour l'audioconférence dans le centre d'administration Skype Entreprise ou en utilisant Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="334d3-140">The dial-in numbers from your ACP are retained until the user is manually provisioned for dial-in conferencing in Skype admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="334d3-141">Mise à jour des réunions lorsque les paramètres d'audioconférence d'un utilisateur changent</span><span class="sxs-lookup"><span data-stu-id="334d3-141">Updating meetings when a user's dial-in conferencing settings change</span></span>

<span data-ttu-id="334d3-142">MMS mettra à jour les réunions existantes de Skype Entreprise et Microsoft Teams dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="334d3-142">MMS will update an existing Skype for Business online user's meetings in the following cases:</span></span>
  
- <span data-ttu-id="334d3-143">Lorsque vous attribuez ou supprimez une licence d' **audioconférence** .</span><span class="sxs-lookup"><span data-stu-id="334d3-143">When you assign or remove PSTN Conferencing license</span></span>
    
- <span data-ttu-id="334d3-144">Lorsque vous activez ou désactivez les services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="334d3-144">When you enable or disable dial-in conferencing</span></span>
    
- <span data-ttu-id="334d3-145">Lorsque vous modifiez ou réinitialisez l'ID de conférence pour un utilisateur configuré pour les réunions publiques.</span><span class="sxs-lookup"><span data-stu-id="334d3-145">When you change or reset the Conference ID for a user configured to use public meetings</span></span>
    
- <span data-ttu-id="334d3-146">Lorsque vous déplacez l'utilisateur vers un nouveau pont d'audioconférence.</span><span class="sxs-lookup"><span data-stu-id="334d3-146">When you move the user to a new dial-in conferencing bridge</span></span>
    
- <span data-ttu-id="334d3-147">Lorsqu'un numéro de cellulaire n'est pas attribué depuis un pont d'audioconférence.</span><span class="sxs-lookup"><span data-stu-id="334d3-147">When a phone number is unassigned from a dial-in conferencing bridge.</span></span> <span data-ttu-id="334d3-148">Il s'agit d'un scénario complexe qui nécessite des étapes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="334d3-148">This is a complex scenario which requires additional steps.</span></span> <span data-ttu-id="334d3-149">Pour en savoir plus, consultez la section [Modifiez les numéros payants ou les numéros gratuits sur votre pont d'audioconférence](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="334d3-149">For more information, see [Change the toll or toll-free numbers on your dial-in conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="334d3-150">MMS ne met à jour les réunions que lorsque vous utilisez le pont Microsoft.</span><span class="sxs-lookup"><span data-stu-id="334d3-150">MMS only updates meetings when you're using the Microsoft bridge.</span></span> <span data-ttu-id="334d3-151">Si vous utilisez un fournisseur d'audioconférence tiers, les utilisateurs devront mettre à jour leurs réunions manuellement.</span><span class="sxs-lookup"><span data-stu-id="334d3-151">If you are using a third-party dial-in conferencing provider, the users will need to update their meetings manually.</span></span> <span data-ttu-id="334d3-152">Dans ce cas, vous pouvez utiliser l'[outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="334d3-152">In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="334d3-153">Seules certaines modifications des paramètres d'audioconférence d'un utilisateur déclenchent MMS.</span><span class="sxs-lookup"><span data-stu-id="334d3-153">Not all changes to a user's dial-in conferencing settings trigger MMS.</span></span> <span data-ttu-id="334d3-154">Les deux modifications suivantes n'entraînent pas la mise à jour des réunions par MMS :</span><span class="sxs-lookup"><span data-stu-id="334d3-154">Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="334d3-155">la modification de l'adresse SIP de l'organisateur de la réunion (qu'il s'agisse de son nom d'utilisateur SIP ou son domaine SIP) ;</span><span class="sxs-lookup"><span data-stu-id="334d3-155">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="334d3-156">la modification de l'URL de réunion de votre entreprise à l'aide de la commande [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).</span><span class="sxs-lookup"><span data-stu-id="334d3-156">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="334d3-157">Que se passe-t-il lorsque MMS met à jour des réunions ?</span><span class="sxs-lookup"><span data-stu-id="334d3-157">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="334d3-158">Lorsque MMS détecte que les réunions d'un utilisateur doivent être mises à jour, le service effectue les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="334d3-158">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="334d3-159">Identifier toutes les réunions Skype Entreprise et Microsoft Teams planifiées par l'utilisateur dans le futur</span><span class="sxs-lookup"><span data-stu-id="334d3-159">Identify all Skype meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="334d3-160">Toutes les réunions Skype Entreprise ou Microsoft Teams qui ont eu lieu avant l'exécution de MMS sont ignorées
</span><span class="sxs-lookup"><span data-stu-id="334d3-160">Any Skype meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="334d3-161">Seules les réunions dont l'utilisateur est l'organisateur sont mises à jour
</span><span class="sxs-lookup"><span data-stu-id="334d3-161">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="334d3-162">Il remplace le bloc d'informations de la réunion en ligne dans les détails de la réunion.</span><span class="sxs-lookup"><span data-stu-id="334d3-162">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="334d3-163">Il envoie des mises à jour à tous les destinataires de la réunion de la part de l'organisateur.</span><span class="sxs-lookup"><span data-stu-id="334d3-163">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="334d3-164">**Combien de temps faut-il pour que MMS fonctionne ?**</span><span class="sxs-lookup"><span data-stu-id="334d3-164">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="334d3-165">Le temps nécessaire au MMS pour migrer des réunions varie en fonction du nombre d'utilisateurs impliqués et du nombre total de réunions Skype Entreprise ou Microsoft Teams que chaque utilisateur a dans son calendrier.</span><span class="sxs-lookup"><span data-stu-id="334d3-165">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype meetings each user has on their calendar.</span></span> <span data-ttu-id="334d3-166">La migration dure au minimum 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="334d3-166">At a minimum, it will take 10 minutes to run.</span></span> <span data-ttu-id="334d3-167">Bien que des migrations importantes puissent prendre jusqu'à 12 heures, la plupart sont effectuées en moins d'une heure.</span><span class="sxs-lookup"><span data-stu-id="334d3-167">While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="334d3-168">**Limites et problèmes potentiels**</span><span class="sxs-lookup"><span data-stu-id="334d3-168">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="334d3-169">Seules les réunions Skype Entreprise ou Microsoft Teams qui ont été planifiées en cliquant sur le bouton **Ajouter une réunion Skype** dans Outlook sur le Web ou en utilisant le module d'extension Réunion Skype pour Outlook sont migrées.</span><span class="sxs-lookup"><span data-stu-id="334d3-169">Only the Skype meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="334d3-170">En d'autres termes, si un utilisateur copie et colle les informations relatives à une réunion en ligne Skype dans une nouvelle réunion, cette nouvelle réunion n'est pas mise à jour.</span><span class="sxs-lookup"><span data-stu-id="334d3-170">In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="334d3-p114">Lorsqu'une réunion est migrée, MMS remplace tous les éléments du bloc d'information de la réunion en ligne. Ainsi, si un utilisateur a modifié ce bloc, ses modifications sont écrasées. Le contenu indiqué dans les détails de la réunion et qui ne fait pas partie du bloc d'informations de la réunion en ligne n'est pas modifié.</span><span class="sxs-lookup"><span data-stu-id="334d3-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![Le bloc de réunion mis à jour par MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="334d3-p115">Le contenu relatif à la réunion qui a été créé ou joint à la réunion (tableaux blancs, sondages, etc.) n'est pas conservé après l'exécution de MMS Si les organisateurs de votre réunion ont joint du contenu aux réunions à l'avance, ce contenu doit être recréé après l'exécution de MMS.</span><span class="sxs-lookup"><span data-stu-id="334d3-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="334d3-p116">Le lien vers les notes de réunion partagées dans l'élément du calendrier, ainsi que dans Skype, est également écrasé. Le contenu des notes de réunion enregistrées dans OneNote n'est pas supprimé : seul le lien vers les notes partagées est écrasé.</span><span class="sxs-lookup"><span data-stu-id="334d3-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="334d3-179">Les réunions comptant plus de 250 participants (organisateur inclus) ne feront pas l'objet d'une migration.</span><span class="sxs-lookup"><span data-stu-id="334d3-179">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="334d3-180">Certains caractères Unicode dans le corps de l'invitation peuvent être mis à jour de manière incorrecte et remplacés par l'un des caractères spéciaux suivants : ï, ¿, ½, �.</span><span class="sxs-lookup"><span data-stu-id="334d3-180">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="334d3-181">Que voient les utilisateurs lorsque MMS met à jour leurs réunions ?</span><span class="sxs-lookup"><span data-stu-id="334d3-181">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="334d3-182">Tout comme l'outil de migration de réunion, MMS envoie des mises à jour de réunion à la place des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="334d3-182">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users.</span></span> <span data-ttu-id="334d3-183">Vos utilisateurs ne verront ainsi qu'un nouveau cycle de notifications d'approbation pour leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="334d3-183">Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings.</span></span> <span data-ttu-id="334d3-184">Cela peut être déroutant pour les utilisateurs. Nous vous recommandons donc d'avertir vos utilisateurs à l'avance, non seulement lorsque vous migrez de vos locaux vers Skype Entreprise Online, mais aussi lorsque vous effectuez des changements d'audioconférence qui déclencheront MMS.</span><span class="sxs-lookup"><span data-stu-id="334d3-184">This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make dial-in conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="334d3-185">Gestion de MMS</span><span class="sxs-lookup"><span data-stu-id="334d3-185">Managing MMS</span></span>

<span data-ttu-id="334d3-186">Vous devez utiliser Windows PowerShell pour gérer MMS et vérifier le statut des migrations en cours.</span><span class="sxs-lookup"><span data-stu-id="334d3-186">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations.</span></span> <span data-ttu-id="334d3-187">Les informations contenues dans cette section supposent que vous maîtrisez suffisamment PowerSHell pour gérer votre organisation dans Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="334d3-187">The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization.</span></span> <span data-ttu-id="334d3-188">Si vous êtes nouveau dans PowerShell, consultez la section [Utilisation de PowerShell pour gérer votre organisation Skype Entreprise](setting-up-the-meeting-migration-service-mms.md#WPSInfo) à la fin de cet article.</span><span class="sxs-lookup"><span data-stu-id="334d3-188">If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="334d3-189">Comment puis-je vérifier le statut des migrations de réunion ?</span><span class="sxs-lookup"><span data-stu-id="334d3-189">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="334d3-p119">Utilisez l'applet de commande  `Get-CsMeetingMigrationStatus` pour vérifier le statut des migrations de réunion. Vous trouverez ci-dessous plusieurs exemples.</span><span class="sxs-lookup"><span data-stu-id="334d3-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="334d3-192">Pour obtenir un statut récapitulatif pour toutes les migrations MMS, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="334d3-192">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="334d3-193">Cela vous permettra de bénéficier de la vue tabulaire suivante des états de toutes les migrations :</span><span class="sxs-lookup"><span data-stu-id="334d3-193">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="334d3-194">État UserCount---------------</span><span class="sxs-lookup"><span data-stu-id="334d3-194">State UserCount---------------</span></span><br/> <span data-ttu-id="334d3-195">En attente 21</span><span class="sxs-lookup"><span data-stu-id="334d3-195">Pending 21</span></span><br/><span data-ttu-id="334d3-196">En cours 6</span><span class="sxs-lookup"><span data-stu-id="334d3-196">InProgress 6</span></span><br/> <span data-ttu-id="334d3-197">Échec 2</span><span class="sxs-lookup"><span data-stu-id="334d3-197">Failed 2</span></span> <br/> <span data-ttu-id="334d3-198">Succès 131</span><span class="sxs-lookup"><span data-stu-id="334d3-198">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="334d3-p120">Si certaines des migrations ont le statut Échoué, agissez de façon à résoudre ces problèmes le plus tôt possible. Il est impossible de participer aux réunions organisées par ces utilisateurs tant que ces problèmes ne sont pas résolus. Consultez la section [Que faire en cas d'erreur ?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="334d3-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="334d3-p121">Pour obtenir les détails complets de toutes les migrations d'une période précise, vous pouvez utiliser les paramètres  `StartTime` et `EndTime`. Par exemple, la commande suivante permet d'obtenir les détails complets de toutes les migrations qui ont eu lieu du 1er au 8 octobre 2016.</span><span class="sxs-lookup"><span data-stu-id="334d3-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="334d3-p122">Vous pouvez également vérifier le statut de migration d'un utilisateur particulier, en utilisant le paramètre  `UserId`. Ainsi, la commande suivante permet d'obtenir le statut de l'utilisateur ashaw@contoso.com :</span><span class="sxs-lookup"><span data-stu-id="334d3-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="334d3-206">Que faire en cas d'erreur ?</span><span class="sxs-lookup"><span data-stu-id="334d3-206">What do I do if there is an error?</span></span>
<span data-ttu-id="334d3-207"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="334d3-207"><a name="Troubleshooting"> </a></span></span>

<span data-ttu-id="334d3-208">Lorsque vous exécutez l'applet de commande  `Get-CsMeetingMigrationStatus` pour obtenir une vue récapitulative et remarquez que le statut Échouéconcernent une ou plusieurs migrations, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="334d3-208">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="334d3-p123">Identifiez les utilisateurs concernés. Exécutez la commande suivante pour obtenir la liste des utilisateurs concernés, ainsi que l'erreur spécifique signalée :</span><span class="sxs-lookup"><span data-stu-id="334d3-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="334d3-211">Pour chaque utilisateur, exécutez l'[outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047) afin de migrer manuellement leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="334d3-211">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="334d3-212">Si la migration ne fonctionne toujours pas avec l'outil de migration de réunions, vous disposez de deux options :</span><span class="sxs-lookup"><span data-stu-id="334d3-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="334d3-213">demander aux utilisateurs de créer de nouvelles réunions Skype ;</span><span class="sxs-lookup"><span data-stu-id="334d3-213">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="334d3-214">[contacter le support technique](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="334d3-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="334d3-215">Activation et désactivation de MMS</span><span class="sxs-lookup"><span data-stu-id="334d3-215">Enabling and disabling MMS</span></span>
<span data-ttu-id="334d3-216"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="334d3-216"><a name="Troubleshooting"> </a></span></span>

<span data-ttu-id="334d3-217">MMS est activé par défaut pour toutes les organisations, mais peut être désactivé au besoin.</span><span class="sxs-lookup"><span data-stu-id="334d3-217">MMS is enabled by default for all organizations, but it can be disabled as needed.</span></span> <span data-ttu-id="334d3-218">Par exemple, si vous souhaitez effectuer une migration, manuellement, de toutes les réunions ou si vous utilisez un fournisseur d'audioconférence tiers, il se peut que vous n'ayez pas besoin de MMS en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="334d3-218">For example, if you want to manually migrate all meetings or if you use a third-party dial-in conferencing provider, you may not need MMS running.</span></span> <span data-ttu-id="334d3-219">Vous pouvez également choisir de désactiver MMS temporairement.</span><span class="sxs-lookup"><span data-stu-id="334d3-219">You may also choose to temporarily disable MMS.</span></span> <span data-ttu-id="334d3-220">Par exemple, vous pouvez apporter des modifications importantes aux paramètres d'audioconférence de votre organisation et vous ne voulez pas que MMS s'exécute tant que toutes les modifications ne sont pas terminées.</span><span class="sxs-lookup"><span data-stu-id="334d3-220">For example, you may be doing substantial changes to the dial-in conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="334d3-p125">Pour voir si MMS est activé pour votre entreprise, exécutez la commande suivante et vérifier la valeur du paramètre  `MeetingMigrationEnabled`. Si le paramètre a pour valeur $true, MMS est activé.</span><span class="sxs-lookup"><span data-stu-id="334d3-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="334d3-223">Pour désactiver MMS, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="334d3-223">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="334d3-224">Pour activer MMS, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="334d3-224">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="334d3-225">Activation et désactivation de MMS uniquement pour les modifications de services d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="334d3-225">Enabling and disabling MMS only for dial-in conferencing changes</span></span>
<span data-ttu-id="334d3-226"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="334d3-226"><a name="Troubleshooting"> </a></span></span>

<span data-ttu-id="334d3-227">Vous pouvez également désactiver MMS uniquement pour les modifications de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="334d3-227">You can also disable MMS only for dial-in conferencing changes.</span></span> <span data-ttu-id="334d3-228">Il continuera à s'exécuter lorsqu'un utilisateur est migré deSkype Entreprise local vers Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="334d3-228">It will still run when a user is migrated from Skype on-premises to Skype for Business Online.</span></span> <span data-ttu-id="334d3-229">Pour vérifier l'état actuel du MMS pour les mises à jour des audioconférences, exécutez la commande suivante et vérifiez la valeur du  `AutomaticallyMigrateUserMeetings` paramètre.</span><span class="sxs-lookup"><span data-stu-id="334d3-229">To check the current MMS status for dial-in conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter.</span></span> <span data-ttu-id="334d3-230">Si ce paramètre est défini sur $true, MMS est configuré pour mettre à jour les réunions d'utilisateurs lorsque les paramètres d'audioconférence sont modifiés.</span><span class="sxs-lookup"><span data-stu-id="334d3-230">If this parameter is set to$true, MMS is set to update user meetings when dial-in conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="334d3-231">Pour désactiver MMS pour les audioconférences, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="334d3-231">To disable MMS for dial-in conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="334d3-232">Pour activer MMS pour les audioconférences, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="334d3-232">To enable MMS for dial-in conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="334d3-233">Comment puis-je exécuter manuellement une migration de réunion pour un utilisateur ?</span><span class="sxs-lookup"><span data-stu-id="334d3-233">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="334d3-234"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="334d3-234"><a name="Troubleshooting"> </a></span></span>

<span data-ttu-id="334d3-235">En plus des migrations automatiques de réunion, vous pouvez également exécuter manuellement la migration de réunion pour un utilisateur, en exécutant le cmdlet **Start-CsExMeetingMigration**.</span><span class="sxs-lookup"><span data-stu-id="334d3-235">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**. This cmdlet addsthe user in meeting migration queue. Meeting Migration Service will read the user request and migrate their meetings. You can check the status of meeting migration by cmdlet Get-CsMeetingMigrationStatus.</span></span> <span data-ttu-id="334d3-236">Ce cmdlet ajoute l'utilisateur dans la file d'attente de migration de réunion.</span><span class="sxs-lookup"><span data-stu-id="334d3-236">This cmdlet adds the user in meeting migration queue.</span></span> <span data-ttu-id="334d3-237">Meeting Migration Service lira la demande de l'utilisateur et effectuera une migration de leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="334d3-237">Meeting Migration Service will read the user request and migrate their meetings.</span></span> <span data-ttu-id="334d3-238">Vous pouvez vérifier le statut de la migration des réunions par cmdlet **Get-CsMeetingMigrationStatus**.</span><span class="sxs-lookup"><span data-stu-id="334d3-238">You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="334d3-239">Voici un exemple qui déclenche la migration de réunion pour l'utilisateur ashaw@contoso.com :</span><span class="sxs-lookup"><span data-stu-id="334d3-239">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="334d3-240">Utilisation de PowerShell pour gérer votre entreprise dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="334d3-240">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="334d3-241"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="334d3-241"><a name="WPSInfo"> </a></span></span>

 <span data-ttu-id="334d3-242">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="334d3-242">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="334d3-243">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="334d3-243">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="334d3-244">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="334d3-244">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="334d3-p128">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="334d3-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="334d3-p129">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="334d3-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="334d3-251">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="334d3-251">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="334d3-252">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="334d3-252">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="334d3-253">Depuis le **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="334d3-253">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="334d3-254">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="334d3-254">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="334d3-255">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="334d3-255">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="334d3-256">Pour plus d'informations sur le démarrage de Windows PowerShell, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou[Connexion à Skype Entreprise Online à l'aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="334d3-256">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="334d3-p130">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="334d3-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="334d3-260">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="334d3-260">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="334d3-261">Pourquoi vous devez utiliser Office 365 PowerShell
</span><span class="sxs-lookup"><span data-stu-id="334d3-261">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="334d3-p131">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="334d3-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="334d3-264">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="334d3-264">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="334d3-265">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="334d3-265">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="334d3-266">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="334d3-266">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="334d3-267">Sujets connexes</span><span class="sxs-lookup"><span data-stu-id="334d3-267">Related topics</span></span>

[<span data-ttu-id="334d3-268">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="334d3-268">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
