---
title: Préparer la forêt actuelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Pour préparer la forêt des services de domaine Active Directory, vous devez étendre correctement le schéma, comme décrit dans la rubrique Exécution de la préparation du schéma, et vous assurer que le schéma a été répliqué.
ms.openlocfilehash: eaeabfb543d258e65b387afeafddf15367f6caf7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815434"
---
# <a name="prepare-current-forest"></a>Préparer la forêt actuelle

Pour préparer la forêt des services de domaine Active Directory, vous devez étendre correctement le schéma, comme décrit dans la rubrique Exécution de la préparation du [schéma,](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)et vous assurer que le schéma a été répliqué.

Après avoir terminé ces conditions préalables, vous pouvez commencer **l’étape 3 : Préparer la forêt actuelle**. Pour préparer la forêt, connectez-vous à un ordinateur à la racine de la forêt en tant que membre des administrateurs de domaine à la racine de la forêt ou en tant que membre des administrateurs d’entreprise pour la forêt que vous préparez.

1. Dans l'Assistant Déploiement, à l'**Étape 3 : Préparer la forêt actuelle**, cliquez sur **Exécuter**.

2. Sur la page **Préparer la forêt**, cliquez sur **Suivant**.

    > [!NOTE]
    > La préparation de la forêt vous permet de choisir où placer les groupes universels pour Skype Entreprise Server 2015. Choisissez un emplacement cohérent avec les conditions requises de votre organisation.

3. Sur la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**. Assurez-vous qu’il n’y a aucune erreur. Examinez les avertissements pour déterminer s’ils sont attendus et typiques pour votre infrastructure.

4. Sous la colonne **Action** du journal, développez Préparation de la **forêt,** recherchez un résultat d’exécution à la fin de chaque tâche pour vérifier que la préparation de la forêt s’est correctement terminée, fermez le journal, puis cliquez sur **\<Success\>** **Terminer.**

5. Attendez que la réplication des services de domaine Active Directory soit terminée ou forcez la réplication vers tous les contrôleurs de domaine répertoriés dans le logiciel en ligne Sites et **services Active Directory** pour le contrôleur de domaine racine de la forêt, avant d’effectuer la préparation du domaine. Forcez la réplication entre les contrôleurs de domaine sur tous les sites Active Directory pour faire en sorte que la réplication au sein de ces sites se produise en quelques minutes.

    > [!TIP]
    > Si vous devez consulter les fichiers journaux créés par l’Assistant Déploiement de Skype Entreprise Server, vous pouvez les trouver sur l’ordinateur sur lequel l’Assistant Déploiement a été exécuté, dans l’annuaire Utilisateurs de l’utilisateur des services de domaine Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur s’est connecté en tant qu’administrateur de domaine dans le Contoso.net de domaine, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp


