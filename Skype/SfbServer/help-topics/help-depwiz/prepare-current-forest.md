---
title: Préparer la forêt actuelle
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Pour préparer la forêt des Services de domaine Active Directory, vous devez correctement étendre le schéma, comme décrit dans la rubrique Préparation du schéma en cours d’exécution et assurez-vous que le schéma a répliqué.
ms.openlocfilehash: 80218036b6eaee5abb0156ca6a13678f9b9f2238
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-current-forest"></a>Préparer la forêt actuelle
 
Pour préparer la forêt des Services de domaine Active Directory, vous devez correctement étendre le schéma, comme décrit dans la rubrique [Préparation du schéma en cours d’exécution](http://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)et assurez-vous que le schéma a répliqué.
  
Après avoir rempli ces conditions préalables, vous pouvez passer à l’**Étape 3 : Préparer la forêt actuelle**. Pour préparer la forêt, connectez-vous à un ordinateur dans la racine de la forêt en tant que membre du groupe Administrateurs du domaine ou en tant que membre du groupe Administrateurs d’entreprise dans la forêt que vous préparez.
  
1. Dans l’Assistant Déploiement, à l’**Étape 3 : Préparer la forêt actuelle**, cliquez sur **Exécuter**.
    
2. Dans la page **Préparer la forêt**, cliquez sur **Suivant**.
    
    > [!NOTE]
    > Préparation de la forêt vous permet de choisir l’emplacement où placer les groupes universels pour Skype pour Business Server 2015. Sélectionnez un emplacement conforme aux besoins de votre organisation. 
  
3. Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**. Assurez-vous qu’il n’y a pas d’erreurs. Consultez les avertissements pour vous assurer qu’ils sont ordinaires et conformes à votre infrastructure.
    
4. Dans la colonne **Action** , dans le journal, développez la **Préparation de la forêt**, recherchez un ** \<succès\> ** les résultats de l’exécution à la fin de chaque tâche pour vérifier que la préparation de forêt s’est terminée correctement, fermez le journal, puis cliquez sur fin de ** **.
    
5. Attendez la réplication de Services de domaine Active Directory exécuter, ou forcer la réplication sur tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **Services et Sites Active Directory** pour le contrôleur de domaine racine de forêt, avant d’exécuter la préparation du domaine. Forcer la réplication entre les contrôleurs de domaine dans tous les sites Active Directory pour forcer la réplication ait lieu dans les minutes.
    
    > [!TIP]
    > Si vous devez passer en revue les fichiers journaux qui sont créés par le Skype pour l’Assistant de déploiement de Business Server, vous les trouverez sur l’ordinateur où l’Assistant de déploiement a été exécuté, dans le répertoire des utilisateurs de l’utilisateur des Services de domaine Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

