---
title: Définir Microsoft Teams’interface utilisateur des appareils Android
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Découvrez comment définir l’interface utilisateur sur Teams appareils Android.
ms.openlocfilehash: 32f5129330bf46657f126fc00f7eddc2fc30f090
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279382"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Définir Microsoft Teams’interface utilisateur des appareils Android

Microsoft Teams appareils Android peuvent afficher une interface utilisateur spécifique en fonction du type de licence attribué au compte connecté. Vous pouvez remplacer ce comportement et contrôler l’interface affichée. Cet article décrit en détail comment l’interface utilisateur par défaut est choisie et comment vous pouvez la modifier à l’aide d’une stratégie Powershell.

Il existe trois types d’interfaces utilisateur sur Teams appareils Android :

1. Utilisateur
2. Zone commune
3. Réunion

Si vous [](/microsoftteams/user-access) attribuez une licence utilisateur à un compte, tel qu’une licence E3 ou E5, l’appareil Teams affiche l’interface utilisateur par défaut, qui est entièrement prévue pour la plupart des scénarios d’utilisateur. Toutefois, si un appareil effectue une fonction spécifique, telle qu’un téléphone commun ou une salle de réunion, il existe des interfaces utilisateur spécifiques pour ces utilisations.

Les trois images suivantes montrent comment l’interface utilisateur change en fonction de la licence attribuée au compte d’utilisateur. 

## <a name="end-user-interface"></a>Interface utilisateur final 

Une licence E5 est attribuée au compte d’utilisateur. Il s’agit d’une licence utilisateur, de sorte que l’appareil affiche l’interface utilisateur par défaut :

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="Interface du mode utilisateur.":::

## <a name="common-area-interface"></a>Interface en zone commune

Dans cette image, un espace commun a été attribué au compte [d’Téléphone utilisateur](/microsoftteams/set-up-common-area-phones). Les téléphones en zone commune sont principalement utilisés pour effectuer et recevoir des appels téléphoniques. Ainsi, le pavé de numérotation s’affiche sur l’écran :

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="Interface téléphonique en zone commune.":::

## <a name="meeting-interface"></a>Interface de réunion

Cette image montre un compte d’utilisateur avec [Salles Microsoft Teams Standard licence attribuée](/MicrosoftTeams/rooms/rooms-licensing). salles Teams licences sont destinées à être utilisées dans les salles de réunion ou les espaces partagés. L’interface utilisateur change donc pour faciliter la réunion en affichant l’affichage Calendrier :

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="Interface de réunion.":::

> [!NOTE]
> La modification de l’interface utilisateur n’affecte pas votre capacité à utiliser d’autres fonctionnalités sous licence. Par exemple, même si l’affichage par défaut de la licence Salles d’équipe est l’affichage Calendrier, vous pouvez toujours passer et recevoir des appels téléphoniques de réseau téléphonique de commutateur public (PSTN) si la licence et la configuration du compte sont correctes.

> [!IMPORTANT]
> D’autres éléments de l’interface changent. Par exemple, pour empêcher les utilisateurs finaux de se dé sortant d’un téléphone local commun ou d’un appareil de salle de réunion, l’option « Se dé connecter » sur ces appareils est déplacée vers une partie du menu des paramètres qui nécessite des autorisations d’administrateur pour y accéder.

## <a name="override-automatic-user-interface-detection"></a>Remplacer la détection automatique de l’interface utilisateur

Dans certains cas, vous pouvez choisir d’attribuer une licence à un compte qui ne correspond pas à son utilisation prévue. Par exemple, vous pouvez attribuer une licence utilisateur à un compte destiné à se salles Teams sur Android. Par défaut, vous voyez l’interface utilisateur final au lieu de l’interface de salle de réunion. Pour remplacer l’interface par défaut, créez une stratégie Teams [IP Téléphone et](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) appliquez-la à ce compte.

> [!NOTE]
> La licence attribuée au compte d’utilisateur doit au moins avoir les mêmes droits de licence que l’interface utilisateur souhaitée. La licence zone Téléphone permet uniquement l’interface utilisateur du téléphone en zone commune. La licence de salle de réunion permet d’utiliser les interfaces utilisateur des salles de réunion et des téléphones en zone commune. Une licence E3 ou E5 prend en charge tous les modes de inscription.

Voici un exemple de la manière de remplacer la détection automatique de licence. Dans cet exemple, supposons qu’une licence E3 ait été affectée à un compte de ressource conf-adams@contoso.com réunion. Lorsque ce compte est signé, vous souhaitez que les utilisateurs voient l’interface utilisateur de la salle de réunion.

### <a name="create-a-new-policy-and-assign-to-user"></a>Créer une stratégie et l’affecter à l’utilisateur

1. Démarrez une session Windows PowerShell connexion à distance et connectez-vous à Microsoft Teams l’aide de l’cmdlet suivante :

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Créez une stratégie Teams ip Téléphone et définissez le mode de connectez-vous sur « MeetingSignIn » :

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Vous pouvez à présent affecter cette nouvelle stratégie au compte de ressource de la salle de réunion :

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Après avoir accordé la stratégie au compte de ressource de la salle de réunion, vous devez attendre que l’affectation de stratégie soit répliquée. Vous devez également vous sortant de l’appareil et vous y remettre.

## <a name="impact-on-microsoft-teams-admin-center"></a>Impact sur le Microsoft Teams d’administration

Microsoft Teams d’administration vous permet de gérer Microsoft Teams appareils mobiles. Pour plus d’informations sur la gestion des appareils à l’Teams centre d’administration, voir [Gérer vos appareils dans Microsoft Teams](device-management.md).


Teams centre d’administration vous permet de gérer Teams téléphones. Les téléphones sont filtrés en fonction de leur fonction : les téléphones d’utilisateur, les téléphones de zone commune et les téléphones de conférence. 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="En-tête téléphones dans Teams centre d’administration.":::

Comme pour la détection de l’interface utilisateur, les Teams téléphoniques sont classés en fonction de la licence attribuée au compte se signant sur le téléphone. Par exemple, si un compte à qui une licence de téléphone de zone commune est attribuée se signe sur un téléphone, il s’affiche à la fois dans **la section Tous** les téléphones par défaut et dans **la section Téléphones** communs.

Si vous souhaitez qu’un téléphone apparaisse dans une autre section, vous pouvez lui attribuer une autre licence ou créer et attribuer une stratégie de Téléphone IP Teams, comme décrit ci-dessus[.](#override-automatic-user-interface-detection)
