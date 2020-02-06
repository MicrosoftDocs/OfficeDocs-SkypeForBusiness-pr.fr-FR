---
title: Stratégie de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Vous pouvez utiliser la page Stratégie de conversation permanente du groupe Conversation permanente pour gérer les stratégies au niveau utilisateur, site, pool ou global, y compris pour configurer la stratégie globale par défaut et créer une ou plusieurs autres stratégies utilisateur et de site pour votre déploiement. Si le serveur Chat permanent est activé pour un utilisateur par stratégie, l’environnement serveur Chat permanent apparaît dans le client.
ms.openlocfilehash: 6692ef8314c3eb1ef38ade8cdbee26d3d76410ef
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822507"
---
# <a name="persistent-chat-policy"></a>Stratégie de conversation permanente
 
Vous pouvez utiliser la page **Stratégie de conversation permanente** du groupe **Conversation permanente** pour gérer les stratégies au niveau utilisateur, site, pool ou global, y compris pour configurer la stratégie globale par défaut et créer une ou plusieurs autres stratégies utilisateur et de site pour votre déploiement. Si le serveur Chat permanent est activé pour un utilisateur par stratégie, l’environnement serveur Chat permanent apparaît dans le client.
  
La stratégie globale est créée automatiquement lorsque vous déployez le serveur Chat permanent et qu’elle peut être configurée, mais pas supprimée. Dans la mesure où la stratégie globale s’applique à tous les utilisateurs, elle ne doit pas être définie par utilisateur.
  
Vous pouvez créer et configurer plusieurs stratégies de site et utilisateurs qui, conjointement avec la stratégie globale, permettent aux utilisateurs de chat permanent. Les stratégies de serveur de chat permanent de pool et de site remplacent la stratégie de serveur de chat permanent global, mais uniquement pour les utilisateurs de ce site. Les stratégies utilisateur remplacent les stratégies utilisateur, de pool et globales pour les utilisateurs auxquels la stratégie utilisateur est affectée.
  
> [!NOTE]
> Pour configurer et utiliser le serveur de chat permanent, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de chat permanent à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous [à la rubrique ajouter un serveur Chat permanent à votre topologie 2015 Skype entreprise Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Stratégie de conversation permanente**, vous pouvez effectuer les tâches suivantes : autorisation et gestion de la stratégie de conversation permanente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Pour configurer la stratégie globale pour la conversation permanente

1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans le panneau de configuration Skype entreprise Server, cliquez sur **conversation permanente**, puis sur **stratégie de conversation persistante**.
    
4. Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut « Global ».
    
   - Dans **Description**, indiquez les détails relatifs à la stratégie de l’utilisateur (par exemple, la stratégie globale pour _centralSiteName_).
    
   - Pour contrôler les discussions permanentes pour tous les sites et les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie de site ou d’un utilisateur, cochez ou décochez la case **activer les discussions permanentes** .
    
6. Cliquez sur **Valider**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Pour créer une stratégie de conversation permanente pour un site

Pour chaque site déployé, vous pouvez créer une stratégie de conversation persistante spécifique au site.
  
La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie.
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Créer**, puis sur **Stratégie de site**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.
    
6. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, « Redmond »).
    
   - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, « Stratégie de salle de conversation pour Redmond »).
    
   - Pour contrôler la conversation permanente pour tous les sites qui ne sont pas contrôlés spécifiquement par le biais d’une stratégie de site, activez ou désactivez la case à cocher **Activer la conversation permanente**.
    
7. Cliquez sur **Valider**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Pour créer une stratégie utilisateur pour la discussion permanente

Le panneau de configuration Skype entreprise Server vous permet de **définir des stratégies**utilisateur qui peuvent être affectées à des utilisateurs.
  
La stratégie utilisateur remplace les stratégies globales et de site, mais uniquement pour les utilisateurs spécifiques auxquels la stratégie utilisateur est affectée.
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.
    
5. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.
    
   - Dans **Description**, indiquez les détails relatifs à la stratégie de l’utilisateur (par exemple, la stratégie de conversation permanente pour un utilisateur spécifique).
    
   - Pour contrôler la conversation permanente de tous les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie utilisateur, activez ou désactivez la case à cocher **activer les discussions permanentes** .
    
6. Cliquez sur **Valider**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Pour appliquer une stratégie utilisateur de conversation permanente à un compte d’utilisateur

Si un utilisateur a été activé pour Skype entreprise Server, vous pouvez appliquer les stratégies appropriées à des utilisateurs spécifiques pour les activer ou les désactiver pour le serveur de chat permanent.
  
Suivez la procédure décrite dans cette rubrique pour appliquer une stratégie d’utilisateur de conversation permanente créée précédemment à un ou plusieurs comptes d’utilisateurs ou groupes d’utilisateurs.
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **modifier l’utilisateur de Lync Server** sous **stratégie de chat persistante**, sélectionnez la stratégie d’utilisateur de conversation permanente que vous voulez appliquer.
    
    > [!NOTE]
    > Les ** \<paramètres\> automatiques** appliquent la stratégie d’effectivité par défaut. Ces paramètres sont appliqués automatiquement par le serveur.
  
6. Cliquez sur **Valider**.
    

