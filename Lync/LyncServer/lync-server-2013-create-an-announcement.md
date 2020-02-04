---
title: 'Lync Server 2013 : créer une annonce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfae1817cb47c769885ca42a7ca3ff6f57f7b669
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="0abca-102">Créer une annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0abca-102">Create an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0abca-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0abca-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0abca-104">Pour créer une annonce, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="0abca-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="0abca-105">Pour des invites audio, enregistrez le fichier audio à l’aide de votre application d’enregistrement audio favorite.</span><span class="sxs-lookup"><span data-stu-id="0abca-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="0abca-106">Pour des invites audio, exécutez l’applet de commande **Import-CsAnnouncementFile** pour importer les contenus du fichier audio vers le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0abca-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="0abca-107">Exécutez l’applet de commande **New-CsAnnouncement** pour créer et nommer l’annonce.</span><span class="sxs-lookup"><span data-stu-id="0abca-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="0abca-108">Effectuez cette étape pour créer des annonces avec une invite audio, une invite TTS ou sans invite.</span><span class="sxs-lookup"><span data-stu-id="0abca-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="0abca-109">Vous pouvez créer une annonce sans invite (par exemple, si vous voulez transférer des appels vers une destination spécifiques sans lire d’invite).</span><span class="sxs-lookup"><span data-stu-id="0abca-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="0abca-110">Affectez la nouvelle annonce à une plage de numéros dans la table des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="0abca-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="0abca-111">Cette rubrique décrit comment importer et créer des annonces.</span><span class="sxs-lookup"><span data-stu-id="0abca-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="0abca-112">Pour plus d’informations sur l’affectation d’annonces dans la table numéro non affecté, voir [configurer la table des numéros non attribués dans Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span><span class="sxs-lookup"><span data-stu-id="0abca-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="0abca-113">Pour créer une annonce</span><span class="sxs-lookup"><span data-stu-id="0abca-113">To create a new announcement</span></span>

1.  <span data-ttu-id="0abca-114">Pour des invites audio, créez le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="0abca-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="0abca-115">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0abca-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="0abca-116">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0abca-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="0abca-117">Pour des invites audio, exécutez :</span><span class="sxs-lookup"><span data-stu-id="0abca-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="0abca-118">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="0abca-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="0abca-p103">Pour transférer des appels vers la messagerie vocale, tapez SIPAddress au format sip:nomutilisateur@nomdomaine;opaque=app:voicemail (par exemple, sip:bob@contoso.com;opaque=app:voicemail). Pour transférer des appels vers un numéro de téléphone, tapez SIPAddress au format sip:number@nomdomaine;user=phone (par exemple, sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="0abca-p103">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="0abca-121">Par exemple, pour spécifier une invite audio :</span><span class="sxs-lookup"><span data-stu-id="0abca-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="0abca-122">Par exemple, pour spécifier une invite TTS :</span><span class="sxs-lookup"><span data-stu-id="0abca-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="0abca-123">Pour plus d’informations sur ces cmdlets et afficher la liste des codes de langue à utiliser dans le paramètre **TextToSpeechPrompt** , voir [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span><span class="sxs-lookup"><span data-stu-id="0abca-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0abca-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0abca-124">See Also</span></span>


[<span data-ttu-id="0abca-125">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="0abca-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="0abca-126">Nouveau-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="0abca-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="0abca-127">Configuration de la table des numéros non attribués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0abca-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

