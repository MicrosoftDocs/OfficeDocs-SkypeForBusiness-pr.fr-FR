---
title: Configuration de la surveillance SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir migré vers Microsoft Skype entreprise Server 2019, vous devez effectuer quelques tâches pour configurer Skype entreprise Server 2019 de manière à utiliser System Center Operations Manager.
ms.openlocfilehash: 79398336bf372fd2ca779d2ec2ff58dc5219da61
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813802"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="ca241-103">Configuration de la surveillance SCOM</span><span class="sxs-lookup"><span data-stu-id="ca241-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="ca241-104">Après la migration vers Skype entreprise Server 2019, vous devez effectuer quelques tâches pour configurer Skype entreprise Server 2019 de manière à utiliser System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ca241-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="ca241-105">Appliquez les mises à jour à un serveur choisi pour gérer la logique de découverte centrale.</span><span class="sxs-lookup"><span data-stu-id="ca241-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="ca241-106">Mettez à jour la clé de Registre du serveur prototype de découverte central.</span><span class="sxs-lookup"><span data-stu-id="ca241-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="ca241-107">Configurer votre serveur de gestion Operations Manager principal de System Center pour remplacer le nœud de découverte central.</span><span class="sxs-lookup"><span data-stu-id="ca241-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="ca241-108">Vous trouverez ci-dessous des instructions pour chacune de ces tâches.</span><span class="sxs-lookup"><span data-stu-id="ca241-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="ca241-109">Appliquez les mises à jour à un serveur choisi pour gérer la logique de découverte centrale.</span><span class="sxs-lookup"><span data-stu-id="ca241-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="ca241-110">Électionnez un serveur sur lequel les fichiers de l’agent Operations Manager System Center Operations Manager sont installés et est configuré en tant que nœud de découverte candidat.</span><span class="sxs-lookup"><span data-stu-id="ca241-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="ca241-111">Appliquez les mises à jour de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="ca241-111">Apply updates to this server.</span></span> <span data-ttu-id="ca241-112">Voir la rubrique [appliquer les mises à jour](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="ca241-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="ca241-113">Mettez à jour la clé de Registre du serveur prototype de découverte central.</span><span class="sxs-lookup"><span data-stu-id="ca241-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="ca241-114">Sur le serveur choisi pour gérer la logique de découverte centralisée, ouvrez une fenêtre de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca241-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="ca241-115">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ca241-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="ca241-116">Dès lors que vous modifiez le registre, il est possible que la commande échoue si la clé de Registre existe déjà.</span><span class="sxs-lookup"><span data-stu-id="ca241-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="ca241-117">Si vous êtes à l’abri de cela, vous pouvez ignorer l’erreur.</span><span class="sxs-lookup"><span data-stu-id="ca241-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="ca241-118">Configurez votre serveur de gestion du gestionnaire d’opérations principales pour remplacer le nœud du centre de découverte central.</span><span class="sxs-lookup"><span data-stu-id="ca241-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="ca241-119">Sur un ordinateur sur lequel est installé la console System Center Operations Manager, développez **objets du pack d’administration** , puis sélectionnez découvertes d' **objets**.</span><span class="sxs-lookup"><span data-stu-id="ca241-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="ca241-120">Cliquez sur **modifier l’étendue**</span><span class="sxs-lookup"><span data-stu-id="ca241-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="ca241-121">Dans la page d' **objets du pack d’administration d’étendue** , sélectionnez **ls découverte candidate**.</span><span class="sxs-lookup"><span data-stu-id="ca241-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="ca241-122">Remplacez la **valeur effective** de la fonction de découverte (LS) par le nom du serveur candidat élu dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="ca241-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="ca241-123">Pour finaliser vos modifications, redémarrez le service d’intégrité sur le serveur de gestion de racines System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ca241-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

