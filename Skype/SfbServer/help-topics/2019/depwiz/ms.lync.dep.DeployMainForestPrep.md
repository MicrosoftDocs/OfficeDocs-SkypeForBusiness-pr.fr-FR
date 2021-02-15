---
title: Préparer la forêt actuelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Pour préparer la forêt des services de domaine Active Directory, vous devez étendre correctement le schéma, comme décrit dans la rubrique Exécution de la préparation du schéma, et vous assurer que le schéma a été répliqué.
ms.openlocfilehash: 4881cb85134fef81cd741d834f319a76d4028e59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833824"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="0ac65-103">Préparer la forêt actuelle</span><span class="sxs-lookup"><span data-stu-id="0ac65-103">Prepare Current Forest</span></span>

<span data-ttu-id="0ac65-104">Pour préparer la forêt des services de domaine Active Directory, vous devez étendre correctement le schéma, comme décrit dans la rubrique Exécution de la préparation du [schéma,](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)et vous assurer que le schéma a été répliqué.</span><span class="sxs-lookup"><span data-stu-id="0ac65-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="0ac65-105">Après avoir terminé ces conditions préalables, vous pouvez commencer **l’étape 3 : Préparer la forêt actuelle**.</span><span class="sxs-lookup"><span data-stu-id="0ac65-105">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**.</span></span> <span data-ttu-id="0ac65-106">Pour préparer la forêt, connectez-vous à un ordinateur à la racine de la forêt en tant que membre des administrateurs de domaine à la racine de la forêt ou en tant que membre des administrateurs d’entreprise pour la forêt que vous préparez.</span><span class="sxs-lookup"><span data-stu-id="0ac65-106">To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="0ac65-107">Dans l'Assistant Déploiement, à l'**Étape 3 : Préparer la forêt actuelle**, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="0ac65-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="0ac65-108">Sur la page **Préparer la forêt**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0ac65-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ac65-109">La préparation de la forêt vous permet de choisir où placer les groupes universels pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0ac65-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server.</span></span> <span data-ttu-id="0ac65-110">Choisissez un emplacement cohérent avec les conditions requises de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0ac65-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="0ac65-111">Sur la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="0ac65-111">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span> <span data-ttu-id="0ac65-112">Assurez-vous qu’il n’y a aucune erreur.</span><span class="sxs-lookup"><span data-stu-id="0ac65-112">Make sure that there are no errors.</span></span> <span data-ttu-id="0ac65-113">Examinez les avertissements pour déterminer s’ils sont attendus et typiques pour votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="0ac65-113">Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="0ac65-114">Sous la colonne **Action** du journal, développez Préparation de la **forêt,** recherchez un résultat d’exécution à la fin de chaque tâche pour vérifier que la préparation de la forêt s’est correctement terminée, fermez le journal, puis cliquez sur **\<Success\>** **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="0ac65-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="0ac65-115">Attendez que la réplication des services de domaine Active Directory soit terminée ou forcez la réplication vers tous les contrôleurs de domaine répertoriés dans le logiciel en ligne Sites et **services Active Directory** pour le contrôleur de domaine racine de la forêt, avant d’effectuer la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="0ac65-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="0ac65-116">Forcez la réplication entre les contrôleurs de domaine sur tous les sites Active Directory pour faire en sorte que la réplication au sein de ces sites se produise en quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="0ac65-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="0ac65-117">Si vous devez consulter les fichiers journaux créés par l’Assistant Déploiement de Skype Entreprise Server, vous pouvez les trouver sur l’ordinateur sur lequel l’Assistant Déploiement a été exécuté, dans l’annuaire Utilisateurs de l’utilisateur des services de domaine Active Directory qui a exécuté l’étape.</span><span class="sxs-lookup"><span data-stu-id="0ac65-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="0ac65-118">Par exemple, si l’utilisateur s’est connecté en tant qu’administrateur de domaine dans le Contoso.net de domaine, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="0ac65-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


