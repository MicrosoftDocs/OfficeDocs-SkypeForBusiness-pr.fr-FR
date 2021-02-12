---
title: Configuration de la surveillance SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir migré vers Microsoft Skype Entreprise Server 2019, vous devez effectuer quelques tâches pour configurer Skype Entreprise Server 2019 afin qu’il fonctionne avec System Center Operations Manager.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754044"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="87d49-103">Configuration de la surveillance SCOM</span><span class="sxs-lookup"><span data-stu-id="87d49-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="87d49-104">Après avoir migré vers Skype Entreprise Server 2019, vous devez effectuer quelques tâches pour configurer Skype Entreprise Server 2019 afin qu’il fonctionne avec System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="87d49-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="87d49-105">Appliquer des mises à jour à un serveur choisi pour gérer la logique de découverte centrale.</span><span class="sxs-lookup"><span data-stu-id="87d49-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="87d49-106">Mettez à jour la clé de Registre du serveur candidat de détection centrale.</span><span class="sxs-lookup"><span data-stu-id="87d49-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="87d49-107">Configurez votre serveur de gestion System Center Operations Manager principal pour remplacer le nœud de découverte centrale candidat.</span><span class="sxs-lookup"><span data-stu-id="87d49-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="87d49-108">Des instructions pour mener à bien chacune de ces tâches sont fournies ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="87d49-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="87d49-109">Appliquer des mises à jour à un serveur choisi pour gérer la logique de découverte centrale.</span><span class="sxs-lookup"><span data-stu-id="87d49-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="87d49-110">Choisissez un serveur sur lequel les fichiers de l’agent System Center Operations Manager sont installés et qui est configuré en tant que nœud candidat de détection centrale.</span><span class="sxs-lookup"><span data-stu-id="87d49-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="87d49-111">Appliquez les mises à jour à ce serveur.</span><span class="sxs-lookup"><span data-stu-id="87d49-111">Apply updates to this server.</span></span> <span data-ttu-id="87d49-112">Consultez la rubrique [Appliquer les mises à jour.](apply-updates.md)</span><span class="sxs-lookup"><span data-stu-id="87d49-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="87d49-113">Mettez à jour la clé de Registre du serveur candidat de détection centrale.</span><span class="sxs-lookup"><span data-stu-id="87d49-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="87d49-114">Sur le serveur choisi pour gérer la logique de découverte centrale, ouvrez une fenêtre Windows PowerShell commande.</span><span class="sxs-lookup"><span data-stu-id="87d49-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="87d49-115">Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="87d49-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="87d49-p102">À chaque modification du Registre, une erreur liée à l’échec de la commande risque de se produire si la clé de Registre existe déjà. Dans ce cas, vous pouvez ignorer cette erreur sans risque.</span><span class="sxs-lookup"><span data-stu-id="87d49-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="87d49-118">Configurez votre serveur de gestion System Center Operations Manager principal pour remplacer le nœud de détection centrale du candidat.</span><span class="sxs-lookup"><span data-stu-id="87d49-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="87d49-119">Sur un ordinateur doté de la console System Center Operations Manager, développez **Objets du pack d’administration**, puis sélectionnez **Détections d’objets**.</span><span class="sxs-lookup"><span data-stu-id="87d49-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="87d49-120">Cliquez sur **Modifier l’étendue**</span><span class="sxs-lookup"><span data-stu-id="87d49-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="87d49-121">Dans la page **Étendre les objets du pack d’administration**, sélectionnez **Candidat de détection LS**.</span><span class="sxs-lookup"><span data-stu-id="87d49-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="87d49-122">Remplacez la **Valeur effective du candidat de détection LS** par le nom du serveur candidat choisi dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="87d49-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="87d49-123">Pour finaliser vos modifications, redémarrez le service d’état d’état sur le serveur de gestion racine System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="87d49-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

