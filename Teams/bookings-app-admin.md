---
title: Visites virtuelles dans Microsoft Teams et l’application Bookings
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams et les visites virtuelles avec l’application Bookings
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125747"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="8be45-103">Visites virtuelles dans Microsoft Teams et l’application Bookings</span><span class="sxs-lookup"><span data-stu-id="8be45-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="8be45-104">L'application Bookings de Microsoft Teams offre un moyen simple de planifier des rendez-vous en personne ou virtuels, tels que des visites médicales, des consultations financières, des entretiens, une assistance à la clientèle, des heures d'ouverture des bureaux de l'éducation, et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="8be45-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="8be45-105">Les planificateurs peuvent gérer plusieurs calendriers des services et du personnel, ainsi que les communications avec les participants internes et externes à partir d’une même expérience.</span><span class="sxs-lookup"><span data-stu-id="8be45-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="8be45-106">Les rendez-vous virtuels eux-mêmes se déroulent via les réunions Microsoft Teams, qui offrent de solides capacités de vidéoconférence.</span><span class="sxs-lookup"><span data-stu-id="8be45-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="8be45-107">Seuls les planificateurs doivent avoir l'application Bookings installée dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8be45-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="8be45-108">Le personnel effectuant ou participant à des rendez-vous virtuels n'a pas besoin de l'application.</span><span class="sxs-lookup"><span data-stu-id="8be45-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="8be45-109">Ils peuvent simplement rejoindre les rendez-vous à partir de leur calendrier Outlook ou Teams ou à partir d'un lien dans leur courriel de confirmation de réservation.</span><span class="sxs-lookup"><span data-stu-id="8be45-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="8be45-110">Conditions préalables à l'utilisation de l'application Bookings dans Teams</span><span class="sxs-lookup"><span data-stu-id="8be45-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="8be45-111">La boîte aux lettres Exchange doit être dans Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8be45-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="8be45-112">Les boîtes aux lettres sur serveur Exchange local ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="8be45-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="8be45-113">Microsoft Bookings doit être désactivé pour l’organisation.</span><span class="sxs-lookup"><span data-stu-id="8be45-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="8be45-114">Les utilisateurs doivent avoir une licence appropriée.</span><span class="sxs-lookup"><span data-stu-id="8be45-114">Users must have an appropriate license.</span></span> <span data-ttu-id="8be45-115">Office 365 A3, A5, E3 et E5, ainsi que Office 365 Business Premium, A3, A5, E3 et E5 sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="8be45-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="8be45-116">Tous les utilisateurs de l’application Bookings et tous les membres du personnel participant aux réunions doivent avoir une licence qui prend en charge la planification de réunions Teams.</span><span class="sxs-lookup"><span data-stu-id="8be45-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="8be45-117">Vos systèmes doivent respecter toutes les [Conditions préalables navigateur et logiciels](hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="8be45-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="8be45-118">Disponibilité de Bookings dans Teams</span><span class="sxs-lookup"><span data-stu-id="8be45-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="8be45-119">L’application Microsoft Bookings pour Teams est disponible sur le bureau et sur le web.</span><span class="sxs-lookup"><span data-stu-id="8be45-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="8be45-120">Elle se trouve sous [Applications dans Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) et sous **Gérer les applications** dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="8be45-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="8be45-121">Contrôler l’accès à Bookings au sein de votre organisation</span><span class="sxs-lookup"><span data-stu-id="8be45-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="8be45-122">Plusieurs méthodes s’offrent à vous pour contrôler qui a accès à l’application Bookings et à des fonctionnalités spécifiques de l’application.</span><span class="sxs-lookup"><span data-stu-id="8be45-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="8be45-123">Pour savoir comment activer ou désactiver Microsoft Bookings dans le Centre d’administration Microsoft 365, et créer une stratégie d’application Bookings pour autoriser les utilisateurs sélectionnés à créer des calendriers Bookings, consultez [Accéder à Microsoft Bookings](https://support.microsoft.com/fr-FR/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span><span class="sxs-lookup"><span data-stu-id="8be45-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/fr-FR/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="8be45-124">Vous pouvez également découvrir comment [Créer une stratégie d’application Teams pour épingler l’application Bookings à certains utilisateurs](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8be45-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="8be45-125">Paramètres de stratégie de réunion recommandés</span><span class="sxs-lookup"><span data-stu-id="8be45-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="8be45-126">Pour optimiser l'expérience de Bookings, créez une stratégie de réunion du personnel pour admettre automatiquement **Tous les membres de votre organisation**.</span><span class="sxs-lookup"><span data-stu-id="8be45-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="8be45-127">Cela permettra au personnel de rejoindre automatiquement le rendez-vous et d’activer l’expérience de salle d’évaluation pour les participants externes.</span><span class="sxs-lookup"><span data-stu-id="8be45-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="8be45-128">Vous pouvez en savoir plus sur l'[admission automatique des personnes aux réunions](meeting-policies-in-teams.md#automatically-admit-people).</span><span class="sxs-lookup"><span data-stu-id="8be45-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="8be45-129">Paramètre d’approbation facultative du personnel</span><span class="sxs-lookup"><span data-stu-id="8be45-129">Optional staff approvals setting</span></span>

<span data-ttu-id="8be45-130">Dans le cadre d’un paramètre de confidentialité supplémentaire, vous pouvez choisir d’obliger les membres du personnel à s’y prendre avant que leurs informations de disponibilité ne soient partagées via Bookings et avant qu’ils ne soient pris en rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="8be45-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="8be45-131">Pour activer ce paramètre, accédez au **Centre d’administration Microsoft 365** \> **Paramètres** \> **Paramètres**, puis sélectionnez **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="8be45-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="8be45-132">Avec ce paramètre désactivé, le personnel reçoit un courrier électronique dans lequel il est invité à approuver l’appartenance à un calendrier de réservation.</span><span class="sxs-lookup"><span data-stu-id="8be45-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="8be45-133">Cette fonctionnalité est déployée progressivement dans le monde entier pour les clients Microsoft 365 et Office 365.</span><span class="sxs-lookup"><span data-stu-id="8be45-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="8be45-134">Si toutes les options ne sont pas encore disponibles dans votre environnement, vérifiez à nouveau dans peu de temps.</span><span class="sxs-lookup"><span data-stu-id="8be45-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="8be45-135">Modifier votre domaine par défaut lors de la configuration des boîtes aux lettres Bookings</span><span class="sxs-lookup"><span data-stu-id="8be45-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="8be45-136">Lors de la configuration d’une boîte aux lettres Bookings, le domaine de courrier par défaut de votre organisation Microsoft 365 ou Office 365 est utilisé.</span><span class="sxs-lookup"><span data-stu-id="8be45-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="8be45-137">Toutefois, cela peut poser des problèmes lors de l'envoi d'invitations de réunion à des destinataires externes. Il est possible que votre invitation soit signalée en tant que courrier indésirable et déplacée vers le dossier de courrier indésirable du destinataire, de sorte que le destinataire ne voie jamais votre invitation.</span><span class="sxs-lookup"><span data-stu-id="8be45-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="8be45-138">Nous vous recommandons de modifier le domaine par défaut avant de créer votre boîte aux lettres Bookings.</span><span class="sxs-lookup"><span data-stu-id="8be45-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="8be45-139">Pour plus d’informations sur la façon de faire, consultez [FAQ sur les domaines](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="8be45-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="8be45-140">Si vous devez modifier le domaine par défaut alors que votre boîte aux lettres Bookings a déjà été créée, vous pouvez le faire avec PowerShell :</span><span class="sxs-lookup"><span data-stu-id="8be45-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="8be45-141">Pour plus d’informations, consultez la documentation PowerShell pour la cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) .</span><span class="sxs-lookup"><span data-stu-id="8be45-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="8be45-142">Si vous utilisez une configuration Exchange hybride, nous vous recommandons de tester minutieusement le flux de courrier entre Exchange local et Exchange Online lorsque vous modifiez le domaine par défaut.</span><span class="sxs-lookup"><span data-stu-id="8be45-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="8be45-143">Envoi de commentaires</span><span class="sxs-lookup"><span data-stu-id="8be45-143">Sending feedback</span></span>

<span data-ttu-id="8be45-144">Vos commentaires sont les bienvenus :</span><span class="sxs-lookup"><span data-stu-id="8be45-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="8be45-145">Expérience utilisateur ou facilité d’utilisation</span><span class="sxs-lookup"><span data-stu-id="8be45-145">User experience or ease of use</span></span>
  - <span data-ttu-id="8be45-146">Lacunes dans les fonctionnalités ou fonctionnalités manquantes</span><span class="sxs-lookup"><span data-stu-id="8be45-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="8be45-147">Bogues ou problèmes</span><span class="sxs-lookup"><span data-stu-id="8be45-147">Bugs or issues</span></span>
  
<span data-ttu-id="8be45-148">Pour envoyer des commentaires, cliquez sur le bouton **Aide** situé en bas de la barre de navigation gauche de Teams, puis cliquez sur **Signaler un problème** pour **TOUS** les problèmes.</span><span class="sxs-lookup"><span data-stu-id="8be45-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="8be45-149">Veuillez noter au début de votre rapport de commentaires que vous envoyez des commentaires sur « Bookings » afin que nous pouvons facilement identifier les problèmes de Bookings.</span><span class="sxs-lookup"><span data-stu-id="8be45-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8be45-150">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="8be45-150">Related topics</span></span>

<span data-ttu-id="8be45-151">
  [Documentation Bookings pour les utilisateurs finaux](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span><span class="sxs-lookup"><span data-stu-id="8be45-151">[Bookings documentation for end users](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span></span>
