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
ms.openlocfilehash: 83a7a0628d76a96318081ec51a039d458ea1570f
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444230"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="3b8c2-103">Utiliser OneDrive entreprise et SharePoint ou un flux pour les enregistrements de réunion</span><span class="sxs-lookup"><span data-stu-id="3b8c2-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="3b8c2-104">Le changement de l’utilisation de Microsoft Stream sur OneDrive entreprise et Microsoft SharePoint pour les enregistrements de réunion sera une approche progressive.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-104">The change from using Microsoft Stream to OneDrive for Business and Microsoft SharePoint for meeting recordings will be a phased approach.</span></span>

|||
|---|-----------------|
|<span data-ttu-id="3b8c2-105">Date</span><span class="sxs-lookup"><span data-stu-id="3b8c2-105">Date</span></span>|<span data-ttu-id="3b8c2-106">Événement</span><span class="sxs-lookup"><span data-stu-id="3b8c2-106">Event</span></span>|
|<span data-ttu-id="3b8c2-107">Débuts du 4e CY20</span><span class="sxs-lookup"><span data-stu-id="3b8c2-107">Early Q4 CY20</span></span>|<span data-ttu-id="3b8c2-108">**L’enregistrement de la réunion teams sur OneDrive entreprise et SharePoint disponible pour la possibilité de participer ou d’être désactivé.**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-108">**Teams meeting recording on OneDrive for Business and SharePoint available for opt in or opt out.**</span></span><br> <span data-ttu-id="3b8c2-109">Les administrateurs de clients peuvent accepter ou désactiver OneDrive entreprise et définir la stratégie d’équipe dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-109">Tenant admins can opt in  or opt out of OneDrive for Business and SharePoint setting the Teams policy in PowerShell</span></span>|
|<span data-ttu-id="3b8c2-110">Milieu du 4e CY20</span><span class="sxs-lookup"><span data-stu-id="3b8c2-110">Mid Q4 CY20</span></span>|<span data-ttu-id="3b8c2-111">**Enregistrement des réunions teams dans OneDrive entreprise et SharePoint par défaut pour les clients qui n’ont pas choisi de désactiver**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-111">**Teams meeting recording on OneDrive for Business and SharePoint set as default for tenants who don't opt out**</span></span><br> <span data-ttu-id="3b8c2-112">C’est le chemin d’accès recommandé pour la plupart des clients</span><span class="sxs-lookup"><span data-stu-id="3b8c2-112">This is the  recommended path for most customers</span></span>|
<span data-ttu-id="3b8c2-113">Q1 CY21</span><span class="sxs-lookup"><span data-stu-id="3b8c2-113">Q1 CY21</span></span>|<span data-ttu-id="3b8c2-114">**L’enregistrement d’équipes de réunion dans un flux classique n’est plus autorisé**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-114">**Saving Teams meeting recording to Classic Stream no longer allowed**</span></span><br><span data-ttu-id="3b8c2-115">Tous les clients enregistrent l’enregistrement des réunions d’équipes dans OneDrive entreprise et SharePoint</span><span class="sxs-lookup"><span data-stu-id="3b8c2-115">All tenants will save Teams meeting recording to OneDrive for Business and SharePoint</span></span>|
|||

<span data-ttu-id="3b8c2-116">Microsoft teams dispose d’une nouvelle méthode pour l’enregistrement des enregistrements de réunion.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-116">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="3b8c2-117">Comme la première phase d’une transition à partir du flux Microsoft classique vers le [nouveau flux](https://docs.microsoft.com/stream/streamnew/new-stream), cette méthode stocke les enregistrements sur Microsoft OneDrive et SharePoint dans Microsoft 365 et offre de nombreux avantages.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-117">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="3b8c2-118">Les avantages de l’utilisation de OneDrive entreprise et SharePoint pour le stockage d’enregistrements sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3b8c2-118">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="3b8c2-119">Stratégies de rétention pour l’enregistrement des réunions Teams (TMR)</span><span class="sxs-lookup"><span data-stu-id="3b8c2-119">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="3b8c2-120">Avantages de OneDrive entreprise et de la gouvernance des informations de SharePoint</span><span class="sxs-lookup"><span data-stu-id="3b8c2-120">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="3b8c2-121">Simplification de la définition des autorisations et du partage</span><span class="sxs-lookup"><span data-stu-id="3b8c2-121">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="3b8c2-122">Partager des enregistrements avec des invités (utilisateurs externes) avec le partage explicite uniquement</span><span class="sxs-lookup"><span data-stu-id="3b8c2-122">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="3b8c2-123">Demander un flux d’accès</span><span class="sxs-lookup"><span data-stu-id="3b8c2-123">Request access flow</span></span>
- <span data-ttu-id="3b8c2-124">Fournir des liens OneDrive entreprise et SharePoint partagés</span><span class="sxs-lookup"><span data-stu-id="3b8c2-124">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="3b8c2-125">Quota accru</span><span class="sxs-lookup"><span data-stu-id="3b8c2-125">Increased quota</span></span>
- <span data-ttu-id="3b8c2-126">Les enregistrements de réunion sont disponibles plus vite</span><span class="sxs-lookup"><span data-stu-id="3b8c2-126">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="3b8c2-127">**Accéder** au support client local</span><span class="sxs-lookup"><span data-stu-id="3b8c2-127">**Go local** tenant support</span></span>
- <span data-ttu-id="3b8c2-128">Prise en charge de plusieurs géographiques : les enregistrements sont stockés dans une zone spécifique à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-128">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="3b8c2-129">Mettre en place votre propre clé (BYOK)</span><span class="sxs-lookup"><span data-stu-id="3b8c2-129">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="3b8c2-130">Amélioration de la qualité de transcription et de l’intervenant</span><span class="sxs-lookup"><span data-stu-id="3b8c2-130">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="3b8c2-131">Certaines limitations sont à prendre en compte :</span><span class="sxs-lookup"><span data-stu-id="3b8c2-131">There are some limitations to consider:</span></span>

- <span data-ttu-id="3b8c2-132">Il s’agit de sous-titres et de transcriptions en anglais uniquement.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-132">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="3b8c2-133">Vous ne serez pas en mesure de rechercher des transcriptions ou leur contenu.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-133">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="3b8c2-134">Vous ne serez pas en mesure de modifier les transcriptions, mais vous pourrez activer/désactiver les légendes.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-134">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="3b8c2-135">Vous pouvez contrôler les personnes avec lesquelles vous partagez l’enregistrement, mais vous ne pouvez pas bloquer les utilisateurs disposant d’un accès partagé pour télécharger l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-135">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="3b8c2-136">Vous ne recevrez pas d’e-mail à la fin de l’enregistrement, mais l’enregistrement s’affichera dans la conversation de la réunion une fois que vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-136">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="3b8c2-137">Cela se produit beaucoup plus rapidement qu’auparavant dans le flux</span><span class="sxs-lookup"><span data-stu-id="3b8c2-137">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="3b8c2-138">Regardez « enregistrement de la réunion » pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-138">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="3b8c2-139">Configurer l’option d’enregistrement de la réunion pour OneDrive entreprise et SharePoint</span><span class="sxs-lookup"><span data-stu-id="3b8c2-139">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="3b8c2-140">Installez la console d’administration PowerShell de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-140">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="3b8c2-141">a.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-141">a.</span></span> <span data-ttu-id="3b8c2-142">Téléchargez [Skype entreprise Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="3b8c2-142">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="3b8c2-143">b.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-143">b.</span></span> <span data-ttu-id="3b8c2-144">Suivez les invites pour l’installer.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-144">Follow the prompts to install it.</span></span>

    <span data-ttu-id="3b8c2-145">c.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-145">c.</span></span> <span data-ttu-id="3b8c2-146">Redémarrez votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-146">Restart your machine.</span></span>

2. <span data-ttu-id="3b8c2-147">Lancer PowerShell en tant qu’administrateur</span><span class="sxs-lookup"><span data-stu-id="3b8c2-147">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="3b8c2-148">Importez le connecteur SkypeOnline et connectez-vous en tant qu’administrateur Teams.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-148">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="3b8c2-149">Utilisez [Set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour définir une stratégie de réunion équipes pour passer du stockage de flux à ODSP.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-149">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="3b8c2-150">Désactiver OneDrive entreprise et SharePoint pour continuer à utiliser le flux</span><span class="sxs-lookup"><span data-stu-id="3b8c2-150">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="3b8c2-151">Même si une stratégie indique qu’il est défini sur **Stream**, il est possible qu’elle ne soit pas définie.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-151">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="3b8c2-152">En règle générale, si la stratégie n’est pas définie, le paramètre par défaut est **flux**.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-152">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="3b8c2-153">Toutefois, si vous souhaitez annuler votre utilisation de SharePoint ou OneDrive, vous devez réinitialiser la stratégie sur **flux** pour vous assurer qu’elle est définie sur la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-153">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="3b8c2-154">Questions fréquemment posées</span><span class="sxs-lookup"><span data-stu-id="3b8c2-154">Frequently asked questions</span></span>

<span data-ttu-id="3b8c2-155">**Où l’enregistrement de la réunion sera-t-il stocké ?**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-155">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="3b8c2-156">Pour les réunions hors-canal, l’enregistrement est stocké dans un dossier intitulé **enregistrements** qui se trouve au niveau supérieur du OneDrive qui appartient à la personne qui a démarré l’enregistrement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-156">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="3b8c2-157">Example</span><span class="sxs-lookup"><span data-stu-id="3b8c2-157">Example:</span></span>

  <span data-ttu-id="3b8c2-158"><i>OneDrive entreprise</i> / de l’enregistreur **Enregistrements**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-158"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="3b8c2-159">Pour les réunions de canal, l’enregistrement est stocké dans la bibliothèque de documents du site d’équipe dans un dossier nommé **enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-159">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="3b8c2-160">Example</span><span class="sxs-lookup"><span data-stu-id="3b8c2-160">Example:</span></span>

  <span data-ttu-id="3b8c2-161"><i>Nom de l’équipe-nom du canal</i> / Des **documents** / ; **Enregistrements**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-161"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="3b8c2-162">**Comment gérer les enregistrements d’anciens employés ?**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-162">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="3b8c2-163">Étant donné que les vidéos sont similaires à n’importe quel autre fichier dans OneDrive et SharePoint, la gestion de la propriété et de la rétention après le départ d’un employé va suivre le [processus OneDrive et SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)normal.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-163">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="3b8c2-164">**Qui dispose des autorisations pour afficher l’enregistrement de la réunion ?**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-164">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="3b8c2-165">Pour les réunions hors-canal, tous les participants à la réunion, à l’exception des utilisateurs externes, sont automatiquement liés à un lien.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-165">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="3b8c2-166">Les utilisateurs externes devront être explicitement ajoutés à la liste partagée par l’organisateur de la réunion ou la personne qui a démarré l’enregistrement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-166">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="3b8c2-167">Pour les réunions de canal, les autorisations sont héritées de la liste propriétaires et membres du canal.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-167">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="3b8c2-168">**Comment gérer les transcriptions ?**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-168">**How can I manage transcripts?**</span></span>

<span data-ttu-id="3b8c2-169">Les clients qui choisissent de bénéficier de cette version d’évaluation ne disposent pas de sous-titres disponibles dans leurs enregistrements de réunion teams migrés vers OneDrive et SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-169">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="3b8c2-170">Nous travaillons à l’ajout de sous-titres, en commençant par des sous-titres en anglais, et des enregistrements de réunion en octobre 2020.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-170">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="3b8c2-171">Les sous-titres seront disponibles dans les enregistrements de réunion teams pour les clients qui ont choisi d’autoriser les transcriptions comme décrit dans la rubrique [enregistrements Cloud teams](cloud-recording.md) .</span><span class="sxs-lookup"><span data-stu-id="3b8c2-171">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="3b8c2-172">Les légendes permettent de créer du contenu inclusive pour les visualiseurs de toutes les aptitudes.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-172">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="3b8c2-173">En tant que propriétaire, vous pouvez masquer les sous-titres, même si la transcription reste disponible dans les équipes, sauf si vous supprimez les sous-titres de teams.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-173">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="3b8c2-174">Découvrir [Comment activer ou désactiver les enregistrements de réunion](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="3b8c2-174">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="3b8c2-175">Les sous-titres sont pris en charge pour les enregistrements des réunions teams pendant 60 jours à compter de la date d’enregistrement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-175">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="3b8c2-176">**Comment le quota de stockage sera-t-il affecté ?**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-176">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="3b8c2-177">Les fichiers d’enregistrements de réunion teams résident dans OneDrive entreprise et SharePoint inclus dans votre quota de ces services.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-177">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="3b8c2-178">Voir [quota SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) et [quota OneDrive entreprise] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="3b8c2-178">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="3b8c2-179">**Comment lire l’enregistrement d’une réunion teams ?**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-179">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="3b8c2-180">Votre vidéo sera lue sur le lecteur vidéo de OneDrive entreprise ou SharePoint, selon l’endroit où vous accédez au fichier.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-180">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="3b8c2-181">**Si vous envisagez d’utiliser l’ajout au flux, les vidéos existantes resteront-elles aussi longtemps que possible.**</span><span class="sxs-lookup"><span data-stu-id="3b8c2-181">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="3b8c2-182">Le flux en tant que plateforme ne sera pas déconseillé dans un avenir proche.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-182">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="3b8c2-183">Les vidéos actuellement actives dans le flux resteront là jusqu’à ce que la migration soit entamée.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-183">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="3b8c2-184">Lors de la migration, ces vidéos seront migrées vers ODSP également.</span><span class="sxs-lookup"><span data-stu-id="3b8c2-184">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="3b8c2-185">Pour plus d’informations, consultez [ici](https://docs.microsoft.com/stream/streamnew/classic-migration) .</span><span class="sxs-lookup"><span data-stu-id="3b8c2-185">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
