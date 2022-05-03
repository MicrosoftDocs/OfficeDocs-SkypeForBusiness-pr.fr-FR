---
title: Cortana l’assistance vocale dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Découvrez comment utiliser l’assistance vocale Cortana avec Teams
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f888e36d9c0cdd19a0fdd8184d72eeee5ad2a45
ms.sourcegitcommit: 9f7372f7568b4275169590510d2b7a0c0ad7577b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "65171700"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana assistance vocale dans Teams

> [!Note]
> Cortana’assistance vocale est prise en charge dans Microsoft Teams applications mobiles pour iOS et Android et Microsoft Teams affiche pour les utilisateurs des États-Unis, du Royaume-Uni, du Canada, de l’Inde et de l’Australie. Salles Microsoft Teams sur Windows est prise en charge uniquement pour les appareils dont les paramètres régionaux sont définis sur en-us. Cortana assistance vocale n’est actuellement pas disponible pour les locataires Cloud de la communauté du secteur public, Cloud de la communauté du secteur public-High, DoD et non-US EDU. Cortana assistance vocale dans l’application mobile Teams est désormais disponible pour les clients edu en-US. L’expansion vers d’autres langues et régions se produira dans le cadre des versions ultérieures.


Cortana l’assistance vocale dans l’application mobile Teams, sur Salles Microsoft Teams sur Windows et sur Microsoft Teams périphériques d’affichage activent Microsoft 365 Entreprise  pour simplifier la communication, la collaboration et les tâches liées aux réunions à l’aide d’un langage naturel parlé. Les utilisateurs peuvent parler à Cortana en sélectionnant le bouton du microphone situé en haut à droite de l’application mobile Teams, ou en disant « Cortana » dans la salle Microsoft Teams ou lors de l’utilisation d’un affichage Microsoft Teams. Pour se connecter rapidement avec leur équipe mains libres et en déplacement, les utilisateurs peuvent dire des requêtes telles que « appeler Megan » ou « envoyer un message à ma prochaine réunion ». Les utilisateurs peuvent également participer à des réunions en disant « Participer à ma prochaine réunion » et utiliser l’assistance vocale pour partager des fichiers, vérifier leur calendrier, etc. Ces expériences d’assistance vocale sont fournies à l’aide [de Cortana services de niveau entreprise](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) qui sont entièrement conformes aux promesses de confidentialité, de sécurité et de conformité de Office 365, comme indiqué dans les [conditions des services en ligne (OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

## <a name="admin-control-and-limitations"></a>Contrôle et limitations de l’administrateur

Cortana assistance vocale dans Teams est fournie à l’aide de services entièrement conformes aux Office 365 promesses de confidentialité, de sécurité et de conformité au niveau de l’entreprise, comme indiqué dans les conditions des services en ligne (OST). La fonctionnalité est activée par défaut pour les locataires.

Les administrateurs de locataire peuvent contrôler qui dans leur locataire peut utiliser Cortana assistance vocale dans Teams à l’aide d’une stratégie (TeamsCortanaPolicy). Cette stratégie est définie au niveau du compte d’utilisateur ou du locataire. Les administrateurs peuvent utiliser le champ CortanaVoiceInvocationMode dans ce contrôle de stratégie pour déterminer si Cortana est désactivé, activé uniquement avec l’appel de bouton d’activation ou avec l’appel de mot de sortie (applicable aux appareils qui le prennent en charge, comme l’affichage Microsoft Teams).

Les administrateurs peuvent utiliser les applets de commande PowerShell suivantes pour gérer cette stratégie (la stratégie n’est actuellement pas disponible dans Microsoft Teams centre d’administration).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Par exemple, la commande ci-dessous crée une stratégie nommée « EmployeeCortanaPolicy », où Cortana assistance vocale dans Microsoft Teams est désactivée.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Cet exemple montre la mise à jour d’une stratégie existante nommée « EmployeeCortanaPolicy » et l’activation de l’assistance vocale Cortana dans Microsoft Teams avec l’appel de boutons d’envoi uniquement. Les utilisateurs pourront appeler Cortana en sélectionnant le bouton de micro Cortana dans Teams. L’appel « Hey Cortana » ou « Cortana ») est désactivé.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Cet exemple montre la mise à jour de la stratégie et l’activation de l’assistance vocale Cortana avec le bouton Push et l’appel de mot de sortie.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

À l’époque, de la version initiale pour Microsoft 365 Entreprise utilisateurs aux États-Unis en anglais, les fonctions suivantes sont disponibles :

- L’application mobile Teams ne prend pas en charge l’activation de wake word, mais elle sera prise en charge à l’avenir.  

- Salles Microsoft Teams sur les appareils d’affichage Windows et Microsoft Teams prendront en charge l’activation du mot de sortie de veille.

## <a name="user-control"></a>Contrôle utilisateur

Les utilisateurs individuels peuvent essayer Cortana assistance vocale sur différents appareils :

- Sélectionnez le bouton microphone dans l’application mobile Teams.

- Sélectionnez le bouton microphone ou dites « Cortana » dans Salles Microsoft Teams.

- Dites « Cortana » sur Microsoft Teams affiche les appareils.

Vous pouvez contrôler si Cortana dans Teams est activé pour votre appareil à l’aide d’un paramètre dans l’appareil.

![affiche la progression des fenêtres mobiles lorsque vous activez Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Salles Microsoft Teams sur Windows

L’apport de modifications au niveau de l’appareil est disponible uniquement si Cortana est activé au niveau du locataire. 

Au niveau de l’appareil, vous pouvez configurer Cortana à utiliser de deux manières différentes. Vous pouvez activer l’une ou l’autre option, ou les deux en même temps : 
- En appuyant sur un microphone, qui est appelé Cortana _Pousser pour parler_
- En disant « Hey, Cortana », qui est appelé _Cortana Activation vocale_

Cortana _push to talk_ est activé par défaut si votre salle est configurée avec l’une des langues suivantes : en-au (Australie), en-ca (Canada), en-gb (Royaume-Uni), en-in (Inde), en-us (États-Unis). [Pour en savoir plus.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana icône déplace le bouton _Présenter_ sous _Plus..._ dans votre console Teams Room. Pour désactiver Cortana _Push to talk_, utilisez PowerShell.[ Pour en savoir plus.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Pour activer Cortana _Activation vocale_, ces conditions doivent être remplies :
- un appareil certifié Cortana doit être connecté à votre Teams Room. Vous trouverez la liste des appareils certifiés à la fin de cet article.
- le Teams Room doit être configuré avec l’une des langues suivantes : en-au (Australie), en-ca (Canada), en-gb (Royaume-Uni), en-in (Inde), en-us (États-Unis). D’autres langues seront disponibles ultérieurement.
- l’une des modifications de configuration suivantes doit être apportée :
  - Activez la fonctionnalité dans Teams centre d’administration [En savoir plus.](/microsoftteams/rooms/rooms-manage)
  - ajoutez l’attribut XML suivant au fichier XML SkypeSettings :

    ```xml
    <SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
    </SkypeSettings> 
    ```
    
Au niveau de la réunion, les modifications sont disponibles uniquement si Cortana _activation vocale_ est activée au niveau de l’appareil.  Pour activer Cortana _activation vocale_ pendant une **réunion,** activez ou **désactivez** le bouton bascule pour désactiver. Une fois la réunion terminée, Cortana revient aux paramètres définis au niveau de l’appareil.


Les modifications apportées au niveau de la réunion sont disponibles si Cortana est activé au niveau de l’appareil.

Pour activer Cortana _activation vocale_ pendant une réunion, déplacez le bouton bascule **activé** ou **désactivé**. Une fois la réunion terminée, Cortana revient aux paramètres définis au niveau de l’appareil.


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana des appareils certifiés pour salles Teams
Cortana _l’activation vocale_ peut être activée si vous utilisez un Lenovo Hub 500 ou si l’un de ces appareils est connecté à votre salle :
- Jabra Panacast 50 
- Microphones de rallye
- Barre vidéo Bose VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech  

