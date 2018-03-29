---
title: Configuration des stratégies d’archivage pour Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer les stratégies d’archivage initiales pour Skype pour les utilisateurs de Business Server 2015.'
ms.openlocfilehash: 9829d0c5ad5ea9e62c2335c3387fcd22623c6751
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-policies-for-skype-for-business-server-2015"></a>Configuration des stratégies d’archivage pour Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment configurer les stratégies d’archivage initiales pour Skype pour les utilisateurs de Business Server 2015.
  
Skype pour Business Server, vous permet d’utiliser des stratégies pour activer et désactiver l’archivage des communications internes et externes communications pour les utilisateurs qui sont hébergés sur Skype pour Business Server. Il s’agit notamment de ce qui suit :
  
- Une stratégie globale qui est créée par défaut lorsque vous déployez Skype pour Business Server
    
- Stratégies facultatives au niveau site qui définissent de quelle manière l’archivage est implémenté pour un site spécifique
    
- Stratégies au niveau de l’utilisateur facultatives qui spécifient comment l’archivage est mis en oeuvre pour des utilisateurs spécifiques
    
Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement. Dans Skype pour le panneau de configuration de Business Server, vous pouvez utiliser la page de **Stratégie d’archivage** du groupe de **surveillance et archivage** pour gérer les stratégies au niveau global, du site et niveaux d’utilisateurs.
  
> [!NOTE]
> Pour contrôler l’implémentation de l’archivage, vous devez définir certaines options, notamment spécifier si les messages instantanés ou les conférences doivent être archivés, si le mode critique est utilisé et les options de vidage. Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans la configuration de l’archivage de site ou de pool. Vous devez définir toutes les options appropriées avant d’activer l’archivage des communications internes ou externes. Pour plus d’informations, voir [configurer l’archivage des options pour Skype pour Business Server 2015](configure-archiving-options.md). 
  
> [!NOTE]
> Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, maintenez la touche Exchange Place le contrôle les stratégies si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange et que leurs boîtes aux lettres sur Place maintenez. 
  
Pour plus d’informations sur les stratégies d’archivage comment fonctionne, y compris la hiérarchie de site globale, et stratégies d’utilisateur, reportez-vous à [planification d’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md). Pour plus d’informations sur la façon de gérer les stratégies après le déploiement, voir [Gérer les règles d’archivage dans Skype pour Business Server 2015](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Stratégie globale

Lorsque vous déployez vos serveurs frontaux, Skype pour Business Server crée une stratégie globale pour l’archivage. Par défaut, l’archivage est désactivé dans la stratégie globale. Si l’archivage est activé pour les communications internes et externes pour votre déploiement complet, sauf si vous définissez les stratégies de site ou de l’utilisateur, qui remplace la stratégie globale, ou si vous utilisez l’intégration de Microsoft Exchange pour certains ou tous des contrôles de la stratégie globale vos utilisateurs. Si vous utilisez l’intégration de Microsoft Exchange, la stratégie globale ne s’applique pas à tous les utilisateurs qui sont hébergés sur Exchange et que les boîtes aux lettres sur Place maintenez.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurer la stratégie globale pour l’archivage de Skype pour bases de données d’archivage Business Server

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.
    
4. Dans la page **Stratégie d’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :
    
   - Dans **Nom**, si vous ne souhaitez pas utiliser le nom par défaut Global, spécifiez un nouveau nom pour la stratégie globale. 
    
   - Dans la zone **Description**, fournissent des informations sur les nouveautés de la stratégie (par exemple, une stratégie globale pour *divisionName* .
    
   - Afin de contrôler l’archivage des communications internes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Afin de contrôler l’archivage des communications externes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
## <a name="site-policies"></a>Stratégies de site

Vous pouvez activer ou désactiver l’archivage pour des sites spécifiques en créant une stratégie d’archivage pour chacun de ces sites. Une stratégie de site remplace la stratégie globale, mais les stratégies utilisateur remplacent les stratégies de site. Les stratégies d’archivage ne s’appliquent que si vous n’utilisez pas l’intégration de Microsoft Exchange, ou si vous utilisez une intégration de Microsoft Exchange, mais ont des utilisateurs qui ne sont pas hébergés sur Exchange et qui disposent de leurs boîtes aux lettres mis sur Place maintenez.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Créer une stratégie d’archivage pour un site

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.
    
    Pour plus d’informations sur les stratégies d’archivage comment fonctionne, y compris la hiérarchie de site globale, et stratégies d’utilisateur, reportez-vous à [planification d’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md).
    
4. Cliquez sur **Créer**, puis sur **Stratégie de site**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.
    
6. Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
   - Dans **Nom**, spécifiez le nom pour la stratégie de site. 
    
   - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de site pour Redmond).
    
   - Pour contrôler l’archivage des communications internes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour contrôler l’archivage des communications externes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
7. Cliquez sur **Valider**.
    
## <a name="user-policies"></a>Stratégies utilisateur

Vous pouvez activer ou désactiver l’archivage pour des utilisateurs spécifiques en créant et en configurant une stratégie d’archivage pour les utilisateurs, puis en appliquant la stratégie à des utilisateurs spécifiques ou à des groupes d’utilisateurs. Les stratégies utilisateur remplacent les stratégies globales ou de site. Les stratégies d’archivage ne s’appliquent que si vous n’utilisez pas l’intégration de Microsoft Exchange, ou si vous utilisez une intégration de Microsoft Exchange, mais ont des utilisateurs qui ne sont pas hébergés sur Exchange et qui disposent de leurs boîtes aux lettres mis sur Place maintenez.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurer une stratégie d’archivage pour les utilisateurs hébergés sur Skype pour Business Server

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.
    
4. Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.
    
5. Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
   - Dans **Nom**, spécifiez le nom de la stratégie utilisateur. 
    
   - Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie utilisateur pour le service juridique).
    
   - Pour contrôler l’archivage des communications internes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour contrôler l’archivage des communications externes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
Une stratégie utilisateur ne s’applique qu’aux utilisateurs auxquels vous affectez la stratégie.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Appliquer un Skype pour l’archivage de stratégie à un utilisateur de Business Server

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier un Skype pour l’utilisateur de Business Server** sous **les stratégies d’archivage**, sélectionnez la stratégie d’archivage de l’utilisateur que vous souhaitez appliquer.
    
    > [!NOTE]
    > La ** \<automatique\> ** les paramètres s’appliquent les paramètres d’installation de serveur par défaut. Le serveur les applique automatiquement.
  
6. Cliquez sur **Valider**.
    

