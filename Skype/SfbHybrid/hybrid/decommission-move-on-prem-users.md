---
title: Déplacer des utilisateurs et des points de terminaison vers le cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Déplacez les utilisateurs et les points de terminaison avant de désaffecter un environnement Skype Entreprise local.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593887"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="eccf2-103">Déplacer les utilisateurs et points de terminaison requis avant de désaffecter votre environnement local</span><span class="sxs-lookup"><span data-stu-id="eccf2-103">Move required users and endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="eccf2-104">Cet article explique comment déplacer les utilisateurs et les points de terminaison d’application requis vers le cloud Microsoft avant de désaffecter votre environnement Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="eccf2-104">This article describes how to move required users and application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="eccf2-105">Il s’agit de l’étape 1 des étapes suivantes pour désaffecter votre environnement local :</span><span class="sxs-lookup"><span data-stu-id="eccf2-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="eccf2-106">**Étape 1. Déplacez tous les utilisateurs et points de terminaison d’application requis de l’local vers le site en ligne.**</span><span class="sxs-lookup"><span data-stu-id="eccf2-106">**Step 1. Move all required users and application endpoints from on-premises to online.**</span></span> <span data-ttu-id="eccf2-107">(Cet article.)</span><span class="sxs-lookup"><span data-stu-id="eccf2-107">(This article.)</span></span>

- <span data-ttu-id="eccf2-108">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="eccf2-108">Step 2.</span></span> <span data-ttu-id="eccf2-109">[Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="eccf2-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="eccf2-110">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="eccf2-110">Step 3.</span></span> <span data-ttu-id="eccf2-111">[Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="eccf2-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="eccf2-112">Déplacer tous les utilisateurs requis de l’local vers le cloud</span><span class="sxs-lookup"><span data-stu-id="eccf2-112">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="eccf2-113">Tous les utilisateurs que vous continuerez à utiliser après avoir effectué la migration doivent d’abord être déplacés de l’local vers le cloud.</span><span class="sxs-lookup"><span data-stu-id="eccf2-113">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="eccf2-114">Vous déplacez les utilisateurs à l’aide des outils d’administration locaux.</span><span class="sxs-lookup"><span data-stu-id="eccf2-114">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="eccf2-115">Pour plus d’informations, voir [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="eccf2-115">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="eccf2-116">Bien qu’il soit possible pour les utilisateurs ayant des comptes Skype Entreprise Server locaux d’utiliser Teams, ces utilisateurs n’ont pas toutes les fonctionnalités de Teams.</span><span class="sxs-lookup"><span data-stu-id="eccf2-116">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="eccf2-117">Ces utilisateurs ne peuvent pas interopérer ou fédérer avec d’autres utilisateurs qui utilisent encore Skype Entreprise (en ligne ou en local).</span><span class="sxs-lookup"><span data-stu-id="eccf2-117">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="eccf2-118">Ces utilisateurs ne peuvent pas non plus recevoir d’appels PSTN dans leur client Teams.</span><span class="sxs-lookup"><span data-stu-id="eccf2-118">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="eccf2-119">Par conséquent, vous devez déplacer ces utilisateurs en ligne.</span><span class="sxs-lookup"><span data-stu-id="eccf2-119">Therefore, you must move these users to online.</span></span> <span data-ttu-id="eccf2-120">Cette étape garantit également que tous les contacts ou réunions créés dans Skype Entreprise Server sont migrés vers Teams.</span><span class="sxs-lookup"><span data-stu-id="eccf2-120">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="eccf2-121">Pour vérifier s’il reste des utilisateurs dans votre déploiement local, exécutez l’cmdlet suivante dans une fenêtre PowerShell Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="eccf2-121">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="eccf2-122">Si des utilisateurs sont renvoyés, examinez la sortie pour déterminer si des comptes doivent être déplacés vers le cloud et, pour ces utilisateurs, suivez les étapes [ci-après.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="eccf2-122">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="eccf2-123">Pour les comptes d’utilisateurs qui ne sont plus nécessaires, exécutez l’cmdlet PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="eccf2-123">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="eccf2-124">L'Disable-CsUser supprimera tous les attributs Skype Entreprise pour tous les utilisateurs qui ont les critères de filtre.</span><span class="sxs-lookup"><span data-stu-id="eccf2-124">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="eccf2-125">Avant de continuer, confirmez que ces comptes ne sont plus nécessaires à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="eccf2-125">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a><span data-ttu-id="eccf2-126">Déplacer des points de terminaison d’application hybride sur site vers Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eccf2-126">Move on-premises hybrid application endpoints to Microsoft 365</span></span>

1. <span data-ttu-id="eccf2-127">Récupérez et exportez les paramètres du point de terminaison de l’application hybride sur site en exécutant la commande PowerShell Skype Entreprise Server sur site suivante :</span><span class="sxs-lookup"><span data-stu-id="eccf2-127">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="eccf2-128">Créez et licensez [de nouveaux](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) comptes de ressources dans Microsoft 365 pour remplacer les points de terminaison d’application hybride locaux existants.</span><span class="sxs-lookup"><span data-stu-id="eccf2-128">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="eccf2-129">Associez les nouveaux comptes de ressources aux points de terminaison d’application hybride existants.</span><span class="sxs-lookup"><span data-stu-id="eccf2-129">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="eccf2-130">Supprimez les numéros de téléphone définis dans les points de terminaison de l’application hybride sur site en exécutant la commande PowerShell Skype Entreprise Server sur site suivante :</span><span class="sxs-lookup"><span data-stu-id="eccf2-130">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="eccf2-131">Étant donné qu’il est possible que les numéros de téléphone de ces comptes ont été gérés dans Microsoft 365 plutôt que sur site, exécutez la commande suivante dans Skype Entreprise Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="eccf2-131">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. <span data-ttu-id="eccf2-132">Affectez des numéros de téléphone aux nouveaux comptes de ressources créés à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="eccf2-132">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="eccf2-133">Pour plus d’informations sur l’affectation d’un numéro de téléphone à un compte de ressource, voir l’article suivant : [Affecter un numéro de service.](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)</span><span class="sxs-lookup"><span data-stu-id="eccf2-133">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="eccf2-134">Supprimez les points de terminaison locaux en exécutant la commande PowerShell Skype Entreprise Server sur site suivante :</span><span class="sxs-lookup"><span data-stu-id="eccf2-134">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="eccf2-135">Vous êtes maintenant prêt à [désactiver votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="eccf2-135">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eccf2-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eccf2-136">See also</span></span>

- [<span data-ttu-id="eccf2-137">Désaffecter votre environnement Skype Entreprise local</span><span class="sxs-lookup"><span data-stu-id="eccf2-137">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="eccf2-138">Désactiver votre configuration hybride</span><span class="sxs-lookup"><span data-stu-id="eccf2-138">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="eccf2-139">Supprimer votre déploiement Skype Entreprise local</span><span class="sxs-lookup"><span data-stu-id="eccf2-139">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




