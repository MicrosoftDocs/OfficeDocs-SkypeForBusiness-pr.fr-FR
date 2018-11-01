---
title: 'Lync Server 2013 : Création d’une annonce'
TOCTitle: Création d’une annonce
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412783(v=OCS.15)
ms:contentKeyID: 49298432
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création d’une annonce dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Pour créer une annonce, vous devez effectuer les tâches suivantes :

1.  Pour des invites audio, enregistrez le fichier audio à l’aide de votre application d’enregistrement audio favorite.

2.  Pour des invites audio, exécutez l’applet de commande **Import-CsAnnouncementFile** pour importer les contenus du fichier audio vers le magasin de fichiers.

3.  Exécutez l’applet de commande **New-CsAnnouncement** pour créer et nommer l’annonce. Effectuez cette étape pour créer des annonces avec une invite audio, une invite TTS ou sans invite.
    
    > [!TIP]  
    > Vous pouvez créer une annonce sans invite (par exemple, si vous voulez transférer des appels vers une destination spécifiques sans lire d’invite).

4.  Affecter la nouvelle annonce à une plage de numéros dans la table des numéros non attribués.

Cette rubrique décrit comment importer et créer des annonces. Pour plus d’informations sur l’attribution d’annonces dans la table des numéros non attribués, reportez-vous à [Configuration de la table des numéros non attribués dans Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).

## Pour créer une nouvelle annonce

1.  Pour des invites audio, créez le fichier audio.

2.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

3.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Pour des invites audio, exécutez :
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  Exécutez :
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    Pour transférer des appels vers la messagerie vocale, tapez SIPAddress dans le format sip:nomutilisateur@nomdomaine;opaque=app:voicemail (par exemple, sip:bob@contoso.com;opaque=app:voicemail). Pour transférer des appels vers un numéro de téléphone, tapez SIPAddress dans le format sip:number@nomdomaine;user=phone (par exemple, sip:+ 14255550121@contoso.com;user=phone).
    
    Par exemple, pour spécifier une invite audio :
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    Par exemple, pour spécifier une invite TTS :
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    Pour plus d’informations sur ces applets de commande et pour voir une liste des codes de langues à utiliser dans le paramètre **TextToSpeechPrompt**, reportez-vous à [New-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAnnouncement).

## Voir aussi

#### Autres ressources

[Import-CsAnnouncementFile](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsAnnouncementFile)  
[New-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAnnouncement)  
[Configuration de la table des numéros non attribués dans Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md)

