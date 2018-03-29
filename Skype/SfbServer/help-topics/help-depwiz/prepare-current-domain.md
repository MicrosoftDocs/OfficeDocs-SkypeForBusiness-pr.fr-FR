---
title: Préparer le domaine actuel
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Pour préparer un domaine à héberger des serveurs exécutant Skype pour Business Server 2015 ou Skype pour les utilisateurs de Business Server, vous devez terminer étape 5 : domaine actuel préparer, comme décrit dans la rubrique à l’aide du programme d’installation s’exécuter préparation du domaine. Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :'
ms.openlocfilehash: e34498dd44d7518300b0e7d4df6a5135b8e51a2d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-current-domain"></a>Préparer le domaine actuel
 
Pour préparer un domaine à héberger des serveurs exécutant Skype pour Business Server 2015 ou Skype pour les utilisateurs de Business Server, vous devez exécuter **étape 5 : préparer le domaine en cours**, comme décrit dans la rubrique [à l’aide du programme d’installation s’exécuter préparation du domaine](http://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :
  
1. À partir de la Skype pour le dossier d’installation de Business Server 2015 ou de support, exécutez Setup.exe pour démarrer le Skype pour l’Assistant de déploiement de Business Server.
    
2. Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.
    
3. À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.
    
4. Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.
    
5. Dans la colonne **Action** , développez la **Préparation du domaine**, recherchez un ** \<succès\> ** les résultats de l’exécution à la fin de chaque tâche et vérifiez que la préparation de domaine s’est terminée correctement, fermez le journal, puis cliquez sur **Terminer**.
    
> [!TIP]
> Si vous devez passer en revue les fichiers journaux qui sont créés par le Skype pour l’Assistant de déploiement de Business Server, vous les trouverez sur l’ordinateur où l’Assistant de déploiement a été exécuté dans le répertoire des utilisateurs de l’utilisateur des Services de domaine Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  

