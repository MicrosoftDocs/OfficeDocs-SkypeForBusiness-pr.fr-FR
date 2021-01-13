---
title: Créer ou supprimer une annonce dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Créez ou supprimez des annonces pour l’application d’annonce dans Skype Entreprise Server Voix Entreprise. Cela affecte la façon dont les appels vers des numéros non affectés sont gérés.
ms.openlocfilehash: 9f2b4fcda8e98d4b939b6b443da875dbe153546c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824904"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="82a0e-104">Créer ou supprimer une annonce dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="82a0e-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="82a0e-105">Créez ou supprimez des annonces pour l’application d’annonce dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="82a0e-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="82a0e-106">Cela affecte la façon dont les appels vers des numéros non affectés sont gérés.</span><span class="sxs-lookup"><span data-stu-id="82a0e-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="82a0e-p103">Lorsque vous configurez des annonces, vous configurez vraiment la manière dont vous voulez que les appels à des numéros non attribués soient traités. Vous pouvez lire une invite, qui peut être un fichier audio ou un fichier de synthèse vocale (TTS), ou bien vous contenter de transférer l’appel vers une destination spécifiée sans lire d’invite.</span><span class="sxs-lookup"><span data-stu-id="82a0e-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="82a0e-p104">Vous devez créer des annonces avant de définir le tableau des numéros non attribués. Vous devez effectuer cette étape pour toutes les annonces utilisant une invite sous forme de fichier audio, de fichier de synthèse vocale (TTS), ou n’utilisant aucune invite.</span><span class="sxs-lookup"><span data-stu-id="82a0e-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="82a0e-111">Cette rubrique décrit comment importer et créer des annonces.</span><span class="sxs-lookup"><span data-stu-id="82a0e-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="82a0e-112">Pour plus d’informations sur l’affectation d’annonces dans la table des chiffres non attribués, voir Configurer la [table Desassigned Number](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span><span class="sxs-lookup"><span data-stu-id="82a0e-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="82a0e-113">Créer une annonce pour les numéros non signés</span><span class="sxs-lookup"><span data-stu-id="82a0e-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="82a0e-114">Pour créer une annonce, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="82a0e-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="82a0e-115">Pour les invites audio, enregistrez le fichier audio à l’aide de votre application d’enregistrement audio favorite.</span><span class="sxs-lookup"><span data-stu-id="82a0e-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="82a0e-116">Pour les invites audio, exécutez l’cmdlet **Import-CsAnnouncementFile** pour importer le contenu du fichier audio dans le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="82a0e-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="82a0e-117">Exécutez **l’cmdlet New-CsAnnouncement** pour créer et nommer l’annonce.</span><span class="sxs-lookup"><span data-stu-id="82a0e-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="82a0e-118">Effectuez cette étape pour créer des annonces avec une invite audio, une invite de reconnaissance vocale (TTS) ou sans invite.</span><span class="sxs-lookup"><span data-stu-id="82a0e-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="82a0e-119">Vous pouvez créer une annonce sans invite (par exemple, si vous souhaitez transférer des appels vers une destination spécifique sans lire de message).</span><span class="sxs-lookup"><span data-stu-id="82a0e-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="82a0e-120">Affectez la nouvelle annonce à une plage de numéro dans la table des chiffres non attribués.</span><span class="sxs-lookup"><span data-stu-id="82a0e-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="82a0e-121">Pour créer une annonce</span><span class="sxs-lookup"><span data-stu-id="82a0e-121">To create a new announcement</span></span>

1. <span data-ttu-id="82a0e-122">Pour les invites audio, créez le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="82a0e-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="82a0e-123">Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.</span><span class="sxs-lookup"><span data-stu-id="82a0e-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="82a0e-124">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="82a0e-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="82a0e-125">Pour les invites audio, exécutez :</span><span class="sxs-lookup"><span data-stu-id="82a0e-125">For audio prompts, run:</span></span>

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="82a0e-126">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="82a0e-126">Run:</span></span>

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="82a0e-127">Pour transférer des appels vers la messagerie vocale, tapez SIPAddress au format sip:username@domainname;opaque=app:voicemail (par exemple, sip:bob@contoso.com;opaque=app:voicemail).</span><span class="sxs-lookup"><span data-stu-id="82a0e-127">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="82a0e-128">Pour transférer des appels vers un numéro de téléphone, tapez SIPAddress au format sip:number@domainname;user=phone (par exemple, sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="82a0e-128">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="82a0e-129">Par exemple, pour spécifier une invite audio :</span><span class="sxs-lookup"><span data-stu-id="82a0e-129">For example, to specify an audio prompt:</span></span>

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="82a0e-130">Par exemple, pour spécifier une invite TTS :</span><span class="sxs-lookup"><span data-stu-id="82a0e-130">For example, to specify a TTS prompt:</span></span>

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="82a0e-131">Pour plus d’informations sur ces cmdlets et pour obtenir la liste des codes de langue à utiliser dans le paramètre **TextToSpeechPrompt,** voir [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="82a0e-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="82a0e-132">Supprimer une annonce pour les numéros non signés</span><span class="sxs-lookup"><span data-stu-id="82a0e-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="82a0e-133">Pour supprimer une annonce</span><span class="sxs-lookup"><span data-stu-id="82a0e-133">To delete an announcement</span></span>

1. <span data-ttu-id="82a0e-134">Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.</span><span class="sxs-lookup"><span data-stu-id="82a0e-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="82a0e-135">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="82a0e-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="82a0e-p108">Répertoriez toutes les annonces de votre organisation. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="82a0e-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```powershell
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="82a0e-p109">Dans la liste obtenue, recherchez l’annonce que vous voulez supprimer et copiez le GUID. À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="82a0e-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="82a0e-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="82a0e-140">For example:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="82a0e-141">Pour plus d’informations sur d’autres options, voir [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) et [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="82a0e-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="82a0e-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82a0e-142">See also</span></span>

[<span data-ttu-id="82a0e-143">Créer ou supprimer une annonce dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="82a0e-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="82a0e-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="82a0e-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="82a0e-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="82a0e-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="82a0e-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="82a0e-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="82a0e-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="82a0e-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

