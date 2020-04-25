---
title: Ajouter un invité à une équipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: Les administrateurs peuvent apprendre à ajouter de nouveaux utilisateurs invités à une organisation dans le bureau et les clients Web Microsoft Teams ainsi que le portail de collaboration inter-entreprise d’Azure Active Directory.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 026fa191dffa160980bfb00e7031490f01ddc6cc
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778219"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="7ff1b-103">Ajouter un invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="7ff1b-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="7ff1b-104">Toutes les personnes ayant un compte de messagerie professionnel ou un compte de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="7ff1b-105">En tant qu’administrateur, vous pouvez ajouter un nouvel utilisateur invité à l’organisation de deux manières :</span><span class="sxs-lookup"><span data-stu-id="7ff1b-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>
- <span data-ttu-id="7ff1b-106">Les administrateurs généraux ou les administrateurs Teams et les propriétaires d’équipe ajoutent un invité à une équipe dans les clients Teams ou dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="7ff1b-107">Pour plus d’informations, voir [Ajouter des invités dans une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="7ff1b-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="7ff1b-108">Si vous n’avez pas encore configuré l’accès invité, suivez les étapes décrites dans la [liste de vérification de l’accès invité](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="7ff1b-108">If you haven't set up guest access yet, go through the steps in the [Guest access checklist](guest-access-checklist.md).</span></span>

> [!NOTE] 
> <span data-ttu-id="7ff1b-109">Cela ne s’applique pas lorsque la fonction **Les administrateurs et utilisateurs ayant le rôle d’inviteur invité peuvent inviter** est activée.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-109">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="7ff1b-110">En effet, le rôle d’inviteur d’invités n’est pas pris en charge dans Teams.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-110">This is because the guest inviter role isn't supported in Teams.</span></span>

- <span data-ttu-id="7ff1b-111">Ajoutez des invités à votre organisation via Azure Active Directory (Azure AD) B2B Collaboration.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-111">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="7ff1b-112">Azure AD B2B Collaboration permet à un administrateur général d’inviter et d’autoriser un ensemble d’utilisateurs externes en chargeant un fichier de valeurs séparées par des virgules (CSV) comportant au maximum 2 000 lignes via le portail de collaboration B2B.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-112">Azure AD B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="7ff1b-113">Pour plus d’informations, voir [Azure Active Directory B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="7ff1b-113">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="7ff1b-114">Azure AD B2B Collaboration permet aux organisations d'imposer un accès conditionnel et des stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-114">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="7ff1b-115">Ces stratégies peuvent être appliquées au niveau locataire, application ou utilisateur individuel, de la même façon qu’elles peuvent être activées pour les employés à plein temps et les membres de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-115">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="7ff1b-116">Les stratégies MFA sont appliquées à l’organisation de ressources.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-116">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="7ff1b-117">Pour plus d’informations, consultez la page [Accès conditionnel pour les utilisateurs B2B Collaboration](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="7ff1b-117">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="7ff1b-118">Non, il n’est pas possible de bloquer des utilisateurs invités individuels.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-118">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="7ff1b-119">Les invités que vous avez déjà ajoutés via Azure AD B2B, des Groupes Microsoft 365 ou SharePoint Online sont déjà prêts.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-119">Guest users you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="7ff1b-120">L’administrateur 365 d’Office ou un propriétaire d’équipe peut ajouter ces invités à leurs équipes respectives.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-120">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="7ff1b-121">Si une équipe est déjà associée à un groupe Office 365 et qu’un invité est ajouté au groupe, celui-ci est accessible à l’équipe.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-121">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="7ff1b-122">L’ajout d’un invité par le biais du groupe Office 365 ne génère pas de message d’invitation à l’invité, de sorte qu’une personne de l’équipe doit avertir l’invité.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-122">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="7ff1b-123">Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="7ff1b-123">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="7ff1b-124">Vous pouvez suivre l'ajout d'invités dans Azure AD ou dans le Centre de conformité de la sécurité &amp; d'Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-124">You can track guest additions in Azure AD or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="7ff1b-125">L’ajout d’un invité dans Microsoft teams est audité et consigné en tant qu’activité d’administration des groupes Azure AD «membre ajouté au groupe».</span><span class="sxs-lookup"><span data-stu-id="7ff1b-125">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="7ff1b-126">Pour plus d’informations, [voir audit et création de rapports sur un](https://go.microsoft.com/fwlink/p/?linkid=858884) utilisateur [de collaboration B2B et effectuez une recherche dans le &amp; journal d'](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)audit dans le centre de conformité de la sécurité Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-126">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>


## <a name="more-information"></a><span data-ttu-id="7ff1b-127">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="7ff1b-127">More information</span></span>

[<span data-ttu-id="7ff1b-128">Autoriser l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7ff1b-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="7ff1b-129">Activer ou désactiver l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7ff1b-129">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="7ff1b-130">Utiliser PowerShell pour contrôler l’accès invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="7ff1b-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
