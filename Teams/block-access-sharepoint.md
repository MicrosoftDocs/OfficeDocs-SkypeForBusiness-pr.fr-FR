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
description: En savoir plus sur la façon de bloquer l’accès à SharePoint pour des utilisateurs spécifiques
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203837"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="a43bc-103">Bloquer l’accès à SharePoint pour des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="a43bc-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="a43bc-104">L’application d’une stratégie d’accès conditionnel (CA) sur SharePoint dans Microsoft 365 est également appliquée aux équipes.</span><span class="sxs-lookup"><span data-stu-id="a43bc-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="a43bc-105">Toutefois, certaines organisations veulent bloquer l’accès aux fichiers SharePoint (Télécharger, télécharger, afficher, modifier, créer) et permettre à leurs employés d’utiliser les clients de bureau, mobiles et Web teams sur des appareils non gérés.</span><span class="sxs-lookup"><span data-stu-id="a43bc-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="a43bc-106">Dans les règles de stratégie d’autorité de certification, le blocage de SharePoint entraînerait le blocage des équipes.</span><span class="sxs-lookup"><span data-stu-id="a43bc-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="a43bc-107">Cet article explique comment vous pouvez contourner cette limitation et permettre à vos employés de continuer à utiliser teams tout en bloquant complètement l’accès aux fichiers stockés dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a43bc-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="a43bc-108">Bloquer ou limiter l’accès sur des appareils non gérés repose sur les stratégies d’accès conditionnel d’Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a43bc-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="a43bc-109">En savoir plus sur la gestion des [licences Azure ad](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="a43bc-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="a43bc-110">Pour obtenir une vue d’ensemble de l’accès conditionnel dans Azure AD, voir [accès conditionnel dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="a43bc-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="a43bc-111">Pour plus d’informations sur les stratégies d’accès SharePoint Online recommandées, voir recommandations en matière [de stratégie pour la sécurisation des sites et fichiers SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="a43bc-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="a43bc-112">Si vous limitez l’accès à des appareils non gérés, les utilisateurs sur les appareils gérés doivent utiliser l’une des [combinaisons de systèmes d’exploitation et navigateurs pris en charge](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), ou leur accès est également limité.</span><span class="sxs-lookup"><span data-stu-id="a43bc-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="a43bc-113">Vous pouvez bloquer ou limiter l’accès pour :</span><span class="sxs-lookup"><span data-stu-id="a43bc-113">You can block or limit access for:</span></span>

- <span data-ttu-id="a43bc-114">Utilisateurs de l’organisation ou seulement certains utilisateurs ou groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="a43bc-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="a43bc-115">Tous les sites au sein de l’organisation ou seulement des sites.</span><span class="sxs-lookup"><span data-stu-id="a43bc-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="a43bc-116">Lorsque l’accès est bloqué, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="a43bc-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="a43bc-117">Bloquez l’accès pour renforcer la sécurité et protéger les données sécurisées.</span><span class="sxs-lookup"><span data-stu-id="a43bc-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="a43bc-118">Lorsque l’accès est bloqué, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="a43bc-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="a43bc-119">Ouvrez le centre d’administration SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a43bc-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="a43bc-120">Développez stratégies d' **Policies**  >  **accès aux**stratégies.</span><span class="sxs-lookup"><span data-stu-id="a43bc-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="a43bc-121">Dans la section **appareils non gérés** , sélectionnez **bloquer l’accès** et sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a43bc-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![section périphériques non gérés pour les stratégies](media/no-sharepoint-access1.png)

4. <span data-ttu-id="a43bc-123">Ouvrez le portail [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) et naviguez jusqu’à **stratégies d’accès conditionnel**.</span><span class="sxs-lookup"><span data-stu-id="a43bc-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="a43bc-124">Vous verrez une nouvelle stratégie créée par SharePoint, semblable à cet exemple :</span><span class="sxs-lookup"><span data-stu-id="a43bc-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![nouvelle stratégie nommée utilisation de restrictions appliquées par l’application pour l’accès au navigateur](media/no-sharepoint-access2.png)

5. <span data-ttu-id="a43bc-126">Mettez à jour la stratégie pour cibler uniquement des utilisateurs ou un groupe spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a43bc-126">Update the policy to target only specific users or a group.</span></span>

    ![Centre d’administration SharePoint avec l’option Sélectionner l’utilisateur en surbrillance.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="a43bc-128">La définition de cette stratégie entraîne la réduction de votre accès au portail d’administration SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a43bc-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="a43bc-129">Nous vous recommandons de configurer la stratégie d’exclusion et de sélectionner les administrateurs généraux et SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a43bc-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="a43bc-130">Vérifier que seul SharePoint est sélectionné comme application Cloud ciblée</span><span class="sxs-lookup"><span data-stu-id="a43bc-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![SharePoint est sélectionné en tant qu’application ciblée.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="a43bc-132">Vous pouvez également mettre à jour des **conditions** pour inclure des clients de bureau.</span><span class="sxs-lookup"><span data-stu-id="a43bc-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![mise en surbrillance des applications de bureau et mobiles.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="a43bc-134">Vérifier que **l’option autoriser l’accès** est activée</span><span class="sxs-lookup"><span data-stu-id="a43bc-134">Make sure that **Grant access** is enabled</span></span>

    ![l’accès accordé est activé.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="a43bc-136">Assurez-vous que l’option **utiliser les restrictions** appliquées aux applications est activée.</span><span class="sxs-lookup"><span data-stu-id="a43bc-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="a43bc-137">Activez votre stratégie, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a43bc-137">Enable your policy and select **Save**.</span></span>

    ![L’application restrictions appliquée est activée.](media/no-sharepoint-access6.png)

<span data-ttu-id="a43bc-139">Pour tester votre stratégie, vous devez vous déconnecter de n’importe quel client, tel que l’application de bureau teams ou le client de synchronisation OneDrive entreprise, puis vous reconnecter pour voir la stratégie qui fonctionne.</span><span class="sxs-lookup"><span data-stu-id="a43bc-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="a43bc-140">Si votre accès a été bloqué, un message s’affiche dans Microsoft Teams, qui indique que l’élément n’existe pas.</span><span class="sxs-lookup"><span data-stu-id="a43bc-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![Message élément introuvable.](media/access-denied-sharepoint.png)

<span data-ttu-id="a43bc-142">Dans SharePoint, vous recevez un message accès refusé.</span><span class="sxs-lookup"><span data-stu-id="a43bc-142">In Sharepoint, you'll receive an access denied message.</span></span>

![Le message accès refusé.](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="a43bc-144">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="a43bc-144">Related topics</span></span>

[<span data-ttu-id="a43bc-145">Contrôler l’accès pour les appareils non gérés dans SharePoint</span><span class="sxs-lookup"><span data-stu-id="a43bc-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
