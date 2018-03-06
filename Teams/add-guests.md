---
title: "Ajouter un invité à une équipe"
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 10/23/2017
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: "Découvrez les outils disponibles pour qu'un administrateur ajoute de nouveaux utilisateurs invités à une organisation, y compris les clients web et de bureau de Microsoft Teams et le portail de collaboration Azure Active Directory B2B."
appliesto:
- Microsoft Teams
ms.openlocfilehash: b885aec6cfd2ca40603a195009b6e001c7e7226e
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="ef9a2-103">Ajouter un invité à une équipe</span><span class="sxs-lookup"><span data-stu-id="ef9a2-103">Add a guest to a team</span></span>
=====================

<span data-ttu-id="ef9a2-104">Seuls les utilisateurs disposant d'une adresse de messagerie correspondant à un compte scolaire ou professionnel Azure Active Directory ou Office 365 peuvent être ajoutés en tant qu'utilisateurs invités.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-104">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>


<span data-ttu-id="ef9a2-105">En tant qu'administrateur, vous pouvez ajouter un nouvel utilisateur invité à l'organisation de deux manières :</span><span class="sxs-lookup"><span data-stu-id="ef9a2-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="ef9a2-106">Les administrateurs globaux qui sont propriétaires d'une équipe et les propriétaires d'équipe peuvent ajouter un invité à une équipe via les clients de bureau ou Web Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span>
- <span data-ttu-id="ef9a2-107">Ajoutez des invités à votre organisation via Azure Active Directory B2B Collaboration.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-107">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="ef9a2-108">Azure Active Directory B2B Collaboration permet à un administrateur global d'inviter et d'autoriser un ensemble d'utilisateurs externes en chargeant un fichier de valeurs séparées par des virgules (CSV) de 2 000 lignes au maximum dans le portail B2B Collaboration.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-108">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="ef9a2-109">Pour plus d'informations, consultez la section [Azure Active Directory B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="ef9a2-109">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>



<span data-ttu-id="ef9a2-110">Azure Active Directory B2B Collaboration permet aux organisations d'imposer l'accès conditionnel et les stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-110">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="ef9a2-111">Ces stratégies peuvent être imposées au niveau du client, de l'application ou d'un utilisateur spécifique, de la même manière qu'elles sont activées pour les employés à plein temps et les membres de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-111">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="ef9a2-112">Ces stratégies sont imposées au niveau de l'organisation des ressources.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-112">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="ef9a2-113">Pour plus d'informations, reportez-vous à la rubrique [Accès conditionnel pour les utilisateurs de B2B collaboration](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="ef9a2-113">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="ef9a2-114">Les utilisateurs invités individuels ne peuvent pas être bloqués.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-114">Individual guest users can't be blocked.</span></span>



<span data-ttu-id="ef9a2-115">Les invités que vous avez déjà ajoutés via des groupes Azure Active Directory B2B, Office 365 ou SharePoint Online sont déjà prêts.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-115">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="ef9a2-116">L'administrateur Office 365 ou un propriétaire d'équipe peut les ajouter dans ses équipes respectives.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-116">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="ef9a2-117">Si une équipe est déjà rattachée à un groupe Office 365 et qu'un invité est ajouté au groupe, l'invité obtient l'accès à l'équipe.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-117">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="ef9a2-118">L'ajout d'un invité via le groupe Office 365 ne génère pas d'e-mail d'invitation, un membre de l'équipe devra donc l'en informer.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-118">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="ef9a2-119">Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="ef9a2-119">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>



<span data-ttu-id="ef9a2-120">Vous pouvez suivre l'ajout d'invités dans Azure Active Directory ou dans le Centre de sécurité &amp; conformité d'Office 365.</span><span class="sxs-lookup"><span data-stu-id="ef9a2-120">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="ef9a2-121">L'ajout d'un invité dans Microsoft Teams est audité et journalisé comme activité d'administration de groupe Azure AD « Membre ajouté au groupe ».</span><span class="sxs-lookup"><span data-stu-id="ef9a2-121">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="ef9a2-122">Pour plus de détails, reportez-vous aux documents [Audit et création de rapports relatifs à un utilisateur B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=858884) et [Effectuer des recherches dans le journal d'audit dans le Centre de sécurité &amp; conformité d'Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="ef9a2-122">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

