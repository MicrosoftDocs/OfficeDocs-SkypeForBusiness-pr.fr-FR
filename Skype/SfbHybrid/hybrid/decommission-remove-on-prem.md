---
title: Désaffecter Skype Entreprise Server
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
description: Instructions de désaffectation de Skype Entreprise Server.
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593886"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="abeb9-103">Supprimer votre déploiement Skype Entreprise local</span><span class="sxs-lookup"><span data-stu-id="abeb9-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="abeb9-104">Cet article explique comment supprimer votre déploiement Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="abeb9-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="abeb9-105">Il s’agit de l’étape 3 des étapes suivantes pour désaffecter votre environnement local :</span><span class="sxs-lookup"><span data-stu-id="abeb9-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="abeb9-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="abeb9-106">Step 1.</span></span> <span data-ttu-id="abeb9-107">[Déplacez tous les utilisateurs et points de terminaison d’application](decommission-move-on-prem-users.md)requis de l’local vers le site en ligne.</span><span class="sxs-lookup"><span data-stu-id="abeb9-107">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="abeb9-108">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="abeb9-108">Step 2.</span></span> <span data-ttu-id="abeb9-109">[Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="abeb9-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="abeb9-110">**Étape 3. Supprimez votre déploiement Skype Entreprise local.**</span><span class="sxs-lookup"><span data-stu-id="abeb9-110">**Step 3. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="abeb9-111">(Cet article)</span><span class="sxs-lookup"><span data-stu-id="abeb9-111">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="abeb9-112">Les étapes décrites dans cet article s’appliquent uniquement si vous utilisez la méthode 2 pour gérer les attributs utilisateur, comme décrit [ici.](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)</span><span class="sxs-lookup"><span data-stu-id="abeb9-112">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="abeb9-113">Si vous utilisez la méthode 1, n’utilisez pas les étapes décrites dans cet article pour supprimer vos serveurs Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="abeb9-113">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="abeb9-114">Au lieu de cela, vous pouvez ré-imager les serveurs.</span><span class="sxs-lookup"><span data-stu-id="abeb9-114">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="abeb9-115">Pour effectuer les étapes de cet article, vous avez besoin de privilèges pour le groupe Administrateurs du schéma et le groupe Administrateurs de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="abeb9-115">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="abeb9-116">Vous aurez besoin de ces privilèges pour annuler le schéma Skype Entreprise Server et les modifications au niveau de la forêt apportées aux services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="abeb9-116">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="abeb9-117">Vous devez également être membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="abeb9-117">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="abeb9-118">Préparer la suppression du déploiement de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="abeb9-118">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="abeb9-119">Après avoir passé tous les comptes d’utilisateur requis vers le cloud, il se peut qu’il reste des objets locaux, tels que des contacts et des applications, que vous devrez nettoyer.</span><span class="sxs-lookup"><span data-stu-id="abeb9-119">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="abeb9-120">Utilisez les étapes ci-dessous pour nettoyer ces objets et assurez-vous que vous êtes membre du groupe Administrateur local et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="abeb9-120">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="abeb9-121">Notez que ExUmContacts et PersistantChatEndPoints ne sont pas disponibles dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="abeb9-121">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="abeb9-122">Si vous avez Skype Entreprise Server 2019, les cmdlets correspondantes dans les étapes ci-dessous doivent être omises.</span><span class="sxs-lookup"><span data-stu-id="abeb9-122">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="abeb9-123">Pour vérifier si des contacts ou des applications sont associés au déploiement local de Skype Entreprise Server, exécutez les cmdlets PowerShell Skype Entreprise Server suivantes.</span><span class="sxs-lookup"><span data-stu-id="abeb9-123">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. <span data-ttu-id="abeb9-124">Examinez les listes de sortie des cmdlets à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="abeb9-124">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="abeb9-125">Ensuite, si des objets peuvent être supprimés, exécutez les cmdlets PowerShell Skype Entreprise Server suivantes :</span><span class="sxs-lookup"><span data-stu-id="abeb9-125">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="abeb9-126">Supprimer votre déploiement Skype Entreprise local</span><span class="sxs-lookup"><span data-stu-id="abeb9-126">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="abeb9-127">Après avoir effectué toutes les étapes préliminaires, vous pouvez supprimer le déploiement de Skype Entreprise en suivant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="abeb9-127">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="abeb9-128">Supprimez logiquement le déploiement de Skype Entreprise Server, à l’exception d’un seul serveur frontal, comme suit :</span><span class="sxs-lookup"><span data-stu-id="abeb9-128">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="abeb9-129">a.</span><span class="sxs-lookup"><span data-stu-id="abeb9-129">a.</span></span> <span data-ttu-id="abeb9-130">Mettez à jour votre topologie Skype Entreprise Server pour qu’elle ne compte qu’un seul pool frontal :</span><span class="sxs-lookup"><span data-stu-id="abeb9-130">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="abeb9-131">Dans le Générateur de topologie, téléchargez une nouvelle copie et accédez au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="abeb9-131">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="abeb9-132">Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="abeb9-132">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="abeb9-133">Dans **Associations,** **décochez Associer un pool edge** (pour les composants multimédias) et cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="abeb9-133">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="abeb9-134">S’il existe plusieurs pools frontux, supprimez associations pour tous les pools restants.</span><span class="sxs-lookup"><span data-stu-id="abeb9-134">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="abeb9-135">Sélectionnez **Action > supprimer le déploiement.**</span><span class="sxs-lookup"><span data-stu-id="abeb9-135">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="abeb9-136">Sélectionnez **Action > publier la topologie.**</span><span class="sxs-lookup"><span data-stu-id="abeb9-136">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="abeb9-137">b.</span><span class="sxs-lookup"><span data-stu-id="abeb9-137">b.</span></span> <span data-ttu-id="abeb9-138">Après avoir publié la topologie, terminez les étapes supplémentaires décrites dans l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="abeb9-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="abeb9-139">Supprimez les annuaires des conférences Skype Entreprise Server en exécutant l’cmdlet PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="abeb9-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="abeb9-140">Finalisez la désinstallation de votre déploiement Skype Entreprise Server en exécutant l’cmdlet PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="abeb9-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="abeb9-141">Si cette étape renvoie une erreur, ouvrez un ticket de support Microsoft pour obtenir de l’aide pour supprimer les objets obsolètes restants.</span><span class="sxs-lookup"><span data-stu-id="abeb9-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="abeb9-142">Supprimez le point de contrôle du service Banque d’administration central en exécutant l’cmdlet PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="abeb9-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="abeb9-143">Annuler les modifications au niveau de la forêt du domaine Active Directory de Skype Entreprise Server en exécutant l’cmdlet PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="abeb9-143">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="abeb9-144">Annuler les modifications apportées au schéma de domaine Active Directory de Skype Entreprise Server en exécutant l’cmdlet PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="abeb9-144">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="abeb9-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="abeb9-145">See also</span></span>

- [<span data-ttu-id="abeb9-146">Désaffecter votre environnement Skype Entreprise local</span><span class="sxs-lookup"><span data-stu-id="abeb9-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="abeb9-147">Déplacer les utilisateurs et les points de terminaison vers le cloud</span><span class="sxs-lookup"><span data-stu-id="abeb9-147">Move user and endpoints to the cloud</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="abeb9-148">Désactiver votre configuration hybride</span><span class="sxs-lookup"><span data-stu-id="abeb9-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)














