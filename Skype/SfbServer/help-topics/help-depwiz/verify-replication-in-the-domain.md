---
title: Vérifier la réplication dans le domaine
ms.reviewer: ''
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
description: 'Pour vérifier la réplication de la préparation du domaine effectuée dans l’étape 1 : préparation du schéma, il est nécessaire d’exécuter une applet de commande à partir de la Skype pour Business Server Management Shell Lync Server Management Shell. Pour exécuter l’applet de commande Windows PowerShell, ouvrez une session un ordinateur qui est un membre du domaine que vous avez préparé et en tant que membre du groupe Admins du domaine. Procédez comme suit :'
ms.openlocfilehash: 32a5a315566fcee07f7214c980843829ef8e229f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234872"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="0cc6c-105">Vérifier la réplication dans le domaine</span><span class="sxs-lookup"><span data-stu-id="0cc6c-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="0cc6c-106">Pour vérifier la réplication de la préparation du domaine effectuée dans **étape 1 : préparer un schéma**, il est nécessaire d’exécuter une applet de commande à partir de la Skype pour Business Server Management Shell Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0cc6c-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="0cc6c-107">Pour exécuter l’applet de commande Windows PowerShell, ouvrez une session un ordinateur qui est un membre du domaine que vous avez préparé et en tant que membre du groupe Admins du domaine.</span><span class="sxs-lookup"><span data-stu-id="0cc6c-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="0cc6c-108">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0cc6c-108">Do the following:</span></span>
  
1. <span data-ttu-id="0cc6c-109">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0cc6c-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="0cc6c-110">Dans Windows PowerShell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0cc6c-110">In Windows PowerShell, type the following:</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="0cc6c-111">Exemple :</span><span class="sxs-lookup"><span data-stu-id="0cc6c-111">For example:</span></span>
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="0cc6c-112">Le paramètre GlobalSettingsDomainController vous permet d’indiquer où sont stockés les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="0cc6c-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="0cc6c-113">Si vos paramètres sont stockés dans le conteneur système (qui est par défaut avec les déploiements de mise à niveau qui n’ont pas le paramètre global migré vers le conteneur de Configuration), vous définissez un contrôleur de domaine à la racine de votre forêt Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="0cc6c-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="0cc6c-114">Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous devez définir un contrôleur de domaine dans la forêt.</span><span class="sxs-lookup"><span data-stu-id="0cc6c-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="0cc6c-115">Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et indique un contrôleur de domaine dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0cc6c-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="0cc6c-116">Si vous omettez le paramètre Domain, le domaine local est utilisé.</span><span class="sxs-lookup"><span data-stu-id="0cc6c-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="0cc6c-117">Cette applet de commande renvoie la valeur **LC_DOMAIN_SETTINGS_STATE_READY**, si la préparation du domaine a réussi.</span><span class="sxs-lookup"><span data-stu-id="0cc6c-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

