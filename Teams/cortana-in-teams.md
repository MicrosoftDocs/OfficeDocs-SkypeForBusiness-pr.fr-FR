---
title: Assistance vocale Cortana dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
- chat-teams-channels-revamp
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f8070644139ebd32157693e941e3206a4e90cdad
ms.sourcegitcommit: 84a832330c0a9f9fb818bbfb22e534fe035c1837
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2023
ms.locfileid: "69693397"
---
# <a name="cortana-voice-assistance-in-teams"></a>Assistance vocale Cortana dans Teams

> [!NOTE]
> L’assistance vocale Cortana est prise en charge dans les applications mobiles Microsoft Teams pour iOS et Android, les affichages Microsoft Teams et les Salles Microsoft Teams sur Windows pour les utilisateurs du États-Unis, du Royaume-Uni, du Canada, de l’Inde et de l’Australie. L’assistance vocale Cortana dans l’application mobile Teams est désormais disponible pour les clients EDU en-US. L’extension à d’autres langues et régions se produira dans le cadre des versions ultérieures. L’assistance vocale Cortana n’est actuellement pas disponible pour les locataires GCC, GCC-High, DoD et non-US EDU.

L’assistance vocale Cortana dans l’application mobile Teams, sur Salles Microsoft Teams sur Windows et sur les appareils d’affichage Microsoft Teams permet aux utilisateurs Microsoft 365 Entreprise de simplifier la communication, la collaboration et les tâches liées aux réunions à l’aide du langage naturel parlé. Les utilisateurs peuvent parler à Cortana en sélectionnant le bouton de microphone situé dans le coin supérieur droit de l’application mobile Teams, ou en disant « Cortana » dans la salle Microsoft Teams ou lors de l’utilisation d’un affichage Microsoft Teams. Pour se connecter rapidement à leur équipe en mode mains libres et en déplacement, les utilisateurs peuvent dire des requêtes telles que « appeler Megan » ou « envoyer un message à ma prochaine réunion ». Les utilisateurs peuvent également participer à des réunions en disant « participer à ma prochaine réunion » et utiliser l’assistance vocale pour partager des fichiers, consulter leur calendrier, etc. Ces expériences d’assistance vocale sont fournies à l’aide de [services d’entreprise Cortana](/microsoft-365/admin/misc/cortana-integration) qui sont entièrement conformes aux promesses de confidentialité, de sécurité et de conformité de Office 365, comme indiqué dans les [Conditions des services en ligne (OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true)

## <a name="admin-control-and-limitations"></a>contrôle Administration et limitations

L’assistance vocale Cortana dans Teams est fournie à l’aide de services entièrement conformes à la Office 365 promesses de confidentialité, de sécurité et de conformité au niveau de l’entreprise, comme indiqué dans les Conditions des services en ligne (OST). La fonctionnalité sera activée par défaut pour les locataires.

Les administrateurs de locataire peuvent contrôler qui dans leur locataire peut utiliser l’assistance vocale Cortana dans Teams à l’aide d’une stratégie (TeamsCortanaPolicy). Cette stratégie est définie au niveau du compte d’utilisateur ou du locataire. Les administrateurs peuvent utiliser le champ CortanaVoiceInvocationMode au sein de ce contrôle de stratégie pour déterminer si Cortana est désactivée, activée avec un appel de bouton poussoir uniquement ou avec un appel de mot de veille (applicable aux appareils qui la prennent en charge, comme l’affichage Microsoft Teams).

Les administrateurs peuvent utiliser les applets de commande PowerShell suivantes pour gérer cette stratégie (la stratégie n’est actuellement pas disponible dans le Centre d’administration Microsoft Teams).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Par exemple, la commande ci-dessous crée une stratégie nommée « EmployeeCortanaPolicy » où l’assistance vocale Cortana dans Microsoft Teams est désactivée.

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Cet exemple montre la mise à jour d’une stratégie existante nommée « EmployeeCortanaPolicy » et l’activation de l’assistance vocale Cortana dans Microsoft Teams avec un appel par bouton pousseur uniquement. Les utilisateurs pourront appeler Cortana en sélectionnant le bouton de micro Cortana dans Teams. L’appel du mot de veille (« Hey Cortana » ou « Cortana ») sera désactivé.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Cet exemple montre la mise à jour de la stratégie et l’activation de l’assistance vocale Cortana avec un bouton poussillon et un appel de mot de veille. (L’activation wake word est prise en charge pour les utilisateurs Microsoft 365 Entreprise aux États-Unis pour l’application mobile Teams, Salles Microsoft Teams sur Windows et l’affichage Microsoft Teams dont la langue est définie sur l’anglais.)

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

## <a name="user-control"></a>Contrôle utilisateur

Les utilisateurs individuels peuvent essayer l’assistance vocale Cortana sur différents appareils :

- Sélectionnez le bouton microphone dans l’application mobile Teams.

- Sélectionnez le bouton du microphone ou dites « Cortana » dans Salles Microsoft Teams.

- L’option « Cortana » sur Microsoft Teams affiche les appareils.

Vous pouvez contrôler si Cortana dans Teams est activée pour votre appareil à l’aide d’un paramètre dans l’appareil.

![montre la progression des fenêtres mobiles lorsque vous activez Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Salles Microsoft Teams sur Windows

Les modifications apportées au niveau de l’appareil sont disponibles uniquement si Cortana est activée au niveau du locataire.

Au niveau de l’appareil, vous pouvez configurer Cortana pour qu’elle soit utilisée de deux manières différentes. Vous pouvez activer l’une ou l’autre option, ou les deux en même temps :

- En appuyant sur un microphone, appelé _Cortana Push pour parler_
- En disant « Hey, Cortana », ce qui s’appelle _Cortana Voice Activation_

Cortana _Push to Talk_ est activé par défaut si votre salle est configurée avec l’une des langues suivantes : en-au (Australie), en-ca (Canada), en-gb (Royaume-Uni), en-in (Inde), en-us (États-Unis). [Pour en savoir plus.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) L’icône Cortana déplace le bouton _Présenter_ sous le menu _Plus..._ de votre console Salle Teams. Pour désactiver Cortana _Push to Talk,_ utilisez PowerShell. [Pour en savoir plus.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1&preserve-view=true)

Pour activer _l’activation vocale de_ Cortana, ces conditions doivent être remplies :

- un appareil certifié Cortana doit être connecté à votre salle Teams. Vous trouverez la liste des appareils certifiés à la fin de cet article.
- La salle Teams doit être configurée avec l’une des langues suivantes : en-au (Australie), en-ca (Canada), en-gb (Royaume-Uni), en-in (Inde), en-us (États-Unis). D’autres langues seront disponibles ultérieurement.
- l’une des modifications de configuration suivantes doit être apportée :
  - activez la fonctionnalité dans le Centre d’administration Teams [En savoir plus.](/microsoftteams/rooms/rooms-manage)
  - ajoutez l’attribut XML suivant au fichier XML SkypeSettings :

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

Au niveau de la réunion, l’apport de modifications n’est disponible que si _l’activation vocale_ cortana est activée au niveau de l’appareil.  Pour activer _l’activation vocale_ de Cortana pendant une réunion, déplacez le bouton bascule **Activé** ou **Désactivé** pour désactiver. Une fois la réunion terminée, Cortana revient aux paramètres définis au niveau de l’appareil.

Les modifications apportées au niveau de la réunion sont disponibles si Cortana est activée au niveau de l’appareil.

Pour activer _l’activation vocale_ de Cortana pendant une réunion, déplacez le bouton bascule **Activé** ou **Désactivé**. Une fois la réunion terminée, Cortana revient aux paramètres définis au niveau de l’appareil.

## <a name="cortana-certified-devices-for-teams-rooms"></a>Appareils certifiés Cortana pour salles Teams

_L’activation vocale_ Cortana peut être activée si vous utilisez un Lenovo Hub 500 ou si vous avez l’un de ces appareils connectés à votre salle :

- Jabra Panacast 50
- Système de conférence Logi Rally Plus
- Barre vidéo Bose VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech
