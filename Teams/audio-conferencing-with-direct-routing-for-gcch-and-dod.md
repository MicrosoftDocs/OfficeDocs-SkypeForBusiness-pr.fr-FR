---
title: Audioconférence avec routage direct, GCCH et DoD
author: cichur
ms.author: v-mahoffman
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
ms.localizationpriority: medium
description: Les administrateurs peuvent en savoir plus sur l’utilisation de l’audioconférence avec le routage direct dans les environnements GCCH et DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a1fade545e2896dac9bc9e486db2b3d31475fe2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763082"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Audioconférence avec routage direct pour GCC High et DoD

L’audioconférence avec routage direct pour Cloud de la communauté du secteur public High et DoD permet aux participants de participer à des réunions Teams dans votre organisation Cloud de la communauté du secteur public High or DoD à l’aide d’un appareil téléphonique. Les participants à la réunion préfèrent peut-être utiliser un appareil téléphonique pour participer à des réunions Teams dans des scénarios tels que lorsque la connectivité Internet est limitée ou lorsque les utilisateurs sont en déplacement et n’ont pas accès à Teams. Les participants peuvent choisir de participer à des réunions en composant un numéro de téléphone d’accès pour votre organisation ou en les faisant appeler sur leur périphérique téléphonique.

Avec l’audioconférence avec routage direct pour Cloud de la communauté du secteur public Haut et DoD, votre organisation utilise ses propres numéros comme numéros de téléphone à composer et tous les appels sortants de réunion vers des périphériques téléphoniques sont acheminés via un routage direct. Pour activer le service, les organisations doivent configurer le routage direct et configurer les numéros de téléphone qui peuvent être utilisés comme numéros de téléphone d’accès. L’exigence d’utiliser le routage direct est différente du service d’audioconférence proposé aux organisations qui ne sont pas en Cloud de la communauté du secteur public Haute et SansD dans le cas où les numéros de téléphone à composer sont fournis par Microsoft.

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Déployer l’audioconférence à l’aide d’un routage direct Cloud de la communauté du secteur public Haut et DoD

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>Étape 1 : obtenir l’audioconférence avec un routage direct pour Cloud de la communauté du secteur public licences Haute ou DoD 

Pour utiliser l’audioconférence dans Cloud de la communauté du secteur public Haut ou DoD, votre organisation et les utilisateurs de votre organisation doivent avoir une licence d’audioconférence avec une licence de routage direct. Voici les licences dont vous avez besoin pour activer l’audioconférence avec routage direct Cloud de la communauté du secteur public Haut ou DoD.

- Cloud de la communauté du secteur public Haute : Licence d’audioconférence - Cloud de la communauté du secteur public Haut client pour votre organisation et Audioconférence - licences haute Cloud de la communauté du secteur public pour vos utilisateurs.

- DoD : Une licence Audioconférence - Client DoD pour votre organisation et Audioconférence - Licences DoD pour vos utilisateurs.

Une licence client et au moins une licence utilisateur sont nécessaires pour activer le service. Vous ne pouvez pas activer le service uniquement avec la licence client ou avec les seules licences utilisateur. Pour obtenir des licences de service pour votre client et les utilisateurs de votre organisation, contactez votre équipe de compte.

> [!IMPORTANT]
> Les utilisateurs ne peuvent pas utiliser l’audioconférence avec routage direct tant que les numéros de téléphone d’accès ne sont pas activés. Nous vous recommandons de ne pas affecter l’audioconférence avec routage direct pour les licences Cloud de la communauté du secteur public High or DoD aux utilisateurs tant que vous n’avez pas installé les numéros de téléphone à composer, comme indiqué dans cet article.  L’omission de ces instructions peut entraîner l’absence complète du pavé de numérotation dans Teams client.

### <a name="step-2-set-up-direct-routing"></a>Étape 2 : configurer le routage direct

Pour configurer le routage direct, consultez les articles suivants :

- [Planifier le routage direct](direct-routing-plan.md)

- [Configurer le routage direct](direct-routing-configure.md)

> [!NOTE]
> Lorsque vous définissez le routage direct, n’oubliez pas d’utiliser les FQDN et ports spécifiques au Cloud de la communauté du secteur public High or DoD décrits dans ces deux articles.

### <a name="step-3-set-up-dial-in-phone-numbers"></a>Étape 3 : configurer les numéros de téléphone à composer

Les numéros de téléphone à composer sont les numéros de téléphone associés à votre pont d’audioconférence. Ces numéros sont utilisés par les participants pour participer à des réunions programmées par les utilisateurs de votre organisation. Ces numéros sont également inclus dans les invitations aux réunions des utilisateurs qui programment des réunions dans votre organisation et sur la page « Rechercher un numéro local ».

#### <a name="define-service-phone-numbers-in-your-tenant"></a>Définir des numéros de téléphone de service dans votre client

Vous pouvez utiliser l’cmdlet New-csHybridTelephone PowerShell pour définir dans votre client des numéros de téléphone de service qui peuvent être utilisés pour router les appels vers le service d’audioconférence via un routage direct. 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

Par exemple :
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>Affectation des numéros de téléphone de service au pont de conférence audio de votre organisation

Vous pouvez affecter des numéros de téléphone de service au pont de conférence Audio de votre organisation à l’aide de l’cmdlet PowerShell Register-csOnlineDialInConferencingServiceNumber.

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

Vous pouvez consulter l’ID de votre pont de conférence audio à l’aide de Get-CsOnlineDialInConferencingBridge. Par exemple :

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>Étape 4 : définir une stratégie globale de routage vocal pour activer le routage des appels sortants à partir des réunions

Le routage des appels sortants effectués vers le réseau PSTN à partir des réunions organisées par les utilisateurs de votre organisation est défini par la stratégie de routage voix globale de votre organisation. Si votre organisation a défini une stratégie globale de routage vocal, vérifiez que la stratégie globale de routage vocal autorise les appels sortants vers le RSTN qui sont censés être initiés à partir de réunions organisées par les utilisateurs de votre organisation. Si votre organisation n’a pas défini de stratégie globale de routage vocal, vous devrez en définir une pour activer le routage des appels sortants vers le RSTN à partir de réunions organisées par les utilisateurs de votre organisation. Veuillez noter que la stratégie globale de routage vocal de votre organisation s’applique également aux appels un-à-un effectués au réseau PSTN par les utilisateurs de votre organisation. Si les appels un-à-un vers le réseau PSTN sont activés pour les utilisateurs de votre organisation, assurez-vous que la stratégie de routage voix globale répond aux besoins de votre organisation pour les deux types d’appels. 

> [!NOTE]
> Location-Based routage n’est pas disponible Microsoft 365 Cloud de la communauté du secteur public (Cloud de la communauté du secteur public) en haut ou en dod. Lors de l’activation de l’audioconférence, vérifiez qu’aucun utilisateur de l’audioconférence dans les environnements Cloud de la communauté du secteur public High ou DoD n’est activé pour le Location-Based routage.

#### <a name="defining-a-global-voice-routing-policy"></a>Définition d’une stratégie globale de routage voix

Une stratégie globale de routage voix peut être définie en définissant une utilisation PSTN, un itinéraire vocal, une stratégie de routage voix et en attribuant la nouvelle stratégie de routage voix comme stratégie de routage voix globale de votre organisation.

Les étapes suivantes décrivent comment définir une nouvelle stratégie de routage voix globale pour une organisation sans. Si votre organisation a déjà défini des stratégies de routage vocal, vérifiez que la configuration suivante n’entre pas en conflit avec les stratégies de routage vocale existantes de votre organisation.

Pour créer une utilisation PSTN dans une session PowerShell distante dans Skype Entreprise Online, utilisez la commande suivante :

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

Pour plus d’informations, [voir Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage)

Pour créer un itinéraire vocal, utilisez la commande suivante :

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

Lors de la définition d’un nouvel itinéraire vocal pour votre organisation, spécifiez une ou plusieurs des passerelles RSTN en ligne PSTN qui ont été définies pour votre organisation dans le cadre de la configuration du routage direct. 

Le modèle de numéro spécifie les appels qui seront acheminés via la liste de passerelles spécifiée en fonction du numéro de téléphone de destination de l’appel. Dans l’exemple ci-dessus, les appels vers n’importe quelle destination dans le monde correspondent à la route vocale. Si vous souhaitez restreindre les numéros de téléphone qui peuvent être composés à partir des réunions des utilisateurs de votre organisation, vous pouvez modifier le modèle de numérotation pour que l’itinéraire vocal corresponde uniquement aux schémas de numéros des destinations autorisées. Notez que si aucun itinéraire vocal ne correspond au modèle de numéro du numéro de téléphone de destination d’un appel donné, l’appel n’est pas acheminé.

Pour plus d’informations, [voir New-CsOnlineVoiceRoute.](/powershell/module/skype/new-csonlinevoiceroute)

Pour créer une stratégie de routage vocal, utilisez la commande suivante :

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

Si plusieurs utilisations PSTN sont définies dans la stratégie de routage voix, elles sont évaluées dans l’ordre dans lequel elles sont définies. Il est recommandé de définir les utilisations PSTN dans l’ordre des plus spécifiques aux plus génériques en termes de schémas de numérox des itinéraires vocaux associés aux utilisations PSTN. Par exemple, si une utilisation PSTN a été définie pour router les appels vers les États-Unis, et qu’une autre utilisation PSTN a été définie pour router les appels vers n’importe quel autre emplacement dans le monde, l’utilisation PSTN pour les appels vers les États-Unis doit être répertoriée dans la stratégie de routage vocal avant l’utilisation PSTN pour router les appels vers n’importe quel autre emplacement dans le monde.

Pour plus d’informations, [voir New-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)

Pour affecter la nouvelle voix à la stratégie de routage vocale globale de votre organisation, utilisez la commande suivante :

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

Pour plus d’informations, [voir Grant-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

Une fois la stratégie de routage voix globale définie, tous les appels sortants effectués à partir de réunions organisées par les utilisateurs de votre organisation sont évalués par rapport aux itinéraires vocaux associés aux utilisations PSTN de la stratégie de routage vocale globale. Les appels sortants seront acheminés en fonction du premier itinéraire vocal qui correspond au modèle de numérotation du numéro de téléphone composé.

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>Étape 5 : affecter des audioconférences avec routage direct pour des Cloud de la communauté du secteur public haute ou dod à vos utilisateurs

Pour attribuer des licences d’audioconférence avec routage direct pour les Cloud de la communauté du secteur public Haute ou DoD à votre utilisateur, consultez Attribuer des [licences à des utilisateurs.](/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>Étape 6 : (Facultatif) consultez la liste des numéros d’audioconférence dans Teams

Pour consulter la liste des numéros d’audioconférence de votre organisation, consultez la liste des numéros d’audioconférence Microsoft Teams. [](see-a-list-of-audio-conferencing-numbers-in-teams.md)

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>Étape 7 : (Facultatif) Définir les langues du attendant automatique pour les numéros de connexion d’Audioconférence de votre organisation

Pour modifier les langues des numéros d’accès d’Audioconférence de votre organisation, consultez définir les langues du attendant automatique pour [l’audioconférence dans Microsoft Teams.](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>Étape 8 : (Facultatif) modifier les paramètres du pont d’audioconférence de votre organisation

Pour modifier les paramètres du pont de conférence audio de votre organisation, consultez Modifier les paramètres d’un pont [d’audioconférence.](change-the-settings-for-an-audio-conferencing-bridge.md)

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>Étape 9 : (Facultatif) Définissez les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs de votre organisation

Pour modifier l’ensemble des numéros de téléphone inclus dans les invitations aux réunions des utilisateurs, consultez Définir les numéros de téléphone inclus dans les [invitations dans Microsoft Teams.](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>Fonctionnalités d’audioconférence non prise en charge dans l’audioconférence avec routage direct pour les Cloud de la communauté du secteur public haut et doD

Voici les fonctionnalités d’audioconférence qui ne sont pas prise en charge dans l’audioconférence avec routage direct pour Cloud de la communauté du secteur public Haut et DoD :

- Notifications d’entrée et de sortie à l’aide de l’enregistrement de nom. Pour l’audioconférence avec routage direct, les notifications d’entrée et de sortie sont lées dans la réunion sous la direction de tonalités.

- Désactivez l’utilisation de numéros gratuits pour l’organisateur spécifique des réunions. Les contrôles au niveau utilisateur pour restreindre l’utilisation de numéros gratuits pour participer aux réunions de votre organisation ne s’appliquent pas aux appels acheminés via le routage direct.

- Envoi d’e-mails de notification aux utilisateurs en cas de modification de leurs paramètres. Les messages électroniques de notification d’audioconférence ne sont pas pris en charge pour l’audioconférence avec routage direct pour les Cloud de la communauté du secteur public haut et doD.
