---
title: Préparer la forêt actuelle
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Pour préparer la forêt des Services de domaine Active Directory, vous devez correctement étendre le schéma, comme décrit dans la rubrique Préparation du schéma en cours d’exécution et vous assurer que le schéma a été répliqué.
ms.openlocfilehash: 2e21b1b3ad2fbfd5ea4194b47710a09366707f64
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882228"
---
# <a name="prepare-current-forest"></a>Préparer la forêt actuelle

Pour préparer la forêt des Services de domaine Active Directory, vous devez correctement étendre le schéma, comme décrit dans la rubrique [Préparation du schéma en cours d’exécution](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)et vous assurer que le schéma a été répliqué.

Après avoir rempli ces conditions préalables, vous pouvez passer à l’**Étape 3 : Préparer la forêt actuelle**. Pour préparer la forêt, connectez-vous à un ordinateur dans la racine de la forêt en tant que membre du groupe Administrateurs du domaine ou en tant que membre du groupe Administrateurs d’entreprise dans la forêt que vous préparez.

1. Dans l’Assistant Déploiement, à l’**Étape 3 : Préparer la forêt actuelle**, cliquez sur **Exécuter**.

2. Dans la page **Préparer la forêt**, cliquez sur **Suivant**.

    > [!NOTE]
    > Préparation de la forêt vous permet de choisir l’emplacement où placer les groupes universels pour Skype pour Business Server. Sélectionnez un emplacement conforme aux besoins de votre organisation.

3. Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**. Assurez-vous qu’il n’y a pas d’erreurs. Consultez les avertissements pour vous assurer qu’ils sont ordinaires et conformes à votre infrastructure.

4. Dans la colonne **Action** , dans le journal, développez **La préparation de la forêt**, recherchez un ** \<réussite\> ** résultat de l’exécution à la fin de chaque tâche pour vérifier que la préparation de forêt terminée avec succès, fermez le fichier journal, puis cliquez sur **Terminer **.

5. Attendre la réplication des Services de domaine Active Directory soit terminée ou forcez la réplication sur tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable **Services et Sites Active Directory** pour le contrôleur de domaine racine de forêt, avant d’exécuter la préparation du domaine. Forcez la réplication entre les contrôleurs de domaine dans tous les sites Active Directory pour forcer la réplication dans les sites se produise en quelques minutes.

    > [!TIP]
    > Si vous avez besoin passer en revue les fichiers journaux qui sont créés par le Skype pour l’Assistant de déploiement Business Server, vous pouvez trouver les sur l’ordinateur où a été exécuté l’Assistant déploiement, dans le répertoire des utilisateurs de l’utilisateur des Services de domaine Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur est connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp


