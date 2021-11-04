---
title: Préparer la forêt actuelle
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Pour préparer la forêt des services de domaine Active Directory, vous devez étendre correctement le schéma, comme décrit dans la rubrique Exécution de la préparation du schéma, et vous assurer que le schéma a été répliqué.
ms.openlocfilehash: b73be89b857e933f9e461371971eff2c247a39b2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761022"
---
# <a name="prepare-current-forest"></a>Préparer la forêt actuelle

Pour préparer la forêt des services de domaine Active Directory, vous devez étendre correctement le schéma, comme décrit dans la rubrique Exécution de la préparation du [schéma,](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema)et vous assurer que le schéma a été répliqué.

Après avoir terminé ces conditions préalables, vous pouvez commencer **l’étape 3 : Préparer la forêt actuelle**. Pour préparer la forêt, connectez-vous à un ordinateur à la racine de la forêt en tant que membre des administrateurs de domaine à la racine de la forêt ou en tant que membre des administrateurs Enterprise pour la forêt que vous préparez.

1. Dans l'Assistant Déploiement, à l'**Étape 3 : Préparer la forêt actuelle**, cliquez sur **Exécuter**.

2. Sur la page **Préparer la forêt**, cliquez sur **Suivant**.

    > [!NOTE]
    > La préparation de la forêt vous permet de choisir où placer les groupes universels pour Skype Entreprise Server 2015. Choisissez un emplacement cohérent avec les conditions requises de votre organisation.

3. Sur la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**. Assurez-vous qu’il n’y a aucune erreur. Examinez les avertissements pour déterminer s’ils sont attendus et typiques pour votre infrastructure.

4. Sous la colonne **Action** du journal, développez Préparation de la **forêt,** recherchez un résultat d’exécution à la fin de chaque tâche pour vérifier que la préparation de la forêt s’est correctement terminée, fermez le journal, puis cliquez sur **\<Success\>** **Terminer.**

5. Attendez que la réplication des services de domaine Active Directory soit terminée ou forcez la réplication vers tous les contrôleurs de domaine répertoriés dans le logiciel en ligne Sites et **services Active Directory** pour le contrôleur de domaine racine de la forêt, avant d’effectuer la préparation du domaine. Forcez la réplication entre les contrôleurs de domaine sur tous les sites Active Directory pour faire en sorte que la réplication au sein de ces sites se produise en quelques minutes.

    > [!TIP]
    > Si vous devez passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype Entreprise Server, vous pouvez les trouver sur l’ordinateur sur lequel l’Assistant Déploiement a été exécuté, dans l’annuaire Utilisateurs de l’utilisateur des services de domaine Active Directory qui a exécuté l’étape. Par exemple, si l’utilisateur s’est connecté en tant qu’administrateur de domaine dans le Contoso.net de domaine, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp