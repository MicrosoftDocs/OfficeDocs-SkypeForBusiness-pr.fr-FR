---
title: Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler si les organisateurs peuvent utiliser des numéros gratuits pour leurs réunions.
ms.openlocfilehash: 6d37fdb6e85f6c1325c4ebea179ad54aab91fa4c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887379"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="1ea66-103">Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques</span><span class="sxs-lookup"><span data-stu-id="1ea66-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="1ea66-104">Si votre organisation possède des numéros gratuits dans son pont d’audioconférence Microsoft, vous pouvez autoriser ou interdire leur utilisation dans les réunions d’organisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1ea66-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="1ea66-105">Par défaut, tous les utilisateurs de votre organisation peuvent utiliser des numéros gratuits, ce qui signifie que si ces numéros sont disponibles, ils peuvent les utiliser pour participer à leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="1ea66-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="1ea66-106">Si vous souhaitez que certains utilisateurs de votre organisation ne puissent pas utiliser les numéros gratuits, vous pouvez leur interdire d’utiliser ces numéros dans leurs réunions via une commande d’activation des numéros gratuits.</span><span class="sxs-lookup"><span data-stu-id="1ea66-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="1ea66-107">Si les numéros gratuits sont désactivés pour un organisateur spécifique :</span><span class="sxs-lookup"><span data-stu-id="1ea66-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="1ea66-108">Un numéro gratuit ne sera plus inclus dans ses invitations à participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="1ea66-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="1ea66-109">Les numéros gratuits ne seront plus répertoriés sur la page « Rechercher un numéro local » qui est référencée dans ses invitations à participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="1ea66-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="1ea66-110">Les utilisateurs ne pourront plus participer à la réunion de cet organisateur spécifique s’ils composent un numéro gratuit de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="1ea66-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="1ea66-111">Toutes les réunions de l’organisateur seront replanifiées automatiquement et le numéro gratuit lui sera retiré.</span><span class="sxs-lookup"><span data-stu-id="1ea66-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="1ea66-112">Tous les courriers électroniques d’invitation de cet organisateur seront renvoyés à tous les participants à ces réunions.</span><span class="sxs-lookup"><span data-stu-id="1ea66-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="1ea66-113">Les utilisateurs peuvent continuer à participer aux réunions de l’organisateur en utilisant des numéros payants.</span><span class="sxs-lookup"><span data-stu-id="1ea66-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="1ea66-114">Désactiver les numéros gratuits pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="1ea66-114">Disabling toll-free numbers for specific users</span></span> 

1. <span data-ttu-id="1ea66-115">Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="1ea66-115">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="1ea66-116">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="1ea66-116">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="1ea66-117">En regard de l’option **Audioconférence**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="1ea66-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="1ea66-118">Désactivez l’option **Include toll-free numbers in meeting requests from this user** (Inclure des numéros gratuits dans les demandes de réunion envoyées par cet utilisateur).</span><span class="sxs-lookup"><span data-stu-id="1ea66-118">Turn off **Include toll-free numbers in meeting requests from this user**.</span></span> 

5. <span data-ttu-id="1ea66-119">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1ea66-119">Click **Save**.</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="1ea66-120">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1ea66-120">**Using Windows PowerShell**</span></span>  

<span data-ttu-id="1ea66-121">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="1ea66-121">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
