---
title: Utiliser le complément Réunion Microsoft Teams dans Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 10/02/2018
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
ms.openlocfilehash: 1c0252d3bf8420711d67aec33aab1041cfe7eb1b
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463131"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="65e6e-103">Utiliser le complément Réunion Teams dans Outlook</span><span class="sxs-lookup"><span data-stu-id="65e6e-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="65e6e-104">Le complément Réunion Teams est installé automatiquement pour les utilisateurs pour lesquels Microsoft Teams et Office 2013 ou Office 2016 sont installés sur leur PC Windows.</span><span class="sxs-lookup"><span data-stu-id="65e6e-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="65e6e-105">Le complément Réunion Teams apparaît sur le ruban Calendrier d'Outlook.</span><span class="sxs-lookup"><span data-stu-id="65e6e-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Capture d'écran du complément Teams sur le ruban Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> <span data-ttu-id="65e6e-107">Les utilisateurs de Windows 7 doivent installer [mise à jour pour Universal Runtime C dans Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) pour le complément de réunion équipes pour travailler.</span><span class="sxs-lookup"><span data-stu-id="65e6e-107">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>

<span data-ttu-id="65e6e-108">Si le complément Réunion Teams n'apparaît pas, demandez aux utilisateurs de fermer Outlook et Teams, de redémarrer d'abord le client Teams, de se connecter à Teams puis de redémarrer le client Outlook, dans cet ordre spécifique.</span><span class="sxs-lookup"><span data-stu-id="65e6e-108">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="65e6e-109">Le complément Réunion Teams n'est pas disponible actuellement pour les utilisateurs Mac.</span><span class="sxs-lookup"><span data-stu-id="65e6e-109">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="65e6e-110">Exigences d'authentification</span><span class="sxs-lookup"><span data-stu-id="65e6e-110">Authentication requirements</span></span>

<span data-ttu-id="65e6e-111">Le complément Réunion Teams requiert de se connecter à Teams en utilisant l'authentification moderne.</span><span class="sxs-lookup"><span data-stu-id="65e6e-111">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="65e6e-112">Si les utilisateurs n'utilisent pas cette méthode pour se connecter, ils pourront continuer à utiliser le client Teams mais ne pourront pas planifier de réunions en ligne Teams à l'aide du complément Outlook.</span><span class="sxs-lookup"><span data-stu-id="65e6e-112">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="65e6e-113">Vous pouvez résoudre ce problème de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="65e6e-113">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="65e6e-114">Si l'authentification moderne n'est pas configurée pour votre organisation, vous devez la configurer.</span><span class="sxs-lookup"><span data-stu-id="65e6e-114">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="65e6e-115">Si l'authentification moderne est configurée, mais qu'ils l'ont annulée dans la boîte de dialogue, vous devez demander aux utilisateurs de se connecter à nouveau en utilisant l'authentification multifacteur.</span><span class="sxs-lookup"><span data-stu-id="65e6e-115">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="65e6e-116">Pour savoir comment configurer l'authentification, reportez-vous à la rubrique [Modèles d'identité et authentification dans Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="65e6e-116">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="65e6e-117">Activer les réunions privées</span><span class="sxs-lookup"><span data-stu-id="65e6e-117">Enable private meetings</span></span>

<span data-ttu-id="65e6e-118">Autoriser la planification pour les réunions privées doit être activée dans le centre d’administration Microsoft Teams du plug-in à déployer.</span><span class="sxs-lookup"><span data-stu-id="65e6e-118">Allow scheduling for private meetings must be enabled in the Microsoft Teams admin center for the plug-in to get deployed.</span></span> <span data-ttu-id="65e6e-119">Dans le centre d’administration, accédez à des **réunions** > de**Stratégies de réunion**et dans la section **Général** , bascule **Autoriser la planification de réunions privées** on.)</span><span class="sxs-lookup"><span data-stu-id="65e6e-119">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Capture d’écran des paramètres dans le centre d’administration équipes Microsoft.](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="65e6e-121">Le client Teams installe le complément correct en déterminant si les utilisateurs ont besoin de la version 32 bits ou 64 bits.</span><span class="sxs-lookup"><span data-stu-id="65e6e-121">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="65e6e-122">Il est possible que les utilisateurs doivent redémarrer Outlook après une installation ou mise à niveau de Teams pour obtenir le complément le plus récent.</span><span class="sxs-lookup"><span data-stu-id="65e6e-122">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="65e6e-123">Autres considérations</span><span class="sxs-lookup"><span data-stu-id="65e6e-123">Other considerations</span></span>

<span data-ttu-id="65e6e-124">Certaines fonctionnalités du complément Réunion Teams sont encore en cours de création. Tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="65e6e-124">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="65e6e-125">Certaines fonctionnalités de réunion en ligne, comme l'enregistrement, les sondages et l'utilisation du tableau blanc ne sont pas encore disponibles.</span><span class="sxs-lookup"><span data-stu-id="65e6e-125">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="65e6e-126">Des options de réunion ne sont pas disponibles pour le moment.</span><span class="sxs-lookup"><span data-stu-id="65e6e-126">Meeting options are currently not available.</span></span>
- <span data-ttu-id="65e6e-127">Actuellement, vous pouvez uniquement inviter des personnes de votre entreprise, car les utilisateurs externes ne peuvent pas encore participer aux réunions.</span><span class="sxs-lookup"><span data-stu-id="65e6e-127">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="65e6e-128">Le complément concerne les réunions planifiées avec des participants spécifiques, pas les réunions dans un canal.</span><span class="sxs-lookup"><span data-stu-id="65e6e-128">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="65e6e-129">Les réunions de canal doivent être planifiées au sein de Teams.</span><span class="sxs-lookup"><span data-stu-id="65e6e-129">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="65e6e-130">Actuellement, le complément Réunion Teams dans Outlook est disponible uniquement pour les utilisateurs Windows, mais il sera pris en charge sur Mac prochainement.</span><span class="sxs-lookup"><span data-stu-id="65e6e-130">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="65e6e-131">Le complément ne fonctionnera pas si un proxy d'authentification se trouve dans le chemin d'accès réseau de l'ordinateur de l'utilisateur et des services Teams.</span><span class="sxs-lookup"><span data-stu-id="65e6e-131">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="65e6e-132">Le complément est déployée incrémentielle et peuvent ne pas être disponible pour votre organisation encore.</span><span class="sxs-lookup"><span data-stu-id="65e6e-132">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="65e6e-133">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="65e6e-133">Troubleshooting</span></span>

<span data-ttu-id="65e6e-134">Si vous ne peut pas obtenir la réunion équipes de complément pour Outlook pour installer, essayez les étapes de dépannage.</span><span class="sxs-lookup"><span data-stu-id="65e6e-134">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="65e6e-135">Vérifiez que toutes les mises à jour disponibles pour le client de bureau Outlook ont été appliquées.</span><span class="sxs-lookup"><span data-stu-id="65e6e-135">Ensure all available updates for Outlook desktop client have been applied</span></span> 
- <span data-ttu-id="65e6e-136">Redémarrez le client de bureau équipes.</span><span class="sxs-lookup"><span data-stu-id="65e6e-136">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="65e6e-137">Déconnectez-vous, puis reconnectez-vous pour le client de bureau équipes.</span><span class="sxs-lookup"><span data-stu-id="65e6e-137">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="65e6e-138">Redémarrez le client de bureau Outlook.</span><span class="sxs-lookup"><span data-stu-id="65e6e-138">Restart the Outlook desktop client.</span></span> <span data-ttu-id="65e6e-139">(Assurez-vous que Outlook n’est pas en cours d’exécution en mode administrateur).</span><span class="sxs-lookup"><span data-stu-id="65e6e-139">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="65e6e-140">Assurez-vous que le nom du compte utilisateur connecté ne contient-elle pas d’espaces.</span><span class="sxs-lookup"><span data-stu-id="65e6e-140">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="65e6e-141">(Ceci est un problème connu et sera corrigé dans une prochaine mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="65e6e-141">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="65e6e-142">Assurez-vous que l’authentification unique (SSO) est activée.</span><span class="sxs-lookup"><span data-stu-id="65e6e-142">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="65e6e-143">Pour des orientations générales sur la procédure de désactivation des compléments, consultez la rubrique [Afficher, gérer et installer des compléments dans les programmes Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="65e6e-143">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="65e6e-144">Découvrez les [réunions et les appels dans Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="65e6e-144">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

