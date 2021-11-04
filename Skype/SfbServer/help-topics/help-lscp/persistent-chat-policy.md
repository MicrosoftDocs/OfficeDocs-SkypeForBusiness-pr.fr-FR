---
title: Stratégie de conversation permanente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Vous pouvez utiliser la page Stratégie de conversation permanente du groupe conversation permanente pour gérer les stratégies au niveau global, pool, site ou utilisateur, y compris la configuration de la stratégie globale par défaut et la création d’une ou de plusieurs stratégies utilisateur et de site supplémentaires pour votre déploiement. Si le serveur de conversation permanente est activé pour un utilisateur par une stratégie, l’environnement de serveur de conversation permanente apparaît dans son client.
ms.openlocfilehash: 5736f0fc41f86331662e88c0f980c19c89be72c4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748190"
---
# <a name="persistent-chat-policy"></a>Stratégie de conversation permanente
 
Vous pouvez utiliser la **page**  Stratégie de conversation permanente du groupe conversation permanente pour gérer les stratégies au niveau global, pool, site ou utilisateur, y compris la configuration de la stratégie globale par défaut et la création d’une ou de plusieurs stratégies utilisateur et de site supplémentaires pour votre déploiement. Si le serveur de conversation permanente est activé pour un utilisateur par une stratégie, l’environnement de serveur de conversation permanente apparaît dans son client.
  
La stratégie globale est créée automatiquement lorsque vous déployez un serveur de conversation permanente et peut être configurée, mais pas supprimée. Étant donné que la stratégie globale s’applique à tous les utilisateurs, elle n’a pas besoin d’être définie par utilisateur.
  
Vous pouvez créer et configurer plusieurs stratégies de site et d’utilisateur qui, avec la stratégie globale, activent les utilisateurs pour le serveur de conversation permanente. Les stratégies de serveur de conversation permanente de pool et de site remplacent la stratégie globale du serveur de conversation permanente, mais uniquement pour les utilisateurs de ce site. Les stratégies utilisateur supplantent les stratégies utilisateur, de pool et globales pour les utilisateurs auxquels la stratégie utilisateur est assignée.
  
> [!NOTE]
> Pour configurer et utiliser le serveur de conversation permanente, vous devez d’abord utiliser le Générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à la topologie, puis publier la topologie. Pour plus d’informations, voir Ajouter un serveur de conversation permanente à [votre topologie Skype Entreprise Server 2015.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md) 
  
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page Stratégie de **conversation** permanente : activer la stratégie de serveur de conversation permanente . gérer la stratégie de serveur de conversation permanente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Pour configurer la stratégie globale pour la conversation permanente

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans Skype Entreprise Server de contrôle, cliquez sur **Conversation** permanente, puis sur **Stratégie de conversation permanente.**
    
4. Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut Globale.
    
   - Dans **Description,** fournissez des détails sur la stratégie utilisateur (par exemple, stratégie globale pour  _centralSiteName_).
    
   - Pour contrôler la conversation permanente pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie de site ou d’une stratégie utilisateur, activez ou activez la case à cocher Activer la **conversation** permanente.
    
6. Cliquez sur **Valider**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Pour créer une stratégie de conversation permanente pour un site

Pour chaque site que vous avez déployé, vous pouvez créer une stratégie de conversation permanente spécifique au site.
  
La configuration de la stratégie du site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie.
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Nouveau**, puis sur **Stratégie de site**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.
    
6. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, Redmond).
    
   - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de salle de conversation pour Redmond).
    
   - Pour contrôler la conversation permanente pour tous les sites qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie de site, activez ou activez la case à cocher Activer la **conversation** permanente.
    
7. Cliquez sur **Valider**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Pour créer une stratégie utilisateur pour la conversation permanente

Dans le Skype Entreprise Server de contrôle d’accès, vous définissez des stratégies utilisateur qui peuvent être affectées à des utilisateurs dans **Utilisateurs.**
  
La stratégie utilisateur supplante les stratégies globale et de site, mais uniquement pour les utilisateurs pour lesquels la stratégie utilisateur est appliquée.
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.
    
5. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.
    
   - Dans **Description,** fournissez des détails sur la stratégie utilisateur (par exemple, stratégie de conversation permanente pour un utilisateur spécifique).
    
   - Pour contrôler la conversation permanente pour tous les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie utilisateur, activez ou activez la case à cocher Activer la **conversation** permanente.
    
6. Cliquez sur **Valider**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Pour appliquer une stratégie d’utilisateur de conversation permanente à un compte d’utilisateur

Si un utilisateur a été activé pour Skype Entreprise Server, vous pouvez appliquer des stratégies appropriées à des utilisateurs spécifiques pour les activer ou les désactiver pour le serveur de conversation permanente.
  
Utilisez la procédure de cette rubrique pour appliquer une stratégie d’utilisateur de conversation permanente créée précédemment à un ou plusieurs comptes d’utilisateurs ou groupes d’utilisateurs.
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier l’utilisateur Lync Server sous** **stratégie** de conversation permanente, sélectionnez la stratégie utilisateur de conversation permanente à appliquer.
    
    > [!NOTE]
    > Les **\<Automatic\>** paramètres appliquent la stratégie effective par défaut. Ces paramètres sont appliqués automatiquement par le serveur.
  
6. Cliquez sur **Valider**.
    

