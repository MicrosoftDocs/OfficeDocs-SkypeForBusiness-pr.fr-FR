---
title: Vérifier la réplication de la préparation de la forêt
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Pour vérifier que la réplication du catalogue global et la création d’objets au cours de la préparation de la forêt ont réussi, faites les opérations suivantes :'
ms.openlocfilehash: 2105ff54f44a4e5ab58b2509348126920f0823b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862841"
---
# <a name="verify-replication-of-forest-preparation"></a>Vérifier la réplication de la préparation de la forêt
 
Pour vérifier que la réplication du catalogue global et la création d’objets au cours de la préparation de la forêt ont réussi, faites les opérations suivantes :
  
1. Sur un contrôleur de domaine (de préférence dans un site distant à partir des autres contrôleurs de domaine), dans la forêt où la préparation de la forêt a été exécuté, ouvrez Utilisateurs et ordinateurs **Active Directory.**
    
2. Dans **Utilisateurs et ordinateurs Active Directory**, développez le nom de domaine de votre forêt ou un domaine enfant.
    
3. Cliquez sur le conteneur **Utilisateurs** dans le volet gauche et recherchez le groupe universel CsAdministrator dans le volet de droite. Si CsAdministrator (parmi huit autres nouveaux groupes universels qui commencent par Cs) est présent, la réplication de la préparation de la forêt a réussi.
    
4. Si les groupes ne sont pas encore présents, vous pouvez forcer la réplication ou attendre 15 minutes, puis actualiser le volet de droite. Lorsque les groupes apparaissent, la réplication est terminée.
    
> [!TIP]
> Si vous souhaitez passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype Entreprise Server, vous pouvez les trouver sur l’ordinateur sur lequel l’Assistant Déploiement a été exécuté, dans l’annuaire Utilisateurs de l’utilisateur des services de domaine Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur s’est connecté en tant qu’administrateur de domaine dans le Contoso.net de domaine, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

