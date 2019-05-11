---
title: Vérifier la réplication de la préparation de la forêt
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour confirmer que la réplication du catalogue Global et la création d’objets pendant la préparation de la forêt a été effectuée, procédez comme suit :'
ms.openlocfilehash: b755aeb6d7d9fe79940472b7b5883d1fdacaeee9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893622"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="30ebf-103">Vérifier la réplication de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="30ebf-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="30ebf-104">Pour confirmer que la réplication du catalogue Global et la création d’objets pendant la préparation de la forêt a été effectuée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30ebf-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="30ebf-105">Sur un contrôleur de domaine (de préférence sur un site distant par rapport aux autres contrôleurs de domaine), dans la forêt où la préparation de la forêt a été effectuée, ouvrez **Utilisateurs et ordinateurs Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="30ebf-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="30ebf-106">Dans **Utilisateurs et ordinateurs Active Directory**, développez le nom de domaine de votre forêt ou un domaine enfant.</span><span class="sxs-lookup"><span data-stu-id="30ebf-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="30ebf-107">Cliquez sur le conteneur **utilisateurs** dans le volet de gauche, recherchez le groupe universel CsAdministrator dans le volet de droite.</span><span class="sxs-lookup"><span data-stu-id="30ebf-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="30ebf-108">Si CsAdministrator (parmi les huit autres nouveaux groupes universels qui commencent par Cs) est présent, la réplication de la préparation de la forêt a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="30ebf-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="30ebf-109">Si le (s) n’est pas encore présent, forcez la réplication ou attendez 15 minutes et actualisez le volet de droite.</span><span class="sxs-lookup"><span data-stu-id="30ebf-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="30ebf-110">Lorsque les groupes apparaissent, la réplication est terminée.</span><span class="sxs-lookup"><span data-stu-id="30ebf-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="30ebf-111">Si vous souhaitez consulter les fichiers journaux qui sont créés par le Skype pour l’Assistant de déploiement Business Server, vous pouvez trouver les sur l’ordinateur où a été exécuté l’Assistant déploiement, dans le répertoire des utilisateurs de l’utilisateur des Services de domaine Active Directory qui a exécuté l’étape.</span><span class="sxs-lookup"><span data-stu-id="30ebf-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="30ebf-112">Par exemple, si l’utilisateur est connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="30ebf-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

