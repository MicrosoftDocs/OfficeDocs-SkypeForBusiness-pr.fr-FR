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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Service de Migration (MMS) de la réunion est un Skype pour le service Business qui s’exécute en arrière-plan et met à jour automatiquement Skype pour les réunions d’entreprise et Teams Microsoft pour les utilisateurs. MMS est conçu pour éliminer le besoin pour les utilisateurs d’exécuter l’outil de Migration de réunion pour mettre à jour leur Skype pour les réunions d’entreprise et Teams Microsoft.
ms.openlocfilehash: b5484459fc01337bd9eb2dad38e9f0e3349abd07
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674584"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="967af-104">Configuration de Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="967af-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="967af-105">Service de Migration (MMS) de la réunion est un Skype pour le service Business qui s’exécute en arrière-plan et met à jour automatiquement Skype pour les réunions d’entreprise et Teams Microsoft pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="967af-105">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users.</span></span> <span data-ttu-id="967af-106">MMS est conçu pour éliminer le besoin pour les utilisateurs d’exécuter l’outil de Migration de réunion pour mettre à jour leur Skype pour les réunions d’entreprise et Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="967af-106">MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.</span></span>  <span data-ttu-id="967af-107">Cet outil ne migre pas les réunions Skype Entreprise vers les réunions Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="967af-107">This tool does not migrate Skype for Business meetings into Microsoft Teams meetings.</span></span>  
  
 <span data-ttu-id="967af-108">**Configuration requise**</span><span class="sxs-lookup"><span data-stu-id="967af-108">**Requirements**</span></span>
  
<span data-ttu-id="967af-109">Pour que MMS fonctionne, les boîtes aux lettres des organisateurs de réunion doivent être sur Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="967af-109">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="967af-110">**Principaux scénarios**</span><span class="sxs-lookup"><span data-stu-id="967af-110">**Primary scenarios**</span></span>
  
<span data-ttu-id="967af-111">MMS met à jour les réunions Skype d'un utilisateur pour les deux situations suivants :</span><span class="sxs-lookup"><span data-stu-id="967af-111">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="967af-112">Lorsque l’utilisateur est migré locale Skype pour Business Server Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="967af-112">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online.</span></span>
    
- <span data-ttu-id="967af-113">Lorsque un administrateur effectue une modification aux paramètres de conférence audio de l’utilisateur qui nécessitent la mise à jour les informations de services d’audioconférence dans les réunions de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="967af-113">When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.</span></span>
    
  <span data-ttu-id="967af-114">**Scénarios courants pour lesquels vous ne pouvez pas utiliser MMS**</span><span class="sxs-lookup"><span data-stu-id="967af-114">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="967af-p103">Voici quelques scénarios courants qui peuvent s'appliquer. Tous ces scénarios prennent en charge la migration. Toutefois, MMS ne fonctionne pas pour ces scénarios ; vous devez utiliser [l'outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="967af-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="967af-118">L'emplacement des boîtes aux lettres de l'utilisateur se trouve sur une version locale de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="967af-118">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="967af-119">À l’aide d’un fournisseur de services d’audioconférence tiers</span><span class="sxs-lookup"><span data-stu-id="967af-119">Using a third-party audio conferencing provider</span></span>
    
- <span data-ttu-id="967af-120">Migration d’utilisateurs de Skype pour Business en ligne pour le serveur local Skype</span><span class="sxs-lookup"><span data-stu-id="967af-120">Migrating users from Skype for Business Online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="967af-121">Mise à jour des réunions lorsqu'un utilisateur sur site est migré vers Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="967af-121">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="967af-122">Il s'agit du scénario de simplification de la transition de vos utilisateurs avec MMS le plus courant.</span><span class="sxs-lookup"><span data-stu-id="967af-122">This is the most common scenario where MMS can help create a smoother transition for your users.</span></span> <span data-ttu-id="967af-123">Lorsqu’un utilisateur est migré à partir d’un Skype locale pour Business Server vers Skype pour Business Online, MMS détecte le nouvel utilisateur et recherchera calendrier de cet utilisateur Skype pour les réunions d’entreprise et Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="967af-123">When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings.</span></span> <span data-ttu-id="967af-124">Les prochaines réunions à jour avec les nouvelles informations de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="967af-124">Any future meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="967af-125">Si vous utilisez actuellement Skype Server 2015 pour l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="967af-125">If you're currently using Skype Server 2015 for audio conferencing</span></span>

<span data-ttu-id="967af-126">Nous vous recommandons de suivre les meilleures pratiques suivantes afin d'exploiter pleinement MMS pour ce scénario :</span><span class="sxs-lookup"><span data-stu-id="967af-126">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="967af-127">Puisque, pour que MMS fonctionne, la boîte aux lettres de l'utilisateur doit être sur Exchange Online, si vous effectuez une migration depuis Exchange Server sur site, déplacez d'abord la boîte aux lettres de l'utilisateur vers Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="967af-127">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="967af-128">Attribuer la licence de **Conférence Audio** à l’utilisateur avant d’exécuter le `Move-CSUser` applet de commande pour la migration de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="967af-128">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user.</span></span> <span data-ttu-id="967af-129">C’est pourquoi MMS met également à jour les réunions lorsque les paramètres de conférence audio sont modifiées pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="967af-129">This is because MMS also updates meetings when audio conferencing settings are changed for a user.</span></span> <span data-ttu-id="967af-130">Si vous n'attribuez pas d'abord la licence, MMS effectue une nouvelle mise à jour de toutes les réunions lorsque de l'attribution.</span><span class="sxs-lookup"><span data-stu-id="967af-130">If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="967af-131">Si vous utilisez actuellement un fournisseur de services d'audioconférence (ACP) tiers</span><span class="sxs-lookup"><span data-stu-id="967af-131">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="967af-132">Avec un fournisseur tiers, ou non MMS s’exécute selon les paramètres de conférence audio de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="967af-132">With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings.</span></span> <span data-ttu-id="967af-133">Vous pouvez choisir de remplacer automatiquement les numéros de téléphone à partir de votre ACP lorsque vous attribuez à un utilisateur une licence de **Conférence Audio** .</span><span class="sxs-lookup"><span data-stu-id="967af-133">You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license.</span></span> <span data-ttu-id="967af-134">Toutefois, vous pouvez également choisir d'éviter un tel remplacement et de conserver les numéros de rendez-vous de votre ACP.</span><span class="sxs-lookup"><span data-stu-id="967af-134">On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP.</span></span> <span data-ttu-id="967af-135">Pour afficher la définition de votre organisation, exécutez la commande Windows PowerShell suivante et vérifiez la valeur du paramètre `AutomaticallyReplaceAcpProvider`.</span><span class="sxs-lookup"><span data-stu-id="967af-135">To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`.</span></span> <span data-ttu-id="967af-136">Si vous avez besoin d'aide pour utiliser PowerShell, consultez la section [Utilisation de PowerShell pour gérer votre entreprise dans Skype Entreprise](setting-up-the-meeting-migration-service-mms.md#WPSInfo) à la fin de cet article.</span><span class="sxs-lookup"><span data-stu-id="967af-136">If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="967af-137">Si la valeur de ce paramètre est $true, MMS exécuter lorsqu’un utilisateur est affecté à une licence de **Conférence Audio** et mettre à jour leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="967af-137">If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings.</span></span> <span data-ttu-id="967af-138">Les numéros de téléphone à partir de votre ACP sont conservés jusqu'à ce que la licence de **Conférence Audio** est attribuée.</span><span class="sxs-lookup"><span data-stu-id="967af-138">The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.</span></span>
    
- <span data-ttu-id="967af-139">Si la valeur de ce paramètre est $false, MMS n’actualise les réunions même si un utilisateur est attribué une licence de **Conférence Audio** .</span><span class="sxs-lookup"><span data-stu-id="967af-139">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence.</span></span> <span data-ttu-id="967af-140">Les numéros de téléphone à partir de votre ACP sont conservés jusqu'à ce que l’utilisateur est configuré manuellement pour l’audioconférence dans Skype pour le centre d’administration Business ou à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="967af-140">The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="967af-141">Mise à jour des réunions lors de la modifient des paramètres de conférence audio d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="967af-141">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="967af-142">MMS met à jour un Skype existant pour les réunions d’entreprise et Teams Microsoft dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="967af-142">MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:</span></span>
  
- <span data-ttu-id="967af-143">Lorsque vous affectez ou supprimez des licences **d’Audioconférence** .</span><span class="sxs-lookup"><span data-stu-id="967af-143">When you assign or remove **Audio Conferencing** license.</span></span>
    
- <span data-ttu-id="967af-144">Lorsque vous activez ou désactivez les services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="967af-144">When you enable or disable audio conferencing.</span></span>
    
- <span data-ttu-id="967af-145">Lorsque vous modifiez ou réinitialisez l’ID de conférence pour un utilisateur configuré pour utiliser des réunions publiques.</span><span class="sxs-lookup"><span data-stu-id="967af-145">When you change or reset the Conference ID for a user configured to use public meetings.</span></span>
    
- <span data-ttu-id="967af-146">Lorsque vous déplacez l’utilisateur vers un nouveau pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="967af-146">When you move the user to a new audio conferencing bridge.</span></span>
    
- <span data-ttu-id="967af-147">Lorsqu’un numéro de téléphone est assigné à partir d’un pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="967af-147">When a phone number is unassigned from a audio conferencing bridge.</span></span> <span data-ttu-id="967af-148">Il s'agit d'un scénario complexe qui nécessite des étapes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="967af-148">This is a complex scenario which requires additional steps.</span></span> <span data-ttu-id="967af-149">Pour plus d’informations, voir [Modifier le numéro payant ou les numéros gratuits sur le pont de conférence Audio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="967af-149">For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="967af-150">MMS effectue uniquement la mise à jour des réunions lorsque vous utilisez le pont Microsoft.</span><span class="sxs-lookup"><span data-stu-id="967af-150">MMS only updates meetings when you're using the Microsoft bridge.</span></span> <span data-ttu-id="967af-151">Si vous utilisez un fournisseur de services d’audioconférence tiers, les utilisateurs doivent mettre à jour leurs réunions manuellement.</span><span class="sxs-lookup"><span data-stu-id="967af-151">If you are using a third-party audio conferencing provider, the users will need to update their meetings manually.</span></span> <span data-ttu-id="967af-152">Dans ce cas, vous pouvez utiliser l'[outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="967af-152">In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="967af-153">Toutes les modifications aux paramètres de conférence audio d’un utilisateur déclenchent MMS.</span><span class="sxs-lookup"><span data-stu-id="967af-153">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="967af-154">Les deux modifications suivantes n'entraînent pas la mise à jour des réunions par MMS :</span><span class="sxs-lookup"><span data-stu-id="967af-154">Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="967af-155">la modification de l'adresse SIP de l'organisateur de la réunion (qu'il s'agisse de son nom d'utilisateur SIP ou son domaine SIP) ;</span><span class="sxs-lookup"><span data-stu-id="967af-155">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="967af-156">la modification de l'URL de réunion de votre entreprise à l'aide de la commande [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).</span><span class="sxs-lookup"><span data-stu-id="967af-156">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="967af-157">Que se passe-t-il lorsque MMS met à jour des réunions ?</span><span class="sxs-lookup"><span data-stu-id="967af-157">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="967af-158">Lorsque MMS détecte que les réunions d'un utilisateur doivent être mises à jour, le service effectue les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="967af-158">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="967af-159">Identifier les Skype pour les réunions d’entreprise et Teams Microsoft l’utilisateur a été planifiée à l’avenir</span><span class="sxs-lookup"><span data-stu-id="967af-159">Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future</span></span>
    
   - <span data-ttu-id="967af-160">N’importe quel Skype pour les réunions Microsoft Teams ou de l’entreprise qui se sont produites avant lors de l’exécution MMS sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="967af-160">Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped</span></span>
    
   - <span data-ttu-id="967af-161">Il met à jour uniquement les réunions dont l'utilisateur est l'organisateur.</span><span class="sxs-lookup"><span data-stu-id="967af-161">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="967af-162">Il remplace le bloc d'informations de la réunion en ligne dans les détails de la réunion.</span><span class="sxs-lookup"><span data-stu-id="967af-162">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="967af-163">Il envoie des mises à jour à tous les destinataires de la réunion de la part de l'organisateur.</span><span class="sxs-lookup"><span data-stu-id="967af-163">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
   <span data-ttu-id="967af-164">**Combien de temps dure l'exécution de MMS ?**</span><span class="sxs-lookup"><span data-stu-id="967af-164">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="967af-165">La quantité de temps faut-il pour MMS migrer des réunions varie en fonction de combien d’utilisateurs est concernés et le nombre total de Skype pour les réunions Microsoft Teams ou de l’entreprise, que chaque utilisateur dispose sur leur calendrier.</span><span class="sxs-lookup"><span data-stu-id="967af-165">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar.</span></span> <span data-ttu-id="967af-166">La migration dure au minimum 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="967af-166">At a minimum, it will take 10 minutes to run.</span></span> <span data-ttu-id="967af-167">Bien que des migrations importantes puissent prendre jusqu'à 12 heures, la plupart sont effectuées en moins d'une heure.</span><span class="sxs-lookup"><span data-stu-id="967af-167">While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="967af-168">**Limites et problèmes potentiels**</span><span class="sxs-lookup"><span data-stu-id="967af-168">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="967af-169">Uniquement la Skype pour les réunions Microsoft Teams ou de l’entreprise qui ont été planifiées en cliquant sur le bouton **Skype ajouter une réunion** dans Outlook sur le Web ou à l’aide du complément de réunion Skype pour Outlook sont migrées.</span><span class="sxs-lookup"><span data-stu-id="967af-169">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="967af-170">En d'autres termes, si un utilisateur copie et colle les informations relatives à une réunion en ligne Skype dans une nouvelle réunion, cette nouvelle réunion n'est pas mise à jour.</span><span class="sxs-lookup"><span data-stu-id="967af-170">In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="967af-p114">Lorsqu'une réunion est migrée, MMS remplace tous les éléments du bloc d'information de la réunion en ligne. Ainsi, si un utilisateur a modifié ce bloc, ses modifications sont écrasées. Le contenu indiqué dans les détails de la réunion et qui ne fait pas partie du bloc d'informations de la réunion en ligne n'est pas modifié.</span><span class="sxs-lookup"><span data-stu-id="967af-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![Le bloc de réunion mis à jour par MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="967af-p115">Le contenu relatif à la réunion qui a été créé ou joint à la réunion (tableaux blancs, sondages, etc.) n'est pas conservé après l'exécution de MMS Si les organisateurs de votre réunion ont joint du contenu aux réunions à l'avance, ce contenu doit être recréé après l'exécution de MMS.</span><span class="sxs-lookup"><span data-stu-id="967af-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="967af-p116">Le lien vers les notes de réunion partagées dans l'élément du calendrier, ainsi que dans Skype, est également écrasé. Le contenu des notes de réunion enregistrées dans OneNote n'est pas supprimé : seul le lien vers les notes partagées est écrasé.</span><span class="sxs-lookup"><span data-stu-id="967af-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="967af-179">Les réunions comptant plus de 250 participants (organisateur inclus) ne feront pas l'objet d'une migration.</span><span class="sxs-lookup"><span data-stu-id="967af-179">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="967af-180">Certains caractères Unicode dans le corps de l'invitation peuvent être mis à jour de manière incorrecte et remplacés par l'un des caractères spéciaux suivants : ï, ¿, ½, �.</span><span class="sxs-lookup"><span data-stu-id="967af-180">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="967af-181">Que voient les utilisateurs lorsque MMS met à jour leurs réunions ?</span><span class="sxs-lookup"><span data-stu-id="967af-181">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="967af-182">Tout comme l'outil de migration de réunion, MMS envoie des mises à jour de réunion à la place des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="967af-182">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users.</span></span> <span data-ttu-id="967af-183">Vos utilisateurs ne verront ainsi qu'un nouveau cycle de notifications d'approbation pour leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="967af-183">Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings.</span></span> <span data-ttu-id="967af-184">Cela peut être source de confusion pour les utilisateurs, nous vous recommandons d’informer vos utilisateurs à l’avance pas uniquement lorsque vous migrez les de locale vers Skype pour Business Online, mais également lorsque vous apportez des modifications de services d’audioconférence qui déclenchera MMS.</span><span class="sxs-lookup"><span data-stu-id="967af-184">This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="967af-185">Gestion de MMS</span><span class="sxs-lookup"><span data-stu-id="967af-185">Managing MMS</span></span>

<span data-ttu-id="967af-186">Vous devez utiliser Windows PowerShell pour gérer les MMS et vérifiez l’état des migrations en cours.</span><span class="sxs-lookup"><span data-stu-id="967af-186">You need to use Windows PowerShell to manage MMS and check the status of ongoing migrations.</span></span> <span data-ttu-id="967af-187">Cette section suppose que vous maîtrisez suffisamment PowerSHell pour gérer votre entreprise dans Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="967af-187">The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization.</span></span> <span data-ttu-id="967af-188">Si vous débutez PowerShell, voir la section [à l’aide de PowerShell pour gérer votre Skype pour l’organisation de l’entreprise](setting-up-the-meeting-migration-service-mms.md#WPSInfo) à la fin de cet article.</span><span class="sxs-lookup"><span data-stu-id="967af-188">If you are new to PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="967af-189">Comment puis-je vérifier le statut des migrations de réunion ?</span><span class="sxs-lookup"><span data-stu-id="967af-189">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="967af-p119">Utilisez l'applet de commande  `Get-CsMeetingMigrationStatus` pour vérifier le statut des migrations de réunion. Vous trouverez ci-dessous plusieurs exemples.</span><span class="sxs-lookup"><span data-stu-id="967af-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="967af-192">Pour obtenir un statut récapitulatif pour toutes les migrations MMS, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="967af-192">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="967af-193">Cela vous permettra de bénéficier de la vue tabulaire suivante des états de toutes les migrations :</span><span class="sxs-lookup"><span data-stu-id="967af-193">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="967af-194">État UserCount---------------</span><span class="sxs-lookup"><span data-stu-id="967af-194">State UserCount---------------</span></span><br/> <span data-ttu-id="967af-195">En attente 21</span><span class="sxs-lookup"><span data-stu-id="967af-195">Pending 21</span></span><br/><span data-ttu-id="967af-196">En cours 6</span><span class="sxs-lookup"><span data-stu-id="967af-196">InProgress 6</span></span><br/> <span data-ttu-id="967af-197">Échec 2</span><span class="sxs-lookup"><span data-stu-id="967af-197">Failed 2</span></span> <br/> <span data-ttu-id="967af-198">Succès 131</span><span class="sxs-lookup"><span data-stu-id="967af-198">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="967af-p120">Si certaines des migrations ont le statut Échoué, agissez de façon à résoudre ces problèmes le plus tôt possible. Il est impossible de participer aux réunions organisées par ces utilisateurs tant que ces problèmes ne sont pas résolus. Consultez la section [Que faire en cas d'erreur ?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="967af-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="967af-p121">Pour obtenir les détails complets de toutes les migrations d'une période précise, vous pouvez utiliser les paramètres  `StartTime` et `EndTime`. Par exemple, la commande suivante permet d'obtenir les détails complets de toutes les migrations qui ont eu lieu du 1er au 8 octobre 2016.</span><span class="sxs-lookup"><span data-stu-id="967af-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="967af-p122">Vous pouvez également vérifier le statut de migration d'un utilisateur particulier, en utilisant le paramètre  `UserId`. Ainsi, la commande suivante permet d'obtenir le statut de l'utilisateur ashaw@contoso.com :</span><span class="sxs-lookup"><span data-stu-id="967af-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="967af-206">Que faire en cas d'erreur ?</span><span class="sxs-lookup"><span data-stu-id="967af-206">What do I do if there is an error?</span></span>
<span data-ttu-id="967af-207"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="967af-207"></span></span>

<span data-ttu-id="967af-208">Lorsque vous exécutez l'applet de commande  `Get-CsMeetingMigrationStatus` pour obtenir une vue récapitulative et remarquez que le statut Échouéconcernent une ou plusieurs migrations, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="967af-208">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="967af-p123">Identifiez les utilisateurs concernés. Exécutez la commande suivante pour obtenir la liste des utilisateurs concernés, ainsi que l'erreur spécifique signalée :</span><span class="sxs-lookup"><span data-stu-id="967af-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
   ```
   Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastMessage
   ```

2. <span data-ttu-id="967af-211">Pour chaque utilisateur, exécutez l'[outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047) afin de migrer manuellement leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="967af-211">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="967af-212">Si la migration ne fonctionne toujours pas avec l'outil de migration de réunions, vous disposez de deux options :</span><span class="sxs-lookup"><span data-stu-id="967af-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
   - <span data-ttu-id="967af-213">demander aux utilisateurs de créer de nouvelles réunions Skype ;</span><span class="sxs-lookup"><span data-stu-id="967af-213">Have the users create new Skype meetings.</span></span>
    
   - <span data-ttu-id="967af-214">[contacter le support technique](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="967af-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="967af-215">Activation et désactivation de MMS</span><span class="sxs-lookup"><span data-stu-id="967af-215">Enabling and disabling MMS</span></span>
<span data-ttu-id="967af-216"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="967af-216"></span></span>

<span data-ttu-id="967af-217">MMS est activé par défaut pour toutes les organisations, mais peut être désactivé au besoin.</span><span class="sxs-lookup"><span data-stu-id="967af-217">MMS is enabled by default for all organizations, but it can be disabled as needed.</span></span> <span data-ttu-id="967af-218">Par exemple, si vous souhaitez migrer manuellement toutes les réunions ou si vous utilisez un fournisseur de services d’audioconférence tiers, vous devrez pas MMS en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="967af-218">For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running.</span></span> <span data-ttu-id="967af-219">Vous pouvez également choisir de désactiver MMS temporairement.</span><span class="sxs-lookup"><span data-stu-id="967af-219">You may also choose to temporarily disable MMS.</span></span> <span data-ttu-id="967af-220">Par exemple, vous pouvez le faire des modifications importantes pour les paramètres de conférence audio pour votre organisation et vous ne voulez pas que MMS exécute jusqu'à ce que toutes les modifications sont terminées.</span><span class="sxs-lookup"><span data-stu-id="967af-220">For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="967af-p125">Pour voir si MMS est activé pour votre entreprise, exécutez la commande suivante et vérifier la valeur du paramètre  `MeetingMigrationEnabled`. Si le paramètre a pour valeur $true, MMS est activé.</span><span class="sxs-lookup"><span data-stu-id="967af-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="967af-223">Pour désactiver MMS, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="967af-223">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="967af-224">Pour activer ce paramètre, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="967af-224">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="967af-225">Activation et désactivation MMS uniquement pour les modifications de services d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="967af-225">Enabling and disabling MMS only for audio conferencing changes</span></span>
<span data-ttu-id="967af-226"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="967af-226"></span></span>

<span data-ttu-id="967af-227">Vous pouvez également désactiver MMS uniquement pour les modifications de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="967af-227">You can also disable MMS only for audio conferencing changes.</span></span> <span data-ttu-id="967af-228">Il s’exécute lorsqu’un utilisateur est migré Skype pour Business local à Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="967af-228">It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online.</span></span> <span data-ttu-id="967af-229">Pour vérifier l’état MMS en cours des mises à jour de la conférence audio, exécutez la commande suivante et vérifiez la valeur de la `AutomaticallyMigrateUserMeetings` paramètre.</span><span class="sxs-lookup"><span data-stu-id="967af-229">To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter.</span></span> <span data-ttu-id="967af-230">Si ce paramètre est défini sur true$, MMS est définie à mettre à jour des réunions de l’utilisateur lors de la modification des paramètres de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="967af-230">If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="967af-231">Pour désactiver MMS pour les conférences audio, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="967af-231">To disable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="967af-232">Pour activer MMS pour les conférences audio, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="967af-232">To enable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="967af-233">Comment puis-je exécuter manuellement une migration de réunion pour un utilisateur ?</span><span class="sxs-lookup"><span data-stu-id="967af-233">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="967af-234"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="967af-234"></span></span>

<span data-ttu-id="967af-235">Outre les migrations automatiques de réunion, vous pouvez également exécuter la migration de la réunion manuellement pour un utilisateur en exécutant l’applet de commande **Start-CsExMeetingMigration**.</span><span class="sxs-lookup"><span data-stu-id="967af-235">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**.</span></span> <span data-ttu-id="967af-236">Ce cmdlet ajoute l'utilisateur dans la file d'attente de migration de réunion.</span><span class="sxs-lookup"><span data-stu-id="967af-236">This cmdlet adds the user in meeting migration queue.</span></span> <span data-ttu-id="967af-237">Meeting Migration Service lira la demande de l'utilisateur et effectuera une migration de leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="967af-237">Meeting Migration Service will read the user request and migrate their meetings.</span></span> <span data-ttu-id="967af-238">Vous pouvez vérifier le statut de la migration des réunions par cmdlet **Get-CsMeetingMigrationStatus**.</span><span class="sxs-lookup"><span data-stu-id="967af-238">You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="967af-239">Voici un exemple qui déclenche la migration de réunion pour l'utilisateur ashaw@contoso.com :</span><span class="sxs-lookup"><span data-stu-id="967af-239">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="967af-240">Utilisation de PowerShell pour gérer votre entreprise dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="967af-240">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="967af-241"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="967af-241"></span></span>

 <span data-ttu-id="967af-242">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="967af-242">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="967af-243">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="967af-243">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="967af-244">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="967af-244">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="967af-p128">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="967af-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="967af-p129">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="967af-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="967af-251">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="967af-251">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="967af-252">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="967af-252">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="967af-253">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="967af-253">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="967af-254">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="967af-254">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="967af-255">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="967af-255">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
>   ```
>   Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>   $credential = Get-Credential
>   $session = New-CsOnlineSession -Credential $credential
>   Import-PSSession $session
>   ```
> <span data-ttu-id="967af-256">Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="967af-256">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
- <span data-ttu-id="967af-p130">Windows PowerShell permet de gérer les utilisateurs et ce qu’ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l’aide d’un point d’administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="967af-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="967af-260">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="967af-260">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="967af-261">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="967af-261">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="967af-p131">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l’utilisation du centre d’administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="967af-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="967af-264">Meilleures méthodes de gestion d’Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="967af-264">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="967af-265">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="967af-265">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="967af-266">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="967af-266">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="967af-267">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="967af-267">Related topics</span></span>

[<span data-ttu-id="967af-268">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="967af-268">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
