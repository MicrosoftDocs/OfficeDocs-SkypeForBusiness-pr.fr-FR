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
localization_priority: Normal
description: Cet article décrit la configuration de votre organisation et de vos salles Teams pour prendre en charge la prise en charge de la prise en charge de la réunion tierce à Cisco WebEx et Zoom.
ms.openlocfilehash: ef14d1f342c6f2b34ad7c948a2688fa39a09801d
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796688"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="ebd81-103">Activer Teams de salle pour participer à des réunions tierces</span><span class="sxs-lookup"><span data-stu-id="ebd81-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="ebd81-104">Salles Microsoft Teams appareils prendre en charge une expérience tactile unique pour participer à des réunions en ligne tierces(ou rejoindre directement les invités).</span><span class="sxs-lookup"><span data-stu-id="ebd81-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="ebd81-105">Lorsqu’elle est activée, vous pouvez utiliser un appareil salles Teams pour participer à des réunions hébergées sur Cisco WebEx et Zoom, tout aussi facilement que vous pouvez participer à des réunions hébergées dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ebd81-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="ebd81-106">Avant de pouvoir participer à des réunions tierces à partir d salles Teams appareil, vous devez avoir les mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="ebd81-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="ebd81-107">Configurez la boîte salles Teams de salle de l’Exchange Online de l’appareil pour traiter les invitations à des réunions tierces.</span><span class="sxs-lookup"><span data-stu-id="ebd81-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="ebd81-108">Assurez-vous que votre organisation n’a pas de stratégie qui vous empêche de vous connecter à des services de réunion tiers.</span><span class="sxs-lookup"><span data-stu-id="ebd81-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="ebd81-109">Configurez vos salles Teams pour autoriser les réunions tierces.</span><span class="sxs-lookup"><span data-stu-id="ebd81-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="ebd81-110">Les sections suivantes vous indiquent comment suivre chacune de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="ebd81-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="ebd81-111">Étape 1 : autoriser le traitement des invitations de calendrier pour les réunions tierces</span><span class="sxs-lookup"><span data-stu-id="ebd81-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="ebd81-112">La première chose que vous devez faire pour activer une expérience de jointage tactile unique à partir d’un appareil Salles d’équipe est de définir les règles de traitement du calendrier pour la boîte aux lettres de salle Exchange Online de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ebd81-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="ebd81-113">La boîte aux lettres de la salle doit autoriser les réunions externes et conserver le corps et l’objet du message afin qu’il puisse voir l’URL nécessaire pour participer à la réunion tierce.</span><span class="sxs-lookup"><span data-stu-id="ebd81-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="ebd81-114">Pour définir ces options de boîte aux lettres de salle à l’aide de la cmdlet [Set-CalendarProcessing,](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="ebd81-114">To set these room mailbox options using the [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="ebd81-115">Connecter à Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebd81-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="ebd81-116">Pour plus d’informations, voir Connecter à [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) avec l’authentification de base ou Connecter pour [Exchange Online PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)à l’aide de l’authentification multifacteur, selon votre méthode d’authentification.</span><span class="sxs-lookup"><span data-stu-id="ebd81-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="ebd81-117">Si vous ne la connaissez pas, obtenez le nom d’utilisateur principal (UPN) de la boîte aux lettres de salle en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ebd81-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="ebd81-118">Recherchez le nom de la boîte aux lettres de salle associée à salles Teams appareil et notez son nom d’utilisateur utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ebd81-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="ebd81-119">Une fois que vous avez trouvé le nom d’utilisateur général de la boîte aux lettres de salle, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="ebd81-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="ebd81-120">Remplacez `<UserPrincipalName>` par le upn de la boîte aux lettres de salle :</span><span class="sxs-lookup"><span data-stu-id="ebd81-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="ebd81-121">En savoir plus [sur Exchange Online PowerShell.](/powershell/exchange/exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="ebd81-121">Learn more about [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="ebd81-122">Étape 2 : configurer Office 365 protection contre les menaces et réécrire le lien</span><span class="sxs-lookup"><span data-stu-id="ebd81-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="ebd81-123">Pour permettre une expérience de participer en une seule fois, les informations de lien d’accès à la réunion tierce doivent être présentes et lisibles dans l’invitation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="ebd81-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="ebd81-124">Si votre organisation utilise la fonctionnalité liens sécurisés [Office 365 Advanced Threat Protection,](/microsoft-365/security/office-365-security/atp-safe-links) ou si vous utilisez une solution tierce qui analyse toutes les URL entrantes et sortantes de menaces, cela peut modifier les URL de participer à la réunion et rendre la réunion non reconnue par l’appareil salles Teams.</span><span class="sxs-lookup"><span data-stu-id="ebd81-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="ebd81-125">Pour vous assurer que cela ne se produit pas, vous devez ajouter les URL du service de réunion tiers à la liste « Ne pas réécrire » des liens sécurisés ATP ou la liste des exceptions de réécriture d’URL tierces.</span><span class="sxs-lookup"><span data-stu-id="ebd81-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="ebd81-126">Pour ajouter des URL de service de réunion tierces à la liste Liens sécurisés ATP, suivez les étapes de la procédure Configurer une liste d’URL de ne pas réécrire personnalisée à l’aide de liens [sécurisés ATP.](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="ebd81-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="ebd81-127">Si vous utilisez une solution tierce, consultez les instructions de cette solution pour ajouter des URL à sa liste d’exceptions de réécriture d’URL.</span><span class="sxs-lookup"><span data-stu-id="ebd81-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="ebd81-128">Voici quelques exemples d’entrées que vous devrez peut-être ajouter à votre liste de liens sécurisés ATP « Ne pas réécrire » ou liste d’exceptions de réécriture d’URL tierces :</span><span class="sxs-lookup"><span data-stu-id="ebd81-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="ebd81-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="ebd81-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="ebd81-130">**Zoom,** `*.zoom.us*` `*.zoom.com*` , `*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="ebd81-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="ebd81-131">Pour obtenir la liste complète des URL à ajouter à votre liste de liens sécurisés ATP, « ne pas réécrire » ou la liste d’exceptions de réécriture d’URL tierce, contactez le fournisseur de services de réunion tiers à partir de qui vous souhaitez accepter les invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="ebd81-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="ebd81-132">Ajoutez uniquement les URL de confiance à votre liste de liens sécurisés ATP « Ne pas réécrire » ou liste d’exceptions de réécriture d’URL tierces.</span><span class="sxs-lookup"><span data-stu-id="ebd81-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="ebd81-133">Étape 3 : activer les réunions tierces sur l’appareil</span><span class="sxs-lookup"><span data-stu-id="ebd81-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="ebd81-134">La dernière étape à prendre est d’autoriser chaque salles Teams à participer à des réunions tierces.</span><span class="sxs-lookup"><span data-stu-id="ebd81-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="ebd81-135">Les réunions tierces nécessitent un nom d’utilisateur et une adresse e-mail pour les rejoindre.</span><span class="sxs-lookup"><span data-stu-id="ebd81-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="ebd81-136">Si le nom d’utilisateur et l’adresse de courrier que vous devez utiliser sont différents de la boîte aux lettres de salle de l’appareil, vous devez les ajouter à votre appareil.</span><span class="sxs-lookup"><span data-stu-id="ebd81-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="ebd81-137">Vous pouvez le faire dans les paramètres de l’appareil ou dans le fichier de configuration XML.</span><span class="sxs-lookup"><span data-stu-id="ebd81-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="ebd81-138">Utiliser les paramètres de l’appareil</span><span class="sxs-lookup"><span data-stu-id="ebd81-138">Use device settings</span></span>

<span data-ttu-id="ebd81-139">Pour configurer l’appareil salles Teams’aide de son écran tactile, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="ebd81-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="ebd81-140">Sur l’Salles Microsoft Teams, sélectionnez **Plus...**.</span><span class="sxs-lookup"><span data-stu-id="ebd81-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="ebd81-141">Sélectionnez **Paramètres,** puis entrez le nom d’utilisateur et le mot de passe de l’administrateur de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ebd81-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="ebd81-142">Allez dans **l’onglet Réunions** et sélectionnez **Cisco WebEx,** **Zoom,** ou les deux.</span><span class="sxs-lookup"><span data-stu-id="ebd81-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="ebd81-143">Si vous voulez participer à des réunions avec le nom d’utilisateur et l’adresse de courrier associés à la boîte aux lettres de la salle, sélectionnez **Participer avec les informations de la salle.**</span><span class="sxs-lookup"><span data-stu-id="ebd81-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="ebd81-144">Si vous voulez participer à des réunions avec  un autre nom d’utilisateur et une adresse de courrier, sélectionnez Participer avec des informations personnalisées et entrez le nom d’utilisateur et l’adresse e-mail que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="ebd81-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="ebd81-145">Sélectionnez **Enregistrer et quitter.**</span><span class="sxs-lookup"><span data-stu-id="ebd81-145">Select **Save and exit**.</span></span> <span data-ttu-id="ebd81-146">Votre appareil redémarre.</span><span class="sxs-lookup"><span data-stu-id="ebd81-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="ebd81-147">Utiliser le fichier SkypeSettings.xml configuration de l’ordinateur</span><span class="sxs-lookup"><span data-stu-id="ebd81-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="ebd81-148">Les paramètres suivants peuvent être ajoutés au `SkypeSettings.xml` fichier situé dans `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` .</span><span class="sxs-lookup"><span data-stu-id="ebd81-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="ebd81-149">Pour plus d’informations sur le fichier, voir Gérer Salles Microsoft Teams paramètres d’une console à distance avec `SkypeSettings.xml` un fichier de configuration [XML.](xml-config-file.md)</span><span class="sxs-lookup"><span data-stu-id="ebd81-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="ebd81-150">Pour activer les réunions Cisco WebEx, définissez l’élément `WebExMeetingsEnabled` XML sur **True,** comme suit.</span><span class="sxs-lookup"><span data-stu-id="ebd81-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="ebd81-151">Pour activer les réunions de zoom, définissez l’élément `ZoomMeetingsEnabled` XML sur **True,** comme suit.</span><span class="sxs-lookup"><span data-stu-id="ebd81-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="ebd81-152">Vous pouvez éventuellement spécifier un nom d’utilisateur et une adresse de courrier personnalisés pour participer à des réunions tierces à l’aide des éléments XML suivants.</span><span class="sxs-lookup"><span data-stu-id="ebd81-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="ebd81-153">Si les valeurs que vous fournissez ne sont pas valides, l’appareil salles Teams utilise par défaut le nom d’utilisateur et l’adresse de courrier de la boîte aux lettres de salle.</span><span class="sxs-lookup"><span data-stu-id="ebd81-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="ebd81-154">Pour participer à une réunion Cisco WebEx à partir d’un appareil salles Teams, la réunion Cisco doit être hébergée dans Réunions WebEx Pro à l’aide de la version WBS WBS 40.7 ou ultérieure de l’application web Cisco WebEx.</span><span class="sxs-lookup"><span data-stu-id="ebd81-154">To join a Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted in WebEx Meetings Pro using Cisco WebEx web application version WBS 40.7 or later.</span></span> 
