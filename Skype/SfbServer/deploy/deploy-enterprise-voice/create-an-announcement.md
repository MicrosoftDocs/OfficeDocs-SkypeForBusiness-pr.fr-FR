---
title: Créer ou supprimer une annonce dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Créer ou supprimer des annonces pour application d’annonce dans Skype pour Business Server Enterprise Voice. Cela affecte le traitement des appels à des numéros non attribués.
ms.openlocfilehash: 46d743fa81db22ff7a528a6ba8ea99c5b8d6b4ec
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server-2015"></a>Créer ou supprimer une annonce dans Skype pour Business Server 2015
 
Créer ou supprimer des annonces pour application d’annonce dans Skype pour Business Server Enterprise Voice. Cela affecte le traitement des appels à des numéros non attribués.
  
Lorsque vous configurez des annonces, vous configurez vraiment la manière dont vous voulez que les appels à des numéros non attribués soient traités. Vous pouvez lire une invite, qui peut être un fichier audio ou un fichier de synthèse vocale (TTS) ou vous contenter de transférer l’appel vers une destination spécifiée sans lire d’invite.
  
Vous devez créer des annonces avant de définir le tableau des numéros non attribués. Vous devez effectuer cette étape pour toutes les annonces utilisant une invite sous forme de fichier audio, de fichier de synthèse vocale (TTS) ou n’utilisant aucune invite.
  
Cette rubrique décrit comment importer et créer des annonces. Pour plus d’informations sur l’assignation des annonces dans la table des numéros non attribuée, voir [configurer la Table des numéros non attribués](http://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).
  
## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Création d’une annonce pour les numéros non attribués

Pour créer une annonce, vous devez effectuer les tâches suivantes : 
  
1. Pour des invites audio, enregistrez le fichier audio à l’aide de votre application d’enregistrement audio favorite.
    
2. Pour des invites audio, exécutez la cmdlet **Import-CsAnnouncementFile** pour importer le contenu du fichier audio vers le magasin de fichiers.
    
3. Exécutez l’applet de commande **New-CsAnnouncement** pour créer et nommer l’annonce. Effectuez cette étape pour créer des annonces avec une invite audio, une invite TTS ou sans invite.
    
    > [!TIP]
    > Vous pouvez créer une annonce sans invite (par exemple, si vous voulez transférer des appels vers une destination spécifiques sans lire d’invite). 
  
4. Affectez la nouvelle annonce à une plage de numéros dans la table des numéros non attribués.
    
### <a name="to-create-a-new-announcement"></a>Pour créer une annonce

1. Pour des invites audio, créez le fichier audio.
    
2. Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.
    
3. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
4. Pour des invites audio, exécutez :
    
   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Exécutez :
    
   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Pour transférer des appels vers la messagerie vocale, tapez SIPAddress au format sip:nomutilisateur@nomdomaine;opaque=app:voicemail (par exemple, sip:bob@contoso.com;opaque=app:voicemail). Pour transférer des appels vers un numéro de téléphone, tapez SIPAddress au format sip:number@nomdomaine;user=phone (par exemple, sip:+ 14255550121@contoso.com;user=phone).
    
    Par exemple, pour spécifier une invite audio :
    
   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    Par exemple, pour spécifier une invite TTS :
    
   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

  Pour plus d’informations sur ces applets de commande et pour afficher la liste des codes de langue à utiliser dans le paramètre **TextToSpeechPrompt** , voir [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).
    
## <a name="delete-an-announcement-for-unassigned-numbers"></a>Suppression d’une annonce pour les numéros non attribués

### <a name="to-delete-an-announcement"></a>Pour supprimer une annonce

1. Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Répertoriez toutes les annonces de votre organisation. À partir de la ligne de commande, exécutez la commande suivante :
     
   ```
   Get-CsAnnouncement
   ```

4. Dans la liste obtenue, recherchez l’annonce à supprimer et copiez le GUID. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
   ```

    Exemple :
    
   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > Pour plus d’informations sur d’autres options, voir [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) et [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps). 
  
## <a name="see-also"></a>Voir aussi

#### 

[Créer ou supprimer une annonce dans Skype pour Business Server 2015](create-an-announcement.md)
#### 

[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)
  
[Nouvelle-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)
  
[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)
  
[Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

