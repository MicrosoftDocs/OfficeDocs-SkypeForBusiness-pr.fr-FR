---
title: Préparer le serveur Standard Edition (introduction)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Pour commencer l’installation d’un serveur Skype entreprise Server 2015 Standard Edition Server qui contient le magasin de gestion central et d’autres services colocalisés que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui sera devenir un serveur Standard Edition Server. La page Préparer le serveur Standard Edition détaille les conditions requises pour l’installation initiale. L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.
ms.openlocfilehash: a426d734c7644511d31a5b53d3a4939c95f979f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823468"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="94167-105">Préparer le serveur Standard Edition (introduction)</span><span class="sxs-lookup"><span data-stu-id="94167-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="94167-106">Pour commencer l’installation d’un serveur Skype entreprise Server 2015 Standard Edition Server qui contient le magasin de gestion central et d’autres services colocalisés que vous sélectionnez, vous devez être connecté en tant que membre du groupe Administrateurs local sur le serveur qui sera devenir un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="94167-106">To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="94167-107">La page **Préparer le serveur Standard Edition** détaille les conditions requises pour l’installation initiale.</span><span class="sxs-lookup"><span data-stu-id="94167-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="94167-108">L’ordinateur doit être membre du domaine dans lequel vous allez le déployer, et vous devez avoir réussi la préparation du schéma, de la forêt et du domaine pour votre forêt.</span><span class="sxs-lookup"><span data-stu-id="94167-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="94167-109">Cette tâche particulière est conçue pour configurer un serveur Standard Edition comme premier serveur de votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="94167-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="94167-110">Cette tâche installe le magasin de gestion central, qui est SQL Server Express, sur le serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="94167-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="94167-111">Si vous disposez déjà d’un autre serveur Standard Edition ou d’un pool frontal déployé, vous devez cliquer sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="94167-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94167-112">À l’issue de cette tâche, vous allez installer le générateur de topologie (si vous ne l’avez pas déjà installé) et configurer votre document topologique.</span><span class="sxs-lookup"><span data-stu-id="94167-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="94167-113">Vous ne pouvez pas publier votre document topologique tant que vous n’avez pas de banque d’administration centrale disponible, qui est déployée en exécutant la tâche décrite dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="94167-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

