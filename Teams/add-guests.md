---
title: Ajouter un invité à une équipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/31/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
description: Découvrez les outils disponibles pour qu'un administrateur ajoute de nouveaux utilisateurs invités à une organisation, y compris les clients web et de bureau de Microsoft Teams et le portail de collaboration Azure Active Directory B2B.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27f1f344313111561c9f1c3a5e57dc1bd0ae20cb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202871"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="4f0bb-103">Ajouter un invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="4f0bb-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="4f0bb-104">Toute personne possédant un compte de messagerie consommateur ou de l’entreprise, comme Outlook, Gmail ou d’autres personnes, peut participer à en tant qu’invité dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="4f0bb-105">En tant qu'administrateur, vous pouvez ajouter un nouvel utilisateur invité à l'organisation de deux manières :</span><span class="sxs-lookup"><span data-stu-id="4f0bb-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="4f0bb-106">Les administrateurs globaux qui sont propriétaires d'une équipe et les propriétaires d'équipe peuvent ajouter un invité à une équipe via les clients de bureau ou Web Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span> <span data-ttu-id="4f0bb-107">Pour plus d’informations, consultez la rubrique [Ajouter des invités à une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span><span class="sxs-lookup"><span data-stu-id="4f0bb-107">For more details, check out [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span></span>
- <span data-ttu-id="4f0bb-108">Ajoutez des invités à votre organisation via Azure Active Directory B2B Collaboration.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-108">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="4f0bb-109">Azure Active Directory B2B Collaboration permet à un administrateur global d'inviter et d'autoriser un ensemble d'utilisateurs externes en chargeant un fichier de valeurs séparées par des virgules (CSV) de 2 000 lignes au maximum dans le portail B2B Collaboration.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-109">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="4f0bb-110">Pour plus d'informations, consultez la section [Azure Active Directory B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="4f0bb-110">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="4f0bb-111">Azure Active Directory B2B Collaboration permet aux organisations d'imposer l'accès conditionnel et les stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-111">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="4f0bb-112">Ces stratégies peuvent être imposées au niveau du client, de l'application ou d'un utilisateur spécifique, de la même manière qu'elles sont activées pour les employés à plein temps et les membres de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-112">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="4f0bb-113">Ces stratégies sont imposées au niveau de l'organisation des ressources.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-113">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="4f0bb-114">Pour plus d'informations, reportez-vous à la rubrique [Accès conditionnel pour les utilisateurs de B2B collaboration](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="4f0bb-114">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="4f0bb-115">Les utilisateurs invités individuels ne peuvent pas être bloqués.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-115">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="4f0bb-116">Les utilisateurs invités que vous avez déjà été ajoutés par le biais d’Azure Active Directory B2B, groupes d’Office 365 ou SharePoint Online êtes prêts à commencer.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-116">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="4f0bb-117">L'administrateur Office 365 ou un propriétaire d'équipe peut les ajouter dans ses équipes respectives.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-117">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="4f0bb-118">Si une équipe est déjà rattachée à un groupe Office 365 et qu'un invité est ajouté au groupe, l'invité obtient l'accès à l'équipe.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-118">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="4f0bb-119">L'ajout d'un invité via le groupe Office 365 ne génère pas d'e-mail d'invitation, un membre de l'équipe devra donc l'en informer.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-119">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="4f0bb-120">Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="4f0bb-120">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="4f0bb-121">Vous pouvez suivre l'ajout d'invités dans Azure Active Directory ou dans le Centre de sécurité &amp; conformité d'Office 365.</span><span class="sxs-lookup"><span data-stu-id="4f0bb-121">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="4f0bb-122">L'ajout d'un invité dans Microsoft Teams est audité et journalisé comme activité d'administration de groupe Azure AD « Membre ajouté au groupe ».</span><span class="sxs-lookup"><span data-stu-id="4f0bb-122">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="4f0bb-123">Pour plus de détails, reportez-vous aux documents [Audit et création de rapports relatifs à un utilisateur B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=858884) et [Effectuer des recherches dans le journal d'audit dans le Centre de sécurité &amp; conformité d'Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="4f0bb-123">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="4f0bb-124">Accès invité et accès externe (fédération)</span><span class="sxs-lookup"><span data-stu-id="4f0bb-124">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="4f0bb-125">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="4f0bb-125">More information</span></span>

[<span data-ttu-id="4f0bb-126">Autoriser l'accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f0bb-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="4f0bb-127">Activer ou désactiver l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f0bb-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="4f0bb-128">Utiliser PowerShell pour contrôler l'accès invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="4f0bb-128">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
