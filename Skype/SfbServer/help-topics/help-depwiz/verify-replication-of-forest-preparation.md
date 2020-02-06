---
title: Vérifier la réplication de la préparation de la forêt
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Pour vérifier que la réplication du catalogue global et la création des objets lors de la préparation de la forêt ont abouti, procédez comme suit :'
ms.openlocfilehash: 5f02707b8a98ec9869aa2b2b4d867bb45351371b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823278"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="57f12-103">Vérifier la réplication de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="57f12-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="57f12-104">Pour vérifier que la réplication du catalogue global et la création des objets lors de la préparation de la forêt ont abouti, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="57f12-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="57f12-105">Sur un contrôleur de domaine (de préférence sur un site distant par rapport aux autres contrôleurs de domaine), dans la forêt où la préparation de la forêt a été effectuée, ouvrez **Utilisateurs et ordinateurs Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="57f12-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="57f12-106">Dans **Utilisateurs et ordinateurs Active Directory**, développez le nom de domaine de votre forêt ou un domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="57f12-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="57f12-107">Cliquez sur le conteneur **utilisateurs** dans le volet gauche, puis recherchez l’CsAdministrator de groupe universel dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="57f12-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="57f12-108">S’il s’agit de CsAdministrator (entre huit nouveaux groupes universels qui commencent par CS), la réplication de la préparation de la forêt a abouti.</span><span class="sxs-lookup"><span data-stu-id="57f12-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="57f12-109">Si le ou les groupes ne sont pas encore présents, vous pouvez le faire ou patienter 15 minutes et actualiser le volet de droite.</span><span class="sxs-lookup"><span data-stu-id="57f12-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="57f12-110">Lorsque les groupes apparaissent, la réplication est terminée.</span><span class="sxs-lookup"><span data-stu-id="57f12-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="57f12-111">Si vous souhaitez consulter les fichiers journaux créés par l’Assistant Déploiement de Skype entreprise, vous pouvez les retrouver sur l’ordinateur sur lequel l’Assistant déploiement a été exécuté, dans l’annuaire utilisateurs de l’utilisateur services de domaine Active Directory (AD FS) qui a exécuté l’étape.</span><span class="sxs-lookup"><span data-stu-id="57f12-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="57f12-112">Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="57f12-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

