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
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Pour vérifier que la réplication du catalogue global et la création des objets lors de la préparation de la forêt ont abouti, procédez comme suit :'
ms.openlocfilehash: 4f17b62fd0756019bab105df323215571557dce2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700649"
---
# <a name="verify-replication-of-forest-preparation"></a>Vérifier la réplication de la préparation de la forêt
 
Pour vérifier que la réplication du catalogue global et la création des objets lors de la préparation de la forêt ont abouti, procédez comme suit :
  
1. Sur un contrôleur de domaine (de préférence sur un site distant par rapport aux autres contrôleurs de domaine), dans la forêt où la préparation de la forêt a été effectuée, ouvrez **Utilisateurs et ordinateurs Active Directory**.
    
2. Dans **Utilisateurs et ordinateurs Active Directory**, développez le nom de domaine de votre forêt ou un domaine enfant.
    
3. Cliquez sur le conteneur **utilisateurs** dans le volet gauche, puis recherchez l’CsAdministrator de groupe universel dans le volet droit. S’il s’agit de CsAdministrator (entre huit nouveaux groupes universels qui commencent par CS), la réplication de la préparation de la forêt a abouti.
    
4. Si le ou les groupes ne sont pas encore présents, vous pouvez le faire ou patienter 15 minutes et actualiser le volet de droite. Lorsque les groupes apparaissent, la réplication est terminée.
    
> [!TIP]
> Si vous souhaitez consulter les fichiers journaux créés par l’Assistant Déploiement de Skype entreprise, vous pouvez les retrouver sur l’ordinateur sur lequel l’Assistant déploiement a été exécuté, dans l’annuaire utilisateurs de l’utilisateur services de domaine Active Directory (AD FS) qui a exécuté l’étape. Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

