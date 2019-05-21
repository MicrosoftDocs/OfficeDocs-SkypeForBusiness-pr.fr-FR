---
title: Préparer le domaine actuel
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Pour préparer un domaine pour l’hébergement de serveurs exécutant Skype entreprise Server 2015 ou les utilisateurs de Skype entreprise Server, vous devez suivre l’étape 5: préparer le domaine actuel, comme décrit dans la rubrique utilisation du programme d’installation pour exécuter la préparation du domaine. Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :'
ms.openlocfilehash: 93fef28bdcaa720f1adcf893ec634dbe8f373780
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283877"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="d30dd-105">Préparer le domaine actuel</span><span class="sxs-lookup"><span data-stu-id="d30dd-105">Prepare Current Domain</span></span>

<span data-ttu-id="d30dd-106">Pour préparer un domaine pour l’hébergement de serveurs exécutant Skype entreprise Server 2015 ou les utilisateurs de Skype entreprise Server, vous devez suivre l' **étape 5: préparer le domaine actuel**, comme décrit dans la rubrique [utilisation du programme d’installation pour exécuter la préparation du domaine](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span><span class="sxs-lookup"><span data-stu-id="d30dd-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="d30dd-107">Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient.</span><span class="sxs-lookup"><span data-stu-id="d30dd-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="d30dd-108">Pour préparer le domaine :</span><span class="sxs-lookup"><span data-stu-id="d30dd-108">To prepare the domain:</span></span>

1. <span data-ttu-id="d30dd-109">Dans le dossier d’installation ou le média de Skype entreprise Server 2015, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d30dd-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="d30dd-110">Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.</span><span class="sxs-lookup"><span data-stu-id="d30dd-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="d30dd-111">À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d30dd-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="d30dd-112">Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="d30dd-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="d30dd-113">Dans la colonne **action** , développez **Domain PREP**, recherchez un \*\* \<résultat\> \*\* d’exécution réussie à la fin de chaque tâche pour vérifier que la préparation du domaine s’est déroulée correctement, fermez le journal, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d30dd-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="d30dd-114">Si vous avez besoin de passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype entreprise, vous pouvez les retrouver sur l’ordinateur sur lequel l’Assistant déploiement a été exécuté dans le répertoire utilisateurs de l’utilisateur de services de domaine Active Directory (AD FS) qui a exécuté l’étape.</span><span class="sxs-lookup"><span data-stu-id="d30dd-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="d30dd-115">Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="d30dd-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


