---
title: Créer ou supprimer une annonce dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Créer ou supprimer des annonces pour application d’annonce dans Skype pour Business Server Voix Entreprise. Cela affecte le traitement des appels à des numéros non attribués.
ms.openlocfilehash: 043b2a4b6552386b2a8b0b2fee1cdd0249fe7f21
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server-2015"></a><span data-ttu-id="63838-104">Créer ou supprimer une annonce dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="63838-104">Create or delete an announcement in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="63838-105">Créer ou supprimer des annonces pour application d’annonce dans Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="63838-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="63838-106">Cela affecte le traitement des appels à des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="63838-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="63838-p103">Lorsque vous configurez des annonces, vous configurez vraiment la manière dont vous voulez que les appels à des numéros non attribués soient traités. Vous pouvez lire une invite, qui peut être un fichier audio ou un fichier de synthèse vocale (TTS) ou vous contenter de transférer l’appel vers une destination spécifiée sans lire d’invite.</span><span class="sxs-lookup"><span data-stu-id="63838-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>
  
<span data-ttu-id="63838-p104">Vous devez créer des annonces avant de définir le tableau des numéros non attribués. Vous devez effectuer cette étape pour toutes les annonces utilisant une invite sous forme de fichier audio, de fichier de synthèse vocale (TTS) ou n’utilisant aucune invite.</span><span class="sxs-lookup"><span data-stu-id="63838-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>
  
<span data-ttu-id="63838-111">Cette rubrique décrit comment importer et créer des annonces.</span><span class="sxs-lookup"><span data-stu-id="63838-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="63838-112">Pour plus d’informations sur l’affectation des annonces dans la table des numéros non attribuée, reportez-vous à la section [configurer la Table des numéros non attribués](http://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span><span class="sxs-lookup"><span data-stu-id="63838-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](http://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>
  
## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="63838-113">Création d’une annonce pour les numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="63838-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="63838-114">Pour créer une annonce, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="63838-114">To create a new announcement, you need to perform the following steps:</span></span> 
  
1. <span data-ttu-id="63838-115">Pour des invites audio, enregistrez le fichier audio à l’aide de votre application d’enregistrement audio favorite.</span><span class="sxs-lookup"><span data-stu-id="63838-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>
    
2. <span data-ttu-id="63838-116">Pour les invites audio, exécutez la cmdlet **Import-CsAnnouncementFile** pour importer le contenu du fichier audio à un magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="63838-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>
    
3. <span data-ttu-id="63838-117">Exécutez l’applet de commande **New-CsAnnouncement** pour créer et nommer l’annonce.</span><span class="sxs-lookup"><span data-stu-id="63838-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="63838-118">Effectuez cette étape pour créer des annonces avec une invite audio, une invite TTS ou sans invite.</span><span class="sxs-lookup"><span data-stu-id="63838-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="63838-119">Vous pouvez créer une annonce sans invite (par exemple, si vous voulez transférer des appels vers une destination spécifiques sans lire d’invite).</span><span class="sxs-lookup"><span data-stu-id="63838-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span> 
  
4. <span data-ttu-id="63838-120">Affectez la nouvelle annonce à une plage de numéros dans la table des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="63838-120">Assign the new announcement to a number range in the unassigned number table.</span></span>
    
### <a name="to-create-a-new-announcement"></a><span data-ttu-id="63838-121">Pour créer une annonce</span><span class="sxs-lookup"><span data-stu-id="63838-121">To create a new announcement</span></span>

1. <span data-ttu-id="63838-122">Pour des invites audio, créez le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="63838-122">For audio prompts, create the audio file.</span></span>
    
2. <span data-ttu-id="63838-123">Ouvrez une session sur l’ordinateur où est installé Skype pour Business Server Management Shell en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires, comme décrit dans **Déléguer les autorisations de configuration**.</span><span class="sxs-lookup"><span data-stu-id="63838-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
3. <span data-ttu-id="63838-124">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="63838-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
4. <span data-ttu-id="63838-125">Pour des invites audio, exécutez :</span><span class="sxs-lookup"><span data-stu-id="63838-125">For audio prompts, run:</span></span>
    
   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="63838-126">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="63838-126">Run:</span></span>
    
   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="63838-p107">Pour transférer des appels vers la messagerie vocale, tapez SIPAddress au format sip:nomutilisateur@nomdomaine;opaque=app:voicemail (par exemple, sip:bob@contoso.com;opaque=app:voicemail). Pour transférer des appels vers un numéro de téléphone, tapez SIPAddress au format sip:number@nomdomaine;user=phone (par exemple, sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="63838-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="63838-129">Par exemple, pour spécifier une invite audio :</span><span class="sxs-lookup"><span data-stu-id="63838-129">For example, to specify an audio prompt:</span></span>
    
   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="63838-130">Par exemple, pour spécifier une invite TTS :</span><span class="sxs-lookup"><span data-stu-id="63838-130">For example, to specify a TTS prompt:</span></span>
    
   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

  <span data-ttu-id="63838-131">Pour plus de détails sur ces applets de commande et pour afficher la liste des codes langue à utiliser dans le paramètre **TextToSpeechPrompt** , reportez-vous à la section [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="63838-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>
    
## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="63838-132">Suppression d’une annonce pour les numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="63838-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="63838-133">Pour supprimer une annonce</span><span class="sxs-lookup"><span data-stu-id="63838-133">To delete an announcement</span></span>

1. <span data-ttu-id="63838-134">Ouvrez une session sur l’ordinateur où est installé Skype pour Business Server Management Shell en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires, comme décrit dans **Déléguer les autorisations de configuration**.</span><span class="sxs-lookup"><span data-stu-id="63838-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="63838-135">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="63838-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="63838-p108">Répertoriez toutes les annonces de votre organisation. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="63838-p108">List all the announcements in your organization. At the command line, run:</span></span>
     
   ```
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="63838-p109">Dans la liste obtenue, recherchez l’annonce à supprimer et copiez le GUID. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="63838-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>
    
   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
   ```

    <span data-ttu-id="63838-140">Exemple :</span><span class="sxs-lookup"><span data-stu-id="63838-140">For example:</span></span>
    
   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="63838-141">Pour plus d’informations sur plus d’options, consultez [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) et [CsAnnouncement de la supprimer](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="63838-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="63838-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="63838-142">See also</span></span>

#### 

[<span data-ttu-id="63838-143">Créer ou supprimer une annonce dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="63838-143">Create or delete an announcement in Skype for Business Server 2015</span></span>](create-an-announcement.md)
#### 

[<span data-ttu-id="63838-144">Importation-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="63838-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)
  
[<span data-ttu-id="63838-145">Nouvelle-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="63838-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)
  
[<span data-ttu-id="63838-146">Supprimer-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="63838-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)
  
[<span data-ttu-id="63838-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="63838-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

