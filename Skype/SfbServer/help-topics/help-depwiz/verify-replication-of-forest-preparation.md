---
title: Vérification de la réplication de la préparation de la forêt
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Pour confirmer que la réplication du catalogue Global et la création d’objets au cours de la préparation de la forêt ont réussi, effectuez les opérations suivantes :'
ms.openlocfilehash: cfb993a9a80bf4b37e76712a58aa6c1fb0c270c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-forest-preparation"></a>Vérification de la réplication de la préparation de la forêt
 
Pour confirmer que la réplication du catalogue Global et la création d’objets au cours de la préparation de la forêt ont réussi, effectuez les opérations suivantes :
  
1. Sur un contrôleur de domaine (de préférence sur un site distant par rapport aux autres contrôleurs de domaine), dans la forêt où la préparation de la forêt a été effectuée, ouvrez **Utilisateurs et ordinateurs Active Directory**.
    
2. Dans **Utilisateurs et ordinateurs Active Directory**, développez le nom de domaine de votre forêt ou un domaine enfant.
    
3. Cliquez sur le conteneur **utilisateurs** dans le volet gauche et recherchez le groupe universel CsAdministrator dans le volet de droite. Si CsAdministrator (parmi les huit autres nouveaux groupes universels qui commencent par Cs) est présent, la réplication de la préparation de la forêt a réussi.
    
4. Si l’ou les groupes n’est pas encore présent, vous pouvez forcer la réplication ou attendez 15 minutes et actualiser le volet de droite. Lorsque les groupes apparaissent, la réplication est terminée.
    
> [!TIP]
> Si vous souhaitez passer en revue les fichiers journaux qui sont créés par le Skype pour l’Assistant de déploiement de Business Server, vous pouvez les retrouver sur l’ordinateur où l’Assistant de déploiement a été exécuté, dans le répertoire des utilisateurs de l’utilisateur des Services de domaine Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

