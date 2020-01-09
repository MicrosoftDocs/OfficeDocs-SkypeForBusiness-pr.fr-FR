---
title: Vérifier la réplication dans le domaine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Pour vérifier la réplication de la préparation du domaine accomplie à l’étape 1 : préparer le schéma, il est nécessaire d’exécuter une cmdlet à partir de Skype entreprise Server Management Shell Lync Server Management Shell. Pour exécuter l’applet de cmdlet Windows PowerShell, connectez-vous à un ordinateur membre du domaine que vous avez préparé et en tant que membre du groupe administrateurs de domaine. Procédez comme suit :'
ms.openlocfilehash: f20806a11850276032bae19b4311734669be5a53
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989049"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="f3114-105">Vérifier la réplication dans le domaine</span><span class="sxs-lookup"><span data-stu-id="f3114-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="f3114-106">Pour vérifier la réplication de la préparation du domaine accomplie à l' **étape 1 : préparer le schéma**, il est nécessaire d’exécuter une cmdlet à partir de Skype entreprise Server Management Shell Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f3114-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="f3114-107">Pour exécuter l’applet de cmdlet Windows PowerShell, connectez-vous à un ordinateur membre du domaine que vous avez préparé et en tant que membre du groupe administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="f3114-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="f3114-108">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f3114-108">Do the following:</span></span>
  
1. <span data-ttu-id="f3114-109">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f3114-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f3114-110">Dans Windows PowerShell, tapez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f3114-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="f3114-111">Exemple :</span><span class="sxs-lookup"><span data-stu-id="f3114-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="f3114-112">Le paramètre GlobalSettingsDomainController vous permet d’indiquer où sont stockés les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="f3114-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="f3114-113">Si vos paramètres sont stockés dans le conteneur système (qui est généralement utilisé avec des déploiements de mise à niveau pour lesquels le paramètre global n’a pas été migré vers le conteneur de configuration), vous définissez un contrôleur de domaine à la racine de votre forêt de services de domaine Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f3114-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="f3114-114">Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous devez définir un contrôleur de domaine dans la forêt.</span><span class="sxs-lookup"><span data-stu-id="f3114-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="f3114-115">Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et indique un contrôleur de domaine dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3114-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="f3114-116">Si vous omettez le paramètre Domain, le domaine local est utilisé.</span><span class="sxs-lookup"><span data-stu-id="f3114-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="f3114-117">Cette applet de commande renvoie la valeur **LC_DOMAIN_SETTINGS_STATE_READY**, si la préparation du domaine a réussi.</span><span class="sxs-lookup"><span data-stu-id="f3114-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

