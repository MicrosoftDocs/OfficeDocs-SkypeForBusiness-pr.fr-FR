---
title: Bloquer l’accès à SharePoint pour des utilisateurs spécifiques
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment bloquer l’accès à SharePoint pour des utilisateurs spécifiques
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203837"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="bb2c6-103">Bloquer l’accès à SharePoint pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="bb2c6-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="bb2c6-104">Toute stratégie d’accès conditionnel appliquée sur SharePoint dans Microsoft 365 est également appliquée à Teams.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="bb2c6-105">Toutefois, certaines organisations souhaitent bloquer l’accès aux fichiers SharePoint (chargement, téléchargement, affichage, modification et création), et permettre à leurs employés d’utiliser les clients Teams de bureau, mobiles et web sur les appareils non gérés.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="bb2c6-106">Dans les règles de stratégie d’accès conditionnel, le blocage de SharePoint conduirait également au blocage de Teams.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="bb2c6-107">Cet article décrit la manière dont vous pouvez contourner cette limitation et permettre à vos employés de continuer à utiliser Teams tout en bloquant l’accès aux fichiers stockés dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="bb2c6-108">Le blocage ou la limitation de l’accès sur des appareils non gérés s’appuie sur les stratégies d’accès conditionnel Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="bb2c6-109">En savoir plus sur la [gestion des licences Azure AD](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="bb2c6-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="bb2c6-110">Pour obtenir une vue d’ensemble de l’accès conditionnel dans Azure AD, voir [Accès conditionnel dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="bb2c6-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="bb2c6-111">Pour plus d’informations sur les stratégies d’accès SharePoint Online recommandées, voir [Recommandations en matière de stratégie pour la sécurisation des sites et fichiers SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="bb2c6-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="bb2c6-112">Si vous limitez l’accès sur des appareils non gérés, les utilisateurs sur les appareils gérés doivent utiliser l’une des [combinaisons de systèmes d’exploitation et de navigateurs prises en charge](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition). Dans le cas contraire, ils disposeront également d’un accès limité.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="bb2c6-113">Vous pouvez bloquer ou limiter l’accès pour :</span><span class="sxs-lookup"><span data-stu-id="bb2c6-113">You can block or limit access for:</span></span>

- <span data-ttu-id="bb2c6-114">Les utilisateurs de l’organisation, ou certains utilisateurs ou groupes de sécurité uniquement.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="bb2c6-115">Tous les sites de votre organisation, ou certains sites uniquement.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="bb2c6-116">Lorsque l’accès est bloqué, les utilisateurs voient un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="bb2c6-117">Le blocage de l’accès renforce la sécurité et protège les données sécurisées.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="bb2c6-118">Lorsque l’accès est bloqué, les utilisateurs voient un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="bb2c6-119">Ouvrez le Centre d’administration SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="bb2c6-120">Développez **Politiques** > **Stratégies d’accès**.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="bb2c6-121">Dans la section **Appareils non gérés**, sélectionnez **Bloquer l’accès**, puis **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![la section Appareils non gérés pour les stratégies](media/no-sharepoint-access1.png)

4. <span data-ttu-id="bb2c6-123">Ouvrez le portail [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) et accédez à **Stratégies d’accès conditionnel**.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="bb2c6-124">Une nouvelle stratégie semblable à celle-ci est créée par SharePoint :</span><span class="sxs-lookup"><span data-stu-id="bb2c6-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![une nouvelle stratégie nommée Utiliser les restrictions appliquées par l’application pour l’accès au navigateur](media/no-sharepoint-access2.png)

5. <span data-ttu-id="bb2c6-126">Mettez à jour la stratégie pour cibler uniquement des utilisateurs spécifiques ou un groupe.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-126">Update the policy to target only specific users or a group.</span></span>

    ![centre d’administration SharePoint avec la section Sélectionner un utilisateur mise en évidence.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="bb2c6-128">La définition de cette stratégie permettra de réduire l’accès au portail d’administration SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="bb2c6-129">Nous vous recommandons de configurer la stratégie d’exclusion et de sélectionner les administrateurs globaux et SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="bb2c6-130">Vérifiez que seul SharePoint est sélectionné en tant qu’application cloud ciblée</span><span class="sxs-lookup"><span data-stu-id="bb2c6-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![SharePoint est sélectionné en tant qu’application ciblée.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="bb2c6-132">Mettez à jour les **conditions** afin d’inclure également les clients de bureau.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![applications de bureau et mobiles mises en évidence.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="bb2c6-134">Assurez-vous que l’option **Accorder l’accès** est activée.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-134">Make sure that **Grant access** is enabled</span></span>

    ![l’option Accorder l’accès est activée.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="bb2c6-136">Assurez-vous que **Utiliser les restrictions appliquées par l’application** est activé.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="bb2c6-137">Activez votre stratégie et sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-137">Enable your policy and select **Save**.</span></span>

    ![Les restrictions appliquées par l’application sont activées.](media/no-sharepoint-access6.png)

<span data-ttu-id="bb2c6-139">Pour tester votre stratégie, vous devez vous déconnecter de n’importe quel client, par exemple, l’application de bureau Teams ou le client de synchronisation OneDrive Entreprise, puis vous reconnecter afin d’afficher la stratégie active.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="bb2c6-140">Si votre accès a été bloqué, un message indiquant qu’il n’est peut-être pas disponible s’affiche dans Teams.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![Message concernant l’élément introuvable.](media/access-denied-sharepoint.png)

<span data-ttu-id="bb2c6-142">Dans SharePoint, vous recevrez un message d’accès refusé.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-142">In Sharepoint, you'll receive an access denied message.</span></span>

![Message d’accès refusé.](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="bb2c6-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb2c6-144">Related topics</span></span>

[<span data-ttu-id="bb2c6-145">Contrôler l’accès des appareils non gérés dans SharePoint</span><span class="sxs-lookup"><span data-stu-id="bb2c6-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
