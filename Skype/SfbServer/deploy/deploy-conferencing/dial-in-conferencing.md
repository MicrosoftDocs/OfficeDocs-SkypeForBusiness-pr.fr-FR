---
title: Configuration des conférences rendez-vous dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer l’appel de conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: f6d724f522ac264699a3bf7a3fb63749f7da0c05
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server-2015"></a><span data-ttu-id="00504-103">Configuration des conférences rendez-vous dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="00504-103">Configure dial-in conferencing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="00504-104">**Résumé :** Lisez cette rubrique pour savoir comment configurer l’appel de conférence dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="00504-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="00504-105">Après avoir créé une topologie qui inclut la charge de conférence et des conférences à distance sélectionnée, vous devez exécuter des étapes supplémentaires pour configurer les conférences à distance.</span><span class="sxs-lookup"><span data-stu-id="00504-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="00504-106">Avant de lire cette rubrique, veillez à ce que vous avez lu le [Plan pour les conférences à distance dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [matérielle et logicielle requise pour les conférences dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)et le diagramme de flux [déploiement et liste de vérification pour les conférences à distance](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span><span class="sxs-lookup"><span data-stu-id="00504-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server 2015](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server 2015](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="00504-107">Pour configurer la conférence rendez-vous, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="00504-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="00504-108">Configure dial plans</span><span class="sxs-lookup"><span data-stu-id="00504-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="00504-109">Configure dial-in conferencing regions</span><span class="sxs-lookup"><span data-stu-id="00504-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="00504-110">Configure dial-in access numbers</span><span class="sxs-lookup"><span data-stu-id="00504-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="00504-111">Configure conferencing policies</span><span class="sxs-lookup"><span data-stu-id="00504-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="00504-112">Assign a Line URI to a user account</span><span class="sxs-lookup"><span data-stu-id="00504-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="00504-113">De plus, vous pouvez effectuer les tâches facultatives suivantes.</span><span class="sxs-lookup"><span data-stu-id="00504-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="00504-114">Pour plus d’informations sur ces tâches facultatives, consultez [gérer à distance conférence dans Skype pour Business Server 2015](../../manage/conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="00504-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server 2015](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="00504-115">Gestion des stratégies de code confidentiel pour les conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="00504-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="00504-116">Gestion du mappage des clés des commandes DTMF</span><span class="sxs-lookup"><span data-stu-id="00504-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="00504-117">Création d’un annuaire de conférences</span><span class="sxs-lookup"><span data-stu-id="00504-117">Create conference directories</span></span>
    
- <span data-ttu-id="00504-118">Gestion des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence</span><span class="sxs-lookup"><span data-stu-id="00504-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="00504-119">Test des paramètres de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="00504-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="00504-120">Envoi d’un message électronique de bienvenue aux utilisateurs rendez-vous</span><span class="sxs-lookup"><span data-stu-id="00504-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="00504-121">Configurer des plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="00504-121">Configure dial plans</span></span>
<span data-ttu-id="00504-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="00504-122"></span></span>

<span data-ttu-id="00504-123">Lorsque vous déployez la conférence rendez-vous, vous devez créer ou modifier un ou plusieurs plans de routage des numéros de téléphone d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="00504-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="00504-124">Vous devez également vous assurer que chaque plan de numérotation contienne au moins une règle de normalisation--une règle qui convertit des extensions téléphoniques en numéros de téléphone complète au format E.164.</span><span class="sxs-lookup"><span data-stu-id="00504-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="00504-p104">Les utilisateurs de conférences rendez-vous participent à des conférences en tant qu’utilisateurs d’entreprise authentifiés en entrant leur code confidentiel et leur numéro de téléphone. Vous avez besoin d’une règle de normalisation pour convertir les numéros de poste en numéros de téléphone complets afin que les utilisateurs puissent être authentifiés lorsqu’ils saisissent simplement un numéro de poste.</span><span class="sxs-lookup"><span data-stu-id="00504-p104">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="00504-127">Pour configurer des plans de numérotation pour la conférence rendez-vous :</span><span class="sxs-lookup"><span data-stu-id="00504-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="00504-128">Que vous déployiez ou non Voix Entreprise, modifiez le plan de numérotation global pour ajouter une région de conférence rendez-vous et veillez à ce qu’une règle de normalisation convertisse avec précision vos numéros d’accès.</span><span class="sxs-lookup"><span data-stu-id="00504-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="00504-129">Pour obtenir des instructions détaillées, reportez-vous à la section [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="00504-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="00504-130">Si vous n’avez pas déployé Voix Entreprise, créez des plans de numérotation pour vos numéros d’accès aux conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="00504-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="00504-131">Veillez à inclure une région de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="00504-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="00504-132">Pour obtenir des instructions détaillées, reportez-vous à la section [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="00504-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="00504-133">Si vous avez déployé Voix Entreprise, modifiez, si nécessaire, les plans de numérotation de Voix Entreprise pour inclure des régions et utilisez les règles de normalisation appropriées pour les numéros d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="00504-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="00504-134">Vous pouvez également créer des plans de numérotation dédiés, utilisés exclusivement pour les numéros d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="00504-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="00504-135">Pour obtenir des instructions détaillées, reportez-vous à la section [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="00504-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="00504-136">Pour plus d’informations sur la création de règles de normalisation, consultez [créer ou modifier une règle de normalisation dans Skype pour 2015 de Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="00504-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business 2015](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="00504-137">Configuration des régions de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="00504-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="00504-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="00504-138"></span></span>

<span data-ttu-id="00504-p108">Lorsque vous créez un plan de numérotation, vous spécifiez la région de conférence rendez-vous qui s’applique au plan de numérotation. La région de conférence rendez-vous associe des numéros d’accès aux conférences rendez-vous au plan de numérotation approprié. Quand vous créez le numéro d’accès à la conférence rendez-vous, vous sélectionnez les régions qui associent le numéro d’accès aux plans de numérotation appropriés.</span><span class="sxs-lookup"><span data-stu-id="00504-p108">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="00504-142">Comme il est important de spécifier une région pour tous les plans de numérotation, nous vous recommandons de vérifier que tous les plans de numérotation sont associés à des régions de conférence.</span><span class="sxs-lookup"><span data-stu-id="00504-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="00504-143">Utilisez l’applet de commande **Get-CsDialPlan** pour vérifier qu’une région est configurée pour tous les plans de numérotation de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="00504-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="00504-144">Si ce n’est pas le cas, vous pouvez utiliser l’applet de commande **Set-CsDialPlan** pour configurer la région.</span><span class="sxs-lookup"><span data-stu-id="00504-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="00504-145">Vous pouvez également utiliser Skype pour le panneau de configuration de Business Server pour mettre à jour la zone de dans des plans de numérotation existant.</span><span class="sxs-lookup"><span data-stu-id="00504-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="00504-146">Pour plus d’informations sur l’utilisation de Skype pour le panneau de configuration de Business Server, consultez [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="00504-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="00504-147">Pour vérifier que la région est correctement configurée dans les plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="00504-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="00504-148">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="00504-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="00504-149">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="00504-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="00504-150">Exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="00504-150">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="00504-151">Exemple :</span><span class="sxs-lookup"><span data-stu-id="00504-151">For example:</span></span>
    
   ```
   Get-CsDialPlan
   ```

   <span data-ttu-id="00504-152">Dans cet exemple, tous les plans de numérotation configurés pour votre organisation sont renvoyés.</span><span class="sxs-lookup"><span data-stu-id="00504-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="00504-153">Vérifiez les plans de numérotation renvoyés pour identifier ceux ne comportant pas la région de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="00504-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="00504-154">Pour plus d’informations, consultez [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="00504-154">For more information, see [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="00504-155">Pour définir la propriété de région d’un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="00504-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="00504-156">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="00504-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="00504-157">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="00504-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="00504-158">Pour tous les plans de numérotation ne comportant pas de région de conférence rendez-vous, exécutez :</span><span class="sxs-lookup"><span data-stu-id="00504-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="00504-159">Exemple :</span><span class="sxs-lookup"><span data-stu-id="00504-159">For example:</span></span>
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="00504-160">Dans cet exemple, le plan de numérotation dont l’identité est Redmond est modifié afin de définir la propriété DialinConferencingRegion sur « US West Coast ».</span><span class="sxs-lookup"><span data-stu-id="00504-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="00504-161">Pour plus d’informations, voir [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="00504-161">For more information, see [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="00504-162">Configurer les numéros d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="00504-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="00504-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="00504-163"></span></span>

<span data-ttu-id="00504-164">Lorsque vous déployez des conférences rendez-vous, vous devez configurer les numéros de téléphone que les utilisateurs peuvent appeler à partir du réseau téléphonique commuté pour participer à la partie audio des conférences.</span><span class="sxs-lookup"><span data-stu-id="00504-164">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="00504-165">Ces numéros s’affichent dans les invitations à une réunion et sur la page web des paramètres de configuration des conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="00504-165">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="00504-166">Avant de créer des numéros d’accès aux conférences rendez-vous, vous devez planifier vos régions de conférences rendez-vous puis configurer les plans de numérotation correspondants.</span><span class="sxs-lookup"><span data-stu-id="00504-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="00504-167">Pour plus d’informations sur les zones, reportez-vous à [planification pour les conférences à distance dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="00504-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server 2015](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="00504-168">Pour plus d’informations sur la configuration des plans pour les conférences à distance d’appel, consultez [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="00504-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="00504-p112">Vous ne pouvez pas utiliser un nouveau numéro d’accès pour la conférence rendez-vous tant que la réplication AD DS de ce numéro n’est pas terminée. La réplication peut durer plusieurs heures.</span><span class="sxs-lookup"><span data-stu-id="00504-p112">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete. Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="00504-171">Une fois que vous avez créé les numéros d’accès aux conférences rendez-vous, vous pouvez modifier le nom complet des objets contact Active Directory pour permettre aux utilisateurs d’identifier plus facilement le numéro d’accès approprié.</span><span class="sxs-lookup"><span data-stu-id="00504-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="00504-172">Pour modifier le nom d’affichage, utilisez l’applet de commande [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="00504-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="00504-173">Vous ne devez pas modifier manuellement les objets Active Directory.</span><span class="sxs-lookup"><span data-stu-id="00504-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="00504-174">Pour créer un numéro d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="00504-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="00504-175">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="00504-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="00504-176">Ouvrez Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="00504-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="00504-177">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.</span><span class="sxs-lookup"><span data-stu-id="00504-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="00504-178">Dans la page **Numéro d’accès entrant**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="00504-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="00504-179">Cliquez sur **Nouveau** pour ouvrir **Nouveau numéro d’accès entrant**.</span><span class="sxs-lookup"><span data-stu-id="00504-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="00504-180">Cliquez sur l’un des numéros d’accès entrant dans la liste, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="00504-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00504-p114">Utiliser le champ de recherche pour rechercher le contenu d’une colonne dans la liste des numéros d’accès entrant peut ne pas produire les résultats que vous attendez. Par conséquent, triez la liste selon la colonne qui vous intéresse pour identifier le numéro d’accès entrant que vous voulez afficher ou modifier.</span><span class="sxs-lookup"><span data-stu-id="00504-p114">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="00504-p115">Dans **Numéro affiché**, tapez le numéro de téléphone que les utilisateurs du réseau téléphonique commuté (RTC) composent pour rejoindre une conférence. Ce numéro est affiché dans les invitations aux réunions et dans la page web des paramètres des conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="00504-p115">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference. This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="00504-185">In **Nom d’affichage**, tapez la description du numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="00504-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="00504-186">Il s’agit de celui qui est associé au numéro d’accès à distance dans Skype pour les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="00504-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="00504-187">Ce nom est affiché dans le client lorsqu’un utilisateur appelle le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="00504-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="00504-p117">Dans **URI de ligne**, tapez le numéro E.164 du numéro d’accès entrant au format d’URI TEL, avec le symbole + avant le numéro et sans espace. Par exemple, tel :+14255550200.</span><span class="sxs-lookup"><span data-stu-id="00504-p117">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00504-190">Le même URI de ligne ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="00504-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="00504-191">Dans **URI SIP**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="00504-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="00504-192">Dans la zone de texte, tapez un URI SIP (Session Initiation Protocol) unique pour ce numéro d’accès à une conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="00504-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="00504-193">Cet URI SIP est affiché dans divers emplacements, y compris, mais non limité, pour appeler des messages de notification et les versions antérieures de clients Lync.</span><span class="sxs-lookup"><span data-stu-id="00504-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00504-p119">Le même URI SIP ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous. Il n’est pas possible de modifier l’URI SIP une fois que le numéro d’accès est créé. Le seul moyen de modifier l’URI SIP est de supprimer et de recréer le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="00504-p119">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="00504-197">Dans la zone de liste déroulante, cliquez sur le domaine de l’application de la surveillance du conférence qui prend en charge ce nombre d’accès à distance.</span><span class="sxs-lookup"><span data-stu-id="00504-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="00504-198">Dans **Pool**, cliquez sur le pool qui exécute l’instance d’Intendant Conférence qui prend en charge ce numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="00504-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00504-199">Si vous devez modifier le pool après avoir créé le numéro d’accès, vous devez utiliser l’applet de commande [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) ou supprimer et recréer le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="00504-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="00504-200">Dans **Langue principale**, cliquez sur la langue des invites pour ce numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="00504-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="00504-p120">La langue principale est la langue que l’Intendant Conférence utilise pour répondre aux appels. Les langues prises en charge sont affichées avec chaque numéro de téléphone d’accès dans la page web des paramètres des conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="00504-p120">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="00504-203">(Facultatif) Dans **Langues secondaires (quatre au maximum)**, cliquez sur **Ajouter**, sélectionnez les langues supplémentaires que vous souhaitez prendre en charge pour les personnes qui appellent ce numéro d’accès entrant, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="00504-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="00504-p121">Vous pouvez sélectionner jusqu’à quatre langues secondaires pour chaque numéro d’accès entrant. Les utilisateurs peuvent sélectionner une langue secondaire avant d’entrer l’ID de la conférence à laquelle ils souhaitent participer.</span><span class="sxs-lookup"><span data-stu-id="00504-p121">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="00504-206">Pour ajouter une région pour le numéro d’accès à distance, dans **les régions associés**, cliquez sur **Ajouter**, cliquez sur une ou plusieurs zones qui sont associés à des plans de numérotation de ce numéro d’accès à distance, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="00504-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="00504-207">Pour supprimer une région du numéro d’accès entrant, sous **Régions associées**, cliquez sur la région que vous souhaitez supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="00504-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="00504-208">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="00504-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="00504-209">Configuration des stratégies de conférence</span><span class="sxs-lookup"><span data-stu-id="00504-209">Configure conferencing policies</span></span>
<span data-ttu-id="00504-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="00504-210"></span></span>

<span data-ttu-id="00504-p122">Une stratégie de conférence est un paramètre de compte d’utilisateur qui spécifie les modalités de la conférence pour les participants. Vous pouvez créer des stratégies de conférence avec une étendue de site ou d’utilisateur. Les paramètres de stratégie de conférence englobent de nombreux aspects de la planification de la conférence et de la participation. Plusieurs paramètres de stratégies de conférence prennent en charge la conférence rendez-vous pour les participants. Lorsque vous configurez une conférence rendez-vous, vous devez vérifier que ces champs sont correctement définis pour votre organisation, et vous devez les modifier uniquement en cas de nécessité.</span><span class="sxs-lookup"><span data-stu-id="00504-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="00504-216">Pour plus d’informations sur la configuration des stratégies de la conférence, voir [Gérer les stratégies de conférence dans Skype pour Business Server 2015](../../manage/conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="00504-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server 2015](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="00504-217">Assign a Line URI to a user account</span><span class="sxs-lookup"><span data-stu-id="00504-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="00504-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="00504-218"></span></span>

<span data-ttu-id="00504-219">Les utilisateurs d’appels entrants doivent entrer un numéro de téléphone ou de poste, ainsi qu’un code confidentiel pour participer à des conférences en qualité d’utilisateurs authentifiés.</span><span class="sxs-lookup"><span data-stu-id="00504-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="00504-220">La téléphonie **Ligne URI** spécifié sur Skype pour les comptes d’utilisateurs de serveur d’entreprise est requise pour l’authentification.</span><span class="sxs-lookup"><span data-stu-id="00504-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="00504-221">La procédure décrite dans cette rubrique explique comment affecter un **URI de ligne** pour un compte utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="00504-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="00504-222">Si vous devez attribuer un **URI de ligne** à plusieurs comptes utilisateur, vous pouvez créer un script à l’aide de l’applet de commande **Set-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="00504-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="00504-223">Pour plus d’informations sur l’utilisation d’un exemple de script pour attribuer des **URI de ligne** à plusieurs comptes d’utilisateurs, voir [Attribuer des URI de ligne à plusieurs utilisateurs](https://go.microsoft.com/fwlink/p/?linkId=196945).</span><span class="sxs-lookup"><span data-stu-id="00504-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="00504-224">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-UserAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="00504-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="00504-225">Ouvrez Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="00504-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="00504-226">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="00504-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="00504-227">Dans le champ de recherche, tapez le nom de l’utilisateur à configurer pour une conférence rendez-vous ou cliquez sur **Ajouter un filtre** pour spécifier les champs de la recherche, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="00504-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="00504-228">Double-cliquez sur le nom utilisateur pour ouvrir la boîte de dialogue **Modifier l’utilisateur Skype Entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="00504-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="00504-229">Sous **Téléphonie**, dans le champ **URI de ligne**, tapez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200).</span><span class="sxs-lookup"><span data-stu-id="00504-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00504-230">Vous pouvez spécifier un **URI de ligne** uniquement si l’option **Téléphonie** est définie sur **De PC à PC uniquement**, **Voix Entreprise**, **Contrôle d’appel distant** ou **Contrôle d’appel distant uniquement**.</span><span class="sxs-lookup"><span data-stu-id="00504-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="00504-231">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="00504-231">Click **Commit**.</span></span>
    

