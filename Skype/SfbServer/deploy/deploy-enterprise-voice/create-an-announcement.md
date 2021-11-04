---
title: Créer ou supprimer une annonce dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Créez ou supprimez des annonces pour l’application Annonce dans Skype Entreprise Server Voix Entreprise. Cela affecte la façon dont les appels vers des numéros non affectés sont gérés.
ms.openlocfilehash: 3a5fdbcb5f9c4e72790f35f73cef791868634ce9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765922"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Créer ou supprimer une annonce dans Skype Entreprise Server

Créez ou supprimez des annonces pour l’application Annonce dans Skype Entreprise Server Voix Entreprise. Cela affecte la façon dont les appels vers des numéros non affectés sont gérés.

Lorsque vous configurez des annonces, vous configurez vraiment la manière dont vous voulez que les appels à des numéros non attribués soient traités. Vous pouvez lire une invite, qui peut être un fichier audio ou un fichier de synthèse vocale (TTS), ou bien vous contenter de transférer l’appel vers une destination spécifiée sans lire d’invite.

Vous devez créer des annonces avant de définir le tableau des numéros non attribués. Vous devez effectuer cette étape pour toutes les annonces utilisant une invite sous forme de fichier audio, de fichier de synthèse vocale (TTS), ou n’utilisant aucune invite.

Cette rubrique décrit comment importer et créer des annonces. Pour plus d’informations sur l’affectation d’annonces dans la table des chiffres non attribués, voir Configurer la [table Desassigned Number](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table).

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Créer une annonce pour les numéros non signés

Pour créer une annonce, vous devez effectuer les étapes suivantes :

1. Pour les invites audio, enregistrez le fichier audio à l’aide de votre application d’enregistrement audio favorite.

2. Pour les invites audio, exécutez l’cmdlet **Import-CsAnnouncementFile** pour importer le contenu du fichier audio dans le magasin de fichiers.

3. Exécutez **l’cmdlet New-CsAnnouncement** pour créer et nommer l’annonce. Effectuez cette étape pour créer des annonces avec une invite audio, une invite de reconnaissance vocale (TTS) ou sans invite.

    > [!TIP]
    > Vous pouvez créer une annonce sans invite (par exemple, si vous souhaitez transférer des appels vers une destination spécifique sans lire de message).

4. Affectez la nouvelle annonce à une plage de numéro dans la table des chiffres non attribués.

### <a name="to-create-a-new-announcement"></a>Pour créer une annonce

1. Pour les invites audio, créez le fichier audio.

2. Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.

3. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**

4. Pour les invites audio, exécutez :

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Exécutez :  

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Pour transférer des appels vers la messagerie vocale, tapez SIPAddress au format sip:username@domainname;opaque=app:voicemail (par exemple, sip:bob@contoso.com;opaque=app:voicemail). Pour transférer des appels vers un numéro de téléphone, tapez SIPAddress au format sip:number@domainname;user=phone (par exemple, sip:+ 14255550121@contoso.com;user=phone).

    Par exemple, pour spécifier une invite audio :

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    Par exemple, pour spécifier une invite TTS :

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   Pour plus d’informations sur ces cmdlets et pour obtenir la liste des codes de langue à utiliser dans le paramètre **TextToSpeechPrompt,** voir [New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps).

## <a name="delete-an-announcement-for-unassigned-numbers"></a>Supprimer une annonce pour les numéros non supprimés

### <a name="to-delete-an-announcement"></a>Pour supprimer une annonce

1. Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.

2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**

3. Répertoriez toutes les annonces de votre organisation. À partir de la ligne de commande, exécutez la commande suivante :

   ```powershell
   Get-CsAnnouncement
   ```

4. Dans la liste obtenue, recherchez l’annonce que vous voulez supprimer et copiez le GUID. À partir de la ligne de commande, exécutez la commande suivante :

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    Par exemple :

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > Pour plus d’informations sur d’autres options, voir [Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps) et [Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps).

## <a name="see-also"></a>Voir aussi

[Créer ou supprimer une annonce dans Skype Entreprise Server](create-an-announcement.md)

[Import-CsAnnouncementFile](/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps)