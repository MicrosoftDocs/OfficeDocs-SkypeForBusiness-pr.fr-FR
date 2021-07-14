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
description: Instructions de désaffectation des Skype Entreprise Server.
ms.openlocfilehash: a69ba2d9a3bbdce8bee342c3554b758138ad1d87
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420789"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="79dd0-103">Supprimez votre déploiement sur site de Skype pour entreprises.</span><span class="sxs-lookup"><span data-stu-id="79dd0-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="79dd0-104">Cet article explique comment supprimer votre déploiement Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="79dd0-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="79dd0-105">Il s’agit de l’étape 4 des étapes suivantes pour désaffecter votre environnement local :</span><span class="sxs-lookup"><span data-stu-id="79dd0-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="79dd0-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="79dd0-106">Step 1.</span></span> <span data-ttu-id="79dd0-107">[Déplacez tous les utilisateurs requis de l’local vers le site en ligne.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="79dd0-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="79dd0-108">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="79dd0-108">Step 2.</span></span> <span data-ttu-id="79dd0-109">[Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="79dd0-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="79dd0-110">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="79dd0-110">Step 3.</span></span> [<span data-ttu-id="79dd0-111">Migrer les points de terminaison de l’application hybride de l’local vers le mode en ligne</span><span class="sxs-lookup"><span data-stu-id="79dd0-111">Migrate hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="79dd0-112">**Étape 4. Supprimez votre déploiement Skype Entreprise local.**</span><span class="sxs-lookup"><span data-stu-id="79dd0-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="79dd0-113">(Cet article)</span><span class="sxs-lookup"><span data-stu-id="79dd0-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="79dd0-114">Les étapes décrites dans cet article s’appliquent uniquement si vous utilisez la méthode 2 pour gérer les attributs utilisateur, comme décrit [ici.](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)</span><span class="sxs-lookup"><span data-stu-id="79dd0-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="79dd0-115">Si vous utilisez la méthode 1, n’utilisez pas les étapes décrites dans cet article pour supprimer Skype Entreprise serveurs.</span><span class="sxs-lookup"><span data-stu-id="79dd0-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="79dd0-116">Au lieu de cela, vous pouvez ré-imager les serveurs.</span><span class="sxs-lookup"><span data-stu-id="79dd0-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="79dd0-117">Pour effectuer les étapes de cet article, vous avez besoin de privilèges pour le groupe Administrateurs du schéma et le groupe Administrateurs Enterprise schéma.</span><span class="sxs-lookup"><span data-stu-id="79dd0-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="79dd0-118">Vous aurez besoin de ces privilèges pour annuler le schéma Skype Entreprise Server et les modifications au niveau de la forêt apportées aux services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="79dd0-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="79dd0-119">Vous devez également être membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="79dd0-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="79dd0-120">Préparer la suppression du déploiement Skype Entreprise déploiement</span><span class="sxs-lookup"><span data-stu-id="79dd0-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="79dd0-121">Après avoir passé tous les comptes d’utilisateur requis vers le cloud, il se peut qu’il reste des objets locaux, tels que des contacts et des applications, que vous devrez nettoyer.</span><span class="sxs-lookup"><span data-stu-id="79dd0-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="79dd0-122">Utilisez les étapes ci-dessous pour nettoyer ces objets et assurez-vous que vous êtes membre du groupe Administrateur local et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="79dd0-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="79dd0-123">Notez que ExUmContacts et PersistantChatEndPoints ne sont pas disponibles Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="79dd0-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="79dd0-124">Si vous avez Skype Entreprise Server 2019, les cmdlets correspondantes dans les étapes ci-dessous doivent être omises.</span><span class="sxs-lookup"><span data-stu-id="79dd0-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="79dd0-125">Pour vérifier si des contacts ou des applications sont associés au déploiement Skype Entreprise Server local, exécutez les cmdlets PowerShell Skype Entreprise Server suivantes.</span><span class="sxs-lookup"><span data-stu-id="79dd0-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

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
2. <span data-ttu-id="79dd0-126">Examinez les listes de sortie des cmdlets à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="79dd0-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="79dd0-127">Ensuite, si des objets peuvent être supprimés, exécutez les Skype Entreprise Server cmdlets PowerShell suivantes :</span><span class="sxs-lookup"><span data-stu-id="79dd0-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

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
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="79dd0-128">Supprimez votre déploiement sur site de Skype pour entreprises.</span><span class="sxs-lookup"><span data-stu-id="79dd0-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="79dd0-129">Après avoir effectué toutes les étapes préliminaires, vous pouvez supprimer le déploiement Skype Entreprise en suivant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="79dd0-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="79dd0-130">Supprimez logiquement le Skype Entreprise Server déploiement, à l’exception d’un seul frontal, comme suit :</span><span class="sxs-lookup"><span data-stu-id="79dd0-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   1. <span data-ttu-id="79dd0-131">Mettez à jour Skype Entreprise Server topologie principale pour qu’elle ne compte qu’un seul pool frontal :</span><span class="sxs-lookup"><span data-stu-id="79dd0-131">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

      1. <span data-ttu-id="79dd0-132">Dans le Générateur de topologie, téléchargez une nouvelle copie et accédez au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="79dd0-132">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
      1. <span data-ttu-id="79dd0-133">Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="79dd0-133">Right-click the pool, and then click **Edit Properties**.</span></span>
      1. <span data-ttu-id="79dd0-134">Dans **Associations,** **décochez Associer un pool edge** (pour les composants multimédias) et cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="79dd0-134">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
      1. <span data-ttu-id="79dd0-135">S’il existe plusieurs pools frontux, supprimez associations pour tous les pools restants.</span><span class="sxs-lookup"><span data-stu-id="79dd0-135">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
      1. <span data-ttu-id="79dd0-136">Sélectionnez **Action > supprimer le déploiement.**</span><span class="sxs-lookup"><span data-stu-id="79dd0-136">Select **Action > Remove Deployment**.</span></span>
      1. <span data-ttu-id="79dd0-137">Sélectionnez **Action > publier la topologie.**</span><span class="sxs-lookup"><span data-stu-id="79dd0-137">Select **Action > Publish Topology**.</span></span>

    1. <span data-ttu-id="79dd0-138">Après avoir publié la topologie, terminez les étapes supplémentaires décrites dans l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="79dd0-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="79dd0-139">Supprimez Skype Entreprise Server des conférences en exécutant l’Skype Entreprise Server cmdlet PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="79dd0-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="79dd0-140">Finalisez la désinstallation de votre déploiement Skype Entreprise Server en exécutant l’Skype Entreprise Server cmdlet PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="79dd0-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="79dd0-141">Si cette étape renvoie une erreur, ouvrez un ticket de support Microsoft pour obtenir de l’aide pour supprimer les objets obsolètes restants.</span><span class="sxs-lookup"><span data-stu-id="79dd0-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="79dd0-142">Supprimez le point de contrôle du service Banque d’administration central en exécutant l’Skype Entreprise Server cmdlet PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="79dd0-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="79dd0-143">Pour annuler Skype Entreprise Server modifications au niveau du domaine Active Directory, exécutez l’Skype Entreprise Server cmdlet PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="79dd0-143">Undo Skype for Business Server Active Directory domain-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="79dd0-144">Pour annuler Skype Entreprise Server modifications au niveau de la forêt Active Directory, exécutez l’Skype Entreprise Server cmdlet PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="79dd0-144">Undo Skype for Business Server Active Directory forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="79dd0-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79dd0-145">See also</span></span>

- [<span data-ttu-id="79dd0-146">Mise hors service de votre environnement Skype pour entreprises sur site</span><span class="sxs-lookup"><span data-stu-id="79dd0-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="79dd0-147">Déplacer tous les utilisateurs requis de l’local vers le site en ligne</span><span class="sxs-lookup"><span data-stu-id="79dd0-147">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="79dd0-148">Désactiver votre configuration hybride</span><span class="sxs-lookup"><span data-stu-id="79dd0-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="79dd0-149">Déplacer des points de terminaison d’application hybride de l’local vers le mode en ligne</span><span class="sxs-lookup"><span data-stu-id="79dd0-149">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

