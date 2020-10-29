---
title: Visites virtuelles avec Microsoft teams et l’application Réservations
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
ms.reviewer: ''
description: Microsoft teams et les visites virtuelles à l’aide de l’application Réservations
ms.openlocfilehash: 684c442765b868ca96e9d1bf243817f9378f0b5d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790616"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="c489b-103">Visites virtuelles avec Microsoft teams et l’application Réservations</span><span class="sxs-lookup"><span data-stu-id="c489b-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="c489b-104">L’application livres de Microsoft teams vous permet de planifier facilement des rendez-vous en personne et des rendez-vous virtuels, tels que les visites de santé, les consultations financières, les entretiens, le support client, les heures consacrées au bureau et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="c489b-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="c489b-105">Les planificateurs peuvent gérer plusieurs calendriers de départements et de membres du personnel, ainsi que des communications avec les participants internes et externes à partir d’une seule et même interface.</span><span class="sxs-lookup"><span data-stu-id="c489b-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="c489b-106">Les rendez-vous virtuels eux-mêmes sont conservés par le biais des réunions de Microsoft Teams, qui offrent de puissantes fonctionnalités de visioconférence.</span><span class="sxs-lookup"><span data-stu-id="c489b-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="c489b-107">Pour les seuls planificateurs, l’application réservations doit être installée dans Teams.</span><span class="sxs-lookup"><span data-stu-id="c489b-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="c489b-108">Le personnel responsable ou participant aux rendez-vous virtuel n’a pas besoin de l’application.</span><span class="sxs-lookup"><span data-stu-id="c489b-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="c489b-109">Ils peuvent simplement joindre des rendez-vous à partir du calendrier Outlook ou teams ou d’un lien dans leur adresse de messagerie de confirmation de réservation.</span><span class="sxs-lookup"><span data-stu-id="c489b-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="c489b-110">Conditions préalables à l’utilisation de l’application Réservations dans teams</span><span class="sxs-lookup"><span data-stu-id="c489b-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="c489b-111">La boîte aux lettres Exchange doit être dans Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c489b-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="c489b-112">Les boîtes aux lettres Exchange Server locales ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="c489b-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="c489b-113">La documentation Microsoft doit être activée pour l’organisation.</span><span class="sxs-lookup"><span data-stu-id="c489b-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="c489b-114">Les utilisateurs doivent disposer d’une licence appropriée.</span><span class="sxs-lookup"><span data-stu-id="c489b-114">Users must have an appropriate license.</span></span> <span data-ttu-id="c489b-115">Office 365 a3, a5, E3 et E5, ainsi que Microsoft 365 Business standard, a3, a5, E3 et E5 sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c489b-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="c489b-116">Tous les utilisateurs de l’application réservations et de tous les membres du personnel participant à la réunion doivent disposer d’une licence qui prend en charge la planification des réunions Teams.</span><span class="sxs-lookup"><span data-stu-id="c489b-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="c489b-117">Vos systèmes doivent répondre à la [Configuration requise pour les logiciels et les navigateurs](hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="c489b-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="c489b-118">Disponibilité des réservations dans teams</span><span class="sxs-lookup"><span data-stu-id="c489b-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="c489b-119">L’application Microsoft bookings pour teams est disponible sur l’ordinateur de bureau et sur le Web.</span><span class="sxs-lookup"><span data-stu-id="c489b-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="c489b-120">Vous pouvez le trouver sous [applications dans Microsoft teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) et sous **gérer les applications** dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="c489b-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="c489b-121">Contrôler l’accès aux réservations au sein de votre organisation</span><span class="sxs-lookup"><span data-stu-id="c489b-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="c489b-122">Il existe plusieurs méthodes pour contrôler les utilisateurs qui ont accès à l’application réservations et à des fonctionnalités spécifiques de l’application.</span><span class="sxs-lookup"><span data-stu-id="c489b-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="c489b-123">Pour plus d’informations sur l’activation ou la désactivation de Microsoft bookings dans le centre d’administration 365 Microsoft et sur la création d’une stratégie d’application de documentation pour permettre aux utilisateurs sélectionnés de créer des calendriers de classeurs, voir [accéder à la documentation Microsoft](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span><span class="sxs-lookup"><span data-stu-id="c489b-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="c489b-124">Vous pouvez également apprendre à [créer une stratégie d’application teams pour épingler l’application réservations pour certains utilisateurs](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c489b-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="c489b-125">Paramètres de stratégie de réunion recommandés</span><span class="sxs-lookup"><span data-stu-id="c489b-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="c489b-126">Pour garantir une meilleure utilisation des réservations, créez une stratégie de réunion du personnel pour admettre automatiquement tous les membres **de votre organisation** .</span><span class="sxs-lookup"><span data-stu-id="c489b-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization** .</span></span> <span data-ttu-id="c489b-127">Cela permettra aux membres du personnel de rejoindre automatiquement le rendez-vous et d’activer la salle d’attente pour les participants externes.</span><span class="sxs-lookup"><span data-stu-id="c489b-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="c489b-128">Vous pouvez en savoir plus sur l' [admission automatique de personnes à une réunion](meeting-policies-in-teams.md#automatically-admit-people).</span><span class="sxs-lookup"><span data-stu-id="c489b-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="c489b-129">Paramètre facultatif d’approbation du personnel</span><span class="sxs-lookup"><span data-stu-id="c489b-129">Optional staff approvals setting</span></span>

<span data-ttu-id="c489b-130">En tant que paramètre de confidentialité supplémentaire, vous pouvez choisir d’exiger que le personnel s’abonne pour que les informations de disponibilité du programme soient partagées par le biais de réservations et avant d’être réservées à un rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="c489b-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="c489b-131">Pour activer ce paramètre, accédez à paramètres des paramètres du **Centre d’administration Microsoft 365** \> **Settings** \> **Settings** , puis sélectionnez **réservations** .</span><span class="sxs-lookup"><span data-stu-id="c489b-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings** , then select **Bookings** .</span></span>

<span data-ttu-id="c489b-132">Lorsque ce paramètre est activé, le personnel reçoit un message électronique lui demandant d’approuver l’appartenance à un calendrier de réservation.</span><span class="sxs-lookup"><span data-stu-id="c489b-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="c489b-133">Cette fonctionnalité est déployée progressivement à travers le monde pour les clients Microsoft 365 et Office 365.</span><span class="sxs-lookup"><span data-stu-id="c489b-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="c489b-134">Si toutes les options ne sont pas encore disponibles dans votre environnement, revenez à la prochaine version.</span><span class="sxs-lookup"><span data-stu-id="c489b-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="c489b-135">Modification de votre domaine par défaut lors de la configuration de la boîte aux lettres de réservations</span><span class="sxs-lookup"><span data-stu-id="c489b-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="c489b-136">Lorsque vous configurez une boîte aux lettres de réservations, le domaine de messagerie par défaut de votre organisation Microsoft 365 ou Office 365 est utilisé.</span><span class="sxs-lookup"><span data-stu-id="c489b-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="c489b-137">Toutefois, cela peut poser des problèmes lors de l’envoi d’invitations de réunion à des destinataires externes ; votre invitation peut être signalée comme courrier indésirable et déplacée vers le dossier courrier indésirable du destinataire, afin que le destinataire ne puisse jamais voir votre invitation.</span><span class="sxs-lookup"><span data-stu-id="c489b-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="c489b-138">Nous vous recommandons de modifier le domaine par défaut avant de créer votre boîte aux lettres de réservations.</span><span class="sxs-lookup"><span data-stu-id="c489b-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="c489b-139">Pour plus d’informations sur la façon de procéder, consultez le [Forum aux questions](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)sur les domaines.</span><span class="sxs-lookup"><span data-stu-id="c489b-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="c489b-140">Si vous devez modifier le domaine par défaut après la création de la boîte aux lettres de manuel, vous pouvez le faire avec PowerShell :</span><span class="sxs-lookup"><span data-stu-id="c489b-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="c489b-141">Pour plus d’informations, consultez la documentation PowerShell pour l’applet de passe [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) .</span><span class="sxs-lookup"><span data-stu-id="c489b-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="c489b-142">Si vous utilisez une configuration Exchange hybride, nous vous conseillons de tester soigneusement le flux de messagerie entre Exchange et Exchange Online lors de la modification du domaine par défaut.</span><span class="sxs-lookup"><span data-stu-id="c489b-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="c489b-143">Envoi de commentaires</span><span class="sxs-lookup"><span data-stu-id="c489b-143">Sending feedback</span></span>

<span data-ttu-id="c489b-144">Vos commentaires sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="c489b-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="c489b-145">Utilisation ou convivialité</span><span class="sxs-lookup"><span data-stu-id="c489b-145">User experience or ease of use</span></span>
  - <span data-ttu-id="c489b-146">Lacunes de fonctionnalités ou fonctionnalités manquantes</span><span class="sxs-lookup"><span data-stu-id="c489b-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="c489b-147">Bogues ou problèmes</span><span class="sxs-lookup"><span data-stu-id="c489b-147">Bugs or issues</span></span>
  
<span data-ttu-id="c489b-148">Pour envoyer des commentaires, cliquez sur le bouton **aide** en bas de la barre de navigation gauche de teams, puis cliquez sur **signaler un problème** pour **tous les** problèmes.</span><span class="sxs-lookup"><span data-stu-id="c489b-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="c489b-149">Veuillez noter au début de votre rapport de commentaires que vous envoyez des commentaires sur « réservations » pour nous permettre d’identifier facilement les problèmes liés aux réservations.</span><span class="sxs-lookup"><span data-stu-id="c489b-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c489b-150">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="c489b-150">Related topics</span></span>

[<span data-ttu-id="c489b-151">Documentation relative aux réservations pour les utilisateurs finaux</span><span class="sxs-lookup"><span data-stu-id="c489b-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
