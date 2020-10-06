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
ms.openlocfilehash: b31972ed662b6752286fa2ff33b80150496cfb0f
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361334"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="62a1d-103">Utiliser OneDrive entreprise et SharePoint ou un flux pour les enregistrements de réunion</span><span class="sxs-lookup"><span data-stu-id="62a1d-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="62a1d-104">Les modifications apportées à l’utilisation de Microsoft Stream pour OneDrive Entreprise et SharePoint pour les enregistrements de réunion auront une approche progressive.</span><span class="sxs-lookup"><span data-stu-id="62a1d-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="62a1d-105">Au démarrage, les administrateurs de clients peuvent choisir cette nouvelle option de flux de travail dès aujourd’hui et commencer à voir les enregistrements téléchargés automatiquement dans OneDrive entreprise et SharePoint en octobre 2020.</span><span class="sxs-lookup"><span data-stu-id="62a1d-105">At launch, tenant admins can choose this new workflow option today and will start seeing recordings auto-upload to OneDrive for Business and SharePoint in October 2020.</span></span> <span data-ttu-id="62a1d-106">En novembre, vous devrez annuler votre abonnement si vous voulez continuer à utiliser le flux et à quelques instants dans les 2021 au début, nous aurons besoin de tous les clients d’utiliser OneDrive entreprise et SharePoint pour les nouveaux enregistrements de réunion.</span><span class="sxs-lookup"><span data-stu-id="62a1d-106">In November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="62a1d-107">Microsoft teams dispose d’une nouvelle méthode pour l’enregistrement des enregistrements de réunion.</span><span class="sxs-lookup"><span data-stu-id="62a1d-107">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="62a1d-108">Comme départ du flux, la méthode utilise Microsoft OneDrive et SharePoint dans Microsoft 365 et offre de nombreux avantages.</span><span class="sxs-lookup"><span data-stu-id="62a1d-108">As a departure from Stream, the method uses Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="62a1d-109">Les avantages de l’utilisation de OneDrive entreprise et SharePoint pour le stockage d’enregistrements sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="62a1d-109">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="62a1d-110">Stratégies de rétention pour l’enregistrement des réunions Teams (TMR)</span><span class="sxs-lookup"><span data-stu-id="62a1d-110">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="62a1d-111">Avantages de OneDrive entreprise et de la gouvernance des informations de SharePoint</span><span class="sxs-lookup"><span data-stu-id="62a1d-111">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="62a1d-112">Simplification de la définition des autorisations et du partage</span><span class="sxs-lookup"><span data-stu-id="62a1d-112">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="62a1d-113">Partager des enregistrements avec des invités (utilisateurs externes) avec le partage explicite uniquement</span><span class="sxs-lookup"><span data-stu-id="62a1d-113">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="62a1d-114">Demander un flux d’accès</span><span class="sxs-lookup"><span data-stu-id="62a1d-114">Request access flow</span></span>
- <span data-ttu-id="62a1d-115">Fournir des liens OneDrive entreprise et SharePoint partagés</span><span class="sxs-lookup"><span data-stu-id="62a1d-115">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="62a1d-116">Quota accru</span><span class="sxs-lookup"><span data-stu-id="62a1d-116">Increased quota</span></span>
- <span data-ttu-id="62a1d-117">Les enregistrements de réunion sont disponibles plus vite</span><span class="sxs-lookup"><span data-stu-id="62a1d-117">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="62a1d-118">**Accéder** au support client local</span><span class="sxs-lookup"><span data-stu-id="62a1d-118">**Go local** tenant support</span></span>
- <span data-ttu-id="62a1d-119">Prise en charge de plusieurs géographiques : les enregistrements sont stockés dans une zone spécifique à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="62a1d-119">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="62a1d-120">Mettre en place votre propre clé (BYOK)</span><span class="sxs-lookup"><span data-stu-id="62a1d-120">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="62a1d-121">Amélioration de la qualité de transcription et de l’intervenant</span><span class="sxs-lookup"><span data-stu-id="62a1d-121">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="62a1d-122">Certaines limitations sont à prendre en compte :</span><span class="sxs-lookup"><span data-stu-id="62a1d-122">There are some limitations to consider:</span></span>

- <span data-ttu-id="62a1d-123">Il s’agit de sous-titres et de transcriptions en anglais uniquement.</span><span class="sxs-lookup"><span data-stu-id="62a1d-123">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="62a1d-124">Vous ne serez pas en mesure de rechercher des transcriptions ou leur contenu.</span><span class="sxs-lookup"><span data-stu-id="62a1d-124">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="62a1d-125">Vous ne serez pas en mesure de modifier les transcriptions, mais vous pourrez activer/désactiver les légendes.</span><span class="sxs-lookup"><span data-stu-id="62a1d-125">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="62a1d-126">Vous pouvez contrôler les personnes avec lesquelles vous partagez l’enregistrement, mais vous ne pouvez pas bloquer les utilisateurs disposant d’un accès partagé pour télécharger l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="62a1d-126">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="62a1d-127">Vous ne recevrez pas d’e-mail à la fin de l’enregistrement, mais l’enregistrement s’affichera dans la conversation de la réunion une fois que vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="62a1d-127">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="62a1d-128">Cela se produit beaucoup plus rapidement qu’auparavant dans le flux</span><span class="sxs-lookup"><span data-stu-id="62a1d-128">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="62a1d-129">Regardez « enregistrement de la réunion » pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="62a1d-129">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="62a1d-130">Configurer l’option d’enregistrement de la réunion pour OneDrive entreprise et SharePoint</span><span class="sxs-lookup"><span data-stu-id="62a1d-130">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="62a1d-131">Installez la console d’administration PowerShell de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="62a1d-131">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="62a1d-132">a.</span><span class="sxs-lookup"><span data-stu-id="62a1d-132">a.</span></span> <span data-ttu-id="62a1d-133">Téléchargez [Skype entreprise Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="62a1d-133">Download [Skype for Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="62a1d-134">b.</span><span class="sxs-lookup"><span data-stu-id="62a1d-134">b.</span></span> <span data-ttu-id="62a1d-135">Suivez les invites pour l’installer.</span><span class="sxs-lookup"><span data-stu-id="62a1d-135">Follow the prompts to install it.</span></span>

    <span data-ttu-id="62a1d-136">c.</span><span class="sxs-lookup"><span data-stu-id="62a1d-136">c.</span></span> <span data-ttu-id="62a1d-137">Redémarrez votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="62a1d-137">Restart your machine.</span></span>

2. <span data-ttu-id="62a1d-138">Lancer PowerShell en tant qu’administrateur</span><span class="sxs-lookup"><span data-stu-id="62a1d-138">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="62a1d-139">Importez le connecteur SkypeOnline et connectez-vous en tant qu’administrateur Teams.</span><span class="sxs-lookup"><span data-stu-id="62a1d-139">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="62a1d-140">Utilisez [Set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour définir une stratégie de réunion équipes pour passer du stockage de flux à ODSP.</span><span class="sxs-lookup"><span data-stu-id="62a1d-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="62a1d-141">Désactiver OneDrive entreprise et SharePoint pour continuer à utiliser le flux</span><span class="sxs-lookup"><span data-stu-id="62a1d-141">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="62a1d-142">Même si une stratégie indique qu’il est défini sur **Stream**, il est possible qu’elle ne soit pas définie.</span><span class="sxs-lookup"><span data-stu-id="62a1d-142">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="62a1d-143">En règle générale, si la stratégie n’est pas définie, le paramètre par défaut est **flux**.</span><span class="sxs-lookup"><span data-stu-id="62a1d-143">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="62a1d-144">Toutefois, si vous souhaitez annuler votre utilisation de SharePoint ou OneDrive, vous devez réinitialiser la stratégie sur **flux** pour vous assurer qu’elle est définie sur la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="62a1d-144">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="62a1d-145">Questions fréquemment posées</span><span class="sxs-lookup"><span data-stu-id="62a1d-145">Frequently asked questions</span></span>

<span data-ttu-id="62a1d-146">**Où l’enregistrement de la réunion sera-t-il stocké ?**</span><span class="sxs-lookup"><span data-stu-id="62a1d-146">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="62a1d-147">Pour les réunions hors canal, l’enregistrement est stocké dans un dossier nommé.</span><span class="sxs-lookup"><span data-stu-id="62a1d-147">For non-Channel meetings, the recording is stored in a folder named.</span></span> <span data-ttu-id="62a1d-148">Enregistrements \* \* qui se trouve au niveau supérieur du OneDrive qui appartient à la personne qui a démarré l’enregistrement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="62a1d-148">Recordings\*\* that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="62a1d-149">Example</span><span class="sxs-lookup"><span data-stu-id="62a1d-149">Example:</span></span>

  <span data-ttu-id="62a1d-150"><i>OneDrive entreprise</i> / de l’enregistreur **Enregistrements**</span><span class="sxs-lookup"><span data-stu-id="62a1d-150"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="62a1d-151">Pour les réunions de canal, l’enregistrement est stocké dans la bibliothèque de documents du site d’équipe dans un dossier nommé **enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="62a1d-151">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="62a1d-152">Example</span><span class="sxs-lookup"><span data-stu-id="62a1d-152">Example:</span></span>

  <span data-ttu-id="62a1d-153"><i>Nom de l’équipe-nom du canal</i> / Des **documents** / ; **Enregistrements**</span><span class="sxs-lookup"><span data-stu-id="62a1d-153"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="62a1d-154">**Qui dispose des autorisations pour afficher l’enregistrement de la réunion ?**</span><span class="sxs-lookup"><span data-stu-id="62a1d-154">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="62a1d-155">Pour les réunions hors-canal, tous les participants à la réunion, à l’exception des utilisateurs externes, sont automatiquement liés à un lien.</span><span class="sxs-lookup"><span data-stu-id="62a1d-155">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="62a1d-156">Les utilisateurs externes devront être explicitement ajoutés à la liste partagée par l’organisateur de la réunion ou la personne qui a démarré l’enregistrement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="62a1d-156">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="62a1d-157">Pour les réunions de canal, les autorisations sont héritées de la liste propriétaires et membres du canal.</span><span class="sxs-lookup"><span data-stu-id="62a1d-157">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="62a1d-158">**Comment gérer les transcriptions ?**</span><span class="sxs-lookup"><span data-stu-id="62a1d-158">**How can I manage transcripts?**</span></span>

<span data-ttu-id="62a1d-159">Les clients qui choisissent de bénéficier de cette version d’évaluation ne disposent pas de sous-titres disponibles dans leurs enregistrements de réunion teams migrés vers OneDrive et SharePoint.</span><span class="sxs-lookup"><span data-stu-id="62a1d-159">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="62a1d-160">Nous travaillons à l’ajout de sous-titres, en commençant par des sous-titres en anglais, et des enregistrements de réunion en octobre 2020.</span><span class="sxs-lookup"><span data-stu-id="62a1d-160">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="62a1d-161">Les sous-titres seront disponibles dans les enregistrements de réunion teams pour les clients qui ont choisi d’autoriser les transcriptions comme décrit dans la rubrique [enregistrements Cloud teams](cloud-recording.md) .</span><span class="sxs-lookup"><span data-stu-id="62a1d-161">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="62a1d-162">Les légendes permettent de créer du contenu inclusive pour les visualiseurs de toutes les aptitudes.</span><span class="sxs-lookup"><span data-stu-id="62a1d-162">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="62a1d-163">En tant que propriétaire, vous pouvez masquer les sous-titres, même si la transcription reste disponible dans les équipes, sauf si vous supprimez les sous-titres de teams.</span><span class="sxs-lookup"><span data-stu-id="62a1d-163">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="62a1d-164">Découvrir [Comment activer ou désactiver les enregistrements de réunion](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="62a1d-164">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="62a1d-165">Les sous-titres sont pris en charge pour les enregistrements des réunions teams pendant 60 jours à compter de la date d’enregistrement de la réunion.</span><span class="sxs-lookup"><span data-stu-id="62a1d-165">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="62a1d-166">**Comment le quota de stockage sera-t-il affecté ?**</span><span class="sxs-lookup"><span data-stu-id="62a1d-166">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="62a1d-167">Les fichiers d’enregistrements de réunion teams résident dans OneDrive entreprise et SharePoint inclus dans votre quota de ces services.</span><span class="sxs-lookup"><span data-stu-id="62a1d-167">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="62a1d-168">Voir [quota SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) et [quota OneDrive entreprise] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="62a1d-168">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="62a1d-169">**Comment lire l’enregistrement d’une réunion teams ?**</span><span class="sxs-lookup"><span data-stu-id="62a1d-169">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="62a1d-170">Votre vidéo sera lue sur le lecteur vidéo de OneDrive entreprise ou SharePoint, selon l’endroit où vous accédez au fichier.</span><span class="sxs-lookup"><span data-stu-id="62a1d-170">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="62a1d-171">**Si vous envisagez d’utiliser l’ajout au flux, les vidéos existantes resteront-elles aussi longtemps que possible.**</span><span class="sxs-lookup"><span data-stu-id="62a1d-171">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="62a1d-172">Le flux en tant que plateforme ne sera pas déconseillé dans un avenir proche.</span><span class="sxs-lookup"><span data-stu-id="62a1d-172">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="62a1d-173">Les vidéos actuellement actives dans le flux resteront là jusqu’à ce que la migration soit entamée.</span><span class="sxs-lookup"><span data-stu-id="62a1d-173">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="62a1d-174">Lors de la migration, ces vidéos seront migrées vers ODSP également.</span><span class="sxs-lookup"><span data-stu-id="62a1d-174">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="62a1d-175">Pour plus d’informations, consultez [ici](https://docs.microsoft.com/stream/streamnew/classic-migration) .</span><span class="sxs-lookup"><span data-stu-id="62a1d-175">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
