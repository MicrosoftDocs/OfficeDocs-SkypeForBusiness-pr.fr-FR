---
title: Activer ou désactiver l'accès invité de Microsoft Teams
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Activer ou désactiver la fonctionnalité d’accès invité dans Microsoft Teams
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498120"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="bbba6-103">Activer ou désactiver l'accès invité de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbba6-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="bbba6-104">En tant qu'administrateur d'Office 365, vous devez activer la fonctionnalité Invité pour que vous ou les utilisateurs de votre organisation (notamment les propriétaires d'équipe) puissiez ajouter des invités.</span><span class="sxs-lookup"><span data-stu-id="bbba6-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="bbba6-105">Les paramètres d'invité sont définis dans Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bbba6-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="bbba6-106">Il faut environ 2 à 24 heures pour que les modifications prennent effet dans votre organisation Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbba6-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="bbba6-107">Si un utilisateur voit le message « Contactez votre administrateur » lorsqu'il essaye d'ajouter un invité à son équipe, il est probable que la fonctionnalité d'invité ne soit pas activée ou que les paramètres ne sont pas encore actifs.</span><span class="sxs-lookup"><span data-stu-id="bbba6-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="bbba6-108">Pour activer l’expérience complète de la fonctionnalité d’accès invité, il est important de comprendre la dépendance des autorisations principales entre Microsfot Teams, Azure Active Directory et Office 365.</span><span class="sxs-lookup"><span data-stu-id="bbba6-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="bbba6-109">Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="bbba6-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a><span data-ttu-id="bbba6-110">Configurer l’accès invité dans les équipes & Skype entreprise centre d’administration</span><span class="sxs-lookup"><span data-stu-id="bbba6-110">Configure guest access in the Teams & Skype for Business admin center</span></span>

1.  <span data-ttu-id="bbba6-111">Connectez-vous au portail les équipes & Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="bbba6-111">Sign in to the Teams & Skype for Business admin center.</span></span>

2.  <span data-ttu-id="bbba6-112">Sélectionnez les **paramètres à l’échelle de la société** > **accès invité**.</span><span class="sxs-lookup"><span data-stu-id="bbba6-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="bbba6-113">La valeur du bouton bascule **Autoriser l’accès invité dans les équipes Microsoft** **sur**.</span><span class="sxs-lookup"><span data-stu-id="bbba6-113">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="bbba6-114">Autoriser le commutateur d’accès invité activé</span><span class="sxs-lookup"><span data-stu-id="bbba6-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="bbba6-115">Définir la bascule pour **appel**, la **réunion**et **messagerie** **sur** ou **désactiver**, en fonction de l’accès que vous souhaitez autoriser.</span><span class="sxs-lookup"><span data-stu-id="bbba6-115">Set the toggles for **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the access you want to allow.</span></span>

5.  <span data-ttu-id="bbba6-116">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bbba6-116">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="bbba6-117">Utilisation de PowerShell pour activer ou désactiver les accès invité</span><span class="sxs-lookup"><span data-stu-id="bbba6-117">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="bbba6-118">Télécharger le Skype pour le module Business Online PowerShell à partir dehttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="bbba6-118">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="bbba6-119">Se connecter à une session PowerShell à la Skype pour le point de terminaison Business en ligne.</span><span class="sxs-lookup"><span data-stu-id="bbba6-119">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="bbba6-120">Vérifiez votre configuration et si `AllowGuestUser` est `$False`, utilisez l’applet de commande [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) pour le définir sur `$True`.</span><span class="sxs-lookup"><span data-stu-id="bbba6-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="bbba6-121">Vous pouvez maintenant avoir des utilisateurs invités dans les équipes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="bbba6-121">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="bbba6-122">Informations complémentaires</span><span class="sxs-lookup"><span data-stu-id="bbba6-122">More information</span></span>

<span data-ttu-id="bbba6-123">Regardez la vidéo suivante pour plus d’informations sur l’accès invité.</span><span class="sxs-lookup"><span data-stu-id="bbba6-123">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="bbba6-124">Ajout d'invités dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbba6-124">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
