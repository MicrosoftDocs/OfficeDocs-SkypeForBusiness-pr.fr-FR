---
title: Vérifier la réplication de la préparation de la forêt
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour vérifier que la réplication du catalogue global et la création d’objets au cours de la préparation de la forêt ont réussi, faites les opérations suivantes :'
ms.openlocfilehash: 299b738bbfa14ad13825e5c08e87c03167c9f4cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801594"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="db26e-103">Vérifier la réplication de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="db26e-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="db26e-104">Pour vérifier que la réplication du catalogue global et la création d’objets au cours de la préparation de la forêt ont réussi, faites les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="db26e-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="db26e-105">Sur un contrôleur de domaine (de préférence dans un site distant à partir des autres contrôleurs de domaine), dans la forêt où la préparation de la forêt a été exécuté, ouvrez Utilisateurs et ordinateurs **Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="db26e-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="db26e-106">Dans **Utilisateurs et ordinateurs Active Directory**, développez le nom de domaine de votre forêt ou un domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="db26e-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="db26e-107">Cliquez sur le conteneur **Utilisateurs** dans le volet gauche et recherchez le groupe universel CsAdministrator dans le volet de droite.</span><span class="sxs-lookup"><span data-stu-id="db26e-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="db26e-108">Si CsAdministrator (parmi huit autres nouveaux groupes universels qui commencent par Cs) est présent, la réplication de la préparation de la forêt a réussi.</span><span class="sxs-lookup"><span data-stu-id="db26e-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="db26e-p102">Si les groupes ne sont pas encore présents, vous pouvez forcer la réplication ou attendre 15 minutes, puis actualiser le volet de droite. Lorsque les groupes apparaissent, la réplication est terminée.</span><span class="sxs-lookup"><span data-stu-id="db26e-p102">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane. When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="db26e-111">Si vous souhaitez passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype Entreprise Server, vous pouvez les trouver sur l’ordinateur sur lequel l’Assistant Déploiement a été exécuté, dans l’annuaire Utilisateurs de l’utilisateur des services de domaine Active Directory qui a exécuté l’étape.</span><span class="sxs-lookup"><span data-stu-id="db26e-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="db26e-112">Par exemple, si l’utilisateur s’est connecté en tant qu’administrateur de domaine dans le Contoso.net de domaine, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="db26e-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

