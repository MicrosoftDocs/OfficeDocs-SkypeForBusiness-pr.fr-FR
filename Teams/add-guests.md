---
title: Ajouter un invité à une équipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: sbhatta
description: Découvrez les outils disponibles pour qu'un administrateur ajoute de nouveaux utilisateurs invités à une organisation, y compris les clients web et de bureau de Microsoft Teams et le portail de collaboration Azure Active Directory B2B.
appliesto:
- Microsoft Teams
ms.openlocfilehash: efd44fade33f611148dc2ab4ca9afb4040705123
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772739"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="25373-103">Ajouter un invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="25373-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="25373-104">Toute personne possédant un compte de messagerie consommateur ou de l’entreprise, comme Outlook, Gmail ou d’autres personnes, peut participer à en tant qu’invité dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="25373-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>


<span data-ttu-id="25373-105">En tant qu'administrateur, vous pouvez ajouter un nouvel utilisateur invité à l'organisation de deux manières :</span><span class="sxs-lookup"><span data-stu-id="25373-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="25373-106">Les administrateurs globaux qui sont propriétaires d'une équipe et les propriétaires d'équipe peuvent ajouter un invité à une équipe via les clients de bureau ou Web Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="25373-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span>
- <span data-ttu-id="25373-107">Ajoutez des invités à votre organisation via Azure Active Directory B2B Collaboration.</span><span class="sxs-lookup"><span data-stu-id="25373-107">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="25373-108">Azure Active Directory B2B Collaboration permet à un administrateur global d'inviter et d'autoriser un ensemble d'utilisateurs externes en chargeant un fichier de valeurs séparées par des virgules (CSV) de 2 000 lignes au maximum dans le portail B2B Collaboration.</span><span class="sxs-lookup"><span data-stu-id="25373-108">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="25373-109">Pour plus d'informations, consultez la section [Azure Active Directory B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="25373-109">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>



<span data-ttu-id="25373-110">Azure Active Directory B2B Collaboration permet aux organisations d'imposer l'accès conditionnel et les stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B.</span><span class="sxs-lookup"><span data-stu-id="25373-110">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="25373-111">Ces stratégies peuvent être imposées au niveau du client, de l'application ou d'un utilisateur spécifique, de la même manière qu'elles sont activées pour les employés à plein temps et les membres de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="25373-111">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="25373-112">Ces stratégies sont imposées au niveau de l'organisation des ressources.</span><span class="sxs-lookup"><span data-stu-id="25373-112">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="25373-113">Pour plus d'informations, reportez-vous à la rubrique [Accès conditionnel pour les utilisateurs de B2B collaboration](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="25373-113">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="25373-114">Les utilisateurs invités individuels ne peuvent pas être bloqués.</span><span class="sxs-lookup"><span data-stu-id="25373-114">Individual guest users can't be blocked.</span></span>



<span data-ttu-id="25373-115">Les utilisateurs invités que vous avez déjà été ajoutés par le biais d’Azure Active Directory B2B, groupes d’Office 365 ou SharePoint Online êtes prêts à commencer.</span><span class="sxs-lookup"><span data-stu-id="25373-115">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="25373-116">L'administrateur Office 365 ou un propriétaire d'équipe peut les ajouter dans ses équipes respectives.</span><span class="sxs-lookup"><span data-stu-id="25373-116">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="25373-117">Si une équipe est déjà rattachée à un groupe Office 365 et qu'un invité est ajouté au groupe, l'invité obtient l'accès à l'équipe.</span><span class="sxs-lookup"><span data-stu-id="25373-117">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="25373-118">L'ajout d'un invité via le groupe Office 365 ne génère pas d'e-mail d'invitation, un membre de l'équipe devra donc l'en informer.</span><span class="sxs-lookup"><span data-stu-id="25373-118">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="25373-119">Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="25373-119">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>



<span data-ttu-id="25373-120">Vous pouvez suivre l'ajout d'invités dans Azure Active Directory ou dans le Centre de sécurité &amp; conformité d'Office 365.</span><span class="sxs-lookup"><span data-stu-id="25373-120">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="25373-121">L'ajout d'un invité dans Microsoft Teams est audité et journalisé comme activité d'administration de groupe Azure AD « Membre ajouté au groupe ».</span><span class="sxs-lookup"><span data-stu-id="25373-121">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="25373-122">Pour plus de détails, reportez-vous aux documents [Audit et création de rapports relatifs à un utilisateur B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=858884) et [Effectuer des recherches dans le journal d'audit dans le Centre de sécurité &amp; conformité d'Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="25373-122">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="more-information"></a><span data-ttu-id="25373-123">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="25373-123">More information</span></span>

[<span data-ttu-id="25373-124">Autoriser l'accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25373-124">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="25373-125">Activer ou désactiver l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25373-125">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="25373-126">Utiliser PowerShell pour contrôler l'accès invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="25373-126">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)