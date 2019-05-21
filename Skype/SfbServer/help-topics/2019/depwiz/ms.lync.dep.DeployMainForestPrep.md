---
title: Préparer la forêt actuelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Pour préparer la forêt services de domaine Active Directory (AD FS), vous devez prolonger le schéma comme décrit dans la rubrique exécution de la préparation du schéma et vérifier que le schéma a été répliqué.
ms.openlocfilehash: 810bfae1fd308ef943f41846a8baef774f4f724e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303396"
---
# <a name="prepare-current-forest"></a>Préparer la forêt actuelle

Pour préparer la forêt services de domaine Active Directory (AD FS), vous devez prolonger le schéma comme décrit dans la rubrique exécution de la [préparation du schéma](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)et vérifier que le schéma a été répliqué.

Après avoir rempli ces conditions préalables, vous pouvez passer à l’**Étape 3 : Préparer la forêt actuelle**. Pour préparer la forêt, connectez-vous à un ordinateur dans la racine de la forêt en tant que membre du groupe Administrateurs du domaine ou en tant que membre du groupe Administrateurs d’entreprise dans la forêt que vous préparez.

1. Dans l’Assistant Déploiement, à l’**Étape 3 : Préparer la forêt actuelle**, cliquez sur **Exécuter**.

2. Dans la page **Préparer la forêt**, cliquez sur **Suivant**.

    > [!NOTE]
    > La préparation de la forêt vous permet de choisir l’emplacement des groupes universels pour Skype entreprise Server. Sélectionnez un emplacement conforme aux besoins de votre organisation.

3. Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**. Assurez-vous qu’il n’y a pas d’erreurs. Consultez les avertissements pour vous assurer qu’ils sont ordinaires et conformes à votre infrastructure.

4. Dans la colonne **action** du journal, développez **Forest PREP**, recherchez un ** \<\> ** résultat d’exécution réussie à la fin de chaque tâche pour vérifier que la préparation de la forêt s’est déroulée correctement, fermez le journal, puis cliquez sur **Terminer. **.

5. Attendez la fin de la réplication des services de domaine Active Directory, ou forcez la réplication vers tous les contrôleurs de domaine figurant dans le composant logiciel enfichable **sites et services Active Directory** pour le contrôleur de domaine racine de la forêt avant d’exécuter la préparation du domaine. Forcez la réplication entre les contrôleurs de domaine dans tous les sites Active Directory pour que la réplication au sein des sites se produise en quelques minutes.

    > [!TIP]
    > Si vous avez besoin de passer en revue les fichiers journaux créés par l’Assistant Déploiement de Skype entreprise, vous pouvez les retrouver sur l’ordinateur sur lequel l’Assistant déploiement a été exécuté, dans l’annuaire utilisateurs de l’utilisateur de services de domaine Active Directory (AD FS) qui a exécuté l’étape. Par exemple, si l’utilisateur connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans: C:\Users\Administrator.Contoso\AppData\Local\Temp


