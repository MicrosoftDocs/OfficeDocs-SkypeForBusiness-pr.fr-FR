---
title: Autoriser les appareils salles Teams à participer à des réunions tierces
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Cet article explique comment configurer votre organisation et salles Teams des appareils pour prendre en charge la participation de réunions tierces à Cisco Webex et Zoom.
ms.openlocfilehash: 1cbcd54983c9122467fbf133cc97b2c189857c96
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268199"
---
# <a name="enable-teams-rooms-devices-to-join-third-party-meetings"></a>Autoriser les appareils salles Teams à participer à des réunions tierces

Salles Microsoft Teams appareils prennent en charge une expérience tactile permettant de participer à des réunions en ligne tierces, également appelées participations directes à des invités. Lorsque cette option est activée, vous pouvez utiliser salles Teams pour participer à des réunions hébergées sur Cisco Webex et Zoom tout aussi facilement que vous pouvez participer à des réunions hébergées dans Microsoft Teams.

Appareils et services pris en charge :

- MTR sur Windows, tous les modèles certifiés – Zoom, Cisco Webex

- Modèles certifiés MTR sur Android, Poly, Yealink et Logitech – Zoom

> [!NOTE]
> Pour participer à une réunion Cisco Webex à partir d’un appareil salles Teams, la réunion Cisco doit être hébergée dans Webex Meetings Pro à l’aide de Cisco Webex webex version WBS 40.7 ou ultérieure. 

Avant de pouvoir participer à des réunions tierces à partir de salles Teams, vous devez effectuer les opérations suivantes :

1. Configurez la boîte aux lettres Exchange Online salle du salles Teams pour traiter les invitations à des réunions tierces.
2. Assurez-vous que votre organisation n’a pas de stratégies qui vous empêcheraient de vous connecter à des services de réunion tiers.
3. Configurez salles Teams pour autoriser les réunions tierces.

Les sections suivantes vous montrent comment effectuer chacune de ces étapes.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Étape 1 : Autoriser le traitement des invitations au calendrier pour les réunions tierces

La première chose que vous devez faire pour activer une expérience de jointure tactile à partir des salles d’équipe consiste à définir les règles de traitement du calendrier pour la boîte aux lettres Exchange Online salle de l’appareil. La boîte aux lettres de salle doit autoriser les réunions externes et conserver le corps et l’objet du message afin qu’il puisse voir l’URL nécessaire pour rejoindre la réunion tierce. Pour définir ces options de boîte aux lettres de salle à l’aide de l’applet [de commande Set-CalendarProcessing, procédez](/powershell/module/exchange/set-calendarprocessing.) comme suit :

1. Connectez-vous à Exchange Online PowerShell. Pour plus d’informations, consultez [Se connecter à Exchange Online PowerShell avec l’authentification de base](/powershell/exchange/connect-to-exchange-online-powershell) ou [se connecter à Exchange Online PowerShell à l’aide de l’authentification multifacteur](/powershell/exchange/mfa-connect-to-exchange-online-powershell), en fonction de votre méthode d’authentification.

2. Obtenez le nom d’utilisateur principal (UPN) de la boîte aux lettres de la salle si vous ne le connaissez pas en exécutant la commande suivante :

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Recherchez le nom de la boîte aux lettres de salle associée à votre appareil salles Teams et notez son UPN.

4. Une fois que vous avez trouvé l’UPN de la boîte aux lettres de la salle, exécutez la commande suivante. Remplacez par `<UserPrincipalName>` l’UPN de la boîte aux lettres de salle :

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

En savoir plus sur [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Étape 2 : Configurer Office 365 Protection contre les menaces et réécrire les liens

Pour activer l’expérience de participation tactile, les informations de lien de participation à la réunion de la réunion tierce doivent être présentes et lisibles dans l’invitation à la réunion. Si votre organisation utilise la fonctionnalité [de liens sécurisés Microsoft Defender pour Office 365](/microsoft-365/security/office-365-security/safe-links), ou si vous utilisez une solution tierce qui analyse toutes les URL entrantes et sortantes à la recherche de menaces, elle peut modifier les URL de participation à la réunion et rendre la réunion méconnaissable par l’appareil salles Teams. Pour vous assurer que cela ne se produit pas, vous devez ajouter les URL du service de réunion tiers à defender pour [Office 365 Liens fiables **Ne réécrivez pas** la liste](/microsoft-365/security/office-365-security/safe-links) ou la liste d’exceptions de réécriture d’URL tierce.

 Si vous utilisez une solution tierce, reportez-vous aux instructions de cette solution pour ajouter des URL à sa liste d’exceptions de réécriture d’URL.

Voici quelques exemples d’entrées que vous devrez peut-être ajouter à votre Defender pour Office 365 Liens fiables *Ne réécrivez pas* la liste ou la liste d’exceptions de réécriture d’URL tierce :

- **Cisco Webex** `*.webex.com/*`
- **Zoom**`*.zoom.us/*`, , `*.zoom.com/*``*.zoomgov.com/*`

Pour obtenir la liste complète des URL à ajouter à votre Defender pour Office 365 Liens fiables *Ne réécrivez pas* la liste ou la liste d’exceptions de réécriture d’URL tierce, contactez le fournisseur de services de réunion tiers à partir duquel vous souhaitez accepter les invitations à la réunion.

> [!CAUTION]
> Ajoutez uniquement les URL de confiance à votre Microsoft Defender pour Office 365 Liens sécurisés *Ne réécrivez pas* la liste ou la liste d’exceptions de réécriture d’URL tierce.

## <a name="step-3a-enable-third-party-meetings-on-teams-rooms-on-windows"></a>Étape 3a : Activer des réunions tierces sur salles Teams sur Windows

La dernière étape à effectuer consiste à autoriser salles Teams à participer à des réunions tierces. Les réunions tierces nécessitent un nom d’utilisateur et une adresse e-mail pour les rejoindre. Si le nom d’utilisateur et l’adresse e-mail que vous devez utiliser sont différents de la boîte aux lettres de salle de l’appareil, vous devez les ajouter à votre appareil. Vous pouvez le faire dans les paramètres salles Teams ou dans le fichier de configuration XML. Vous pouvez le faire dans les paramètres de salles Teams sur n’importe quel salles Teams compatible ou dans le fichier de configuration XML pour salles Teams sur Windows.

### <a name="use-device-settings"></a>Utiliser les paramètres de l’appareil

Pour configurer salles Teams sur Windows à l’aide de la console à écran tactile, procédez comme suit :

1. Dans la console Salles Microsoft Teams, sélectionnez **Plus**.
2. Sélectionnez **Paramètres**, puis entrez le nom d’utilisateur et le mot de passe de l’administrateur de l’appareil.
3. Accédez à l’onglet **Réunions** et sélectionnez un fournisseur de réunion tiers que vous souhaitez activer (par exemple, **Webex**, **Zoom**, etc.).
4. Si vous souhaitez participer à des réunions avec le nom d’utilisateur et l’adresse e-mail associés à la boîte aux lettres de la salle, **sélectionnez Rejoindre avec les informations de la salle**.
5. Si vous souhaitez participer à des réunions avec un autre nom d’utilisateur et une adresse e-mail, sélectionnez **Joindre avec des informations personnalisées** et entrez le nom d’utilisateur et l’adresse e-mail que vous souhaitez utiliser.
6. Sélectionnez **Enregistrer et quitter**. Votre appareil redémarre.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Utiliser le fichier de configuration SkypeSettings.xml

Les paramètres suivants peuvent être ajoutés au `SkypeSettings.xml` fichier situé dans `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Pour plus d’informations sur le `SkypeSettings.xml` fichier, consultez [Gérer les paramètres d’une console Salles Microsoft Teams à distance avec un fichier de configuration XML](xml-config-file.md).

Pour activer les réunions Cisco Webex, définissez l’élément `WebexMeetingsEnabled` XML sur **True**, comme suit.

```xml
<WebexMeetingsEnabled>True</WebexMeetingsEnabled>
```

Pour activer les réunions Zoom, définissez l’élément `ZoomMeetingsEnabled` XML sur **True**, comme suit.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Vous pouvez éventuellement spécifier un nom d’utilisateur et une adresse e-mail personnalisés pour participer à des réunions tierces à l’aide des éléments XML suivants. Si les valeurs que vous fournissez ne sont pas valides, l’appareil salles Teams utilise par défaut le nom d’utilisateur et l’adresse e-mail de la boîte aux lettres de la salle.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```
## <a name="step-3b-enable-third-party-meetings-on-teams-rooms-on-android"></a>Étape 3b : Activer des réunions tierces sur salles Teams sur Android

Pour configurer salles Teams sur Android à l’aide de la console à écran tactile ou de l’écran avant de la pièce, procédez comme suit :

1.  Dans la console Salles Microsoft Teams ou sur l’écran avant de la salle, sélectionnez **Plus**.
2.  Sélectionnez **Paramètres** et :
    -   Si vous utilisez un compte personnel (par exemple, un compte avec une licence E5), choisissez l’option **Réunions** .
    -   Si vous utilisez un compte partagé (par exemple, un compte de ressource avec une licence salles Teams), choisissez **Paramètres de l’appareil**, recherchez les **paramètres Administration Teams**, entrez un mot de passe d’administrateur et choisissez une option **Réunions**.
      > [!NOTE]
      > Certains fabricants d’appareils ont besoin d’un mot de passe d’administrateur avant d’accéder aux **paramètres** de l’appareil.

    ![Paramètres de réunion pour MTR sur Android](..\media\mtrandroid.png)

3.  Sélectionnez un fournisseur de réunion tiers que vous souhaitez activer.
4.  Si vous souhaitez participer à des réunions avec un nom d’utilisateur et une adresse e-mail personnalisés, sélectionnez **Rejoindre avec un nom et un e-mail personnalisés**. Pour mettre à jour les informations personnelles personnalisées, **appuyez sur Modifier les informations personnalisées** et entrez votre nom et votre adresse e-mail préférés.

