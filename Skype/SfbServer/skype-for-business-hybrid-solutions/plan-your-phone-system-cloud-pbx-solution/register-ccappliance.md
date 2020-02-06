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
description: L’applet de commande Register-CcAppliance enregistre les informations de l’appliance vers un site RTC dans une configuration client en ligne. Une appliance doit être enregistrée avant d’être déployée et gérée par le service de gestion de Skype Entreprise, version Cloud Connector.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824300"
---
# <a name="register-ccappliance"></a><span data-ttu-id="565cd-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="565cd-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="565cd-105">L’applet de commande Register-CcAppliance enregistre les informations de l’appliance vers un site RTC dans une configuration client en ligne.</span><span class="sxs-lookup"><span data-stu-id="565cd-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="565cd-106">Une appliance doit être enregistrée avant d’être déployée et gérée par le service de gestion de Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="565cd-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="565cd-107">Exemples</span><span class="sxs-lookup"><span data-stu-id="565cd-107">Examples</span></span>
<span data-ttu-id="565cd-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="565cd-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="565cd-109">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="565cd-109">Example 1</span></span>

<span data-ttu-id="565cd-110">L’exemple suivant enregistre les informations de l’appliance actuelle dans une configuration de client en ligne :</span><span class="sxs-lookup"><span data-stu-id="565cd-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="565cd-111">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="565cd-111">Example 2</span></span>

<span data-ttu-id="565cd-112">L’exemple suivant vérifie la configuration d’enregistrement local sans connexion à une configuration de client en ligne :</span><span class="sxs-lookup"><span data-stu-id="565cd-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="565cd-113">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="565cd-113">Example 3</span></span>

<span data-ttu-id="565cd-114">L’exemple suivant enregistre l’appliance actuelle sous le nom « Appliance1 » sur le site RTC « Site1 » :</span><span class="sxs-lookup"><span data-stu-id="565cd-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="565cd-115">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="565cd-115">Detailed Description</span></span>
<span data-ttu-id="565cd-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="565cd-116"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="565cd-117">Vous devez fournir le mot de passe et le nom du compte d'administrateur du client.</span><span class="sxs-lookup"><span data-stu-id="565cd-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="565cd-118">Utilisez le compte que vous avez créé pour la gestion en ligne dans Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="565cd-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="565cd-119">Dans la version 1.4.2 et les versions antérieures, suivez les instructions pour fournir le mot de passe du certificat externe, le mot de passe d’administrateur du mode sans échec, le mot de passe d’administrateur de domaine et le mot de passe d’administrateur</span><span class="sxs-lookup"><span data-stu-id="565cd-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="565cd-120">Dans la version 2,0 et les versions ultérieures, suivez les instructions pour fournir le mot de passe du certificat externe, le mot de passe CceService et le mot de passe CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="565cd-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="565cd-121">À la fin de l’enregistrement, redémarrez le service de gestion des connecteurs Cloud et connectez-vous aux services en tant que compte CceService.</span><span class="sxs-lookup"><span data-stu-id="565cd-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="565cd-p104">Le nom du site combiné au nom de domaine complet (FQDN) externe du serveur Edge dans le fichier CloudConnector.ini est considéré comme une identité du site RTC. Si ni le nom du site ni le FQDN externe du serveur Edge n’ont été utilisés pour inscrire un site, un nouveau site est créé pour cette appliance dans une configuration de client en ligne. Si une identité de site RTC est trouvée, un site RTC utilise cette identité et l’appliance est enregistrée sur ce site RTC. </span><span class="sxs-lookup"><span data-stu-id="565cd-p104">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration. If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="565cd-125">Dans la situation suivante, l’applet de commande échoue et indique que le Site1 est déjà inscrit : </span><span class="sxs-lookup"><span data-stu-id="565cd-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="565cd-126">Le nom du site est Site1 et le nom de domaine complet (FQDN) externe du serveur Edge est edgserver1.contoso.com. </span><span class="sxs-lookup"><span data-stu-id="565cd-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="565cd-127">Un site RTC dont le nom est Site1 et le nom de domaine complet (FQDN) externe du serveur Edge est edgserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="565cd-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="565cd-128">Un site RTC dont le nom est NewSite et le nom de domaine complet (FQDN) externe du serveur Edge est edgserver1.contoso.com a été inscrit. </span><span class="sxs-lookup"><span data-stu-id="565cd-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="565cd-p105">Le nom de l'appliance combiné au nom de domaine complet (FQDN) du serveur de médiation dans le fichier CloudConnector.ini est considéré comme une identité de l’appliance. Si ni le nom de l'appliance ni le nom de domaine complet (FQDN) du serveur de médiation n’ont été utilisés pour inscrire une appliance, une nouvelle appliance est créée dans la configuration de client en ligne. Si l’appliance est déjà inscrite, l’applet de commande échoue.</span><span class="sxs-lookup"><span data-stu-id="565cd-p105">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity. If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration. If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="565cd-132">Dans la situation suivante, l’applet de commande échoue et indique que l’appliance est déjà inscrite : </span><span class="sxs-lookup"><span data-stu-id="565cd-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="565cd-133">Le nom de l'appliance est Appliance1 et le nom de domaine complet (FQDN) du serveur de médiation est ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="565cd-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="565cd-134">Dans le site RTC actuel, si une appliance dont le nom est Appliance1 et le nom de domaine complet (FQDN) du serveur de médiation est ms.vdomain.com ou une appliance dont le nom est NewAppliance et le FQDN du serveur de médiation est ms1.vdomain.com a été inscrit.</span><span class="sxs-lookup"><span data-stu-id="565cd-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="565cd-135">Paramètres</span><span class="sxs-lookup"><span data-stu-id="565cd-135">Parameters</span></span>
<span data-ttu-id="565cd-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="565cd-136"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="565cd-137">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="565cd-137">**Parameter**</span></span>|<span data-ttu-id="565cd-138">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="565cd-138">**Required**</span></span>|<span data-ttu-id="565cd-139">**Type**</span><span class="sxs-lookup"><span data-stu-id="565cd-139">**Type**</span></span>|<span data-ttu-id="565cd-140">**Description**</span><span class="sxs-lookup"><span data-stu-id="565cd-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="565cd-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="565cd-141">SiteName</span></span>  <br/> |<span data-ttu-id="565cd-142">Facultatif </span><span class="sxs-lookup"><span data-stu-id="565cd-142">Optional</span></span>  <br/> |<span data-ttu-id="565cd-143">System.String</span><span class="sxs-lookup"><span data-stu-id="565cd-143">System.String</span></span>  <br/> |<span data-ttu-id="565cd-p106">Nom du site RTC sur lequel l’appliance est inscrite. La valeur par défaut est la valeur SiteName dans le fichier CloudConnector.ini. </span><span class="sxs-lookup"><span data-stu-id="565cd-p106">PSTN site name to which the appliance is registered. Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="565cd-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="565cd-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="565cd-147">Facultatif </span><span class="sxs-lookup"><span data-stu-id="565cd-147">Optional</span></span>  <br/> |<span data-ttu-id="565cd-148">System.String</span><span class="sxs-lookup"><span data-stu-id="565cd-148">System.String</span></span>  <br/> |<span data-ttu-id="565cd-p107">Nom de l’appliance actuelle. La valeur par défaut est le nom de l’ordinateur du serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="565cd-p107">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="565cd-151">Local</span><span class="sxs-lookup"><span data-stu-id="565cd-151">Local</span></span>  <br/> |<span data-ttu-id="565cd-152">Facultatif</span><span class="sxs-lookup"><span data-stu-id="565cd-152">Optional</span></span>  <br/> |<span data-ttu-id="565cd-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="565cd-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="565cd-154">Vérification des configurations d’inscription locale sans connexion à la configuration du client en ligne.</span><span class="sxs-lookup"><span data-stu-id="565cd-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="565cd-155">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="565cd-155">Input Types</span></span>
<span data-ttu-id="565cd-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="565cd-156"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="565cd-p108">Aucun. L’applet de commande Register-CcAppliance n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="565cd-p108">None. The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="565cd-159">Types de retours</span><span class="sxs-lookup"><span data-stu-id="565cd-159">Return Types</span></span>
<span data-ttu-id="565cd-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="565cd-160"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="565cd-161">Aucun</span><span class="sxs-lookup"><span data-stu-id="565cd-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="565cd-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="565cd-162">See also</span></span>
<span data-ttu-id="565cd-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="565cd-163"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="565cd-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="565cd-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="565cd-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="565cd-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="565cd-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="565cd-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="565cd-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="565cd-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

