---
title: Préparer la forêt actuelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Pour préparer la forêt services de domaine Active Directory (AD FS), vous devez prolonger le schéma comme décrit dans la rubrique exécution de la préparation du schéma et vérifier que le schéma a été répliqué.
ms.openlocfilehash: 8c472588dc67ef0e8bc86afb86bcad200df307f0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691809"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="c429b-103">Préparer la forêt actuelle</span><span class="sxs-lookup"><span data-stu-id="c429b-103">Prepare Current Forest</span></span>

<span data-ttu-id="c429b-104">Pour préparer la forêt services de domaine Active Directory (AD FS), vous devez prolonger le schéma comme décrit dans la rubrique exécution de la [préparation du schéma](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)et vérifier que le schéma a été répliqué.</span><span class="sxs-lookup"><span data-stu-id="c429b-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="c429b-p101">Après avoir rempli ces conditions préalables, vous pouvez passer à l’**Étape 3 : Préparer la forêt actuelle**. Pour préparer la forêt, connectez-vous à un ordinateur dans la racine de la forêt en tant que membre du groupe Administrateurs du domaine ou en tant que membre du groupe Administrateurs d’entreprise dans la forêt que vous préparez.</span><span class="sxs-lookup"><span data-stu-id="c429b-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="c429b-107">Dans l’Assistant Déploiement, à l’**Étape 3 : Préparer la forêt actuelle**, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c429b-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="c429b-108">Dans la page **Préparer la forêt**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c429b-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c429b-109">La préparation de la forêt vous permet de choisir l’emplacement des groupes universels pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c429b-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server.</span></span> <span data-ttu-id="c429b-110">Sélectionnez un emplacement conforme aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c429b-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="c429b-p103">Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**. Assurez-vous qu’il n’y a pas d’erreurs. Consultez les avertissements pour vous assurer qu’ils sont ordinaires et conformes à votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="c429b-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="c429b-114">Dans la colonne **action** du journal, développez **Forest PREP**, recherchez un \*\* \<\> \*\* résultat d’exécution réussie à la fin de chaque tâche pour vérifier que la préparation de la forêt s’est déroulée correctement, fermez le journal, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="c429b-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="c429b-115">Attendez la fin de la réplication des services de domaine Active Directory, ou forcez la réplication vers tous les contrôleurs de domaine figurant dans le composant logiciel enfichable **sites et services Active Directory** pour le contrôleur de domaine racine de la forêt avant d’exécuter la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="c429b-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="c429b-116">Forcez la réplication entre les contrôleurs de domaine dans tous les sites Active Directory pour que la réplication au sein des sites se produise en quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="c429b-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="c429b-117">Si vous avez besoin de passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype entreprise, vous pouvez les retrouver sur l’ordinateur sur lequel l’Assistant déploiement a été exécuté, dans l’annuaire utilisateurs de l’utilisateur de services de domaine Active Directory (AD FS) qui a exécuté l’étape.</span><span class="sxs-lookup"><span data-stu-id="c429b-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="c429b-118">Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="c429b-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


