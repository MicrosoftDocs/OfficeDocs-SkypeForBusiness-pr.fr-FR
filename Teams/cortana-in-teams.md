---
title: Cortana’assistance vocale dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Découvrez comment utiliser Cortana’assistance vocale avec Teams
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
ms.openlocfilehash: 967586ecfb9d29ab5b99725e2873a9d29d01e3bd
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62403598"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana’assistance vocale dans Teams

> [!Note]
> Cortana l’assistance vocale est prise en charge dans les applications mobiles Microsoft Teams pour iOS et Android et les écrans Microsoft Teams pour les utilisateurs aux États-Unis, au Royaume-Uni, au Canada, en Inde et en Australie. Salles Microsoft Teams sur Windows n’est pris en charge que pour les appareils dont les paramètres régionaux sont définies sur fr-FR. Cortana’assistance vocale vocale n’est actuellement pas disponible pour les Cloud de la communauté du secteur public, Cloud de la communauté du secteur public-Haut, DoD et les locataires EDU autres que les États-Unis. Cortana’assistance vocale dans l’Teams mobile est désormais disponible pour les clients EDU en France. Une extension vers d’autres langues et régions sera mise en place dans le cadre des prochaines publication.


Cortana’assistance vocale dans l’application mobile Teams, sur Salles Microsoft Teams sur Windows et sur Microsoft Teams périphériques d’affichage activent Microsoft 365 Entreprise  les utilisateurs afin de simplifier la communication, la collaboration et les tâches liées aux réunions à l’aide du langage naturel parlé. Les utilisateurs peuvent parler à Cortana en sélectionnant le bouton du microphone situé dans le coin supérieur droit de l’application mobile Teams, ou en disant « Cortana » dans la salle Microsoft Teams ou lors de l’utilisation d’un écran Microsoft Teams' Pour communiquer rapidement avec leur équipe en mains libres et en cours, les utilisateurs peuvent envoyer des requêtes, telles que « Appeler Megan » ou « envoyer un message à ma prochaine réunion ». Les utilisateurs peuvent également participer à des réunions en disant « Rejoindre ma prochaine réunion » et utiliser l’assistance vocale pour partager des fichiers, consulter leur calendrier, etc. Ces expériences d’assistance vocale sont tenues à l’aide de [services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) Cortana de niveau entreprise qui respectent pleinement les promesses de confidentialité, de sécurité et de conformité de Office 365, comme le reflètent les conditions des services en ligne [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

## <a name="admin-control-and-limitations"></a>Contrôle et limitations de l’administrateur

Cortana’assistance vocale dans Teams est livrée à l’aide de services qui respectent pleinement les promesses de confidentialité, de sécurité et de conformité au niveau Office 365 au niveau de l’entreprise, comme indiqué dans les conditions des services en ligne (OST). La fonctionnalité sera activée par défaut pour les locataires.

Les administrateurs des locataires peuvent contrôler qui dans leur client peut utiliser Cortana’assistance vocale dans Teams à l’aide d’une stratégie (TeamsCortanaPolicy). Cette stratégie est définie au niveau du compte d’utilisateur ou du client. Les administrateurs peuvent utiliser le champ CortanaVoiceInvocationMode au sein de ce contrôle de stratégie pour déterminer si Cortana est désactivé, activé avec l’appel du bouton d’appel uniquement ou avec l’appel de mot de sortie (applicable aux appareils qui le supportent, comme l’affichage Microsoft Teams).

Les administrateurs peuvent utiliser les cmdlets PowerShell suivantes pour gérer cette stratégie (la stratégie n’est actuellement pas disponible dans Microsoft Teams centre d’administration).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Par exemple, la commande ci-dessous crée une stratégie avec le nom « EmployeeCortanaPolicy » dans laquelle l’assistance vocale Cortana dans Microsoft Teams est désactivée.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Cet exemple illustre la mise à jour d’une stratégie existante avec le nom « EmployeeCortanaPolicy » et l’activation de l Cortana’assistance vocale dans Microsoft Teams avec appel du bouton d’appel uniquement. Les utilisateurs pourront appeler Cortana en sélectionnant le bouton Cortana micro dans Teams. Le mot de veille (« Hey Cortana » ou « Cortana ») appel est désactivé.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Cet exemple illustre la mise à jour de la stratégie et l’activation Cortana’assistance vocale avec le bouton Push et l’appel de word de veille.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

À l’heure de la publication initiale Microsoft 365 Entreprise utilisateurs aux États-Unis en anglais, les fonctions suivantes sont disponibles :

- L Teams’application mobile ne prendra pas en charge l’activation de word de veille, mais elle sera prise en charge à l’avenir.  

- Salles Microsoft Teams sur les Windows’affichage Microsoft Teams’écran de veille 365 365 365 365 365 365 365 365 365 367 365 467

## <a name="user-control"></a>Contrôle de l’utilisateur

Les utilisateurs individuels peuvent essayer Cortana’assistance vocale sur différents appareils :

- Sélectionnez le bouton microphone dans l’Teams’application mobile.

- Sélectionnez le bouton du microphone ou dites « Cortana » dans Salles Microsoft Teams.

- Dites « Cortana » sur Microsoft Teams affiche les appareils.

Vous pouvez contrôler si le Cortana dans Teams est activé pour votre appareil à l’aide d’un paramètre de l’appareil.

![montre la progression des fenêtres mobiles lorsque vous activez Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Salles Microsoft Teams sur Windows

Les modifications apportées au niveau de l’appareil sont disponibles uniquement si Cortana est activé au niveau du client. 

Au niveau de l’appareil, vous pouvez configurer Cortana à utiliser de deux manières différentes. Vous pouvez activer l’une ou l’autre des options, ou les deux en même temps : 
- En appuyant sur un microphone, Cortana _appuyer pour parler_
- En disant « Bonjour, Cortana », Cortana _activation vocale_

Cortana Push _to talk_ est activé par défaut si votre salle est définie avec l’une des langues suivantes : en-au (Australia), en-ca (Canada), en-gb (Royaume-Uni), en-in (Inde), en-us (États-Unis). [Pour en savoir plus.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana’icône va remplacer le _bouton_ Présenter sous _l’icône Plus..._ dans votre console Teams de salle. Pour désactiver Cortana _Appuyez pour parler et_ utiliser PowerShell.[ Pour en savoir plus.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Pour activer Cortana _activation vocale_, les conditions ci-après doivent être remplies :
- un Cortana certifié doit être connecté à votre salle Teams réunion. Une liste des périphériques certifiés est à la fin de cet article.
- La salle Teams doit être définie avec l’une des langues suivantes : en-au (Australia), en-ca (Canada), en-gb (Royaume-Uni), en-in (Inde), en-us (États-Unis). D’autres langues seront disponibles ultérieurement.
- Une des modifications de configuration suivantes doit être apportée :
  - activer la fonctionnalité dans Teams centre d’administration [En savoir plus.](/microsoftteams/rooms/rooms-manage)
  - ajoutez l’attribut XML suivant au fichier XML SkypeSettings :

    ```xml
    <SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
    </SkypeSettings> 
    ```
    
Au niveau de la réunion, apporter des modifications est disponible uniquement Cortana _activation_ de la voix est activée au niveau de l’appareil.  Pour activer Cortana _activation vocale_ pendant une **réunion,** activez ou désactivez **le bouton** bascule. Une fois la réunion terminée, Cortana à la définition des paramètres au niveau de l’appareil.


Apporter des modifications au niveau de la réunion est disponible si Cortana est activé au niveau de l’appareil.

Pour activer Cortana _activation vocale_ pendant une réunion, activez ou désactivation le bouton **bascule**. Une fois la réunion terminée, Cortana à la définition des paramètres au niveau de l’appareil.


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana certifiés pour l’salles Teams
Cortana _activation_ vocale peut être activée si vous utilisez un Lenovo Hub 500 ou si l’un de ces appareils est connecté à votre salle :
- JabraCast 50 
- Microphones microphones microphones
- Bose Video Bar VB1

