---
title: Configurer des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Résumé : Lisez cette rubrique pour découvrir comment créer des stratégies utilisateur initiales pour le serveur de conversation permanente Skype Entreprise Server 2015. Les stratégies utilisateur de conversation permanente déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.'
ms.openlocfilehash: 71003f6befa3e6c47cd65829c3703a45527e5964
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832858"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurer des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour découvrir comment créer des stratégies utilisateur initiales pour le serveur de conversation permanente Skype Entreprise Server 2015. Les stratégies utilisateur de conversation permanente déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.
  
Vous pouvez gérer les stratégies utilisateur du serveur de conversation permanente aux niveaux suivants : global, site ou utilisateur. Initialement, vous configurez la stratégie globale pour activer les paramètres de conversation permanente pour tous les utilisateurs de votre déploiement, puis créez des stratégies utilisateur et de site supplémentaires pour contrôler si la conversation permanente est activée pour des utilisateurs et des sites spécifiques.
  
Cette rubrique comprend les sections suivantes :
  
- Configurer la stratégie globale
    
- Créer une stratégie de site
    
- Créer une stratégie utilisateur
    
- Appliquer une stratégie à un utilisateur ou à un groupe d’utilisateurs
    
> [!NOTE] 
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015.

## <a name="configure-the-global-policy"></a>Configurer la stratégie globale

Pour configurer la stratégie globale :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans Skype Entreprise Server de contrôle, cliquez sur **Conversation** permanente, puis sur **Stratégie de conversation permanente.**
    
4. Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit : 
    
   - Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut Globale.
    
   - Dans **Description,** fournissez des détails sur la stratégie utilisateur (par exemple, stratégie globale pour  _centralSiteName_).
    
   - Pour contrôler la conversation permanente pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie de site ou d’une stratégie utilisateur, activez ou activez la case à cocher Activer la **conversation** permanente.
    
6. Cliquez sur **Valider**.
    
## <a name="create-a-site-policy"></a>Créer une stratégie de site

Pour chaque site que vous avez déployé, vous pouvez créer une stratégie de conversation permanente spécifique au site. La configuration de la stratégie du site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie. Pour créer une stratégie de site :
  
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
    
## <a name="create-a-user-policy"></a>Créer une stratégie utilisateur

Vous pouvez créer des stratégies spécifiques à l’utilisateur qui remplacent la stratégie globale et les stratégies de site à laquelle l’utilisateur appartient. Pour créer une stratégie utilisateur :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.
    
5. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.
    
   - Dans **Description,** fournissez des détails sur la stratégie utilisateur (par exemple, stratégie de conversation permanente pour un utilisateur spécifique).
    
   - Pour contrôler la conversation permanente pour tous les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie utilisateur, activez ou activez la case à cocher Activer la **conversation** permanente.
    
6. Cliquez sur **Valider**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Appliquer une stratégie à un compte d’utilisateur

Après avoir créé des stratégies, vous pouvez les appliquer à un compte d’utilisateur comme suit :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier Skype Entreprise Server utilisateur sous** **stratégie** de conversation permanente, sélectionnez la stratégie utilisateur de conversation permanente à appliquer.
    
    > [!NOTE]
    > Les **\<Automatic\>** paramètres appliquent la stratégie effective par défaut. Ces paramètres sont appliqués automatiquement par le serveur.
  
6. Cliquez sur **Valider**.
    

