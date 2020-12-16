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
ms.openlocfilehash: 82369c534a616796382b1de69e37c64f15392f9b
ms.sourcegitcommit: db0dc45520503753567e99c0c016f0265d45aa66
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682383"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="78a35-103">Permettre aux appareils de salle d’équipe de rejoindre des réunions tierces</span><span class="sxs-lookup"><span data-stu-id="78a35-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="78a35-104">Les appareils de salle Microsoft teams prennent en charge une interface utilisateur pour joindre des réunions en ligne tierces, également appelées invité direct Join.</span><span class="sxs-lookup"><span data-stu-id="78a35-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="78a35-105">Lorsque cette option est activée, vous pouvez utiliser un appareil de salle d’équipe pour participer à des réunions hébergées sur Cisco WebEx et zoomer tout aussi facilement que vous pouvez participer à des réunions hébergées dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="78a35-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="78a35-106">Pour pouvoir participer à des réunions tierces à partir d’un appareil de salle d’équipe, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="78a35-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="78a35-107">Configurez la boîte aux lettres Exchange Online de la salle de réunion pour les invitations aux réunions tierces.</span><span class="sxs-lookup"><span data-stu-id="78a35-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="78a35-108">Assurez-vous que votre organisation n’a pas de stratégies qui vous empêchez de vous connecter à des services de réunion tiers.</span><span class="sxs-lookup"><span data-stu-id="78a35-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="78a35-109">Configurez les appareils de salles de votre équipe pour autoriser les réunions tierces.</span><span class="sxs-lookup"><span data-stu-id="78a35-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="78a35-110">Les sections suivantes vous expliquent comment effectuer chacune de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="78a35-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="78a35-111">Étape 1 : autoriser le traitement des invitations de calendrier pour les réunions tierces</span><span class="sxs-lookup"><span data-stu-id="78a35-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="78a35-112">La première chose à faire pour activer une fonction de participation à une seule action à partir d’un appareil de salle d’équipe consiste à définir les règles de traitement du calendrier de la boîte aux lettres Exchange Online de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="78a35-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="78a35-113">La boîte aux lettres de salle doit autoriser les réunions externes et conserver le corps et l’objet du message afin qu’il puisse voir l’URL requise pour joindre la réunion tierce.</span><span class="sxs-lookup"><span data-stu-id="78a35-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="78a35-114">Pour définir ces options de boîte aux lettres de salle à l’aide de l’applet de commande [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="78a35-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="78a35-115">Connectez-vous à Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78a35-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="78a35-116">Pour plus d’informations, voir [se connecter à Exchange Online PowerShell avec l’authentification de base](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) ou [vous connecter à Exchange Online PowerShell à l’aide](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)de la méthode d’authentification multifacteur.</span><span class="sxs-lookup"><span data-stu-id="78a35-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="78a35-117">Obtenez le nom d’utilisateur principal (UPN) de la boîte aux lettres de salle si vous ne le connaissez pas en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="78a35-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="78a35-118">Recherchez le nom de la boîte aux lettres de salle associée à votre appareil de salle d’équipe et notez son UPN.</span><span class="sxs-lookup"><span data-stu-id="78a35-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="78a35-119">Une fois que vous avez trouvé le nom d’utilisateur principal de la boîte aux lettres de salle, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="78a35-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="78a35-120">Remplacez `<UserPrincipalName>` par le nom d’utilisateur principal de la boîte de réception de la salle :</span><span class="sxs-lookup"><span data-stu-id="78a35-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="78a35-121">En savoir plus sur [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="78a35-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="78a35-122">Étape 2 : configurer la protection contre les menaces et la réécriture dans Office 365</span><span class="sxs-lookup"><span data-stu-id="78a35-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="78a35-123">Pour activer l’accès en une seule fois, les informations sur le lien de participation à une réunion à partir de la réunion tierce doivent être présentes et lisibles dans l’invitation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="78a35-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="78a35-124">Si votre organisation utilise la fonctionnalité de [liaison sécurisée d’Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) , ou si vous utilisez une solution tierce qui analyse les URL entrantes et sortantes des menaces, elle peut changer les URL de la réunion et rendre la réunion non évidente par le périphérique Teams.</span><span class="sxs-lookup"><span data-stu-id="78a35-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="78a35-125">Pour que cela ne se produise pas, vous devez ajouter les URL du service de réunion tiers aux liens de sécurité ATP « ne pas réécrire » ou l’URL tierce.</span><span class="sxs-lookup"><span data-stu-id="78a35-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="78a35-126">Pour ajouter des URL de service de réunion tierces à la liste des liens approuvés ATP, suivez les étapes de la rubrique Configurer une liste d’URL sans réécriture [personnalisée à l’aide de liens approuvés ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="78a35-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="78a35-127">Si vous utilisez une solution tierce, reportez-vous aux instructions de cette solution pour ajouter des URL à sa liste d’exceptions de réécriture d’URL.</span><span class="sxs-lookup"><span data-stu-id="78a35-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="78a35-128">Vous trouverez ci-dessous des exemples d’entrées que vous devrez peut-être ajouter à votre liste de liens sécurisés ATP « ne pas réécrire » liste ou liste d’exceptions de réécriture d’URL tierces :</span><span class="sxs-lookup"><span data-stu-id="78a35-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="78a35-129">**Cisco Webex**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="78a35-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="78a35-130">**Zoom** `*.zoom.us*` , `*.zoom.com*` , `*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="78a35-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="78a35-131">Pour obtenir la liste complète des URL que vous pouvez ajouter à votre liste de liens sécurisés ATP « ne pas réécrire » liste ou liste d’exceptions de réécriture d’URL tierce partie, contactez le fournisseur de service de réunion tiers dont vous souhaitez accepter les invitations à une réunion.</span><span class="sxs-lookup"><span data-stu-id="78a35-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="78a35-132">Ajoutez uniquement des URL dignes de confiance à vos liens approuvés ATP « ne pas réécrire » liste ou liste d’exceptions de réécriture d’URL tierce partie.</span><span class="sxs-lookup"><span data-stu-id="78a35-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="78a35-133">Étape 3 : activer les réunions tierces sur l’appareil</span><span class="sxs-lookup"><span data-stu-id="78a35-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="78a35-134">La dernière étape consiste à autoriser chaque appareil de salle d’équipe à rejoindre des réunions tierces.</span><span class="sxs-lookup"><span data-stu-id="78a35-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="78a35-135">Les réunions tierces nécessitent un nom d’utilisateur et une adresse de messagerie pour pouvoir les rejoindre.</span><span class="sxs-lookup"><span data-stu-id="78a35-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="78a35-136">Si le nom d’utilisateur et l’adresse de messagerie que vous devez utiliser diffèrent de la boîte aux lettres de salle de l’appareil, vous devez les ajouter à votre appareil.</span><span class="sxs-lookup"><span data-stu-id="78a35-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="78a35-137">Pour cela, vous pouvez utiliser les paramètres de l’appareil ou le fichier de configuration XML.</span><span class="sxs-lookup"><span data-stu-id="78a35-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="78a35-138">Utiliser les paramètres de l’appareil</span><span class="sxs-lookup"><span data-stu-id="78a35-138">Use device settings</span></span>

<span data-ttu-id="78a35-139">Pour configurer le périphérique de salle d’équipe à l’aide de son écran tactile, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="78a35-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="78a35-140">Sur l’appareil Microsoft Teams, sélectionnez **autres...**.</span><span class="sxs-lookup"><span data-stu-id="78a35-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="78a35-141">Sélectionnez **paramètres**, puis entrez le nom d’utilisateur et le mot de passe de l’administrateur de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="78a35-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="78a35-142">Accédez à l’onglet **réunions** , puis sélectionnez **Cisco Webex**, **Zoom**, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="78a35-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="78a35-143">Si vous souhaitez participer à des réunions avec le nom d’utilisateur et l’adresse de messagerie associés à la boîte aux lettres de salle, sélectionnez **participer à des informations de salle**.</span><span class="sxs-lookup"><span data-stu-id="78a35-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="78a35-144">Si vous souhaitez participer à des réunions avec un nom d’utilisateur et une adresse de messagerie de secours, sélectionnez **participer avec des informations personnalisées** , puis entrez le nom d’utilisateur et l’adresse de messagerie que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="78a35-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="78a35-145">Sélectionnez **enregistrer et quitter**.</span><span class="sxs-lookup"><span data-stu-id="78a35-145">Select **Save and exit**.</span></span> <span data-ttu-id="78a35-146">Votre appareil va redémarrer.</span><span class="sxs-lookup"><span data-stu-id="78a35-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="78a35-147">Utiliser le fichier de configuration SkypeSettings.xml</span><span class="sxs-lookup"><span data-stu-id="78a35-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="78a35-148">Les paramètres suivants peuvent être ajoutés au `SkypeSettings.xml` fichier figurant dans `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` .</span><span class="sxs-lookup"><span data-stu-id="78a35-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="78a35-149">Pour plus d’informations sur le `SkypeSettings.xml` fichier, reportez-vous à la section [gérer les paramètres de la console de Microsoft teams à distance à l’aide d’un fichier de configuration XML](xml-config-file.md).</span><span class="sxs-lookup"><span data-stu-id="78a35-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="78a35-150">Pour activer les réunions Cisco WebEx, définissez l' `WebExMeetingsEnabled` élément XML sur **true**, comme suit.</span><span class="sxs-lookup"><span data-stu-id="78a35-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="78a35-151">Pour activer les réunions de zoom, définissez l' `ZoomMeetingsEnabled` élément XML sur **true**, comme suit.</span><span class="sxs-lookup"><span data-stu-id="78a35-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="78a35-152">Vous pouvez éventuellement spécifier un nom d’utilisateur et une adresse de courrier personnalisés pour participer à des réunions tierces à l’aide des éléments XML suivants.</span><span class="sxs-lookup"><span data-stu-id="78a35-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="78a35-153">Si les valeurs que vous spécifiez ne sont pas valides, l’appareil de salle teams utilise par défaut le nom d’utilisateur et l’adresse de courrier de la salle.</span><span class="sxs-lookup"><span data-stu-id="78a35-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="78a35-154">Pour participer à une réunion Cisco WebEx à partir d’un appareil d’équipe, la réunion Cisco doit être hébergée à l’aide de la version WBS 40,7 ou d’une version ultérieure de l’application Web Cisco.</span><span class="sxs-lookup"><span data-stu-id="78a35-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

