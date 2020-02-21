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
ms.openlocfilehash: 108d0ed2800abcb572b7706a26fe9b0c2fab4500
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a>Créer une annonce dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Pour créer une annonce, vous devez effectuer les étapes suivantes :

1.  Pour les invites audio, enregistrez le fichier audio à l’aide de votre application d’enregistrement audio favorite.

2.  Pour les invites audio, exécutez l’applet de commande **Import-CsAnnouncementFile** pour importer le contenu du fichier audio dans le magasin de fichiers.

3.  Exécutez la cmdlet **New-CsAnnouncement** pour créer et nommer l’annonce. Effectuez cette étape pour créer des annonces avec une invite audio, une invite de conversion de texte par synthèse vocale ou sans invite.
    
    <div>
    

    > [!TIP]  
    > Vous pouvez créer une annonce sans invite (par exemple, si vous souhaitez transférer des appels vers une destination spécifique sans lire de message).

    
    </div>

4.  Affectez la nouvelle annonce à une plage de numéros dans la table des numéros non attribués.

Cette rubrique décrit comment importer et créer des annonces. Pour plus d’informations sur l’attribution d’annonces dans la table des numéros non attribués, reportez-vous à [la rubrique Configurer le tableau des numéros non attribués dans Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).

<div>

## <a name="to-create-a-new-announcement"></a>Pour créer une annonce

1.  Pour les invites audio, créez le fichier audio.

2.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

3.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

4.  Pour les invites audio, exécutez :
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  Générer
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    Pour le transfert d’appels vers la messagerie vocale, tapez SIPAddress au format SIP : username@domainname ; opaque = app : messagerie vocale (par exemple, SIP : bob@contoso. com ; opaque = application : messagerie vocale). Pour le transfert des appels vers un numéro de téléphone, tapez SIPAddress au format SIP : number@domainname ; User = Phone (par exemple, SIP : + 14255550121@contoso. com ; user = Phone).
    
    Par exemple, pour spécifier une invite audio :
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    Par exemple, pour spécifier une invite TTS :
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    Pour plus d’informations sur ces applets de commande et pour afficher une liste des codes de langue à utiliser dans le paramètre **TextToSpeechPrompt** , voir [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[Configuration de la table des numéros non attribués dans Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

