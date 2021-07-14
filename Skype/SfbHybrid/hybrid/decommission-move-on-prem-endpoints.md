---
title: Migrer des points de terminaison d’application hybride vers le cloud
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
description: Migrez les points de terminaison d’application hyrid avant de désaffecter Skype Entreprise environnement local.
ms.openlocfilehash: 7315ee807bb79b9186cd92ccc19074021b2fcfa1
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420799"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="f6ec9-103">Migrer des points de terminaison d’application hybride avant de désaffecter votre environnement local</span><span class="sxs-lookup"><span data-stu-id="f6ec9-103">Migrate hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="f6ec9-104">Cet article explique comment déplacer les points de terminaison d’application hybride requis vers le cloud Microsoft avant de désaffecter votre environnement Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="f6ec9-105">Il s’agit de l’étape 3 des étapes suivantes pour désaffecter votre environnement local :</span><span class="sxs-lookup"><span data-stu-id="f6ec9-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="f6ec9-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-106">Step 1.</span></span> [<span data-ttu-id="f6ec9-107">Déplacer tous les utilisateurs requis de l’local vers le site en ligne</span><span class="sxs-lookup"><span data-stu-id="f6ec9-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="f6ec9-108">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-108">Step 2.</span></span> <span data-ttu-id="f6ec9-109">[Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="f6ec9-110">**Étape 3. Migrez les points de terminaison des applications hybrides de l’local vers le mode en ligne.**</span><span class="sxs-lookup"><span data-stu-id="f6ec9-110">**Step 3. Migrate hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="f6ec9-111">(Cet article)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-111">(This article)</span></span>

- <span data-ttu-id="f6ec9-112">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-112">Step 4.</span></span> <span data-ttu-id="f6ec9-113">[Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="f6ec9-114">Migrer tous les points de terminaison d’application hybride requis de l’local vers le mode en ligne</span><span class="sxs-lookup"><span data-stu-id="f6ec9-114">Migrate all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="f6ec9-115">Avant de pouvoir déplacer ces points de terminaison en ligne, vous devez vous assurer que vous avez mis à jour les enregistrements DNS pour qu’ils pointent vers Microsoft 365 pour tous les domaines sip utilisés par les points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="f6ec9-116">N’ignorez pas qu’une fois que vous mettez à jour le DNS pour pointer vers Microsoft 365, les points de terminaison d’application hybride existants ne seront plus découvrables tant que vous n’aurez pas terminé cette étape.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-116">Be aware that once you update DNS to point to Microsoft 365, any existing hybrid application endpoints will no longer be discoverable until you complete this step.</span></span> <span data-ttu-id="f6ec9-117">Étant donné que cette étape (création de comptes de ressources en ligne) n’est pas possible si les enregistrements DNS pointent vers l’environnement local, vous devez planifier les deux étapes 2 et 3 dans la même fenêtre de maintenance.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-117">Since this step (creating online Resource Accounts) is not possible if DNS records point to on-premises you should plan to do both steps 2 and 3 in the same maintenance window.</span></span> <span data-ttu-id="f6ec9-118">Pour plus d’informations, [voir Désactiver votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-118">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="f6ec9-119">Récupérez et exportez les paramètres du point de terminaison de l’application hybride sur site en exécutant la commande PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="f6ec9-119">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="f6ec9-120">Créez et licensez [de](/microsoftteams/manage-resource-accounts) nouveaux comptes de ressources Microsoft 365 pour remplacer les points de terminaison d’application hybride locaux existants.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-120">Create and license new [Resource Accounts](/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="f6ec9-121">Associez les nouveaux comptes de ressources aux points de terminaison d’application hybride existants.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-121">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="f6ec9-122">Supprimez les numéros de téléphone définis dans les points de terminaison de l’application hybride sur site en exécutant la commande PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="f6ec9-122">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="f6ec9-123">Étant donné qu’il est possible que les numéros de téléphone de ces comptes ont été gérés en Microsoft 365 plutôt qu’en local, exécutez la commande suivante dans Skype Entreprise Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="f6ec9-123">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="f6ec9-124">Affectez des numéros de téléphone aux nouveaux comptes de ressources créés à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-124">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="f6ec9-125">Pour plus d’informations sur l’affectation d’un numéro de téléphone à un compte de ressource, voir l’article suivant : [Affecter un numéro de service.](/microsoftteams/manage-resource-accounts#assign-a-service-number)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-125">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="f6ec9-126">Supprimez les points de terminaison locaux en exécutant la commande PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="f6ec9-126">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="f6ec9-127">Vous êtes maintenant prêt à supprimer votre déploiement Skype Entreprise [local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="f6ec9-127">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f6ec9-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6ec9-128">See also</span></span>

- [<span data-ttu-id="f6ec9-129">Mise hors service de votre environnement Skype pour entreprises sur site</span><span class="sxs-lookup"><span data-stu-id="f6ec9-129">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="f6ec9-130">Déplacer tous les utilisateurs requis de l’local vers le site en ligne</span><span class="sxs-lookup"><span data-stu-id="f6ec9-130">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="f6ec9-131">Désactiver votre configuration hybride</span><span class="sxs-lookup"><span data-stu-id="f6ec9-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="f6ec9-132">Supprimez votre déploiement sur site de Skype pour entreprises.</span><span class="sxs-lookup"><span data-stu-id="f6ec9-132">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




