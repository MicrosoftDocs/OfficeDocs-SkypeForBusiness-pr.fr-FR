---
title: Configurer l’application Réunions Skype pour qu’elle fonctionne avec Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
description: Les administrateurs peuvent utiliser le centre Microsoft Teams d’administration pour configurer l’Skype réunions de l’utilisateur avec Teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29887ee89c8db36e6d5116118e0ec4fbc2a3e0ff
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856443"
---
# <a name="configure-the-skype-meetings-app-to-work-with-teams"></a><span data-ttu-id="6a734-103">Configurer l’application Réunions Skype pour qu’elle fonctionne avec Teams</span><span class="sxs-lookup"><span data-stu-id="6a734-103">Configure the Skype Meetings App to work with Teams</span></span>

<span data-ttu-id="6a734-104">Après la mise à niveau d’un utilisateur vers Microsoft Teams, les administrateurs peuvent utiliser le Centre d’administration Microsoft Teams pour spécifier l’application préférée que les utilisateurs utiliseront pour rejoindre Skype Entreprise réunions.</span><span class="sxs-lookup"><span data-stu-id="6a734-104">After a user is upgraded to Microsoft Teams, admins can use the Microsoft Teams admin center to specify the preferred app that users will use to join Skype for Business meetings.</span></span>

<span data-ttu-id="6a734-105">Pour spécifier l Skype application Réunions comme application préférée :</span><span class="sxs-lookup"><span data-stu-id="6a734-105">To specify the Skype for Meetings App as the preferred app:</span></span>

1. <span data-ttu-id="6a734-106">Se connecter au centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6a734-106">Sign in to the Microsoft Teams admin center.</span></span>
2. <span data-ttu-id="6a734-107">Dans le volet gauche, sous **Paramètres** à l’échelle de l’organisation, **sélectionnez Teams mise à niveau.**</span><span class="sxs-lookup"><span data-stu-id="6a734-107">In the left pane, under **Org-wide settings**, select **Teams upgrade**.</span></span>
3. <span data-ttu-id="6a734-108">Dans la page Teams mise à niveau,  sous Préférences d’application, sélectionnez l’application Réunions Skype dans l’application Preferred (Preferred) pour que les **utilisateurs** participent à Skype Entreprise liste de listes dans la liste suivante.</span><span class="sxs-lookup"><span data-stu-id="6a734-108">On the Teams upgrade page, under **App preferences**, select **Skype Meetings App**  from the **Preferred app for users to join Skype for Business meetings** drop-down list.</span></span>

    ![Sélectionnez l’application Préférée pour que les utilisateurs participent Skype Entreprise réunions](media/teams-configure-skype-meetings-app-to-work-with-teams-image1.png)

## <a name="known-limitations"></a><span data-ttu-id="6a734-110">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="6a734-110">Known limitations</span></span>

<span data-ttu-id="6a734-111">Les utilisateurs qui utilisent Skype’application Réunions avec Teams sont soumis aux limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a734-111">Users who use the Skype Meetings App with Teams are subject to the following limitations:</span></span>

- <span data-ttu-id="6a734-112">Les utilisateurs n’ont pas la possibilité de modifier leur périphérique vidéo.</span><span class="sxs-lookup"><span data-stu-id="6a734-112">Users have no option to change their video device.</span></span>
- <span data-ttu-id="6a734-113">Après la mise à niveau d’un utilisateur vers Teams, si l’utilisateur se trouve dans une réunion à l’aide de l’application Réunions Skype puis reçoit un appel sur Teams, la réunion dans l’application Réunions Skype n’est pas mise en attente.</span><span class="sxs-lookup"><span data-stu-id="6a734-113">After a user is upgraded to Teams, if the user is in a meeting using the Skype Meetings App and then receives a call on Teams, the meeting in Skype Meetings App is not placed on hold.</span></span> <span data-ttu-id="6a734-114">Au lieu de cela, l’utilisateur est connecté aux deux appels.</span><span class="sxs-lookup"><span data-stu-id="6a734-114">Instead, the user is connected to both calls.</span></span>

## <a name="more-information"></a><span data-ttu-id="6a734-115">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="6a734-115">More information</span></span>

- [<span data-ttu-id="6a734-116">Qu’est-Skype’application Réunions (Application Web Skype Entreprise)</span><span class="sxs-lookup"><span data-stu-id="6a734-116">What is Skype Meetings App (Skype for Business Web App)</span></span>](https://support.office.microsoft.com/article/what-is-skype-meetings-app-skype-for-business-web-app-1ff3d412-718a-4982-8ff2-a4992608cdb5)
- <span data-ttu-id="6a734-117">[Configuration réseau minimale requise pour l’application Réunions Skype](/previous-versions/office/communications/mt845808(v=ocs.16))</span><span class="sxs-lookup"><span data-stu-id="6a734-117">[Skype Meetings App minimum network requirements](/previous-versions/office/communications/mt845808(v=ocs.16))</span></span>