---
title: Configuration des stratégies d’archivage de Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer les stratégies d’archivage initiales pour Skype pour les utilisateurs Business Server.'
ms.openlocfilehash: 88840d10cbd7a71b32b5079a8600018b97e8b0c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876449"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Configuration des stratégies d’archivage de Skype pour Business Server
 
**Résumé :** Lisez cette rubrique pour savoir comment configurer les stratégies d’archivage initiales pour Skype pour les utilisateurs Business Server.
  
Dans Skype pour Business Server, vous utilisez des stratégies pour activer et désactiver l’archivage des communications internes et les communications externes pour les utilisateurs qui sont hébergés sur Skype pour Business Server. Il s’agit notamment de ce qui suit :
  
- Une stratégie globale qui est créée par défaut lorsque vous déployez Skype pour Business Server
    
- Stratégies facultatives au niveau site qui définissent de quelle manière l’archivage est implémenté pour un site spécifique
    
- Stratégies facultatives au niveau de l’utilisateur qui spécifient comment l’archivage est implémenté pour des utilisateurs spécifiques
    
Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement. Dans Skype pour le panneau de configuration serveur Business, vous pouvez utiliser la page **Stratégie d’archivage** du groupe **d’archivage et surveillance** pour gérer les stratégies au niveau global, site et les niveaux de l’utilisateur.
  
> [!NOTE]
> Pour contrôler l’implémentation de l’archivage, vous devez définir certaines options, notamment spécifier si les messages instantanés ou les conférences doivent être archivés, si le mode critique est utilisé et les options de vidage. Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans la configuration de l’archivage de site ou de pool. Vous devez définir toutes les options appropriées avant d’activer l’archivage des communications internes ou externes. Pour plus d’informations, voir [configurer les options de Skype pour Business Server d’archivage](configure-archiving-options.md). 
  
> [!NOTE]
> Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, le contrôle de stratégies de blocage sur Place Exchange si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange et mettre les boîtes aux lettres en blocage sur Place. 
  
Pour plus d’informations sur les stratégies de l’archivage fonctionne, notamment la hiérarchie des globale, de site et stratégies d’utilisateur, voir [planifier l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md). Pour plus d’informations sur la gestion des stratégies après le déploiement, voir [Gérer les stratégies d’archivage de Skype pour Business Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Stratégie globale

Lorsque vous déployez vos serveurs frontaux, Skype pour Business Server crée une stratégie globale pour l’archivage. Par défaut, l’archivage est désactivé dans la stratégie globale. Contrôle de la stratégie globale si l’archivage est activé pour les communications internes et externes pour votre déploiement entière, sauf si vous définissez des stratégies de site ou d’utilisateur, qui remplace la stratégie globale, ou si vous utilisez l’intégration de Microsoft Exchange pour tout ou partie des vos utilisateurs. Si vous utilisez l’intégration de Microsoft Exchange, la stratégie globale ne s’applique pas à tous les utilisateurs hébergés sur Exchange et mettre les boîtes aux lettres en blocage sur Place.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurer la stratégie globale pour l’archivage pour Skype pour les bases de données d’archivage Business Server

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Stratégie d’archivage**.
    
4. Dans la page **Stratégie d’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :
    
   - Dans **Nom**, si vous ne souhaitez pas utiliser le nom par défaut Global, spécifiez un nouveau nom pour la stratégie globale. 
    
   - Dans **Description**, fournissez les informations sur les nouveautés de la stratégie (par exemple, stratégie globale de *Nom_division* .
    
   - Afin de contrôler l’archivage des communications internes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Afin de contrôler l’archivage des communications externes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
## <a name="site-policies"></a>Stratégies de site

Vous pouvez activer ou désactiver l’archivage pour des sites spécifiques en créant une stratégie d’archivage pour chacun de ces sites. Une stratégie de site remplace la stratégie globale, mais les stratégies utilisateur remplacent les stratégies de site. Stratégies d’archivage s’appliquent uniquement si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous n’utilisez pas l’intégration de Microsoft Exchange, mais mettre les quelques utilisateurs qui ne sont pas hébergés sur Exchange et à leurs boîtes aux lettres en blocage sur Place.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Créer une stratégie d’archivage pour un site

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.
    
3. Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Stratégie d’archivage**.
    
    Pour plus d’informations sur les stratégies de l’archivage fonctionne, notamment la hiérarchie des globale, de site et stratégies d’utilisateur, voir [planifier l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Cliquez sur **Créer**, puis sur **Stratégie de site**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.
    
6. Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
   - Dans **Nom**, spécifiez le nom pour la stratégie de site. 
    
   - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de site pour Redmond).
    
   - Pour contrôler l’archivage des communications internes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour contrôler l’archivage des communications externes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
7. Cliquez sur **Valider**.
    
## <a name="user-policies"></a>Stratégies utilisateur

Vous pouvez activer ou désactiver l’archivage pour des utilisateurs spécifiques en créant et en configurant une stratégie d’archivage pour les utilisateurs, puis en appliquant la stratégie à des utilisateurs spécifiques ou à des groupes d’utilisateurs. Les stratégies utilisateur remplacent les stratégies globales ou de site. Stratégies d’archivage s’appliquent uniquement si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous n’utilisez pas l’intégration de Microsoft Exchange, mais mettre les quelques utilisateurs qui ne sont pas hébergés sur Exchange et à leurs boîtes aux lettres en blocage sur Place.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurer une stratégie d’archivage pour les utilisateurs hébergés sur Skype pour Business Server

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Stratégie d’archivage**.
    
4. Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.
    
5. Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
   - Dans **Nom**, spécifiez le nom de la stratégie utilisateur. 
    
   - Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie utilisateur pour le service juridique).
    
   - Pour contrôler l’archivage des communications internes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour contrôler l’archivage des communications externes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
Une stratégie utilisateur ne s’applique qu’aux utilisateurs auxquels vous affectez la stratégie.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Appliquer un Skype pour Business Server stratégie à un utilisateur d’archivage

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier les Skype pour utilisateur Business Server** sous **stratégie d’archivage**, sélectionnez la stratégie utilisateur d’archivage que vous souhaitez appliquer.
    
    > [!NOTE]
    > Le ** \<automatique\> ** paramètres s’appliquent les paramètres d’installation de serveur par défaut. Ces paramètres sont appliqués automatiquement par le serveur.
  
6. Cliquez sur **Valider**.
    

