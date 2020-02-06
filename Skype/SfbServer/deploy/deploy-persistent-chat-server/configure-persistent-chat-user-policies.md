---
title: Configuration des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Résumé : pour plus d’informations sur la création de stratégies utilisateur initiales pour le serveur de conversation persistant dans Skype entreprise Server 2015, consultez la rubrique suivante. Les stratégies utilisateur de conversation permanente déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.'
ms.openlocfilehash: a51304c9e85951e9858d56c511aa8c7519babe51
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795695"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configuration des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Pour plus d’informations sur la création de stratégies utilisateur initiales pour le serveur de chat permanent dans Skype entreprise Server 2015, lisez cette rubrique. Les stratégies utilisateur de conversation permanente déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.
  
Vous pouvez gérer les stratégies d’utilisateur de chat permanent aux niveaux suivants : global, site ou utilisateur. Initialement, vous configurez la stratégie globale pour activer les paramètres de conversation permanente pour tous les utilisateurs de votre déploiement, puis créer des stratégies utilisateur et site supplémentaires afin de déterminer si la conversation permanente est activée pour des utilisateurs ou des sites spécifiques.
  
Cette rubrique contient les sections suivantes :
  
- Configurer la stratégie globale
    
- Créer une stratégie de site
    
- Créer une stratégie utilisateur
    
- Appliquer une stratégie à un utilisateur ou un groupe d’utilisateurs
    
> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.

## <a name="configure-the-global-policy"></a>Configurer la stratégie globale

Pour configurer la stratégie globale :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans le panneau de configuration Skype entreprise Server, cliquez sur **conversation permanente**, puis sur **stratégie de conversation persistante**.
    
4. Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit : 
    
   - Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut « Global ».
    
   - Dans **Description**, indiquez les détails relatifs à la stratégie de l’utilisateur (par exemple, la stratégie globale pour _centralSiteName_).
    
   - Pour contrôler les discussions permanentes pour tous les sites et les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie de site ou d’un utilisateur, cochez ou décochez la case **activer les discussions permanentes** .
    
6. Cliquez sur **Valider**.
    
## <a name="create-a-site-policy"></a>Créer une stratégie de site

Pour chaque site déployé, vous pouvez créer une stratégie de conversation persistante spécifique au site. La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie. Pour créer une stratégie de site :
  
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
    
## <a name="create-a-user-policy"></a>Créer une stratégie utilisateur

Vous pouvez créer des stratégies spécifiques à l’utilisateur qui remplacent la stratégie globale et les stratégies de site auxquelles l’utilisateur appartient. Pour créer une stratégie d’utilisateur :
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.
    
5. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.
    
   - Dans **Description**, indiquez les détails relatifs à la stratégie de l’utilisateur (par exemple, la stratégie de conversation permanente pour un utilisateur spécifique).
    
   - Pour contrôler la conversation permanente de tous les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie utilisateur, activez ou désactivez la case à cocher **activer les discussions permanentes** .
    
6. Cliquez sur **Valider**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Appliquer une stratégie à un compte d’utilisateur

Lorsque vous créez des stratégies, vous pouvez les appliquer à un compte d’utilisateur en procédant comme suit :
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **modifier l’utilisateur de Skype entreprise Server** sous **stratégie de chat persistante**, sélectionnez la stratégie d’utilisateur de conversation permanente que vous voulez appliquer.
    
    > [!NOTE]
    > Les ** \<paramètres\> automatiques** appliquent la stratégie d’effectivité par défaut. Ces paramètres sont appliqués automatiquement par le serveur.
  
6. Cliquez sur **Valider**.
    

