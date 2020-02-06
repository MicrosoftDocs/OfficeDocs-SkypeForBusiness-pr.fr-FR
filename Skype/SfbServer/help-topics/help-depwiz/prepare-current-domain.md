---
title: Préparer le domaine actuel
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
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Pour préparer un domaine pour l’hébergement de serveurs exécutant Skype entreprise Server 2015 ou les utilisateurs de Skype entreprise Server, vous devez suivre l’étape 5 : préparer le domaine actuel, comme décrit dans la rubrique utilisation du programme d’installation pour exécuter la préparation du domaine. Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :'
ms.openlocfilehash: 2f3563c9a1c857e9d4828ca63cf2cb675f524e56
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823548"
---
# <a name="prepare-current-domain"></a>Préparer le domaine actuel

Pour préparer un domaine pour l’hébergement de serveurs exécutant Skype entreprise Server 2015 ou les utilisateurs de Skype entreprise Server, vous devez suivre l' **étape 5 : préparer le domaine actuel**, comme décrit dans la rubrique [utilisation du programme d’installation pour exécuter la préparation du domaine](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :

1. Dans le dossier d’installation ou le média de Skype entreprise Server 2015, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Skype entreprise Server.

2. Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.

3. À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.

4. Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.

5. Dans la colonne **action** , développez **Domain PREP**, recherchez un ** \<résultat\> ** d’exécution réussie à la fin de chaque tâche pour vérifier que la préparation du domaine s’est déroulée correctement, fermez le journal, puis cliquez sur **Terminer**.

> [!TIP]
> Si vous avez besoin de passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype entreprise, vous pouvez les retrouver sur l’ordinateur sur lequel l’Assistant déploiement a été exécuté dans le répertoire utilisateurs de l’utilisateur de services de domaine Active Directory (AD FS) qui a exécuté l’étape. Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp.


