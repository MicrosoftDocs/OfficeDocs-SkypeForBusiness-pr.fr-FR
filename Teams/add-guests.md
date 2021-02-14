---
title: Ajouter un invité à une équipe
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Les administrateurs peuvent découvrir comment ajouter des invités à une organisation dans les clients de bureau et web Microsoft Teams et le portail de collaboration Azure Active Directory B2B.
ms.openlocfilehash: 7f75589c5252998fb0389c743b951c0fe88e613b
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662439"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="87234-103">Ajouter un invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="87234-103">Add a guest to a team</span></span>

<span data-ttu-id="87234-104">Toutes les personnes ayant un compte de messagerie professionnel ou un compte de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="87234-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="87234-105">En tant qu’administrateur, vous pouvez ajouter un nouvel invité à l’organisation de deux façons :</span><span class="sxs-lookup"><span data-stu-id="87234-105">As an admin, you can add a new guest to the organization in a couple of ways:</span></span>

- <span data-ttu-id="87234-106">Les administrateurs généraux ou les administrateurs Teams et les propriétaires d’équipe ajoutent un invité à une équipe dans les clients Teams ou dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="87234-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="87234-107">Pour plus d’informations, voir [Ajouter des invités dans une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="87234-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="87234-108">Si vous n’avez pas encore configuré l’accès invité, suivez les étapes décrites dans [Collaborer avec des invités au sein d’une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="87234-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="87234-109">Ajoutez des invités à votre organisation via Azure Active Directory (Azure AD) B2B Collaboration.</span><span class="sxs-lookup"><span data-stu-id="87234-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="87234-110">Pour plus d’informations, consultez le démarrage rapide : ajouter des invités à votre annuaire [dans le portail Azure.](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)</span><span class="sxs-lookup"><span data-stu-id="87234-110">For details, check out [Quickstart: Add guests to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="87234-111">Les administrateurs peuvent également déléguer dls autorisations d’ajout d’invités à d’autres membres de leur organisation en leur attribuant le rôle d’inviteur d’invités.</span><span class="sxs-lookup"><span data-stu-id="87234-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="87234-112">Pour plus d’informations, consultez [Activer la collaboration externe B2B et gérer les utilisateurs pouvant inviter des invités](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="87234-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="87234-113">Azure AD B2B Collaboration permet aux organisations d'imposer un accès conditionnel et des stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B.</span><span class="sxs-lookup"><span data-stu-id="87234-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="87234-114">Ces stratégies peuvent être appliquées au niveau locataire, application ou utilisateur individuel, de la même façon qu’elles peuvent être activées pour les employés à plein temps et les membres de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="87234-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="87234-115">Les stratégies MFA sont appliquées à l’organisation de ressources.</span><span class="sxs-lookup"><span data-stu-id="87234-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="87234-116">Pour plus d’informations, consultez la page [Accès conditionnel pour les utilisateurs B2B Collaboration](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="87234-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="87234-117">Les invités individuels ne peuvent pas être bloqués.</span><span class="sxs-lookup"><span data-stu-id="87234-117">Individual guests can't be blocked.</span></span>

<span data-ttu-id="87234-118">Les invités que vous avez déjà ajoutés via Azure AD B2B, les groupes Microsoft 365 ou SharePoint sont fin prêts.</span><span class="sxs-lookup"><span data-stu-id="87234-118">Guests you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="87234-119">L’administrateur Microsoft 365 ou un propriétaire d’équipe peut ajouter ces invités à leurs équipes respectives.</span><span class="sxs-lookup"><span data-stu-id="87234-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="87234-120">Si vous ajoutez un invité directement au groupe Microsoft 365 associé à une équipe, l’invité pourra accéder à l’équipe, mais le groupe Microsoft 365 ne génère pas d’e-mail d’invitation à l’invité, un membres de l’équipe devra donc l’en informer.</span><span class="sxs-lookup"><span data-stu-id="87234-120">If you add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="87234-121">Les invités sont soumis aux mêmes limites des services [Microsoft 365 ou Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="87234-121">Guests are subject to  [Microsoft 365 or Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="87234-122">Vous pouvez suivre l'ajout d'invités dans Azure AD ou dans le Centre de sécurité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87234-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="87234-123">L’ajout d’un invité dans Microsoft teams est audité et consigné en tant qu’activité d’administration des groupes Azure AD «membre ajouté au groupe».</span><span class="sxs-lookup"><span data-stu-id="87234-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="87234-124">Pour plus d’informations, voir Audit et signalement d’un utilisateur de [collaboration B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) et Effectuer des recherches dans le journal [d’audit dans le Centre de conformité.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)</span><span class="sxs-lookup"><span data-stu-id="87234-124">For more details, see [Auditing and reporting a B2B collaboration user](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="87234-125">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="87234-125">Related topics</span></span>

[<span data-ttu-id="87234-126">Autoriser l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="87234-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="87234-127">Activer ou désactiver l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="87234-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)
