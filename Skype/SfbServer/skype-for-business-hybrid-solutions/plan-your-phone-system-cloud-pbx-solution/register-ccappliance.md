---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: La cmdlet Register-CcAppliance enregistre les informations d’appliance sur un site PSTN dans une configuration client en ligne. Une appliance doit être inscrite avant de pouvoir être déployée et gérée par le service de gestion de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824300"
---
# <a name="register-ccappliance"></a><span data-ttu-id="f6818-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f6818-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="f6818-105">La cmdlet Register-CcAppliance enregistre les informations d’appliance sur un site PSTN dans une configuration client en ligne.</span><span class="sxs-lookup"><span data-stu-id="f6818-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="f6818-106">Une appliance doit être inscrite avant de pouvoir être déployée et gérée par le service de gestion de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f6818-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="f6818-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="f6818-107">Examples</span></span>
<span data-ttu-id="f6818-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f6818-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="f6818-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="f6818-109">Example 1</span></span>

<span data-ttu-id="f6818-110">L’exemple suivant enregistre les informations actuelles de l’appliance dans une configuration client en ligne :</span><span class="sxs-lookup"><span data-stu-id="f6818-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="f6818-111">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="f6818-111">Example 2</span></span>

<span data-ttu-id="f6818-112">L’exemple suivant vérifie la configuration pour l’inscription locale sans se connecter à une configuration client en ligne :</span><span class="sxs-lookup"><span data-stu-id="f6818-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="f6818-113">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="f6818-113">Example 3</span></span>

<span data-ttu-id="f6818-114">L’exemple suivant inscrit l’appliance actuelle avec le nom « Appliance1 » sur le site PSTN « Site1 » :</span><span class="sxs-lookup"><span data-stu-id="f6818-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="f6818-115">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="f6818-115">Detailed Description</span></span>
<span data-ttu-id="f6818-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f6818-116"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="f6818-117">Vous devez fournir le nom et le mot de passe du compte d’administrateur client.</span><span class="sxs-lookup"><span data-stu-id="f6818-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="f6818-118">Utilisez le compte que vous avez créé pour la gestion en ligne de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f6818-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="f6818-119">Dans la version 1.4.2 et antérieure, suivez les instructions pour fournir le mot de passe du certificat externe, le mot de passe d’administrateur en mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe d’administrateur de la VM.</span><span class="sxs-lookup"><span data-stu-id="f6818-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="f6818-120">Dans la version 2.0 et les ultérieures, suivez les instructions pour fournir le mot de passe du certificat externe, le mot de passe CceService et le mot de passe CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="f6818-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="f6818-121">À la fin de l’inscription, redémarrez le service de gestion Cloud Connector et connectez-vous aux services en tant que compte CceService.</span><span class="sxs-lookup"><span data-stu-id="f6818-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="f6818-122">SiteName combiné au nom de CloudConnector.ini externe du serveur Edge est considéré comme une identité de site PSTN.</span><span class="sxs-lookup"><span data-stu-id="f6818-122">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="f6818-123">Si ni le nom de site, ni le FQDN externe du serveur Edge n’ont été utilisés pour inscrire un site, un nouveau site sera créé pour cette appliance dans une configuration de client en ligne.</span><span class="sxs-lookup"><span data-stu-id="f6818-123">If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration.</span></span> <span data-ttu-id="f6818-124">Si une identité de site PSTN est trouvée, un site PSTN utilisera cette identité et l’appliance sera inscrite sur ce site PSTN.</span><span class="sxs-lookup"><span data-stu-id="f6818-124">If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="f6818-125">Dans la situation suivante, la cmdlet échoue et indique que Site1 est déjà inscrit :</span><span class="sxs-lookup"><span data-stu-id="f6818-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="f6818-126">SiteName est Site1 et le FQDN externe du serveur Edge est edgserver1.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f6818-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="f6818-127">Un site PSTN dont le nom de site est Site1 et le nom de edgserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f6818-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="f6818-128">Un site PSTN dont le nom de site est NewSite et le nom de edgserver1.contoso.com serveur Edge a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="f6818-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="f6818-129">ApplianceName combiné au nom de CloudConnector.ini serveur de médiation est considéré comme une identité appliance.</span><span class="sxs-lookup"><span data-stu-id="f6818-129">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity.</span></span> <span data-ttu-id="f6818-130">Si ni le nom d’appliance, ni le nom de groupe du serveur de médiation n’ont été utilisés pour inscrire une appliance, une nouvelle appliance est créée dans la configuration du client en ligne.</span><span class="sxs-lookup"><span data-stu-id="f6818-130">If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration.</span></span> <span data-ttu-id="f6818-131">Si l’appliance est déjà inscrite, la cmdlet échoue.</span><span class="sxs-lookup"><span data-stu-id="f6818-131">If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="f6818-132">Dans la situation suivante, l’cmdlet échoue et indique que l’appliance est déjà inscrite :</span><span class="sxs-lookup"><span data-stu-id="f6818-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="f6818-133">ApplianceName est Appliance1 et le nom de ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="f6818-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="f6818-134">Dans le site PSTN actuel, si une appliance dont le nom est Appliance1 et le nom de domaine complet du serveur de médiation est ms.vdomain.com ou si une appliance dont le nom est NewAppliance et le nom de domaine complet du serveur de médiation ms1.vdomain.com a été inscrite.</span><span class="sxs-lookup"><span data-stu-id="f6818-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="f6818-135">Paramètres</span><span class="sxs-lookup"><span data-stu-id="f6818-135">Parameters</span></span>
<span data-ttu-id="f6818-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f6818-136"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="f6818-137">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="f6818-137">**Parameter**</span></span>|<span data-ttu-id="f6818-138">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="f6818-138">**Required**</span></span>|<span data-ttu-id="f6818-139">**Type**</span><span class="sxs-lookup"><span data-stu-id="f6818-139">**Type**</span></span>|<span data-ttu-id="f6818-140">**Description**</span><span class="sxs-lookup"><span data-stu-id="f6818-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6818-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="f6818-141">SiteName</span></span>  <br/> |<span data-ttu-id="f6818-142">Facultatif</span><span class="sxs-lookup"><span data-stu-id="f6818-142">Optional</span></span>  <br/> |<span data-ttu-id="f6818-143">System.String</span><span class="sxs-lookup"><span data-stu-id="f6818-143">System.String</span></span>  <br/> |<span data-ttu-id="f6818-144">Nom du site PSTN sur lequel l’appliance est inscrite.</span><span class="sxs-lookup"><span data-stu-id="f6818-144">PSTN site name to which the appliance is registered.</span></span> <span data-ttu-id="f6818-145">La valeur par défaut est La valeur SiteName dans CloudConnector.ini fichier.</span><span class="sxs-lookup"><span data-stu-id="f6818-145">Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="f6818-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="f6818-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="f6818-147">Facultatif</span><span class="sxs-lookup"><span data-stu-id="f6818-147">Optional</span></span>  <br/> |<span data-ttu-id="f6818-148">System.String</span><span class="sxs-lookup"><span data-stu-id="f6818-148">System.String</span></span>  <br/> |<span data-ttu-id="f6818-149">Nom de l’appliance actuelle.</span><span class="sxs-lookup"><span data-stu-id="f6818-149">Name of the current appliance.</span></span> <span data-ttu-id="f6818-150">La valeur par défaut est le nom de l’ordinateur du serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="f6818-150">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="f6818-151">Local</span><span class="sxs-lookup"><span data-stu-id="f6818-151">Local</span></span>  <br/> |<span data-ttu-id="f6818-152">Facultatif</span><span class="sxs-lookup"><span data-stu-id="f6818-152">Optional</span></span>  <br/> |<span data-ttu-id="f6818-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="f6818-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="f6818-154">Vérifiez les configurations d’inscription localement sans vous connecter à la configuration du client en ligne.</span><span class="sxs-lookup"><span data-stu-id="f6818-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f6818-155">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="f6818-155">Input Types</span></span>
<span data-ttu-id="f6818-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f6818-156"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="f6818-157">Aucun.</span><span class="sxs-lookup"><span data-stu-id="f6818-157">None.</span></span> <span data-ttu-id="f6818-158">La cmdlet Register-CcAppliance n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="f6818-158">The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f6818-159">Types de retour</span><span class="sxs-lookup"><span data-stu-id="f6818-159">Return Types</span></span>
<span data-ttu-id="f6818-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f6818-160"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="f6818-161">Aucun</span><span class="sxs-lookup"><span data-stu-id="f6818-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f6818-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6818-162">See also</span></span>
<span data-ttu-id="f6818-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f6818-163"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="f6818-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f6818-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="f6818-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f6818-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="f6818-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f6818-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="f6818-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f6818-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

