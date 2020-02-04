---
title: Préparer le domaine actuel
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour préparer le domaine à l’hébergement de serveurs exécutant Skype entreprise Server ou les utilisateurs de Skype entreprise Server, vous devez effectuer l’étape 5 : préparer le domaine actuel, comme décrit dans la rubrique utilisation de la configuration pour exécuter la préparation du domaine. Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :'
ms.openlocfilehash: 966f80fe799529ec4d208318fa417146db67ea13
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705439"
---
# <a name="prepare-current-domain"></a>Préparer le domaine actuel

Pour préparer le domaine à l’hébergement de serveurs exécutant Skype entreprise Server ou les utilisateurs de Skype entreprise Server, vous devez effectuer l' **étape 5 : préparer le domaine actuel**, comme décrit dans la rubrique [utilisation de la configuration pour exécuter la préparation du domaine](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :

1. Dans le dossier d’installation ou le média de Skype entreprise Server, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Skype entreprise Server.

2. Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.

3. À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.

4. Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.

5. Dans la colonne **action** , développez **Domain PREP**, recherchez un ** \<résultat\> ** d’exécution réussie à la fin de chaque tâche pour vérifier que la préparation du domaine s’est déroulée correctement, fermez le journal, puis cliquez sur **Terminer**.

> [!TIP]
> Si vous avez besoin de passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype entreprise, vous pouvez les retrouver sur l’ordinateur sur lequel l’Assistant déploiement a été exécuté dans le répertoire utilisateurs de l’utilisateur de services de domaine Active Directory (AD FS) qui a exécuté l’étape. Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp.


