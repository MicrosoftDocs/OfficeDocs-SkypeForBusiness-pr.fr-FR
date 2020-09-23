---
title: Utiliser OneDrive et SharePoint pour les enregistrements de réunion
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment basculer du flux vers OneDrive entreprise et le stockage d’enregistrements de réunion SharePoint dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65c0d50686346b715ca7e10b455845927ff22341
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218405"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="01d74-103">Utiliser OneDrive entreprise et SharePoint ou un flux pour les enregistrements de réunion</span><span class="sxs-lookup"><span data-stu-id="01d74-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="01d74-104">Les modifications apportées à l’aide de Microsoft Stream to OneDrive entreprise et de SharePoint pour les enregistrements de réunion seront une approche progressive.</span><span class="sxs-lookup"><span data-stu-id="01d74-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="01d74-105">Au moment de l’exécution, vous serez en mesure de vous abonner à cette expérimentation en novembre, si vous voulez continuer à utiliser le flux de travail et que, à un 2021 moment donné, il est nécessaire que tous les clients utilisent OneDrive entreprise et SharePoint pour les nouveaux enregistrements de réunion.</span><span class="sxs-lookup"><span data-stu-id="01d74-105">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="01d74-106">Microsoft teams dispose d’une nouvelle méthode pour l’enregistrement des enregistrements de réunion.</span><span class="sxs-lookup"><span data-stu-id="01d74-106">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="01d74-107">Comme départ du flux, la méthode utilise Microsoft OneDrive et SharePoint dans Microsoft 365 et offre de nombreux avantages :</span><span class="sxs-lookup"><span data-stu-id="01d74-107">As a departure from Stream, the method uses Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits:</span></span>

<span data-ttu-id="01d74-108">Les avantages de l’utilisation de OneDrive entreprise et SharePoint pour le stockage d’enregistrements sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="01d74-108">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="01d74-109">Stratégies de rétention pour l’enregistrement des réunions Teams (TMR)</span><span class="sxs-lookup"><span data-stu-id="01d74-109">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="01d74-110">Avantages de OneDrive entreprise et de la gouvernance des informations de SharePoint</span><span class="sxs-lookup"><span data-stu-id="01d74-110">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="01d74-111">Simplification de la définition des autorisations et du partage</span><span class="sxs-lookup"><span data-stu-id="01d74-111">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="01d74-112">Partager des enregistrements avec des invités (utilisateurs externes) avec le partage explicite uniquement</span><span class="sxs-lookup"><span data-stu-id="01d74-112">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="01d74-113">Demander un flux d’accès</span><span class="sxs-lookup"><span data-stu-id="01d74-113">Request access flow</span></span>
- <span data-ttu-id="01d74-114">Fournir des liens OneDrive entreprise et SharePoint partagés</span><span class="sxs-lookup"><span data-stu-id="01d74-114">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="01d74-115">Quota accru</span><span class="sxs-lookup"><span data-stu-id="01d74-115">Increased quota</span></span>
- <span data-ttu-id="01d74-116">Les enregistrements de réunion sont disponibles plus vite</span><span class="sxs-lookup"><span data-stu-id="01d74-116">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="01d74-117">**Accéder** au support client local</span><span class="sxs-lookup"><span data-stu-id="01d74-117">**Go local** tenant support</span></span>
- <span data-ttu-id="01d74-118">Prise en charge de plusieurs géographiques : les enregistrements sont stockés dans une zone spécifique à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="01d74-118">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="01d74-119">Mettre en place votre propre clé (BYOK)</span><span class="sxs-lookup"><span data-stu-id="01d74-119">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="01d74-120">Amélioration de la qualité de transcription et de l’intervenant</span><span class="sxs-lookup"><span data-stu-id="01d74-120">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="01d74-121">Certaines limitations sont à prendre en compte :</span><span class="sxs-lookup"><span data-stu-id="01d74-121">There are some limitations to consider:</span></span>

- <span data-ttu-id="01d74-122">Il s’agit de sous-titres et de transcriptions en anglais uniquement.</span><span class="sxs-lookup"><span data-stu-id="01d74-122">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="01d74-123">Vous ne serez pas en mesure de rechercher des transcriptions ou leur contenu.</span><span class="sxs-lookup"><span data-stu-id="01d74-123">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="01d74-124">Vous ne serez pas en mesure de modifier les transcriptions, mais vous pourrez activer/désactiver les légendes.</span><span class="sxs-lookup"><span data-stu-id="01d74-124">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="01d74-125">Vous pouvez contrôler les personnes avec lesquelles vous partagez l’enregistrement, mais vous ne pouvez pas bloquer les utilisateurs disposant d’un accès partagé pour télécharger l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="01d74-125">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="01d74-126">Vous ne recevrez pas d’e-mail à la fin de l’enregistrement, mais l’enregistrement s’affichera dans la conversation de la réunion une fois que vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="01d74-126">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="01d74-127">Cela se produit beaucoup plus rapidement qu’auparavant dans le flux</span><span class="sxs-lookup"><span data-stu-id="01d74-127">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="01d74-128">Regardez « enregistrement de la réunion » pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="01d74-128">Watch "Meeting Recording" for more information.</span></span> 

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8] 

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="01d74-129">Configurer l’option d’enregistrement de la réunion pour OneDrive entreprise et SharePoint</span><span class="sxs-lookup"><span data-stu-id="01d74-129">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="01d74-130">Installez la console d’administration PowerShell de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="01d74-130">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="01d74-131">a.</span><span class="sxs-lookup"><span data-stu-id="01d74-131">a.</span></span> <span data-ttu-id="01d74-132">Téléchargez [Skype entreprise Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="01d74-132">Download [Skype for Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="01d74-133">b.</span><span class="sxs-lookup"><span data-stu-id="01d74-133">b.</span></span> <span data-ttu-id="01d74-134">Suivez les invites pour l’installer.</span><span class="sxs-lookup"><span data-stu-id="01d74-134">Follow the prompts to install it.</span></span>

    <span data-ttu-id="01d74-135">c.</span><span class="sxs-lookup"><span data-stu-id="01d74-135">c.</span></span> <span data-ttu-id="01d74-136">Redémarrez votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="01d74-136">Restart your machine.</span></span>

2. <span data-ttu-id="01d74-137">Lancer PowerShell en tant qu’administrateur</span><span class="sxs-lookup"><span data-stu-id="01d74-137">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="01d74-138">Importez le connecteur SkypeOnline et connectez-vous en tant qu’administrateur Teams.</span><span class="sxs-lookup"><span data-stu-id="01d74-138">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="01d74-139">Utilisez [Set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour définir une stratégie de réunion équipes pour passer du stockage de flux à ODSP.</span><span class="sxs-lookup"><span data-stu-id="01d74-139">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="01d74-140">Désactiver OneDrive entreprise et SharePoint pour continuer à utiliser le flux</span><span class="sxs-lookup"><span data-stu-id="01d74-140">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="01d74-141">Même si une stratégie indique qu’il est déjà défini comme étant en **flux**, il est possible qu’elle ne soit pas définie.</span><span class="sxs-lookup"><span data-stu-id="01d74-141">Even if a policy says it’s already set to **Stream**, it might not be set.</span></span> <span data-ttu-id="01d74-142">S’il n’a aucun effet, la valeur par défaut est Stream.</span><span class="sxs-lookup"><span data-stu-id="01d74-142">If it's set to nothing, then the default is Stream.</span></span> <span data-ttu-id="01d74-143">Si vous voulez annuler votre abonnement, vous **devez** réinitialiser la stratégie en **flux** pour vérifier que le flux est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="01d74-143">If you want to opt-out, you **must** reset the policy to **Stream** to ensure that Stream is the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="01d74-144">Questions fréquemment posées</span><span class="sxs-lookup"><span data-stu-id="01d74-144">Frequently asked questions</span></span>

<span data-ttu-id="01d74-145">**Où l’enregistrement de la réunion sera-t-il stocké ?**</span><span class="sxs-lookup"><span data-stu-id="01d74-145">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="01d74-146">Pour les réunions hors canal, l’enregistrement est stocké dans un dossier nommé.</span><span class="sxs-lookup"><span data-stu-id="01d74-146">For non-Channel meetings, the recording is stored in a folder named.</span></span> <span data-ttu-id="01d74-147">Enregistrements \* \* qui se trouve au niveau supérieur du OneDrive qui appartient à la personne qui a démarré l’enregistrement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="01d74-147">Recordings\*\* that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="01d74-148">Example</span><span class="sxs-lookup"><span data-stu-id="01d74-148">Example:</span></span>

  <span data-ttu-id="01d74-149"><i>OneDrive entreprise</i> / de l’enregistreur **Enregistrements**</span><span class="sxs-lookup"><span data-stu-id="01d74-149"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="01d74-150">Pour les réunions de canal, l’enregistrement est stocké dans la bibliothèque de documents du site d’équipe dans un dossier nommé **enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="01d74-150">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="01d74-151">Example</span><span class="sxs-lookup"><span data-stu-id="01d74-151">Example:</span></span>

  <span data-ttu-id="01d74-152"><i>Nom de l’équipe-nom du canal</i> / Des **documents** / ; **Enregistrements**</span><span class="sxs-lookup"><span data-stu-id="01d74-152"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="01d74-153">**Qui dispose des autorisations pour afficher l’enregistrement de la réunion ?**</span><span class="sxs-lookup"><span data-stu-id="01d74-153">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="01d74-154">Pour les réunions hors-canal, tous les participants à la réunion, à l’exception des utilisateurs externes, sont automatiquement liés à un lien.</span><span class="sxs-lookup"><span data-stu-id="01d74-154">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="01d74-155">Les utilisateurs externes devront être explicitement ajoutés à la liste partagée par l’organisateur de la réunion ou la personne qui a démarré l’enregistrement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="01d74-155">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="01d74-156">Pour les réunions de canal, les autorisations sont héritées de la liste propriétaires et membres du canal.</span><span class="sxs-lookup"><span data-stu-id="01d74-156">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="01d74-157">**Comment gérer les transcriptions ?**</span><span class="sxs-lookup"><span data-stu-id="01d74-157">**How can I manage transcripts?**</span></span>

<span data-ttu-id="01d74-158">Les clients qui choisissent de bénéficier de cette version d’évaluation ne disposent pas de sous-titres disponibles dans leurs enregistrements de réunion teams migrés vers OneDrive et SharePoint.</span><span class="sxs-lookup"><span data-stu-id="01d74-158">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="01d74-159">Nous travaillons à l’ajout de sous-titres, en commençant par des sous-titres en anglais, et des enregistrements de réunion en octobre 2020.</span><span class="sxs-lookup"><span data-stu-id="01d74-159">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="01d74-160">Les sous-titres seront disponibles dans les enregistrements de réunion teams pour les clients qui ont choisi d’autoriser les transcriptions comme décrit dans la rubrique [enregistrements Cloud teams](cloud-recording.md) .</span><span class="sxs-lookup"><span data-stu-id="01d74-160">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="01d74-161">Les légendes permettent de créer du contenu inclusive pour les visualiseurs de toutes les aptitudes.</span><span class="sxs-lookup"><span data-stu-id="01d74-161">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="01d74-162">En tant que propriétaire, vous pouvez masquer les sous-titres, même si la transcription reste disponible dans les équipes, sauf si vous supprimez les sous-titres de teams.</span><span class="sxs-lookup"><span data-stu-id="01d74-162">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="01d74-163">Découvrir [Comment activer ou désactiver les enregistrements de réunion](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="01d74-163">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="01d74-164">Les sous-titres sont pris en charge pour les enregistrements des réunions teams pendant 60 jours à compter de la date d’enregistrement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="01d74-164">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="01d74-165">**Comment le quota de stockage sera-t-il affecté ?**</span><span class="sxs-lookup"><span data-stu-id="01d74-165">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="01d74-166">Les fichiers d’enregistrements de réunion teams résident dans OneDrive entreprise et SharePoint inclus dans votre quota de ces services.</span><span class="sxs-lookup"><span data-stu-id="01d74-166">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="01d74-167">Voir [quota SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) et [quota OneDrive entreprise] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="01d74-167">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="01d74-168">**Comment lire l’enregistrement d’une réunion teams ?**</span><span class="sxs-lookup"><span data-stu-id="01d74-168">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="01d74-169">Votre vidéo sera lue sur le lecteur vidéo de OneDrive entreprise ou SharePoint, selon l’endroit où vous accédez au fichier.</span><span class="sxs-lookup"><span data-stu-id="01d74-169">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>
