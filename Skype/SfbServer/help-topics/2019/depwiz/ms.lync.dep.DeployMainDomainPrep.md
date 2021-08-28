---
title: Préparer le domaine actuel
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour préparer un domaine à héberger des serveurs exécutant des utilisateurs Skype Entreprise Server ou Skype Entreprise Server, vous devez effectuer l’étape 5 : Préparer le domaine actuel, comme décrit dans la rubrique Utilisation du programme d’installation pour exécuter la préparation du domaine. Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :'
ms.openlocfilehash: 74725bde4f50219a2d46cca4ab0ab32daa733b83
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616910"
---
# <a name="prepare-current-domain"></a>Préparer le domaine actuel

Pour préparer un domaine à héberger des serveurs exécutant des utilisateurs Skype Entreprise Server ou Skype Entreprise Server, vous devez effectuer l’étape **5**: Préparer le domaine actuel, comme décrit dans la rubrique Utilisation du programme d’installation pour exécuter la préparation du [domaine.](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation) Pour cela, vous devez être connecté en tant que membre du groupe Administrateurs du domaine dans le domaine que vous préparez ou en tant que membre du groupe Administrateurs d’entreprise de la forêt à laquelle le domaine appartient. Pour préparer le domaine :

1. À partir du Skype Entreprise Server ou du support d’installation, exécutez Setup.exe pour démarrer l’Assistant Skype Entreprise Server déploiement.

2. Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.

3. À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.

4. Sur la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.

5. Sous la colonne **Action,** développez Préparation du **domaine,** recherchez un résultat d’exécution à la fin de chaque tâche pour vérifier que la préparation du domaine s’est correctement terminée, fermez le journal, puis cliquez sur **\<Success\>** **Terminer.**

> [!TIP]
> Si vous devez passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype Entreprise Server, vous pouvez les trouver sur l’ordinateur sur lequel l’Assistant Déploiement a été exécuté dans l’annuaire Utilisateurs de l’utilisateur des services de domaine Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur s’est connecté en tant qu’administrateur de domaine dans le Contoso.net de domaine, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp.