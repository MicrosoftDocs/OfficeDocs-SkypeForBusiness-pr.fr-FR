---
title: Audioconférence avec routage direct, GCCH et DoD
author: LanaChin
ms.author: v-lanac
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
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: L’administrateur peut en savoir plus sur l’utilisation de l’audioconférence avec le routage direct dans les environnements GCCH et DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34fcb84ee0e5126188f47a4ccc231c04ffd093b2
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262491"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audioconférence avec routage direct pour GCC High et DoD

Les conférences audio avec le routage direct de GCC High et DoD permettent aux participants de participer à des réunions d’équipes au sein de votre organisation de la société ou de la DoD, à l’aide d’un appareil téléphonique. Les participants à la réunion peuvent préférer utiliser un appareil téléphonique pour participer à des réunions d’équipes dans des scénarios tels que la connectivité Internet est limitée ou lorsque les utilisateurs sont en déplacement et ne peuvent pas accéder à Teams. Les participants peuvent rejoindre une réunion en composant un numéro de téléphone à composer pour votre organisation ou en faisant appel à la réunion par téléphone.

Dans le cadre de l’audioconférence avec le routage direct de GCC High et DoD, votre organisation utilise ses propres numéros en tant que numéros de téléphone rendez-vous et tous les appels sortants vers les appareils mobiles sont routés via le routage direct. Pour activer le service, les organisations doivent configurer le routage direct et configurer des numéros de téléphone qui peuvent être utilisés en tant que numéros de téléphone à composer. La configuration requise pour l’utilisation du routage direct est différente de celle proposée par le service de conférence rendez-vous par Microsoft, qui n’est pas un service de conférence téléphonique.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Déploiement de l’audioconférence avec le routage direct pour les services d’audioconférence et de DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Étape 1 : obtenir des services d’audioconférence avec le routage direct pour les licences GCC High ou DoD 

Pour utiliser l’audioconférence dans GCC High ou DoD, votre organisation et les utilisateurs de votre organisation doivent disposer d’une conférence audio avec une licence de routage directe attribuée. Vous trouverez ci-dessous les licences dont vous avez besoin pour activer l’audioconférence avec le routage direct pour la fonction DoD High ou DoD.

- GCC High : une audioconférence pour les conférences audio : une licence pour les clients de votre organisation et de l’audioconférence : des licences plus élevées pour vos utilisateurs.

- DoD : licence de client de services d’audioconférence pour les licences de votre organisation et audioconférence-DoD pour vos utilisateurs.

Une licence client et au moins une licence utilisateur sont requises pour activer le service. Vous ne pouvez pas activer le service avec uniquement la licence client ou uniquement pour les licences utilisateur. Pour obtenir des licences de service pour votre client et les utilisateurs de votre organisation, contactez l’équipe de votre compte.

> [!IMPORTANT]
> Les utilisateurs ne peuvent pas être activés pour les conférences audio avec le routage direct tant que les numéros de téléphone de connexion n’ont pas été configurés. Nous vous conseillons de ne pas affecter les conférences audio avec le routage direct pour les licences pour les utilisateurs de la fonction DoD (High ou DoD) aux utilisateurs tant que vous n’avez pas configuré les numéros de téléphone à composer comme décrit dans cet article.

### <a name="step-2-set-up-direct-routing"></a>Étape 2 : configurer le routage direct

Pour configurer le routage direct, voir les articles suivants :

- [Planifier le routage direct](direct-routing-plan.md)

- [Configurer le routage direct](direct-routing-configure.md)

> [!NOTE]
> Lorsque vous configurez le routage direct, n’oubliez pas d’utiliser les noms de domaine complets et les ports de FQDN

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Étape 3 : configurer les numéros de téléphone à composer

Les numéros de téléphone à composer sont les numéros de téléphone associés à votre pont de conférence audio. Ces numéros permettent aux participants de participer à des réunions planifiées par des utilisateurs au sein de votre organisation. Ces numéros sont également inclus dans les invitations aux réunions des utilisateurs qui planifient des réunions au sein de votre organisation et sur la page « Rechercher un numéro local ».

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Définir des numéros de téléphone de service dans votre client

Vous pouvez utiliser l’applet de demande PowerShell New-csHybridTelephoneNumber pour définir des numéros de téléphone de service dans votre client, qui peuvent être utilisés pour acheminer les appels vers le service de visioconférence via le routage direct. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Par exemple :
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Affecter les numéros de téléphone de service au pont de conférence audio de votre organisation

Vous pouvez affecter des numéros de service à votre pont de conférence audio de votre organisation à l’aide de l’applet de méthode PowerShell Register-Csonlinedialinconferencingservicenumberhttp.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Vous pouvez voir l’ID de votre pont de conférence audio à l’aide de Get-CsOnlineDialInConferencingBridge. Par exemple :

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Étape 4 : définir une stratégie de routage de la voix globale pour permettre le routage des appels sortants à partir des réunions

Le routage des appels sortants vers le RTC à partir des réunions organisées par les utilisateurs de votre organisation est défini par la stratégie de routage de la voix globale de votre organisation. Si votre organisation dispose d’une stratégie de routage de la voix globale définie, assurez-vous que la stratégie de routage de la voix globale autorise les appels sortants vers le RTC qui sont censés être initiés à partir de réunions organisées par les utilisateurs de votre organisation. Si votre organisation n’a pas défini de stratégie de routage vocale globale, vous devez en définir une pour permettre le routage des appels sortants vers le RTC à partir des réunions organisées par les utilisateurs de votre organisation. Notez que la stratégie de routage de la voix globale de votre organisation s’applique également aux appels un à un vers le RTC par les utilisateurs de votre organisation. Si les appels un à un vers le RTC sont activés pour les utilisateurs de votre organisation, assurez-vous que la stratégie de routage de la voix globale répond aux besoins de votre organisation pour les deux types d’appels. 

> [!NOTE]
> Le routage basé sur la géolocalisation n’est pas disponible dans les déploiements Microsoft 365 Government Community Cloud (GCC) High ou DoD. Lors de l’activation de l’audioconférence, vérifiez qu’aucun utilisateur de conférence audio dans les environnements GCC High ou DoD n’est activé pour le routage de l’emplacement.

#### <a name="defining-a-global-voice-routing-policy"></a>Définition d’une politique générale de routage de la voix

Une stratégie de routage de la voix globale peut être définie en définissant une utilisation PSTN, un itinéraire vocal, une stratégie de routage de la voix et en attribuant la nouvelle stratégie de routage vocale en tant que stratégie de routage vocale globale de votre organisation.

Les étapes suivantes décrivent la définition d’une nouvelle stratégie de routage de la voix pour une organisation. Si votre organisation a déjà défini des stratégies de routage de la voix, vérifiez que la configuration suivante n’entre pas en conflit avec les stratégies de routage vocal existantes de votre organisation.

Pour créer une nouvelle utilisation RTC dans une session PowerShell distante dans Skype entreprise Online, utilisez la commande suivante :

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Pour plus d’informations, consultez la rubrique [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).

Pour créer une nouvelle gamme vocale, utilisez la commande suivante :

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Lors de la définition d’un nouvel itinéraire vocal pour votre organisation, spécifiez une ou plusieurs des passerelles RTC en ligne RTC définies pour votre organisation lors de la configuration du routage direct. 

Le modèle numérique spécifie les appels routés par le biais de la liste de passerelles spécifiée en fonction du numéro de téléphone de destination de l’appel. Dans l’exemple ci-dessus, les appels vers n’importe quelle destination dans le monde correspondent à la gamme vocale. Si vous souhaitez limiter les numéros de téléphone qui peuvent être numérotés à partir des réunions des utilisateurs de votre organisation, vous pouvez modifier le modèle numérique de manière à ce que l’itinéraire ne corresponde qu’aux modèles de nombre des destinations autorisées. Notez que s’il n’y a pas de itinéraires vocaux correspondant au numéro de téléphone de destination d’un appel donné, l’appel n’est pas acheminé.

Pour plus d’informations, reportez-vous à [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).

Pour créer une nouvelle stratégie de routage vocale, utilisez la commande suivante :

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Si plusieurs utilisations RTC sont définies dans la stratégie de routage vocale, celles-ci sont évaluées dans l’ordre dans lequel elles sont définies. Il est recommandé que les utilisations RTC soient définies dans l’ordre de le plus spécifique au plus générique en termes de modèles de nombre des itinéraires vocaux associés aux utilisations PSTN. Par exemple, si une utilisation PSTN a été définie pour acheminer les appels vers les États-Unis et qu’une autre utilisation PSTN a été définie pour acheminer les appels vers tout autre emplacement dans le monde, l’utilisation RTC pour les appels vers les États-Unis doit être répertoriée dans la stratégie de routage de la voix pour diriger les appels vers tout autre emplacement dans le monde.

Pour plus d’informations, reportez-vous à [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).

Pour affecter la nouvelle route à la politique de routage de la voix globale de votre organisation, utilisez la commande suivante :

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Pour plus d’informations, consultez la rubrique [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

Une fois la stratégie de routage vocale globale définie, tous les appels sortants effectués à partir de réunions organisées par des utilisateurs de votre organisation seront évalués par rapport aux itinéraires vocaux associés aux utilisations RTC de la stratégie de routage vocale globale. Les appels sortants seront routés en fonction du premier itinéraire vocal qui correspond au modèle numérique du numéro de téléphone numéroté.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Étape 5 : attribuer des conférences audio avec le routage direct pour les licences GCC High ou DoD à vos utilisateurs

Pour attribuer une audioconférence à votre utilisateur avec le routage direct de ses licences GCC ou DoD, voir [attribuer des licences aux utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Étape 6 : (facultatif) afficher une liste des numéros de conférence audio dans teams

Pour afficher la liste des numéros de conférence audio de votre organisation, consultez la [liste des numéros de conférence audio dans Microsoft teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Étape 7 : (facultatif) définir les langues du standard automatique pour les numéros d’accès pour les conférences audio de votre organisation

Pour modifier la langue des numéros d’accès pour les conférences audio de votre organisation, voir [définir les langues du standard automatique pour les conférences audio dans Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Étape 8 : (facultatif) modifier les paramètres du pont de conférence audio de votre organisation

Pour modifier les paramètres du pont de conférence audio de votre organisation, voir [modifier les paramètres d’un pont de conférence audio](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Étape 9 : (facultatif) définir les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs de votre organisation

Pour modifier l’ensemble des numéros de téléphone inclus dans les invitations aux réunions des utilisateurs de votre organisation, reportez-vous à [la rubrique définition des numéros de téléphone figurant dans les invitations de Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Les fonctionnalités d’audioconférence ne sont pas prises en charge dans les conférences audio avec le routage direct de GCC High et DoD

Voici les fonctionnalités de l’audioconférence qui ne sont pas prises en charge dans les conférences audio avec le routage direct pour les services de préversion de GCC et de DoD :

- Notifications d’entrée et de sortie utilisant l’enregistrement de nom. Pour les conférences audio avec le routage direct, les notifications d’entrée et de sortie sont lues dans la réunion en tant que tonalités.

- Stratégies de restriction des appels sortants pour les conférences audio. Les contrôles de niveau utilisateur permettant de limiter les appels sortants ne sont pas applicables aux appels sortants de réunion routés via le routage direct.

- Désactivez l’utilisation des numéros sans frais pour l’organisateur de la réunion. Les contrôles de niveau utilisateur permettant de limiter l’utilisation des numéros gratuits pour participer aux réunions de votre organisation ne sont pas applicables aux appels routés via le routage direct.

- Envoyer des notifications par courrier électronique aux utilisateurs en cas de modification de leurs paramètres. Les messages électroniques de notification de l’audioconférence ne sont pas pris en charge pour les conférences audio avec le routage direct pour les services de messagerie générale de GCC.
