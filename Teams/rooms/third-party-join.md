---
title: Activer salles Teams appareils pour participer à des réunions tierces
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Cet article explique comment configurer votre organisation et vos appareils salles Teams pour prendre en charge la prise en charge de la réunion tierce à cisco WebEx et Zoom.
ms.openlocfilehash: d952df95a396e29ffcf393ded068a30459707218
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015244"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Activer Teams de salle pour participer à des réunions tierces

Salles Microsoft Teams appareils prendre en charge une expérience tactile pour participer à des réunions en ligne tierces,également appelée rejoindre directement les invités. Une fois activée, vous pouvez utiliser salles Teams pour participer à des réunions hébergées sur Cisco WebEx et Zoom, tout aussi facilement que vous pouvez participer à des réunions hébergées dans Microsoft Teams.

Avant de pouvoir participer à des réunions tierces à partir salles Teams, vous devez avoir les mesures suivantes :

1. Configurez la boîte salles Teams de la Exchange Online de réunion pour traiter les invitations à des réunions tierces.
2. Assurez-vous que votre organisation n’a pas de stratégie qui vous empêche de vous connecter à des services de réunion tiers.
3. Configurez salles Teams pour autoriser les réunions tierces.

Les sections suivantes vous indiquent comment suivre chacune de ces étapes.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Étape 1 : autoriser le traitement des invitations de calendrier pour les réunions tierces

La première chose que vous devez faire pour activer une expérience de jointage tactile à partir de Salles d’équipe est de définir les règles de traitement du calendrier pour la boîte aux lettres Exchange Online de salle de l’appareil. La boîte aux lettres de la salle doit autoriser les réunions externes et conserver le corps et l’objet du message afin qu’il puisse voir l’URL nécessaire pour participer à la réunion tierce. Pour définir ces options de boîte aux lettres de salle à l’aide de la cmdlet [Set-CalendarProcessing,](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) vous pouvez :

1. Connecter à Exchange Online PowerShell. Pour plus d’informations, voir Connecter à [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) avec l’authentification de base ou Connecter pour Exchange Online PowerShell à l’aide de l’authentification [multifacteur,](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)selon votre méthode d’authentification.

2. Si vous ne la connaissez pas, obtenez le nom d’utilisateur principal (UPN) de la boîte aux lettres de salle en exécutant la commande suivante :

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Recherchez le nom de la boîte aux lettres de salle associée à salles Teams appareil et notez son nom d’utilisateur utilisateur.

4. Une fois que vous avez trouvé le nom d’utilisateur général de la boîte aux lettres de salle, exécutez la commande suivante. Remplacez `<UserPrincipalName>` par le upn de la boîte aux lettres de salle :

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

En savoir plus [sur Exchange Online PowerShell.](/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Étape 2 : configurer Office 365 protection contre les menaces et réécrire le lien

Pour permettre une expérience de participer en une seule fois, les informations de lien d’accès à la réunion tierce doivent être présentes et lisibles dans l’invitation à la réunion. Si votre organisation utilise la fonctionnalité Office 365 Advanced [Threat Protection Coffre Links,](/microsoft-365/security/office-365-security/atp-safe-links) ou si vous utilisez une solution tierce qui analyse toutes les URL entrantes et sortantes de menaces, elle peut modifier les URL de participer à la réunion et rendre la réunion non reconnue par l’appareil salles Teams. Pour vous assurer que cela ne se produit pas, vous devez ajouter les URL du service de réunion tiers à la liste Des liens « ne pas réécrire » ou la liste d’exceptions de réécriture d’URL tierce Coffre s.

Pour ajouter des URL de service de réunion tierces à la liste Liens « Ne pas réécrire » du Coffre atP, suivez les étapes de la procédure Configurer une liste personnalisée d’URL ne pas réécrire à l’aide des liens d’Coffre [ATP.](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide) Si vous utilisez une solution tierce, consultez les instructions de cette solution pour ajouter des URL à sa liste d’exceptions de réécriture d’URL.

Voici quelques exemples d’entrées que vous devrez peut-être ajouter à votre liste d’exceptions ATP Coffre Liens « Ne pas réécrire » ou liste d’exceptions de réécriture d’URL tierces :

- **Cisco WebEx** `*.webex.com*`
- **Zoom,** `*.zoom.us*` `*.zoom.com*` , `*.zoomgov.com*`

Pour obtenir la liste complète des URL à ajouter à votre Coffre Liens « Ne pas réécrire » ou liste d’exceptions de réécriture d’URL tierce, contactez le fournisseur de services de réunion tiers à partir de qui vous voulez accepter les invitations aux réunions. 

> [!CAUTION]
> Ajoutez uniquement les URL de confiance à votre liste d’adresses Coffre Liens « Ne pas réécrire » ou une liste d’exceptions de réécriture d’URL tierce.

## <a name="step-3-enable-third-party-meetings-on-teams-rooms"></a>Étape 3 : activer les réunions tierces sur salles Teams

La dernière étape à vous consiste à autoriser les salles Teams à participer à des réunions tierces. Les réunions tierces nécessitent un nom d’utilisateur et une adresse e-mail pour les rejoindre. Si le nom d’utilisateur et l’adresse de courrier que vous devez utiliser sont différents de la boîte aux lettres de salle de l’appareil, vous devez les ajouter à votre appareil. Vous pouvez le faire dans les paramètres de configuration salles Teams ou dans le fichier de configuration XML.

### <a name="use-device-settings"></a>Utiliser les paramètres de l’appareil

Pour configurer des salles Teams à l’aide de la console à écran tactile, vous pouvez :

1. Sur la console Salles Microsoft Teams, sélectionnez **Plus...**.
2. Sélectionnez **Paramètres,** puis entrez le nom d’utilisateur et le mot de passe de l’administrateur de l’appareil.
3. Allez dans **l’onglet Réunions** et sélectionnez **Cisco WebEx,** **Zoom,** ou les deux.
4. Si vous voulez participer à des réunions avec le nom d’utilisateur et l’adresse de courrier associés à la boîte aux lettres de la salle, sélectionnez Participer **avec les informations de la salle.**
5. Si vous voulez participer à des réunions avec  un autre nom d’utilisateur et une adresse de courrier, sélectionnez Participer avec des informations personnalisées et entrez le nom d’utilisateur et l’adresse de messagerie que vous souhaitez utiliser.
6. Sélectionnez **Enregistrer et quitter.** Votre appareil redémarre.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Utiliser le fichier SkypeSettings.xml configuration de l’ordinateur

Les paramètres suivants peuvent être ajoutés au `SkypeSettings.xml` fichier situé dans `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Pour plus d’informations sur le fichier, voir Gérer Salles Microsoft Teams paramètres d’une console à distance avec `SkypeSettings.xml` un fichier de configuration [XML.](xml-config-file.md)

Pour activer les réunions Cisco WebEx, définissez l’élément `WebExMeetingsEnabled` XML sur **True,** comme suit.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Pour activer les réunions de zoom, définissez l’élément `ZoomMeetingsEnabled` XML sur **True,** comme suit.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Si vous le souhaitez, vous pouvez spécifier un nom d’utilisateur et une adresse de courrier personnalisés pour participer à des réunions tierces à l’aide des éléments XML suivants. Si les valeurs que vous fournissez ne sont pas valides, l’appareil salles Teams utilise par défaut le nom d’utilisateur et l’adresse de courrier de la boîte aux lettres de salle.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Pour participer à une réunion Cisco WebEx à partir d’un appareil salles Teams, la réunion Cisco doit être hébergée dans Réunions WebEx Pro à l’aide de cisco WebEx version WBS 40.7 ou ultérieure. 
