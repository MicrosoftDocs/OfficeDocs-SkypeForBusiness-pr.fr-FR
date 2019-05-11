---
title: Préparer la forêt actuelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Pour préparer la forêt des Services de domaine Active Directory, vous devez correctement étendre le schéma, comme décrit dans la rubrique Préparation du schéma en cours d’exécution et vous assurer que le schéma a été répliqué.
ms.openlocfilehash: 51f3a4bd643ce4d3102d1d0e0c6810fae951c5f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888792"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="f43a2-103">Préparer la forêt actuelle</span><span class="sxs-lookup"><span data-stu-id="f43a2-103">Prepare Current Forest</span></span>

<span data-ttu-id="f43a2-104">Pour préparer la forêt des Services de domaine Active Directory, vous devez correctement étendre le schéma, comme décrit dans la rubrique [Préparation du schéma en cours d’exécution](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)et vous assurer que le schéma a été répliqué.</span><span class="sxs-lookup"><span data-stu-id="f43a2-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="f43a2-p101">Après avoir rempli ces conditions préalables, vous pouvez passer à l’**Étape 3 : Préparer la forêt actuelle**. Pour préparer la forêt, connectez-vous à un ordinateur dans la racine de la forêt en tant que membre du groupe Administrateurs du domaine ou en tant que membre du groupe Administrateurs d’entreprise dans la forêt que vous préparez.</span><span class="sxs-lookup"><span data-stu-id="f43a2-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="f43a2-107">Dans l’Assistant Déploiement, à l’**Étape 3 : Préparer la forêt actuelle**, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f43a2-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="f43a2-108">Dans la page **Préparer la forêt**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f43a2-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f43a2-109">Préparation de la forêt vous permet de choisir l’emplacement où placer les groupes universels pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f43a2-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server 2015.</span></span> <span data-ttu-id="f43a2-110">Sélectionnez un emplacement conforme aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f43a2-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="f43a2-p103">Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**. Assurez-vous qu’il n’y a pas d’erreurs. Consultez les avertissements pour vous assurer qu’ils sont ordinaires et conformes à votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="f43a2-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="f43a2-114">Dans la colonne **Action** , dans le journal, développez **La préparation de la forêt**, recherchez un \*\* \<réussite\> \*\* résultat de l’exécution à la fin de chaque tâche pour vérifier que la préparation de forêt terminée avec succès, fermez le fichier journal, puis cliquez sur \*\*Terminer \*\*.</span><span class="sxs-lookup"><span data-stu-id="f43a2-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="f43a2-115">Attendre la réplication des Services de domaine Active Directory soit terminée ou forcez la réplication sur tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **Services et Sites Active Directory** pour le contrôleur de domaine racine de forêt, avant d’exécuter la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="f43a2-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="f43a2-116">Forcez la réplication entre les contrôleurs de domaine dans tous les sites Active Directory pour forcer la réplication dans les sites se produise en quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="f43a2-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="f43a2-117">Si vous avez besoin passer en revue les fichiers journaux qui sont créés par le Skype pour l’Assistant de déploiement Business Server, vous pouvez trouver les sur l’ordinateur où a été exécuté l’Assistant déploiement, dans le répertoire des utilisateurs de l’utilisateur des Services de domaine Active Directory qui a exécuté l’étape.</span><span class="sxs-lookup"><span data-stu-id="f43a2-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="f43a2-118">Par exemple, si l’utilisateur est connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="f43a2-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


