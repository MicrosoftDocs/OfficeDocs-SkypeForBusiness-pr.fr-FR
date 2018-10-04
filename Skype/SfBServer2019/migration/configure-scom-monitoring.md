---
title: Configurer la surveillance SCOM
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après la migration vers Microsoft Skype pour Business Server 2019, vous devez effectuer certaines tâches pour configurer Skype pour Business Server 2019 travailler avec System Center Operations Manager.
ms.openlocfilehash: c54038bc89c62a9911e684e451a66f4f12a23124
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373741"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="cbbc6-103">Configurer la surveillance SCOM</span><span class="sxs-lookup"><span data-stu-id="cbbc6-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="cbbc6-104">Après avoir migré vers Skype pour Business Server 2019, vous devez effectuer certaines tâches pour configurer Skype pour Business Server 2019 travailler avec System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="cbbc6-105">Mettre à jour un serveur dédié à la gestion de la logique de détection centrale.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="cbbc6-106">Mettre à jour la clé de Registre du serveur de détection centrale candidat.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="cbbc6-107">Configurer votre serveur d’administration System Center Operations Manager principal pour remplacer le nœud candidat de détection centrale.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="cbbc6-108">Instructions pour la réalisation de chacune de ces tâches sont fournies ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="cbbc6-109">Mettre à jour un serveur dédié à la gestion de la logique de détection centrale.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="cbbc6-110">Choisir un serveur ayant System Center Operations Manager fichiers de l’agent installé et configuré comme un nœud candidat de détection.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="cbbc6-111">Appliquer des mises à jour pour ce serveur.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-111">Apply updates to this server.</span></span> <span data-ttu-id="cbbc6-112">Consultez la rubrique [appliquer des mises à jour](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="cbbc6-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="cbbc6-113">Mettre à jour la clé de Registre du serveur de détection centrale candidat.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="cbbc6-114">Sur le serveur dédié à la gestion de la logique de détection centrale, ouvrez une fenêtre de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="cbbc6-115">Dans la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="cbbc6-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="cbbc6-116">Lorsque vous modifiez le Registre, vous pouvez rencontrer une erreur Échec de la commande si la clé de Registre existe déjà.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="cbbc6-117">Si vous rencontrez cette option, vous pouvez ignorer l’erreur.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="cbbc6-118">Configurer votre serveur d’administration System Center Operations Manager principal pour remplacer le nœud Observateur candidat de détection centrale.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="cbbc6-119">Sur un ordinateur sur lequel la console System Center Operations Manager est installée, développez **Objets du Pack d’administration** , puis sélectionnez **Détections d’objets**.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="cbbc6-120">Cliquez sur **Modifier l’étendue**</span><span class="sxs-lookup"><span data-stu-id="cbbc6-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="cbbc6-121">Dans la page **Étendue objets du Pack d’administration** , sélectionnez **Candidat de détection LS**.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="cbbc6-122">Remplacer la **Valeur Effective du candidat de détection LS** sur le nom du serveur candidat choisi dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="cbbc6-123">Pour finaliser vos modifications, redémarrez le service d’intégrité sur le serveur de gestion de System Center Operations Manager racine.</span><span class="sxs-lookup"><span data-stu-id="cbbc6-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

