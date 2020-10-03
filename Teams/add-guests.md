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
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Les administrateurs peuvent apprendre à ajouter de nouveaux utilisateurs invités à une organisation dans le bureau et les clients Web Microsoft Teams ainsi que le portail de collaboration inter-entreprise d’Azure Active Directory.
ms.openlocfilehash: e74819ba46af8a9f6bcf3b2198f78354bf7bfb79
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346175"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="70325-103">Ajouter un invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="70325-103">Add a guest to a team</span></span>

<span data-ttu-id="70325-104">Toutes les personnes ayant un compte de messagerie professionnel ou un compte de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="70325-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="70325-105">En tant qu’administrateur, vous pouvez ajouter un nouvel utilisateur invité à l’organisation de deux manières :</span><span class="sxs-lookup"><span data-stu-id="70325-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>

- <span data-ttu-id="70325-106">Les administrateurs généraux ou les administrateurs Teams et les propriétaires d’équipe ajoutent un invité à une équipe dans les clients Teams ou dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="70325-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="70325-107">Pour plus d’informations, voir [Ajouter des invités dans une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="70325-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="70325-108">Si vous n’avez pas encore configuré l’accès invité, suivez les étapes décrites dans [Collaborer avec des invités au sein d’une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="70325-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="70325-109">Ajoutez des invités à votre organisation via Azure Active Directory (Azure AD) B2B Collaboration.</span><span class="sxs-lookup"><span data-stu-id="70325-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="70325-110">Pour plus d’informations, voir [démarrage rapide : ajouter des utilisateurs invités à votre annuaire dans le portail Azure](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="70325-110">For details, check out [Quickstart: Add guest users to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="70325-111">Les administrateurs peuvent également déléguer dls autorisations d’ajout d’invités à d’autres membres de leur organisation en leur attribuant le rôle d’inviteur d’invités.</span><span class="sxs-lookup"><span data-stu-id="70325-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="70325-112">Pour plus d’informations, consultez [Activer la collaboration externe B2B et gérer les utilisateurs pouvant inviter des invités](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="70325-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="70325-113">Azure AD B2B Collaboration permet aux organisations d'imposer un accès conditionnel et des stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B.</span><span class="sxs-lookup"><span data-stu-id="70325-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="70325-114">Ces stratégies peuvent être appliquées au niveau locataire, application ou utilisateur individuel, de la même façon qu’elles peuvent être activées pour les employés à plein temps et les membres de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="70325-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="70325-115">Les stratégies MFA sont appliquées à l’organisation de ressources.</span><span class="sxs-lookup"><span data-stu-id="70325-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="70325-116">Pour plus d’informations, consultez la page [Accès conditionnel pour les utilisateurs B2B Collaboration](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="70325-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="70325-117">Non, il n’est pas possible de bloquer des utilisateurs invités individuels.</span><span class="sxs-lookup"><span data-stu-id="70325-117">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="70325-118">Les utilisateurs invités que vous avez déjà ajoutés par le biais d’Azure AD B2B, de groupes Microsoft 365 ou de SharePoint sont prêts à l’emploi.</span><span class="sxs-lookup"><span data-stu-id="70325-118">Guest users you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="70325-119">L’administrateur 365 Microsoft ou un propriétaire d’équipe peut ajouter ces invités à leurs équipes respectives.</span><span class="sxs-lookup"><span data-stu-id="70325-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="70325-120">Si vous ajoutez un invité directement au groupe Microsoft 365 associé à une équipe, l’invité obtient l’accès à l’équipe, mais le groupe Microsoft 365 ne génère pas de message d’invitation à l’invité, de sorte qu’une personne de l’équipe doit notifier l’invité.</span><span class="sxs-lookup"><span data-stu-id="70325-120">If add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="70325-121">Les invités sont soumis aux mêmes limites des services [Microsoft 365 ou Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="70325-121">Guests are subject to  [Microsoft 365 or Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="70325-122">Vous pouvez suivre l'ajout d'invités dans Azure AD ou dans le Centre de sécurité Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70325-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="70325-123">L’ajout d’un invité dans Microsoft teams est audité et consigné en tant qu’activité d’administration des groupes Azure AD «membre ajouté au groupe».</span><span class="sxs-lookup"><span data-stu-id="70325-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="70325-124">Pour plus d’informations, reportez-vous à la rubrique [audit et création de rapports sur un utilisateur de collaboration B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) et [recherchez le journal d’audit dans le centre de conformité](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span><span class="sxs-lookup"><span data-stu-id="70325-124">For more details, see [Auditing and reporting a B2B collaboration user](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="70325-125">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="70325-125">Related topics</span></span>

[<span data-ttu-id="70325-126">Autoriser l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="70325-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="70325-127">Activer ou désactiver l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="70325-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)
