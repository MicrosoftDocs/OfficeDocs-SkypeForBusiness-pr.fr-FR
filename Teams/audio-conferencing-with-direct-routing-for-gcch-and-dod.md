---
title: Audioconférence avec routage direct, GCCH et DoD
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Administration pouvez en savoir plus sur l’utilisation de l’audioconférence avec le routage direct dans les environnements GCCH et DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd467b9da8d296c21d4a0405d651bbaa6b001fd3
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641775"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audioconférence avec routage direct pour GCC High et DoD

L’audioconférence avec routage direct pour GCC High et DoD permet aux participants de rejoindre des réunions Teams dans votre organisation GCC High ou DoD à l’aide d’un appareil téléphonique. Les participants à la réunion peuvent préférer utiliser un appareil téléphonique pour participer à des réunions Teams dans des scénarios tels que lorsque la connectivité Internet est limitée ou lorsque les utilisateurs sont sur la route et n’ont pas accès à Teams. Les participants peuvent choisir de participer à des réunions en se rendant à un numéro de téléphone rendez-vous pour votre organisation ou en faisant en sorte que la réunion soit rendez-vous sur leur appareil téléphonique.

Avec l’audioconférence avec routage direct pour GCC High et DoD, votre organisation utilise ses propres numéros comme numéros de téléphone rendez-vous et tous les appels de réunion vers des appareils téléphoniques sont routés via le routage direct. Pour activer le service, les organisations doivent configurer le routage direct et configurer des numéros de téléphone qui peuvent être utilisés comme numéros de téléphone entrants. L’obligation d’utiliser le routage direct est différente du service d’audioconférence offert aux organisations non GCC High et non DoD où les numéros de téléphone rendez-vous sont fournis par Microsoft.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Déployer l’audioconférence avec le routage direct pour GCC High et DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Étape 1 : Obtenir l’audioconférence avec le routage direct pour les licences GCC High ou DoD

Pour utiliser l’audioconférence dans GCC High ou DoD, votre organisation et les utilisateurs de votre organisation doivent disposer d’une audioconférence avec une licence de routage direct affectée. Voici les licences dont vous avez besoin pour activer l’audioconférence avec le routage direct pour GCC High ou DoD.

- GCC High : Une licence d’audioconférence - GCC High Tenant pour votre organisation et audioconférence - Licences GCC High pour vos utilisateurs.

- DoD : Audioconférence - Licence de locataire DoD pour votre organisation et audioconférence - Licences DoD pour vos utilisateurs.

Une licence de locataire et au moins une licence utilisateur sont nécessaires pour activer le service. Vous ne pouvez pas activer le service uniquement avec la licence client ou uniquement avec des licences utilisateur. Pour obtenir des licences de service pour votre locataire et les utilisateurs de votre organisation, contactez votre équipe de compte.

> [!IMPORTANT]
> Les utilisateurs ne peuvent pas être activés pour l’audioconférence avec routage direct tant que les numéros de téléphone rendez-vous ne sont pas configurés. Nous vous recommandons de ne pas attribuer d’audioconférence avec routage direct pour les licences GCC High ou DoD aux utilisateurs tant que vous n’avez pas configuré les numéros de téléphone rendez-vous comme indiqué dans cet article.  Si vous ne suivez pas ces instructions, le pavé de numérotation risque d’être complètement manquant dans le client Teams.

### <a name="step-2-set-up-direct-routing"></a>Étape 2 : Configurer le routage direct

Pour configurer le routage direct, consultez les articles suivants :

- [Planifier le routage direct](direct-routing-plan.md)

- [Configurer le routage direct](direct-routing-configure.md)

> [!NOTE]
> Lorsque vous configurez le routage direct, n’oubliez pas d’utiliser les noms de domaine complets et les ports GCC High ou DoD décrits dans ces deux articles.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Étape 3 : Configurer des numéros de téléphone rendez-vous

Les numéros de téléphone entrants sont les numéros de téléphone associés à votre pont d’audioconférence. Ces numéros sont utilisés par les participants pour participer aux réunions planifiées par les utilisateurs de votre organisation. Ces numéros sont également inclus dans les invitations aux réunions des utilisateurs qui planifient des réunions dans votre organisation et sur la page « Rechercher un numéro local ».

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Définir des numéros de téléphone de service dans votre locataire

Vous pouvez utiliser l’applet de commande PowerShell New-csHybridTelephoneNumber pour définir des numéros de téléphone de service dans votre locataire qui peuvent être utilisés pour acheminer les appels vers le service d’audioconférence via le routage direct.

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Par exemple :

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Affecter les numéros de téléphone du service au pont d’audioconférence de votre organisation

Vous pouvez affecter des numéros de téléphone de service au pont d’audioconférence de votre organisation à l’aide de l’applet de commande PowerShell Register-csOnlineDialInConferencingServiceNumber.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Vous pouvez voir l’ID de votre pont d’audioconférence à l’aide de Get-CsOnlineDialInConferencingBridge. Par exemple :

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Étape 4 : Définir une stratégie globale de routage vocal pour permettre le routage des appels sortants à partir de réunions

Le routage des appels sortants effectués au rtc à partir de réunions organisées par les utilisateurs de votre organisation est défini par la stratégie globale de routage vocal de votre organisation. Si votre organisation a une stratégie de routage vocal globale définie, vérifiez que la stratégie globale de routage vocal autorise les appels sortants vers le rtc qui sont censés être lancés à partir de réunions organisées par les utilisateurs de votre organisation. Si aucune stratégie de routage vocal globale n’est définie dans votre organisation, vous devez en définir une pour activer le routage des appels sortants vers le rtc à partir de réunions organisées par les utilisateurs de votre organisation. Notez que la stratégie de routage vocal global de votre organisation s’applique également aux appels un-à-un effectués au RTC par les utilisateurs de votre organisation. Si les appels un-à-un au RTC sont activés pour les utilisateurs de votre organisation, assurez-vous que la stratégie de routage vocal global répond aux besoins de votre organisation pour les deux types d’appels.

> [!NOTE]
> Location-Based routage n’est pas disponible dans les déploiements Cloud de la communauté microsoft 365 Government (GCC) High ou DoD. Lors de l’activation de l’audioconférence, vérifiez qu’aucun utilisateur d’audioconférence dans les environnements GCC High ou DoD n’est activé pour le routage Location-Based.

#### <a name="defining-a-global-voice-routing-policy"></a>Définition d’une stratégie globale de routage vocal

Une stratégie globale de routage vocal peut être définie en définissant une utilisation RTC, un itinéraire vocal, une stratégie de routage vocal et en affectant la nouvelle stratégie de routage vocal comme stratégie globale de routage vocal de votre organisation.

Les étapes suivantes décrivent comment définir une nouvelle stratégie globale de routage vocal pour une organisation sans une seule. Si des stratégies de routage vocal sont déjà définies dans votre organisation, vérifiez que la configuration suivante n’est pas en conflit avec les stratégies de routage vocale existantes de votre organisation.

Pour créer une utilisation RTC dans une session PowerShell distante dans Teams, utilisez la commande suivante :

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Pour plus d’informations, consultez [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).

Pour créer un itinéraire vocal, utilisez la commande suivante :

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Lors de la définition d’un nouvel itinéraire vocal pour votre organisation, spécifiez une ou plusieurs des passerelles RTC en ligne PSTN qui ont été définies pour votre organisation pendant la configuration du routage direct.

Le modèle de nombre spécifie les appels qui seront acheminés via la liste de passerelles spécifiée en fonction du numéro de téléphone de destination de l’appel. Dans l’exemple ci-dessus, les appels à toutes les destinations dans le monde correspondent à l’itinéraire vocal. Si vous souhaitez limiter les numéros de téléphone qui peuvent être composés à partir des réunions des utilisateurs de votre organisation, vous pouvez modifier le modèle de numéro pour que l’itinéraire vocal corresponde uniquement aux modèles de nombres des destinations autorisées. Notez que s’il n’existe aucun itinéraire vocal qui correspond au modèle de numéro du numéro de téléphone de destination d’un appel donné, l’appel ne sera pas routée.

Pour plus d’informations, consultez [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).

Pour créer une stratégie de routage vocal, utilisez la commande suivante :

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Si plusieurs utilisations RTC sont définies dans la stratégie de routage vocal, elles sont évaluées dans l’ordre dans lequel elles sont définies. Il est recommandé de définir les utilisations RTC dans l’ordre des plus spécifiques aux plus génériques en termes de modèles de nombre des itinéraires vocaux associés aux utilisations RTC. Par exemple, si une utilisation RTC a été définie pour acheminer les appels vers le États-Unis et qu’une autre utilisation rtc a été définie pour acheminer les appels vers n’importe quel autre emplacement dans le monde, l’utilisation rtc pour les appels au États-Unis doit être répertoriée dans la stratégie de routage vocal avant l’utilisation du RTC pour acheminer les appels vers n’importe quel autre emplacement dans le monde.

Pour plus d’informations, consultez [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Pour affecter la nouvelle route vocale à la stratégie globale de routage vocal de votre organisation, utilisez la commande suivante :

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Pour plus d’informations, consultez [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Une fois la stratégie de routage vocal globale définie, tous les appels sortants effectués à partir de réunions organisées par les utilisateurs de votre organisation sont évalués par rapport aux itinéraires vocaux associés aux utilisations RTC de la stratégie globale de routage vocal. Les appels sortants sont routées en fonction de la première route vocale qui correspond au modèle de numéro du numéro de téléphone composé.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Étape 5 : Attribuer l’audioconférence avec routage direct pour les licences GCC High ou DoD à vos utilisateurs

Pour affecter l’audioconférence avec le routage direct pour les licences GCC High ou DoD à votre utilisateur, consultez [Affecter des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Étape 6 : (Facultatif) Afficher la liste des numéros d’audioconférence dans Teams

Pour afficher la liste des numéros d’audioconférence de votre organisation, [accédez à la liste des numéros d’audioconférence dans Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Étape 7 : (Facultatif) Définir les langues du standard automatique pour les numéros de rendez-vous d’audioconférence de votre organisation

Pour modifier les langues des numéros rendez-vous de l’audioconférence de votre organisation, consultez [Définir les langues du standard automatique pour l’audioconférence dans Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Étape 8 : (Facultatif) Modifier les paramètres du pont d’audioconférence de votre organisation

Pour modifier les paramètres du pont d’audioconférence de votre organisation, consultez [Modifier les paramètres d’un pont d’audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Étape 9 : (Facultatif) Définir les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs de votre organisation

Pour modifier l’ensemble des numéros de téléphone inclus dans les invitations aux réunions des utilisateurs est votre organisation, consultez [Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Fonctionnalités d’audioconférence non prises en charge dans l’audioconférence avec routage direct pour GCC High et DoD

Voici les fonctionnalités d’audioconférence qui ne sont pas prises en charge dans l’audioconférence avec routage direct pour GCC High et DoD :

- Notifications d’entrée et de sortie à l’aide de l’enregistrement de noms. Pour l’audioconférence avec routage direct, les notifications d’entrée et de sortie sont lues dans la réunion sous forme de tonalités.

- Désactivez l’utilisation de numéros gratuits pour l’organisateur spécifique des réunions. Les contrôles au niveau de l’utilisateur pour limiter l’utilisation de numéros gratuits pour participer aux réunions de votre organisation ne s’appliquent pas aux appels routées via le routage direct.

- Envoi d’e-mails de notification aux utilisateurs lorsque leurs paramètres changent. Les e-mails de notification d’audioconférence ne sont pas pris en charge pour l’audioconférence avec routage direct pour GCC High et DoD.
