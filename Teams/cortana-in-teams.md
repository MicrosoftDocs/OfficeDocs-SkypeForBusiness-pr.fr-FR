---
title: Cortana’assistance vocale dans Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 45d2112dc7b81d72ccffcb8b4f04471b629d52a1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633398"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana’assistance vocale dans Teams

> [!Note]
> Cortana l’assistance vocale est prise en charge dans les applications mobiles Microsoft Teams pour iOS et Android et les écrans Microsoft Teams pour les utilisateurs aux États-Unis, au Royaume-Uni, au Canada, en Inde et en Australie. Salles Microsoft Teams sur Windows est uniquement pris en charge pour les utilisateurs aux États-Unis. Cortana’assistance vocale vocale n’est actuellement pas disponible pour les Cloud de la communauté du secteur public, Cloud de la communauté du secteur public-Haut, DoD et les locataires EDU autres que les États-Unis. Cortana’assistance vocale dans l’Teams mobile est désormais disponible pour les clients EDU en France. Une extension vers d’autres langues et régions sera mise en place dans le cadre des prochaines publication.

> [!Note]
> Cortana’assistance vocale dans Salles Microsoft Teams est publiée sous Aperçu. Dans sa version d’Cortana, cette fonction est prise en charge uniquement aux États-Unis avec la langue EN-US sur les appareils qui ont des micros Microphones Microphones Connectés.

Cortana’assistance vocale dans l’application mobile Teams, sur Salles Microsoft Teams sur Windows et sur les périphériques d’affichage Microsoft Teams permet aux utilisateurs de Microsoft 365 Entreprise de rationaliser les tâches de communication, de collaboration et de réunion en utilisant le langage naturel parlé. Les utilisateurs peuvent parler à Cortana en sélectionnant le bouton de microphone situé dans le coin supérieur droit de l’application mobile Teams, ou en disant &#8220;Cortana&#8221; dans la salle Microsoft Teams ou lors de l’utilisation d’un écran Microsoft Teams' Pour communiquer rapidement avec leur équipe en mains libres et en cours, les utilisateurs peuvent répondre à des requêtes telles que &#8220;appeler&#8221; ou &#8220;envoyer un message à mon prochain&#8221;. Les utilisateurs peuvent également participer à des réunions en &#8220;participer à ma prochaine&#8221; réunion et utiliser l’assistance vocale pour partager des fichiers, consulter leur calendrier et bien plus encore. Ces expériences d’assistance vocale sont tenues à l’aide de [services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) Cortana de niveau entreprise qui respectent pleinement les promesses de confidentialité, de sécurité et de conformité de Office 365, comme le reflètent les conditions des services en ligne [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

## <a name="admin-control-and-limitations"></a>Contrôle et limitations de l’administrateur

Cortana’assistance vocale dans Teams est livrée à l’aide de services qui respectent pleinement les promesses de confidentialité, de sécurité et de conformité au niveau Office 365 au niveau de l’entreprise, comme indiqué dans les conditions des services en ligne (OST). La fonctionnalité sera activée par défaut pour les locataires.

Les administrateurs des locataires peuvent contrôler qui dans leur client peut utiliser Cortana’assistance vocale dans Teams à l’aide d’une stratégie (TeamsCortanaPolicy). Cette stratégie est définie au niveau du compte d’utilisateur ou du client. Les administrateurs peuvent utiliser le champ CortanaVoiceInvocationMode au sein de ce contrôle de stratégie pour déterminer si Cortana est désactivé, activé avec l’appel du bouton d’appel uniquement ou avec l’appel de mot de sortie (applicable aux appareils qui le supportent, comme l’affichage Microsoft Teams).

Les administrateurs peuvent utiliser les cmdlets PowerShell suivantes pour gérer cette stratégie (la stratégie n’est actuellement pas disponible dans Microsoft Teams centre d’administration).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Par exemple, la commande ci-dessous crée une stratégie avec le nom &#8220;EmployeeCortanaPolicy&#8221; où l’assistance vocale Cortana dans Microsoft Teams est désactivée.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Cet exemple illustre la mise à jour d’une stratégie existante avec le nom &#8220;EmployeeCortanaPolicy&#8221; et l’activation de l’assistance vocale Cortana dans Microsoft Teams avec appel push-button uniquement. Les utilisateurs pourront appeler Cortana en sélectionnant le bouton Cortana micro dans Teams. Le mot de veille (&#8220;Hey Cortana&#8221; ou &#8220;Cortana&#8221;) appel est désactivé.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Cet exemple illustre la mise à jour de la stratégie et l’activation Cortana’assistance vocale avec le bouton Push et l’appel de word de veille.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

À l’heure de la publication initiale pour Microsoft 365 Entreprise utilisateurs aux États-Unis en anglais, les fonctions suivantes sont disponibles :

- L Teams’application mobile ne prendra pas en charge l’activation de word de veille, mais elle sera prise en charge à l’avenir.  

- Salles Microsoft Teams sur les Windows’affichage Microsoft Teams’écran de veille 365 365 665 365 365 365 365 365 365 367 567

## <a name="user-control"></a>Contrôle de l’utilisateur

Les utilisateurs individuels peuvent essayer Cortana’assistance vocale sur différents appareils :

- Sélectionnez le bouton microphone dans l’Teams’application mobile.

- Sélectionnez le bouton du microphone ou dites « Cortana » dans Salles Microsoft Teams.

- Dites « Cortana » sur Microsoft Teams affiche les appareils.

Vous pouvez contrôler si le Cortana dans Teams est activé pour votre appareil à l’aide d’un paramètre de l’appareil.

![montre la progression des fenêtres mobiles lorsque vous activez Cortana](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Salles Microsoft Teams sur Windows

Apporter des modifications au niveau de l’appareil est disponible si Cortana est activé au niveau du client. Cortana sont publiées par défaut.

Pour activer Cortana au niveau de l’appareil, ces attributs XML doivent être ajoutés au fichier XML SkypeSettings :

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Apporter des modifications au niveau de la réunion est disponible si Cortana est activé au niveau de l’appareil.

Pour activer Cortana’assistance vocale pendant une réunion, déplacez le **basculement activé** ou **non.** Une fois la réunion terminée, Cortana à la définition des paramètres au niveau de l’appareil.
