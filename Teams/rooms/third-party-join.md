---
title: Permettre aux appareils de salle d’équipe de rejoindre des réunions tierces
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
localization_priority: Normal
description: Cet article explique comment configurer les appareils de votre organisation et celle de votre équipe pour qu’elle prenne en charge la participation à des réunions à l’aide de Cisco WebEx et de zoom.
ms.openlocfilehash: 708fb7f9d243559a571b2b9016fab1e38aa63114
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372213"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Permettre aux appareils de salle d’équipe de rejoindre des réunions tierces

Les appareils de salle Microsoft teams prennent en charge une interface utilisateur pour joindre des réunions en ligne tierces. Lorsque cette option est activée, vous pouvez utiliser un appareil de salle d’équipe pour rejoindre des réunions hébergées sur Cisco WebEx et zoom<sup>1</sup> tout aussi facilement que vous pouvez rejoindre des réunions hébergées dans Microsoft Teams.

Pour pouvoir participer à des réunions tierces à partir d’un appareil de salle d’équipe, vous devez procéder comme suit :

1. Configurer la boîte aux lettres Exchange Online de la salle de réunion pour les invitations aux réunions tierces
2. Vérifiez que votre organisation n’a pas de stratégies qui vous empêchent de vous connecter à des services de réunion tiers
3. Configurer les appareils de salles de votre équipe pour permettre aux réunions tierces

Les sections suivantes vous expliquent comment effectuer chacune de ces étapes.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Étape 1 : autoriser le traitement des invitations de calendrier pour les réunions tierces

La première chose à faire pour activer une fonction de participation à une seule action à partir d’un appareil de salle d’équipe consiste à définir les règles de traitement du calendrier de la boîte aux lettres Exchange Online de l’appareil. La boîte aux lettres de salle doit autoriser les réunions externes et conserver le corps et l’objet du message afin qu’il puisse voir l’URL requise pour joindre la réunion tierce. Pour définir ces options de boîte aux lettres de salle à l’aide de l’applet de commande [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , procédez comme suit :

1. Connectez-vous à Exchange Online PowerShell. Pour plus d’informations, voir [se connecter à Exchange Online PowerShell avec l’authentification de base](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) ou [vous connecter à Exchange Online PowerShell à l’aide](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)de la méthode d’authentification multifacteur.

2. Obtenez le nom d’utilisateur principal (UPN) de la boîte aux lettres de salle si vous ne le connaissez pas en exécutant la commande suivante :

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. Recherchez le nom de la boîte aux lettres de salle associée à votre appareil de salle d’équipe et notez son UPN.

4. Une fois que vous avez trouvé le nom d’utilisateur principal de la boîte aux lettres de salle, exécutez la commande suivante. Remplacez `<UserPrincipalName>` par le nom d’utilisateur principal de la boîte de réception de la salle :

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

En savoir plus sur [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Étape 2 : configurer la protection contre les menaces et la réécriture dans Office 365

Pour activer l’accès en une seule fois, les informations sur le lien de participation à une réunion à partir de la réunion tierce doivent être présentes et lisibles dans l’invitation à la réunion. Si votre organisation utilise la fonctionnalité de [liaison sécurisée d’Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)   , ou si vous utilisez une solution tierce qui analyse les URL entrantes et sortantes des menaces, elle peut changer les URL de la réunion et rendre la réunion non évidente par le périphérique Teams. Pour que cela ne se produise pas, vous devez ajouter les URL du service de réunion tiers aux liens de sécurité ATP « ne pas réécrire » ou l’URL tierce.

Pour ajouter des URL de service de réunion tierces à la liste des liens approuvés ATP, suivez les étapes de la rubrique Configurer une liste d’URL sans réécriture [personnalisée à l’aide de liens approuvés ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide). Si vous utilisez une solution tierce, reportez-vous aux instructions de cette solution pour ajouter des URL à sa liste d’exceptions de réécriture d’URL.

Vous trouverez ci-dessous des exemples d’entrées que vous devrez peut-être ajouter à votre liste de liens sécurisés ATP « ne pas réécrire » liste ou liste d’exceptions de réécriture d’URL tierces :

- **Cisco Webex**`*.webex.com*`
- **Zoom** `*zoom.us*` , `*zoom.com*` ,`*zoomgov.com*`

Pour obtenir la liste complète des URL que vous pouvez ajouter à votre liste de liens sécurisés ATP « ne pas réécrire » liste ou liste d’exceptions de réécriture d’URL tierce partie, contactez le fournisseur de service de réunion tiers dont vous souhaitez accepter les invitations à une réunion. 

> [!CAUTION]
> Ajoutez uniquement des URL dignes de confiance à vos liens approuvés ATP « ne pas réécrire » liste ou liste d’exceptions de réécriture d’URL tierce partie.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Étape 3 : activer les réunions tierces sur l’appareil

La dernière étape consiste à autoriser chaque appareil de salle d’équipe à rejoindre des réunions tierces. Les réunions tierces nécessitent un nom d’utilisateur et une adresse de messagerie pour pouvoir les rejoindre. Si le nom d’utilisateur et l’adresse de messagerie que vous devez utiliser diffèrent de la boîte aux lettres de salle de l’appareil, vous devez les ajouter à votre appareil. Pour cela, vous pouvez utiliser les paramètres de l’appareil ou le fichier de configuration XML.

### <a name="use-device-settings"></a>Utiliser les paramètres de l’appareil

Pour configurer le périphérique de salle d’équipe à l’aide de son écran tactile, procédez comme suit :

1. Sur l’appareil Microsoft Teams, sélectionnez **autres...**
2. Sélectionnez **paramètres**, puis entrez le nom d’utilisateur et le mot de passe de l’administrateur de l’appareil.
3. Accédez à l’onglet **réunions**,   puis sélectionnez **Cisco Webex**, **Zoom**<sup>1</sup>ou les deux
4. Si vous souhaitez participer à des réunions avec le nom d’utilisateur et l’adresse de messagerie associés à la boîte aux lettres de salle, sélectionnez **participer à des informations de salle** .
5. Si vous souhaitez participer à des réunions avec un nom d’utilisateur et une adresse de messagerie de secours, sélectionnez **participer avec des informations personnalisées** , entrez le nom d’utilisateur et l’adresse de courrier que vous voulez utiliser.
6. Sélectionnez **enregistrer et quitter**. Votre appareil va redémarrer.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Utiliser le fichier de configuration SkypeSettings.xml

Les paramètres suivants peuvent être ajoutés au `SkypeSettings.xml` fichier figurant dans `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Pour plus d’informations sur le `SkypeSettings.xml` fichier, reportez-vous à la section [gérer les paramètres de la console de Microsoft teams à distance à l’aide d’un fichier de configuration XML](xml-config-file.md).

Pour activer les réunions Cisco WebEx, définissez l' `WebExMeetingsEnabled` élément XML sur **true**, comme suit.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Pour activer les réunions de zoom<sup>1</sup> , définissez l' `ZoomMeetingsEnabled` élément XML sur **true**, comme suit.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Vous pouvez éventuellement spécifier un nom d’utilisateur et une adresse de courrier personnalisés pour participer à des réunions tierces à l’aide des éléments XML suivants. Si les valeurs que vous spécifiez ne sont pas valides, l’appareil de salle teams utilise par défaut le nom d’utilisateur et l’adresse de courrier de la salle.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Pour participer à une réunion Cisco WebEx à partir d’un appareil d’équipe, la réunion Cisco doit être hébergée à l’aide de la version WBS 40,7 ou d’une version ultérieure de l’application Web Cisco.

<sup>1</sup> la participation à des réunions avec zoom est actuellement disponible uniquement pour sélectionner des clients de Microsoft teams via le programme d’accès aux technologies.
