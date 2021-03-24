---
title: Préparer le domaine actuel
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Pour préparer un domaine à héberger des serveurs exécutant les utilisateurs de Skype Entreprise Server 2015 ou Skype Entreprise Server, vous devez effectuer l’étape 5 : Préparer le domaine actuel, comme décrit dans la rubrique Utilisation du programme d’installation pour exécuter la préparation du domaine. Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :'
ms.openlocfilehash: c9c33e466b7b0fcc7c2711603c284e5f419960a1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096870"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="d4d65-105">Préparer le domaine actuel</span><span class="sxs-lookup"><span data-stu-id="d4d65-105">Prepare Current Domain</span></span>

<span data-ttu-id="d4d65-106">Pour préparer un domaine à héberger des serveurs exécutant des utilisateurs de Skype Entreprise Server 2015 ou Skype Entreprise Server, vous devez effectuer l’étape **5**: Préparer le domaine actuel, comme décrit dans la rubrique Utilisation du programme d’installation pour exécuter la préparation du [domaine.](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation)</span><span class="sxs-lookup"><span data-stu-id="d4d65-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span></span> <span data-ttu-id="d4d65-107">Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient.</span><span class="sxs-lookup"><span data-stu-id="d4d65-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="d4d65-108">Pour préparer le domaine :</span><span class="sxs-lookup"><span data-stu-id="d4d65-108">To prepare the domain:</span></span>

1. <span data-ttu-id="d4d65-109">À partir du dossier ou du support d’installation de Skype Entreprise Server 2015, exécutez Setup.exe pour démarrer l’Assistant Déploiement de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d4d65-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="d4d65-110">Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.</span><span class="sxs-lookup"><span data-stu-id="d4d65-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="d4d65-111">À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d4d65-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="d4d65-112">Sur la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="d4d65-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="d4d65-113">Sous la colonne **Action,** développez Préparation du **domaine,** recherchez un résultat d’exécution à la fin de chaque tâche pour vérifier que la préparation du domaine s’est correctement terminée, fermez le journal, puis cliquez sur **\<Success\>** **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="d4d65-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="d4d65-114">Si vous devez consulter les fichiers journaux créés par l’Assistant Déploiement de Skype Entreprise Server, vous pouvez les trouver sur l’ordinateur sur lequel l’Assistant Déploiement a été exécuté dans l’annuaire Utilisateurs de l’utilisateur des services de domaine Active Directory qui a exécuté l’étape.</span><span class="sxs-lookup"><span data-stu-id="d4d65-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="d4d65-115">Par exemple, si l’utilisateur s’est connecté en tant qu’administrateur de domaine dans le Contoso.net de domaine, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="d4d65-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>