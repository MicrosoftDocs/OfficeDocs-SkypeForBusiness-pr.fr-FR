---
title: Préparer le domaine actuel
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour préparer un domaine à héberger des serveurs exécutant Skype pour Business Server ou Skype pour les utilisateurs Business Server, vous devez effectuer étape 5 : préparer le domaine actuel, comme décrit dans la rubrique à l’aide du programme d’installation pour exécuter la préparation du domaine. Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :'
ms.openlocfilehash: d2c51b472ad31c52eb86c4dd99d60747ce9bf1df
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21008721"
---
# <a name="prepare-current-domain"></a>Préparer le domaine actuel
 
Pour préparer un domaine à héberger des serveurs exécutant Skype pour Business Server ou Skype pour les utilisateurs Business Server, vous devez effectuer **étape 5 : préparer le domaine actuel**, comme décrit dans la rubrique [à l’aide du programme d’installation pour exécuter la préparation du domaine](http://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :
  
1. À partir de Skype pour le dossier d’installation Business Server ou du support, exécutez Setup.exe pour démarrer le Skype pour l’Assistant de déploiement Business Server.
    
2. Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.
    
3. À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.
    
4. Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.
    
5. Dans la colonne **Action** , développez la **Préparation du domaine**, recherchez un ** \<réussite\> ** résultat de l’exécution à la fin de chaque tâche pour vérifier que la préparation de domaine terminée avec succès, fermez le fichier journal, puis cliquez sur **Terminer**.
    
> [!TIP]
> Si vous avez besoin passer en revue les fichiers journaux qui sont créés par le Skype pour l’Assistant de déploiement Business Server, vous pouvez trouver les sur l’ordinateur où l’Assistant de déploiement a été exécuté dans le répertoire des utilisateurs de l’utilisateur des Services de domaine Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur est connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  

