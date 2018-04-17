---
title: Utiliser le complément Réunion Microsoft Teams dans Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 04/09/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
localization_priority: Normal
description: Microsoft Teams installe un complément dans Outlook qui permet aux utilisateurs de planifier une réunion Teams depuis Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 109911e27a881ea09fb9854bb84ab19222722c39
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="9421c-103">Utiliser le complément Réunion Teams dans Outlook</span><span class="sxs-lookup"><span data-stu-id="9421c-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="9421c-104">Le complément Réunion Teams est installé automatiquement pour les utilisateurs pour lesquels Microsoft Teams et Office 2013 ou Office 2016 sont installés sur leur PC Windows.</span><span class="sxs-lookup"><span data-stu-id="9421c-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="9421c-105">Le complément Réunion Teams apparaît sur le ruban Calendrier d'Outlook.</span><span class="sxs-lookup"><span data-stu-id="9421c-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Capture d'écran du complément Teams sur le ruban Outlook.](media/Teams-add-in-for-Outlook.png)

<span data-ttu-id="9421c-107">Si le complément Réunion Teams n'apparaît pas, demandez aux utilisateurs de fermer Outlook et Teams, de redémarrer d'abord le client Teams, de se connecter à Teams puis de redémarrer le client Outlook, dans cet ordre spécifique.</span><span class="sxs-lookup"><span data-stu-id="9421c-107">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="9421c-108">Le complément Réunion Teams n'est pas disponible actuellement pour les utilisateurs Mac.</span><span class="sxs-lookup"><span data-stu-id="9421c-108">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="9421c-109">Exigences d'authentification</span><span class="sxs-lookup"><span data-stu-id="9421c-109">Authentication requirements</span></span>

<span data-ttu-id="9421c-110">Le complément Réunion Teams requiert de se connecter à Teams en utilisant l'authentification moderne.</span><span class="sxs-lookup"><span data-stu-id="9421c-110">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="9421c-111">Si les utilisateurs n'utilisent pas cette méthode pour se connecter, ils pourront continuer à utiliser le client Teams mais ne pourront pas planifier de réunions en ligne Teams à l'aide du complément Outlook.</span><span class="sxs-lookup"><span data-stu-id="9421c-111">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="9421c-112">Vous pouvez résoudre ce problème de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="9421c-112">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="9421c-113">Si l'authentification moderne n'est pas configurée pour votre organisation, vous devez la configurer.</span><span class="sxs-lookup"><span data-stu-id="9421c-113">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="9421c-114">Si l'authentification moderne est configurée, mais qu'ils l'ont annulée dans la boîte de dialogue, vous devez demander aux utilisateurs de se connecter à nouveau en utilisant l'authentification multifacteur.</span><span class="sxs-lookup"><span data-stu-id="9421c-114">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="9421c-115">Pour savoir comment configurer l'authentification, reportez-vous à la rubrique [Modèles d'identité et authentification dans Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="9421c-115">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="9421c-116">Activer les réunions privées</span><span class="sxs-lookup"><span data-stu-id="9421c-116">Enable private meetings</span></span>

<span data-ttu-id="9421c-117">L'autorisation de planification de réunions privées doit être activée depuis le [Centre d'administration Office 365](https://portal.office.com/adminportal/home) pour que le plug-in soit déployé.</span><span class="sxs-lookup"><span data-stu-id="9421c-117">Allow scheduling for private meetings must be enabled from the [Office 365 admin center](https://portal.office.com/adminportal/home) for the plug-in to get deployed.</span></span>

![Capture d'écran des paramètres dans la section Appels et réunions du Centre d'administration d’Office 365.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="9421c-119">Le client Teams installe le complément correct en déterminant si les utilisateurs ont besoin de la version 32 bits ou 64 bits.</span><span class="sxs-lookup"><span data-stu-id="9421c-119">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="9421c-120">Il est possible que les utilisateurs doivent redémarrer Outlook après une installation ou mise à niveau de Teams pour obtenir le complément le plus récent.</span><span class="sxs-lookup"><span data-stu-id="9421c-120">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="9421c-121">Autres considérations</span><span class="sxs-lookup"><span data-stu-id="9421c-121">Other considerations</span></span>

<span data-ttu-id="9421c-122">Certaines fonctionnalités du complément Réunion Teams sont encore en cours de création. Tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="9421c-122">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="9421c-123">Certaines fonctionnalités de réunion en ligne, comme l'enregistrement, les sondages et l'utilisation du tableau blanc ne sont pas encore disponibles.</span><span class="sxs-lookup"><span data-stu-id="9421c-123">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="9421c-124">Des options de réunion ne sont pas disponibles pour le moment.</span><span class="sxs-lookup"><span data-stu-id="9421c-124">Meeting options are currently not available.</span></span>
- <span data-ttu-id="9421c-125">Actuellement, vous pouvez uniquement inviter des personnes de votre entreprise, car les utilisateurs externes ne peuvent pas encore participer aux réunions.</span><span class="sxs-lookup"><span data-stu-id="9421c-125">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="9421c-126">Le complément concerne les réunions planifiées avec des participants spécifiques, pas les réunions dans un canal.</span><span class="sxs-lookup"><span data-stu-id="9421c-126">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="9421c-127">Les réunions de canal doivent être planifiées au sein de Teams.</span><span class="sxs-lookup"><span data-stu-id="9421c-127">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="9421c-128">Actuellement, le complément Réunion Teams dans Outlook est disponible uniquement pour les utilisateurs Windows, mais il sera pris en charge sur Mac prochainement.</span><span class="sxs-lookup"><span data-stu-id="9421c-128">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="9421c-129">Le complément ne fonctionnera pas si un proxy d'authentification se trouve dans le chemin d'accès réseau de l'ordinateur de l'utilisateur et des services Teams.</span><span class="sxs-lookup"><span data-stu-id="9421c-129">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9421c-130">Identification et résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="9421c-130">Troubleshooting</span></span>

<span data-ttu-id="9421c-131">Si vous ne parvenez pas la réunion des équipes de complément pour Outlook pour installer, essayez les étapes de dépannage.</span><span class="sxs-lookup"><span data-stu-id="9421c-131">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="9421c-132">Redémarrer le client de bureau d’équipes.</span><span class="sxs-lookup"><span data-stu-id="9421c-132">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="9421c-133">Se déconnecter et de vous connecter de nouveau au client Bureau équipes.</span><span class="sxs-lookup"><span data-stu-id="9421c-133">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="9421c-134">Redémarrer le client de bureau Outlook.</span><span class="sxs-lookup"><span data-stu-id="9421c-134">Restart the Outlook desktop client.</span></span> <span data-ttu-id="9421c-135">(Assurez-vous que Outlook n’est pas exécuté en mode administrateur.)</span><span class="sxs-lookup"><span data-stu-id="9421c-135">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="9421c-136">Assurez-vous que le nom du compte utilisateur connecté ne contient-elle pas d’espaces.</span><span class="sxs-lookup"><span data-stu-id="9421c-136">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="9421c-137">(Ceci est un problème connu et sera résolu dans une future mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="9421c-137">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="9421c-138">Assurez-vous que l’authentification unique (SSO) est activé.</span><span class="sxs-lookup"><span data-stu-id="9421c-138">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="9421c-139">Pour des orientations générales sur la procédure de désactivation des compléments, consultez la rubrique [Afficher, gérer et installer des compléments dans les programmes Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="9421c-139">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="9421c-140">Découvrez les [réunions et les appels dans Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="9421c-140">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>
