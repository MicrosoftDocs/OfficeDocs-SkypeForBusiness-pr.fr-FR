---
title: Ajouter un invité à une équipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
localization_priority: Priority
description: Découvrez les outils mis à la disposition d’un administrateur pour ajouter de nouveaux utilisateurs invités à une organisation, notamment la version de bureau et les clients Web Microsoft teams ainsi que le portail de collaboration inter-entreprise d’Azure Active Directory.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67a00b87dbe3f29ce6588d4ff84302df2f07ce69
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221633"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="94be8-103">Ajouter un invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="94be8-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="94be8-104">Toutes les personnes ayant un compte de messagerie professionnel ou un compte de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="94be8-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="94be8-105">En tant qu’administrateur, vous pouvez ajouter un nouvel utilisateur invité à l’organisation de deux manières :</span><span class="sxs-lookup"><span data-stu-id="94be8-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span>
- <span data-ttu-id="94be8-106">Les administrateurs généraux qui sont propriétaires d’une équipe et les propriétaires d’une équipe peuvent ajouter un invité à une équipe par le biais de la version de bureau de Microsoft teams ou des clients Web.</span><span class="sxs-lookup"><span data-stu-id="94be8-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span> <span data-ttu-id="94be8-107">Pour plus d’informations, voir [Ajouter des invités à une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="94be8-107">For more details, check out [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span></span>
- <span data-ttu-id="94be8-108">Ajoutez des invités à votre organisation via Azure Active Directory (Azure AD) B2B Collaboration.</span><span class="sxs-lookup"><span data-stu-id="94be8-108">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="94be8-109">Azure AD B2B Collaboration permet à un administrateur général d’inviter et d’autoriser un ensemble d’utilisateurs externes en chargeant un fichier de valeurs séparées par des virgules (CSV) comportant au maximum 2 000 lignes via le portail de collaboration B2B.</span><span class="sxs-lookup"><span data-stu-id="94be8-109">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="94be8-110">Pour plus d’informations, voir [Azure Active Directory B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="94be8-110">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="94be8-111">Azure AD B2B Collaboration permet aux organisations d'imposer un accès conditionnel et des stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B.</span><span class="sxs-lookup"><span data-stu-id="94be8-111">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="94be8-112">Ces stratégies peuvent être appliquées au niveau locataire, application ou utilisateur individuel, de la même façon qu’elles peuvent être activées pour les employés à plein temps et les membres de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="94be8-112">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="94be8-113">Les stratégies MFA sont appliquées à l’organisation de ressources.</span><span class="sxs-lookup"><span data-stu-id="94be8-113">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="94be8-114">Pour plus d’informations, consultez la page [Accès conditionnel pour les utilisateurs B2B Collaboration](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="94be8-114">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="94be8-115">Non, il n’est pas possible de bloquer des utilisateurs invités individuels.</span><span class="sxs-lookup"><span data-stu-id="94be8-115">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="94be8-116">Les invités que vous avez déjà ajoutés via Azure AD B2B, des Groupes Office 365 ou SharePoint Online sont déjà prêts.</span><span class="sxs-lookup"><span data-stu-id="94be8-116">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="94be8-117">L’administrateur 365 d’Office ou un propriétaire d’équipe peut ajouter ces invités à leurs équipes respectives.</span><span class="sxs-lookup"><span data-stu-id="94be8-117">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="94be8-118">Si une équipe est déjà associée à un groupe Office 365 et qu’un invité est ajouté au groupe, celui-ci est accessible à l’équipe.</span><span class="sxs-lookup"><span data-stu-id="94be8-118">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="94be8-119">L’ajout d’un invité par le biais du groupe Office 365 ne génère pas de message d’invitation à l’invité, de sorte qu’une personne de l’équipe doit avertir l’invité.</span><span class="sxs-lookup"><span data-stu-id="94be8-119">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="94be8-120">Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="94be8-120">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="94be8-121">Vous pouvez suivre l'ajout d'invités dans Azure AD ou dans le Centre de conformité de la sécurité &amp; d'Office 365.</span><span class="sxs-lookup"><span data-stu-id="94be8-121">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="94be8-122">L’ajout d’un invité dans Microsoft teams est audité et consigné en tant qu’activité d’administration des groupes Azure AD «membre ajouté au groupe».</span><span class="sxs-lookup"><span data-stu-id="94be8-122">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="94be8-123">Pour plus d’informations, [voir audit et création de rapports sur un](https://go.microsoft.com/fwlink/p/?linkid=858884) utilisateur [de collaboration B2B et effectuez une recherche dans le &amp; journal d'](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)audit dans le centre de conformité de la sécurité Office 365.</span><span class="sxs-lookup"><span data-stu-id="94be8-123">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="94be8-124">Accès invité et accès externe (fédération)</span><span class="sxs-lookup"><span data-stu-id="94be8-124">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="94be8-125">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="94be8-125">More information</span></span>

[<span data-ttu-id="94be8-126">Autoriser l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94be8-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="94be8-127">Activer ou désactiver l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94be8-127">Turn on or off guest access to Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="94be8-128">Utiliser PowerShell pour contrôler l’accès invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="94be8-128">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
