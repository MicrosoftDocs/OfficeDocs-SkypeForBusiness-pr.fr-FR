---
title: Définir l’interface utilisateur des appareils Android Microsoft Teams
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
ms.openlocfilehash: 830609d1bf02c38a2301c0d5a1b9e62ac836c908
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606833"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Définir l’interface utilisateur des appareils Android Microsoft Teams

Les appareils Android Microsoft Teams peuvent afficher une interface utilisateur spécifique en fonction du type de licence attribué au compte connecté. Vous pouvez remplacer ce comportement et contrôler l’interface affichée. Cet article explique comment l’interface utilisateur par défaut est choisie et comment vous pouvez modifier l’interface à l’aide d’une stratégie PowerShell.

Il existe trois types d’interfaces utilisateur sur les appareils Android Teams :

1. Utilisateur
2. Zone commune
3. Réunion

Si vous [attribuez une licence utilisateur](/microsoftteams/user-access) à un compte, comme une licence E3 ou E5, l’appareil Teams affiche l’interface utilisateur final par défaut qui est entièrement proposée pour la plupart des scénarios utilisateur. Toutefois, si un appareil exécute une fonction spécifique, telle qu’un téléphone de zone commune ou une salle de réunion, il existe des interfaces utilisateur spécifiques pour ces utilisations.

Les trois images suivantes montrent comment l’interface utilisateur change en fonction de la licence attribuée au compte d’utilisateur. 

## <a name="end-user-interface"></a>Interface utilisateur final 

Une licence E5 est attribuée au compte d’utilisateur. Comme il s’agit d’une licence utilisateur, l’appareil affiche l’interface utilisateur final par défaut :

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="Interface en mode utilisateur.":::

## <a name="common-area-interface"></a>Interface de zone commune

Dans cette image, une [licence Common Area Phone](/microsoftteams/set-up-common-area-phones) a été attribuée au compte d’utilisateur. Les téléphones de zone commune sont principalement utilisés pour effectuer et recevoir des appels téléphoniques. Par conséquent, le pavé de numérotation s’affiche sur l’affichage :

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="Interface téléphonique de zone commune.":::

## <a name="meeting-interface"></a>Interface de réunion

Cette image montre un compte d’utilisateur avec une [licence Salles Microsoft Teams](/MicrosoftTeams/rooms/rooms-licensing) attribuée. salles Teams licences sont destinées à être utilisées dans les salles de réunion ou les espaces partagés. L’interface utilisateur change donc pour faciliter la participation à une réunion en affichant l’affichage calendrier :

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="Interface de réunion.":::

> [!NOTE]
> La modification de l’interface utilisateur n’affecte pas votre capacité à utiliser d’autres fonctionnalités sous licence. Par exemple, même si l’affichage par défaut de la licence Salles d’équipe est l’affichage calendrier, vous pouvez toujours passer et recevoir des appels téléphoniques rtc (RTC) si le compte est correctement concédé sous licence et configuré.

> [!IMPORTANT]
> D’autres éléments de l’interface changent. Par exemple, pour empêcher les utilisateurs finaux de se déconnecter d’un téléphone commun ou d’un appareil de salle de réunion, l’option « Déconnexion » sur ces appareils est déplacée vers une partie du menu paramètres qui nécessite des autorisations d’accès de l’administrateur.

## <a name="override-automatic-user-interface-detection"></a>Remplacer la détection automatique de l’interface utilisateur

Dans certains cas, vous pouvez choisir d’attribuer une licence à un compte qui ne correspond pas à son utilisation prévue. Par exemple, vous pouvez attribuer une licence utilisateur à un compte destiné à se connecter à salles Teams sur Android. Par défaut, vous voyez l’interface de l’utilisateur final au lieu de l’interface de salle de réunion. Pour remplacer l’interface par défaut, créez une stratégie [de téléphone IP Teams](/powershell/module/skype/new-csteamsipphonepolicy) et appliquez-la à ce compte.

> [!NOTE]
> La licence affectée au compte d’utilisateur doit avoir au moins les mêmes droits de licence que l’interface utilisateur souhaitée. La licence Common Area Phone autorise uniquement l’interface utilisateur du téléphone common area. La licence de salle de réunion autorise les interfaces utilisateur de salle de réunion et de téléphone de la zone commune. Une licence E3 ou E5 prend en charge tous les modes de connexion.

Voici un exemple de remplacement de la détection automatique des licences. Dans cet exemple, supposons qu’une licence E3 a été attribuée à un compte de ressource de salle de réunion nommé conf-adams@contoso.com. Lorsque ce compte est connecté, vous souhaitez que les utilisateurs voient l’interface utilisateur de la salle de réunion.

### <a name="create-a-new-policy-and-assign-to-user"></a>Créer une stratégie et l’affecter à l’utilisateur

1. Démarrez une session de Windows PowerShell distante et connectez-vous à Microsoft Teams à l’aide de l’applet de commande suivante :

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Créez une stratégie de téléphone IP Teams et définissez le mode de connexion sur « MeetingSignIn » :

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Vous pouvez maintenant affecter cette nouvelle stratégie au compte de ressources de salle de réunion :

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Après avoir accordé la stratégie au compte de ressources de salle de réunion, vous devez attendre la réplication de l’attribution de stratégie. Vous devez également vous déconnecter de l’appareil et vous connecter.

## <a name="impact-on-microsoft-teams-admin-center"></a>Impact sur le Centre d’administration Microsoft Teams

Le Centre d’administration Microsoft Teams vous permet de gérer les appareils Microsoft Teams. Pour plus d’informations sur la gestion des appareils à l’aide du Centre d’administration Teams, consultez [Gérer vos appareils dans Microsoft Teams](device-management.md).


Le Centre d’administration Teams offre la possibilité de gérer les téléphones Teams. Les téléphones sont filtrés dans l’un des trois onglets en fonction de leur fonction : les téléphones utilisateur, les téléphones de zone commune et le téléphone de conférence. 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="En-tête Téléphones dans le Centre d’administration Teams.":::

Comme pour la détection de l’interface utilisateur, les téléphones Teams sont classés en fonction de la licence attribuée au compte qui se connecte au téléphone. Par exemple, si un compte auquel une licence de téléphone de zone commune est attribuée se connecte à un téléphone, ce téléphone s’affiche à la fois dans la section **Tous les téléphones** par défaut et dans la section **Téléphones de la zone commune** .

Si vous souhaitez qu’un téléphone apparaisse dans une autre section, vous pouvez soit attribuer une licence différente au téléphone, soit créer et attribuer une stratégie de téléphone IP Teams comme [décrit ci-dessus](#override-automatic-user-interface-detection).
