---
title: 'Lync Server 2013 : créer une annonce'
description: 'Lync Server 2013 : créer une annonce.'
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
ms.openlocfilehash: cc064686ef86e04b89951fcaac7abbec28b7257c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562390"
---
# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="73096-103">Créer une annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73096-103">Create an announcement in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73096-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="73096-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="73096-105">Pour créer une annonce, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="73096-105">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="73096-106">Pour les invites audio, enregistrez le fichier audio à l’aide de votre application d’enregistrement audio favorite.</span><span class="sxs-lookup"><span data-stu-id="73096-106">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="73096-107">Pour les invites audio, exécutez l’applet de commande **Import-CsAnnouncementFile** pour importer le contenu du fichier audio dans le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="73096-107">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="73096-108">Exécutez la cmdlet **New-CsAnnouncement** pour créer et nommer l’annonce.</span><span class="sxs-lookup"><span data-stu-id="73096-108">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="73096-109">Effectuez cette étape pour créer des annonces avec une invite audio, une invite de conversion de texte par synthèse vocale ou sans invite.</span><span class="sxs-lookup"><span data-stu-id="73096-109">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="73096-110">Vous pouvez créer une annonce sans invite (par exemple, si vous souhaitez transférer des appels vers une destination spécifique sans lire de message).</span><span class="sxs-lookup"><span data-stu-id="73096-110">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="73096-111">Affectez la nouvelle annonce à une plage de numéros dans la table des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="73096-111">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="73096-112">Cette rubrique décrit comment importer et créer des annonces.</span><span class="sxs-lookup"><span data-stu-id="73096-112">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="73096-113">Pour plus d’informations sur l’attribution d’annonces dans la table des numéros non attribués, reportez-vous à [la rubrique Configurer le tableau des numéros non attribués dans Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span><span class="sxs-lookup"><span data-stu-id="73096-113">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="73096-114">Pour créer une annonce</span><span class="sxs-lookup"><span data-stu-id="73096-114">To create a new announcement</span></span>

1.  <span data-ttu-id="73096-115">Pour les invites audio, créez le fichier audio.</span><span class="sxs-lookup"><span data-stu-id="73096-115">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="73096-116">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="73096-116">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="73096-117">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="73096-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="73096-118">Pour les invites audio, exécutez :</span><span class="sxs-lookup"><span data-stu-id="73096-118">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="73096-119">Générer</span><span class="sxs-lookup"><span data-stu-id="73096-119">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="73096-120">Pour le transfert d’appels vers la messagerie vocale, tapez SIPAddress au format SIP : username@domainname ; opaque = app : messagerie vocale (par exemple, SIP : bob@contoso. com ; opaque = application : messagerie vocale).</span><span class="sxs-lookup"><span data-stu-id="73096-120">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="73096-121">Pour le transfert des appels vers un numéro de téléphone, tapez SIPAddress au format SIP : number@domainname ; User = Phone (par exemple, SIP : + 14255550121@contoso. com ; user = Phone).</span><span class="sxs-lookup"><span data-stu-id="73096-121">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="73096-122">Par exemple, pour spécifier une invite audio :</span><span class="sxs-lookup"><span data-stu-id="73096-122">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="73096-123">Par exemple, pour spécifier une invite TTS :</span><span class="sxs-lookup"><span data-stu-id="73096-123">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="73096-124">Pour plus d’informations sur ces applets de commande et pour afficher une liste des codes de langue à utiliser dans le paramètre **TextToSpeechPrompt** , voir [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span><span class="sxs-lookup"><span data-stu-id="73096-124">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="73096-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="73096-125">See Also</span></span>


[<span data-ttu-id="73096-126">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="73096-126">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="73096-127">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="73096-127">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="73096-128">Configuration de la table des numéros non attribués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73096-128">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

