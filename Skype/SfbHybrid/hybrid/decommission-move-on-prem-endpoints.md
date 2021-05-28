---
title: Déplacer des points de terminaison d’application hybride vers le cloud
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
description: Déplacez les points de terminaison d’application hyrid avant de désaffecter Skype Entreprise environnement local.
ms.openlocfilehash: 959a3ed47993f431636fe3c99b8502cf9aa634fe
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684381"
---
# <a name="move-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="ebc6e-103">Déplacer des points de terminaison d’application hybride avant de désaffecter votre environnement local</span><span class="sxs-lookup"><span data-stu-id="ebc6e-103">Move hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="ebc6e-104">Cet article explique comment déplacer les points de terminaison d’application hybride requis vers le cloud Microsoft avant de désaffecter votre environnement Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="ebc6e-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="ebc6e-105">Il s’agit de l’étape 3 des étapes suivantes pour désaffecter votre environnement local :</span><span class="sxs-lookup"><span data-stu-id="ebc6e-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="ebc6e-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="ebc6e-106">Step 1.</span></span> [<span data-ttu-id="ebc6e-107">Déplacer tous les utilisateurs requis de l’local vers le réseau en ligne</span><span class="sxs-lookup"><span data-stu-id="ebc6e-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="ebc6e-108">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="ebc6e-108">Step 2.</span></span> <span data-ttu-id="ebc6e-109">[Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="ebc6e-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="ebc6e-110">**Étape 3. Déplacez les points de terminaison de l’application hybride de l’local vers le mode en ligne.**</span><span class="sxs-lookup"><span data-stu-id="ebc6e-110">**Step 3. Move hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="ebc6e-111">(Cet article)</span><span class="sxs-lookup"><span data-stu-id="ebc6e-111">(This article)</span></span>

- <span data-ttu-id="ebc6e-112">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="ebc6e-112">Step 4.</span></span> <span data-ttu-id="ebc6e-113">[Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="ebc6e-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="ebc6e-114">Déplacer tous les points de terminaison d’application hybride requis de l’local vers le mode en ligne</span><span class="sxs-lookup"><span data-stu-id="ebc6e-114">Move all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="ebc6e-115">Avant de pouvoir déplacer ces points de terminaison en ligne, vous devez vous assurer que vous avez mis à jour les enregistrements DNS pour qu’ils pointent vers Microsoft 365 pour tous les domaines sip utilisés par les points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ebc6e-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="ebc6e-116">Il n’est pas possible de créer des comptes de ressources en ligne si les enregistrements DNS pointent vers l’environnement local.</span><span class="sxs-lookup"><span data-stu-id="ebc6e-116">It is not possible to create online Resource Accounts if DNS records point to on-premises.</span></span> <span data-ttu-id="ebc6e-117">Pour plus d’informations, [voir Désactiver votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="ebc6e-117">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="ebc6e-118">Récupérez et exportez les paramètres du point de terminaison de l’application hybride sur site en exécutant la commande PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="ebc6e-118">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="ebc6e-119">Créez et licensez [de](/microsoftteams/manage-resource-accounts) nouveaux comptes de ressources Microsoft 365 pour remplacer les points de terminaison d’application hybride locaux existants.</span><span class="sxs-lookup"><span data-stu-id="ebc6e-119">Create and license new [Resource Accounts](/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="ebc6e-120">Associez les nouveaux comptes de ressources aux points de terminaison d’application hybride existants.</span><span class="sxs-lookup"><span data-stu-id="ebc6e-120">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="ebc6e-121">Supprimez les numéros de téléphone définis dans les points de terminaison de l’application hybride sur site en exécutant la commande PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="ebc6e-121">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="ebc6e-122">Étant donné qu’il est possible que les numéros de téléphone de ces comptes ont été gérés en Microsoft 365 plutôt qu’en local, exécutez la commande suivante dans Skype Entreprise Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="ebc6e-122">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="ebc6e-123">Affectez des numéros de téléphone aux nouveaux comptes de ressources créés à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="ebc6e-123">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="ebc6e-124">Pour plus d’informations sur l’affectation d’un numéro de téléphone à un compte de ressource, voir l’article suivant : [Affecter un numéro de service.](/microsoftteams/manage-resource-accounts#assign-a-service-number)</span><span class="sxs-lookup"><span data-stu-id="ebc6e-124">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="ebc6e-125">Supprimez les points de terminaison locaux en exécutant la commande PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="ebc6e-125">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="ebc6e-126">Vous êtes maintenant prêt à supprimer votre déploiement Skype Entreprise [local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="ebc6e-126">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ebc6e-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ebc6e-127">See also</span></span>

- [<span data-ttu-id="ebc6e-128">Mise hors service de votre environnement Skype pour entreprises sur site</span><span class="sxs-lookup"><span data-stu-id="ebc6e-128">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="ebc6e-129">Déplacer tous les utilisateurs requis de l’local vers le réseau en ligne</span><span class="sxs-lookup"><span data-stu-id="ebc6e-129">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="ebc6e-130">Désactiver votre configuration hybride</span><span class="sxs-lookup"><span data-stu-id="ebc6e-130">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="ebc6e-131">Supprimez votre déploiement sur site de Skype pour entreprises.</span><span class="sxs-lookup"><span data-stu-id="ebc6e-131">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




