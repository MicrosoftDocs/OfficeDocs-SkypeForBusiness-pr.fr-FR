---
title: Préparer le domaine actuel
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
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Pour préparer un domaine à héberger des serveurs exécutant des utilisateurs Skype Entreprise Server 2015 ou Skype Entreprise Server, vous devez effectuer l’étape 5 : Préparer le domaine actuel, comme décrit dans la rubrique Utilisation du programme d’installation pour exécuter la préparation du domaine. Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :'
ms.openlocfilehash: 99c74ad910228eb73666fd6640b288c5ba84523a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835582"
---
# <a name="prepare-current-domain"></a>Préparer le domaine actuel

Pour préparer un domaine à héberger des serveurs exécutant des utilisateurs Skype Entreprise Server 2015 ou Skype Entreprise Server, vous devez effectuer l’étape **5**: Préparer le domaine actuel, comme décrit dans la rubrique Utilisation du programme d’installation pour exécuter la préparation du [domaine.](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation) Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :

1. À partir du Skype Entreprise Server d’installation ou du support d’installation 2015, exécutez Setup.exe pour démarrer l’Assistant Skype Entreprise Server déploiement.

2. Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.

3. À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.

4. Sur la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.

5. Sous la colonne **Action,** développez Préparation du **domaine,** recherchez un résultat d’exécution à la fin de chaque tâche pour vérifier que la préparation du domaine s’est correctement terminée, fermez le journal, puis cliquez sur **\<Success\>** **Terminer.**

> [!TIP]
> Si vous devez passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype Entreprise Server, vous pouvez les trouver sur l’ordinateur sur lequel l’Assistant Déploiement a été exécuté dans l’annuaire Utilisateurs de l’utilisateur des services de domaine Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur s’est connecté en tant qu’administrateur de domaine dans le Contoso.net de domaine, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp.