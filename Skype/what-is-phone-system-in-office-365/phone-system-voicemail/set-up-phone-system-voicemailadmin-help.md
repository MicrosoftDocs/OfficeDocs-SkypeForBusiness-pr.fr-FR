---
title: "Configurer la messagerie vocale système téléphonique - aide d'administration"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
description: "Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. "
---

# Configurer la messagerie vocale système téléphonique - aide d'administration

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](9c590873-b014-4df3-9e27-1bb97322a79d.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/9c590873-b014-4df3-9e27-1bb97322a79d). 
  
Cet article concerne l' [À propos des rôles d'administrateur Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) et que vous souhaitez configurer la fonctionnalité de messagerie vocale système téléphonique pour tout le monde dans l'entreprise.
  
> [!NOTE]
> Messagerie vocale système téléphonique prend en charge les messages vocaux déposer uniquement dans une boîte aux lettres Exchange et ne prend pas en charge les systèmes de courrier électronique tiers. Comme mécanisme de secours, messagerie vocale système téléphonique permet de renvoyer des messages à l'aide de SMTP, ce qui signifie que les utilisateurs avec une boîte aux lettres sur un système de courrier électronique tiers recevront leurs messages vocaux avec aucune disponibilité garantie service ou d'autres fonctionnalités de messagerie vocale, telles que la modification leurs messages d'accueil et d'autres paramètres. 
  
## Les environnements cloud uniquement : configurer la messagerie vocale système téléphonique

Pour Skype pour les utilisateurs professionnels en ligne et l'appel d'offre, messagerie vocale système téléphonique est automatiquement configurer et sa mise en service pour les utilisateurs une fois que vous leur attribuez une licence **Système téléphonique** et un numéro de téléphone.
  
1. Si la fonctionnalité système téléphonique n'est pas incluse dans votre offre, vous devrez peut-être acheter des licences de composant additionnel **Système téléphonique**. Vous devrez également acheter une licence Exchange Online. Voir [Skype pour les entreprises et Microsoft Teams module complémentaire licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), le [Attribuez Skype pour les entreprises et Microsoft Teams des licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)et les licences Exchange Online pour les membres de votre entreprise. Une fois que vous effectuez cette opération, ils seront en mesure de recevoir des messages vocaux !
    
3. Prise en charge de la messagerie vocale transcription a été ajouté à partir de mars 2017 et est activée par défaut pour toutes les organisations et les utilisateurs. Vous pouvez désactiver la transcription pour votre organisation à l'aide de Windows PowerShell et suivez les étapes décrites ci-dessous.
    
## Système téléphonique aux environnements locaux

Les informations suivantes sont sur la configuration système téléphonique messagerie vocale pour travailler avec des environnements locaux appelant planifier.
  
1. Si la fonctionnalité système téléphonique n'est pas incluse dans votre offre, vous devrez peut-être acheter des licences de composant additionnel **Système téléphonique**. Vous devez également acheter une licence Exchange Online. Voir [Skype pour les entreprises et Microsoft Teams module complémentaire licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), le [Attribuez Skype pour les entreprises et Microsoft Teams des licences](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)et les licences Exchange Online pour les membres de votre entreprise.
    
3. Suivez les instructions dans la section **Activer les utilisateurs pour le système téléphonique voix et de services de messagerie vocale** de la[Configurer Skype pour Business Cloud connecteur Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).
    
4. Prise en charge de la messagerie vocale transcription a été ajouté à partir de mars 2017 et est activée par défaut pour toutes les organisations et les utilisateurs. Vous pouvez désactiver la transcription pour votre organisation à l'aide de Windows PowerShell et suivez les étapes décrites ci-dessous.
    
5. Vous pouvez également consulter la [messagerie vocale PBX Azure prend en charge pour Exchange Server](https://support.microsoft.com/en-us/kb/3195158) pour savoir comment configurer la remise des messages vocaux Azure pour les utilisateurs système téléphonique qui ont une boîte aux lettres locale.
    
## Configuration des stratégies de messagerie vocale pour votre organisation

Transcription de la messagerie vocale est activée par défaut pour toutes les organisations et les utilisateurs ; Toutefois, vous pouvez contrôler il en utilisant les applets de commande [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) et[Grant CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) .
  
> [!IMPORTANT]
> Vous ne pouvez pas créer une nouvelle instance de stratégie de la transcription à l'aide de l'applet de commande **New-CsOnlineVoiceMailPolicy**, et vous ne pouvez pas supprimer une instance de stratégie existante à l'aide de l'applet de commande **Remove-CsOnlineVoiceMailPolicy**.
  
Vous pouvez gérer les paramètres de transcription pour vos utilisateurs à l'aide de stratégies de messagerie vocale. Pour afficher toutes les instances de stratégie de messagerie vocale disponible, vous pouvez utiliser la [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx)[]()applet de commande.
  
 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### Désactivation de la transcription pour votre organisation

Étant donné que le paramètre par défaut de la transcription est activée pour votre organisation, vous souhaiterez peut-être désactivez-le à l'aide [Jeu CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Pour ce faire, exécutez :
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### Désactivation de la transcription pour un utilisateur

Les stratégies utilisateur sont évaluées avant les paramètres par défaut d'organisation. Par exemple, si la transcription de la messagerie vocale est activée pour l'ensemble de vos utilisateurs, vous pouvez affecter une stratégie pour désactiver la transcription pour un utilisateur spécifique à l'aide de l'applet de commande [Grant CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) .
  
Pour désactiver la transcription pour un utilisateur unique, exécutez :
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Le service de messagerie vocale d'Office 365 met en cache les stratégies de messagerie vocale et actualise le cache toutes les 4 heures. Ainsi, jusqu'à 4 heures peuvent être nécessaires pour que les modifications de stratégies soient appliquées. 
  
## Aider vos utilisateurs à découvrir les fonctionnalités de messagerie vocale de Skype Entreprise

Nous avons des informations sur la formation et des articles pour aider vos utilisateurs à réussir avec la messagerie vocale Skype Entreprise. Faire pointer vers les articles suivants :
  
- [Consultation de la messagerie vocale et des options de Skype Entreprise](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): cet article explique comment écouter votre messagerie vocale dans Skype entreprise, modifier votre message d'accueil vocal, modifier vos paramètres de messagerie vocale et écouter votre messagerie vocale à des vitesses différentes.
    
- [Formation Skype Entreprise 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## Rubriques connexes

[Configurer Skype Entreprise Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Voici ce que vous obtenez avec système téléphonique dans Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system-in-office-365.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

