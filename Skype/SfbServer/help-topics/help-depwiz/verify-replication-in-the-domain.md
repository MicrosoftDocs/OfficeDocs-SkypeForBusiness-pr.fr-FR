---
title: Vérifier la réplication dans le domaine
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Pour vérifier la réplication de la préparation du domaine effectuée à l’étape 1 : préparer un schéma, il est nécessaire d’exécuter une applet de commande à partir de la Skype pour Business Server Management Shell Lync Server Management Shell. Pour exécuter l’applet de commande Windows PowerShell, ouvrez une session sur un ordinateur qui est membre du domaine que vous avez préparé et en tant que membre du groupe Admins du domaine. Procédez comme suit :'
ms.openlocfilehash: e3dca892ccb4937bcd84148a954270b4bd1362f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="e38c9-105">Vérifier la réplication dans le domaine</span><span class="sxs-lookup"><span data-stu-id="e38c9-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="e38c9-106">Pour vérifier la réplication de la préparation du domaine dans **étape 1 : préparer le schéma**, il est nécessaire d’exécuter une applet de commande à partir de la Skype pour Business Server Management Shell Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e38c9-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="e38c9-107">Pour exécuter l’applet de commande Windows PowerShell, ouvrez une session sur un ordinateur qui est membre du domaine que vous avez préparé et en tant que membre du groupe Admins du domaine.</span><span class="sxs-lookup"><span data-stu-id="e38c9-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="e38c9-108">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e38c9-108">Do the following:</span></span>
  
1. <span data-ttu-id="e38c9-109">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e38c9-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e38c9-110">Dans Windows PowerShell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e38c9-110">In Windows PowerShell, type the following:</span></span>
    
  ```
  Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
  ```

    <span data-ttu-id="e38c9-111">Exemple :</span><span class="sxs-lookup"><span data-stu-id="e38c9-111">For example:</span></span>
    
  ```
  Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
  ```

    > [!NOTE]
    > <span data-ttu-id="e38c9-112">Le paramètre GlobalSettingsDomainController vous permet d’indiquer où sont stockés les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="e38c9-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="e38c9-113">Si vos paramètres sont stockés dans le conteneur système (ce qui est courant avec les déploiements de mise à niveau qui n’ont pas le paramètre global migré vers le conteneur de Configuration), vous définissez un contrôleur de domaine à la racine de votre forêt des Services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e38c9-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="e38c9-114">Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous devez définir un contrôleur de domaine dans la forêt.</span><span class="sxs-lookup"><span data-stu-id="e38c9-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="e38c9-115">Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et indique un contrôleur de domaine dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e38c9-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="e38c9-116">Si vous omettez le paramètre Domain, le domaine local est utilisé.</span><span class="sxs-lookup"><span data-stu-id="e38c9-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="e38c9-117">Cette applet de commande renvoie une valeur de **LC_DOMAIN_SETTINGS_STATE_READY** si la préparation du domaine a réussi.</span><span class="sxs-lookup"><span data-stu-id="e38c9-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

