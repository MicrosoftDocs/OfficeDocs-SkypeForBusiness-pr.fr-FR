---
title: Utiliser le complément Réunion Microsoft Teams dans Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams installe un complément dans Outlook qui permet aux utilisateurs de planifier une réunion Teams depuis Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 624e6a72daae12d0e40b351cea6039fbe5eb432b
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2019
ms.locfileid: "33994134"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="a89d2-103">Utiliser le complément Réunion Teams dans Outlook</span><span class="sxs-lookup"><span data-stu-id="a89d2-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="a89d2-104">Le complément Réunion Teams est installé automatiquement pour les utilisateurs pour lesquels Microsoft Teams et Office 2013 ou Office 2016 sont installés sur leur PC Windows.</span><span class="sxs-lookup"><span data-stu-id="a89d2-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="a89d2-105">Le complément Réunion Teams apparaît sur le ruban Calendrier d'Outlook.</span><span class="sxs-lookup"><span data-stu-id="a89d2-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Capture d'écran du complément Teams sur le ruban Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> <span data-ttu-id="a89d2-107">Les utilisateurs Windows 7 doivent installer la[mise à jour pour Universal Runtime C dans Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) pour le complément de réunion Teams afin de l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="a89d2-107">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>

<span data-ttu-id="a89d2-108">Si le complément Réunion Teams n'apparaît pas, demandez aux utilisateurs de fermer Outlook et Teams, de redémarrer d'abord le client Teams, de se connecter à Teams puis de redémarrer le client Outlook, dans cet ordre spécifique.</span><span class="sxs-lookup"><span data-stu-id="a89d2-108">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="a89d2-109">Le bouton réunion d’équipes dans Outlook pour Mac s’affiche dans Outlook, ruban Mac si Outlook est en cours d’exécution Build de Production 16.20 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="a89d2-109">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running Production Build 16.20 and later.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="a89d2-110">Exigences d'authentification</span><span class="sxs-lookup"><span data-stu-id="a89d2-110">Authentication requirements</span></span>

<span data-ttu-id="a89d2-111">Le complément Réunion Teams requiert de se connecter à Teams en utilisant l'authentification moderne.</span><span class="sxs-lookup"><span data-stu-id="a89d2-111">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="a89d2-112">Si les utilisateurs n'utilisent pas cette méthode pour se connecter, ils pourront continuer à utiliser le client Teams mais ne pourront pas planifier de réunions en ligne Teams à l'aide du complément Outlook.</span><span class="sxs-lookup"><span data-stu-id="a89d2-112">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="a89d2-113">Vous pouvez résoudre ce problème de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="a89d2-113">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="a89d2-114">Si l'authentification moderne n'est pas configurée pour votre organisation, vous devez la configurer.</span><span class="sxs-lookup"><span data-stu-id="a89d2-114">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="a89d2-115">Si l'authentification moderne est configurée, mais qu'ils l'ont annulée dans la boîte de dialogue, vous devez demander aux utilisateurs de se connecter à nouveau en utilisant l'authentification multifacteur.</span><span class="sxs-lookup"><span data-stu-id="a89d2-115">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="a89d2-116">Pour savoir comment configurer l'authentification, reportez-vous à la rubrique [Modèles d'identité et authentification dans Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a89d2-116">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="a89d2-117">Activer les réunions privées</span><span class="sxs-lookup"><span data-stu-id="a89d2-117">Enable private meetings</span></span>

<span data-ttu-id="a89d2-118">L'autorisation de planification de réunions privées doit être activée depuis le Centre d'administration Microsoft Teams pour que le plug-in soit déployé.</span><span class="sxs-lookup"><span data-stu-id="a89d2-118">Allow scheduling for private meetings must be enabled in the Microsoft Teams admin center for the plug-in to get deployed.</span></span> <span data-ttu-id="a89d2-119">Dans le centre d’administration, accédez à **Réunions** > **Stratégies de la réunion**, puis, dans la section**Général**, définissez\*\*Autoriser la planification des réunions privées \*\* vers sur.)</span><span class="sxs-lookup"><span data-stu-id="a89d2-119">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Capture d’écran des paramètres dans le centre d’administration de Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="a89d2-121">Le client Teams installe le complément correct en déterminant si les utilisateurs ont besoin de la version 32 bits ou 64 bits.</span><span class="sxs-lookup"><span data-stu-id="a89d2-121">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="a89d2-122">Il est possible que les utilisateurs doivent redémarrer Outlook après une installation ou mise à niveau de Teams pour obtenir le complément le plus récent.</span><span class="sxs-lookup"><span data-stu-id="a89d2-122">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="a89d2-123">Autres considérations à prendre en compte</span><span class="sxs-lookup"><span data-stu-id="a89d2-123">Other considerations</span></span>

<span data-ttu-id="a89d2-124">Certaines fonctionnalités du complément Réunion Teams sont encore en cours de création. Tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="a89d2-124">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="a89d2-125">Certaines fonctionnalités de réunion en ligne, comme l'enregistrement, les sondages et l'utilisation du tableau blanc ne sont pas encore disponibles.</span><span class="sxs-lookup"><span data-stu-id="a89d2-125">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="a89d2-126">Des options de réunion ne sont pas disponibles pour le moment.</span><span class="sxs-lookup"><span data-stu-id="a89d2-126">Meeting options are currently not available.</span></span>
- <span data-ttu-id="a89d2-127">Actuellement, vous pouvez uniquement inviter des personnes de votre entreprise, car les utilisateurs externes ne peuvent pas encore participer aux réunions.</span><span class="sxs-lookup"><span data-stu-id="a89d2-127">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="a89d2-128">Le complément concerne les réunions planifiées avec des participants spécifiques, pas les réunions dans un canal.</span><span class="sxs-lookup"><span data-stu-id="a89d2-128">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="a89d2-129">Les réunions de canal doivent être planifiées au sein de Teams.</span><span class="sxs-lookup"><span data-stu-id="a89d2-129">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="a89d2-130">Actuellement, le complément Réunion Teams dans Outlook est disponible uniquement pour les utilisateurs Windows, mais il sera pris en charge sur Mac prochainement.</span><span class="sxs-lookup"><span data-stu-id="a89d2-130">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="a89d2-131">Le complément ne fonctionnera pas si un proxy d'authentification se trouve dans le chemin d'accès réseau de l'ordinateur de l'utilisateur et des services Teams.</span><span class="sxs-lookup"><span data-stu-id="a89d2-131">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="a89d2-132">Le complément est déployé de façon incrémentielle et ne peut pas être encore disponible pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a89d2-132">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a89d2-133">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="a89d2-133">Troubleshooting</span></span>

<span data-ttu-id="a89d2-134">Si vous ne parvenez pas à obtenir le complément de la réunion Teams pour installer Outlook, essayez de suivre ces étapes de dépannage.</span><span class="sxs-lookup"><span data-stu-id="a89d2-134">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="a89d2-135">Assurez-vous que toutes les mises à jour disponibles pour le client de bureau Outlook aient été appliquées</span><span class="sxs-lookup"><span data-stu-id="a89d2-135">Ensure all available updates for Outlook desktop client have been applied</span></span> 
- <span data-ttu-id="a89d2-136">Redémarrez le client de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="a89d2-136">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="a89d2-137">Déconnectez-vous, puis reconnectez-vous pour le client de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="a89d2-137">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="a89d2-138">Fermez le client Outlook pour ordinateur de bureau.</span><span class="sxs-lookup"><span data-stu-id="a89d2-138">Restart the Outlook desktop client.</span></span> <span data-ttu-id="a89d2-139">(Veillez à ce qu' Outlook ne soit pas exécuté en mode d’administration.)</span><span class="sxs-lookup"><span data-stu-id="a89d2-139">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="a89d2-140">Vérifiez que le nom du compte utilisateur connecté ne contienne pas d’espaces.</span><span class="sxs-lookup"><span data-stu-id="a89d2-140">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="a89d2-141">(Il s’agit d’un problème connu qui sera corrigé dans une prochaine mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="a89d2-141">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="a89d2-142">Vérifiez que l’authentification unique de Yammer ne soit pas activée.</span><span class="sxs-lookup"><span data-stu-id="a89d2-142">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="a89d2-143">Pour des orientations générales sur la procédure de désactivation des compléments, consultez la rubrique [Afficher, gérer et installer des compléments dans les programmes Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="a89d2-143">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="a89d2-144">Découvrez les [réunions et les appels dans Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="a89d2-144">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

