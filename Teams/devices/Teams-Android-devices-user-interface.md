---
title: Définir Microsoft l’interface utilisateur des appareils Android Teams
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Devices
description: Découvrez comment définir l’interface utilisateur sur les appareils Android Teams.
ms.openlocfilehash: 0efabef522a791a56ac187da9a63fab10e4ab3e9
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392433"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Définir Microsoft l’interface utilisateur des appareils Android Teams

Microsoft appareils Android Teams peuvent afficher une interface utilisateur spécifique en fonction du type de licence affecté au compte connecté. Vous pouvez remplacer ce comportement et contrôler l’interface affichée. Cet article explique en détail comment l’interface utilisateur par défaut est choisie et comment vous pouvez modifier l’interface à l’aide d’une stratégie PowerShell.

Il existe trois types d’interfaces utilisateur sur les appareils Android Teams :

1. Utilisateur
2. Zone commune
3. Réunion

Si vous [attribuez une licence utilisateur](/microsoftteams/user-access) à un compte, comme une licence E3 ou E5, l’appareil Teams affiche l’interface utilisateur final par défaut, qui est entièrement proposée pour la plupart des scénarios utilisateur. Toutefois, si un appareil exécute une fonction spécifique, telle qu’un téléphone de zone commune ou une salle de réunion, il existe des interfaces utilisateur spécifiques pour ces utilisations.

Les trois images suivantes montrent comment l’interface utilisateur change en fonction de la licence affectée au compte d’utilisateur.

## <a name="end-user-interface"></a>Interface utilisateur final

Une licence E5 est attribuée au compte d’utilisateur. Il s’agit d’une licence utilisateur, de sorte que l’appareil affiche l’interface utilisateur final par défaut :

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="Interface du mode utilisateur.":::

## <a name="common-area-interface"></a>Interface de zone commune

Dans cette image, une [licence d’appareils partagés Microsoft Teams](/microsoftteams/teams-add-on-licensing/teams-shared-device-license) a été attribuée au compte d’utilisateur. Les téléphones de zone commune sont principalement utilisés pour passer et recevoir des appels téléphoniques. Par conséquent, le pavé de numérotation s’affiche sur l’écran :

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="Interface téléphonique de zone commune.":::

## <a name="meeting-interface"></a>Interface de réunion

Cette image montre un compte d’utilisateur avec une [licence Salles Microsoft Teams](/MicrosoftTeams/rooms/rooms-licensing) affectée. salles Teams licences sont destinées à être utilisées dans des salles de réunion ou des espaces partagés, de sorte que l’interface utilisateur change pour faciliter la participation à une réunion en affichant l’affichage Calendrier :

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="Interface de réunion.":::

> [!NOTE]
> La modification de l’interface utilisateur n’affecte pas votre capacité à utiliser d’autres fonctionnalités sous licence. Par exemple, même si l’affichage par défaut de la licence Salles d’équipe est l’affichage Calendrier, vous pouvez toujours effectuer et recevoir des appels téléphoniques RTC (Public Switch Telephone Network) si le compte dispose d’une licence et d’une configuration correctes.

> [!IMPORTANT]
> D’autres éléments de l’interface changent. Par exemple, pour empêcher les utilisateurs finaux de se déconnecter d’un téléphone ou d’un appareil de salle de réunion de zone commune, l’option « Se déconnecter » sur ces appareils est déplacée vers une partie du menu des paramètres qui nécessite des autorisations d’administrateur pour y accéder.

## <a name="override-automatic-user-interface-detection"></a>Remplacer la détection automatique de l’interface utilisateur

Dans certains cas, vous pouvez choisir d’attribuer une licence à un compte qui ne correspond pas à son utilisation prévue. Par exemple, vous pouvez attribuer une licence utilisateur à un compte destiné à vous connecter à salles Teams sur Android. Par défaut, vous voyez l’interface utilisateur final au lieu de l’interface de salle de réunion. Pour remplacer l’interface par défaut, créez une stratégie de [téléphone IP Teams](/powershell/module/skype/new-csteamsipphonepolicy) et appliquez-la à ce compte.

> [!NOTE]
> La licence affectée au compte d’utilisateur doit avoir au moins les mêmes droits de licence que l’interface utilisateur souhaitée. La licence **appareils partagés Microsoft Teams** autorise uniquement l’interface utilisateur du téléphone de zone commune. La licence **salles Teams** autorise les interfaces utilisateur de salle de réunion et de téléphone de zone commune. Une licence E3 ou E5 prend en charge tous les modes de connexion.

Voici un exemple de remplacement de la détection automatique des licences. Dans cet exemple, supposons qu’une licence E3 a été attribuée à un compte de ressource de salle de réunion nommé conf-adams@contoso.com. Lorsque ce compte est connecté, vous souhaitez que les utilisateurs voient l’interface utilisateur de la salle de réunion.

### <a name="create-a-new-policy-and-assign-to-user"></a>Créer une stratégie et l’affecter à l’utilisateur

1. Démarrez une session de Windows PowerShell à distance et connectez-vous à Microsoft Teams à l’aide de l’applet de commande suivante :

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Créez une stratégie Téléphone IP Teams et définissez le mode de connexion sur « MeetingSignIn » :

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Vous pouvez maintenant affecter cette nouvelle stratégie au compte de ressources de salle de réunion :

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Après avoir accordé la stratégie au compte de ressources de salle de réunion, vous devez attendre que l’attribution de stratégie soit répliquée. Vous devez également vous déconnecter de l’appareil et vous reconnecter.

## <a name="impact-on-microsoft-teams-admin-center"></a>Impact sur Microsoft Centre d’administration Teams

Microsoft Centre d’administration Teams vous permet de gérer Microsoft appareils Teams. Pour plus d’informations sur la gestion des appareils à l’aide du Centre d’administration Teams, consultez [Gérer vos appareils dans Microsoft Teams](device-management.md).

Le Centre d’administration Teams permet de gérer les téléphones Teams. Les téléphones sont filtrés dans l’un des trois onglets en fonction de leur fonction : téléphones utilisateur, téléphones de zone commune et téléphone de conférence.

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="En-tête Téléphones dans le Centre d’administration Teams.":::

Comme pour la détection de l’interface utilisateur, les téléphones Teams sont classés en fonction de la licence affectée au compte qui se connecte au téléphone. Par exemple, si un compte auquel est attribuée une licence **d’appareils partagés Microsoft Teams** se connecte à un téléphone, ce téléphone s’affiche à la fois dans la section **Tous les téléphones** par défaut ainsi que dans la section **Téléphones de zone commune**.

Si vous souhaitez qu’un téléphone apparaisse dans une autre section, vous pouvez attribuer une licence différente au téléphone ou créer et attribuer une stratégie Téléphone IP Teams comme [décrit ci-dessus](#override-automatic-user-interface-detection).
