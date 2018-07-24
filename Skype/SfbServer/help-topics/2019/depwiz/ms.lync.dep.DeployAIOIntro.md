---
title: Préparer le serveur Standard Edition (introduction)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation d’un Skype pour serveur Business Server Standard Edition qui contiendra le magasin Central de gestion et autres services colocalisés que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui deviendra le serveur Standard Edition. La page Préparer le serveur Standard Edition détaille les conditions requises pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
ms.openlocfilehash: a1d14b5d651cac9a3a779e78be48ecf45d4980bd
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987070"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="fbbdf-105">Préparer le serveur Standard Edition (introduction)</span><span class="sxs-lookup"><span data-stu-id="fbbdf-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="fbbdf-106">Pour commencer l’installation d’un Skype pour serveur Business Server Standard Edition qui contiendra le magasin Central de gestion et autres services colocalisés que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui deviendra le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fbbdf-106">To begin the installation of a Skype for Business Server Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="fbbdf-107">La page **Préparer le serveur Standard Edition** détaille les conditions requises pour l’installation initiale.</span><span class="sxs-lookup"><span data-stu-id="fbbdf-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="fbbdf-108">L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.</span><span class="sxs-lookup"><span data-stu-id="fbbdf-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="fbbdf-109">Cette tâche particulière est conçue pour configurer un serveur Standard Edition comme premier serveur de votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="fbbdf-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="fbbdf-110">Cela installe le magasin Central de gestion qui est SQL Server Express, sur le serveur Standard Edition server.</span><span class="sxs-lookup"><span data-stu-id="fbbdf-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="fbbdf-111">Si vous disposez déjà d’un autre serveur Standard Edition ou d’un pool frontal déployé, vous devez cliquer sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="fbbdf-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fbbdf-112">Après avoir complété cette tâche, vous installerez le Générateur de topologie (si elle n’avez pas déjà installé) et configurer votre document de topologie.</span><span class="sxs-lookup"><span data-stu-id="fbbdf-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="fbbdf-113">Vous ne pouvez publier votre document de topologie jusqu'à ce que vous ayez un magasin Central de gestion disponible, ce qui est déployé en effectuant les tâches décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="fbbdf-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

