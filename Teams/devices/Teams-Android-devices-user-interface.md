---
title: Définir l’interface utilisateur sur des appareils Android Microsoft Teams
ms.author: mitressl
author: flinchbot
manager: leopaiv
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Découvrez comment définir l’interface utilisateur sur Teams appareils Android.
ms.openlocfilehash: d3b625e4a54a6a9dcb75d0d1518a65b3e91c23185736672458b0fa1bbd6d55e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327350"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Définir l’interface utilisateur sur des appareils Android Microsoft Teams

Microsoft Teams Les appareils Android peuvent afficher une interface utilisateur spécifique en fonction du type de licence attribué au compte connecté. Vous pouvez remplacer ce comportement et contrôler l’interface affichée. Cet article détaille la façon dont l’interface utilisateur par défaut est choisie et comment vous pouvez modifier l’interface à l’aide d’une stratégie Powershell.

Il existe trois types d’interfaces utilisateur sur Teams appareils Android :

1. Utilisateur
2. Zone commune
3. Réunion

Si [](/microsoftteams/user-access) vous attribuez une licence utilisateur à un compte, comme une licence E3 ou E5, l’appareil Teams affiche l’interface utilisateur final par défaut, qui est entièrement présente pour la plupart des scénarios utilisateur. Toutefois, si un appareil effectue une fonction spécifique, telle qu’un téléphone de partie commune ou une salle de réunion, il existe des interfaces utilisateur spécifiques pour ces utilisations.

Les trois images suivantes montrent comment l’interface utilisateur change en fonction de la licence attribuée au compte d’utilisateur. Dans la première image, une licence E5 est attribuée au compte d’utilisateur. Il s’agit d’une licence utilisateur, de sorte que l’appareil affiche l’interface de l’utilisateur final par défaut :

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="Interface du mode utilisateur":::

Dans cette image, une licence de téléphone de partie commune a été attribuée au compte [d’utilisateur.](/microsoftteams/set-up-common-area-phones) Les téléphones de partie commune sont principalement utilisés pour effectuer et recevoir des appels téléphoniques. En tant que tel, le pavé de numérotation s’affiche à l’écran :

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="Interface téléphonique de partie commune":::

Enfin, cette image montre un compte d’utilisateur avec [une licence Salles Microsoft Teams Standard attribuée.](/MicrosoftTeams/rooms/rooms-licensing) salles Teams licences sont destinées à être utilisées dans les salles de réunion ou les espaces partagés, l’interface utilisateur change pour faciliter la réunion en affichant l’affichage Calendrier :

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="Interface de réunion":::

> [!NOTE]
> La modification de l’interface utilisateur n’affecte pas votre capacité à utiliser d’autres fonctionnalités sous licence. Par exemple, même si l’affichage par défaut de la licence Salles d’équipe est l’affichage Calendrier, vous pouvez toujours passer et recevoir des appels téléphoniques du réseau téléphonique commuté (PSTN) si le compte dispose d’une licence et d’une configuration correctes.

> [!IMPORTANT]
> D’autres éléments de l’interface changent. Par exemple, pour empêcher les utilisateurs finaux de se dé connecter à un téléphone de partie commune ou à un appareil de salle de réunion, l’option « Se dé dé connecter » sur ces appareils est déplacée vers une partie du menu Paramètres qui nécessite des autorisations d’administrateur pour y accéder.

## <a name="override-automatic-user-interface-detection"></a>Remplacer la détection automatique de l’interface utilisateur

Dans certains cas, vous pouvez choisir d’attribuer une licence à un compte qui ne correspond pas à son utilisation prévue. Par exemple, vous pouvez attribuer une licence utilisateur à un compte destiné à se salles Teams sur Android. Par défaut, vous voyez l’interface de l’utilisateur final au lieu de l’interface de salle de réunion. Pour remplacer l’interface par défaut, créez une stratégie de Teams [IP Téléphone et](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) appliquez-la à ce compte.

> [!NOTE]
> La licence attribuée au compte d’utilisateur doit avoir au moins les mêmes droits de licence que l’interface utilisateur souhaitée. La licence d’Téléphone commune autorise uniquement l’interface utilisateur de téléphone de partie commune. La licence de salle de réunion autorise les interfaces utilisateur de salle de réunion et de téléphone de partie commune. Une licence E3 ou E5 prend en charge tous les modes de signature.

Voici un exemple de remplacement de la détection automatique des licences. Dans cet exemple, supposons qu’un compte de ressource de salle de réunion conf-adams@contoso.com a reçu une licence E3. Lorsque ce compte est signé, vous souhaitez que les utilisateurs voient l’interface utilisateur de la salle de réunion.

### <a name="create-a-new-policy-and-assign-to-user"></a>Créer une stratégie et affecter à l’utilisateur

1. Démarrez une session Windows PowerShell session distante et connectez-vous Microsoft Teams l’aide de l’cmdlet suivante :

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Créez une stratégie Teams ip Téléphone et définissez le mode de signature sur « MeetingSignIn » :

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Vous pouvez maintenant affecter cette nouvelle stratégie au compte de ressource de salle de réunion :

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Après avoir accordé la stratégie au compte de ressource de salle de réunion, vous devez attendre que l’attribution de stratégie soit répliquée. Vous devrez également vous sortir de l’appareil et vous y revenir.
