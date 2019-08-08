---
title: Configuration de stratégies d’archivage pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Résumé: cette rubrique vous explique comment configurer les stratégies d’archivage initial pour les utilisateurs de Skype entreprise Server.'
ms.openlocfilehash: 4e1bf5d713201604df18db9d63c2057bfa5bb4e8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234549"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Configuration de stratégies d’archivage pour Skype entreprise Server
 
**Résumé:** Pour plus d’informations sur la configuration des stratégies d’archivage initial pour les utilisateurs de Skype entreprise Server, reportez-vous à cette rubrique.
  
Dans Skype entreprise Server, vous utilisez des stratégies pour activer et désactiver l’archivage des communications internes et des communications externes pour les utilisateurs qui sont hébergés sur Skype entreprise Server. Il s’agit notamment de ce qui suit :
  
- Politique globale créée par défaut lors du déploiement de Skype entreprise Server
    
- Stratégies facultatives au niveau site qui définissent de quelle manière l’archivage est implémenté pour un site spécifique
    
- Stratégies de niveau utilisateur facultatives qui spécifient la façon dont l’archivage est implémenté pour des utilisateurs spécifiques
    
Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement. Dans le panneau de configuration Skype entreprise Server, vous pouvez utiliser la page de **stratégie** d’archivage du groupe **archivage et surveillance** pour gérer les stratégies aux niveaux global, site et utilisateur.
  
> [!NOTE]
> Pour contrôler l’implémentation de l’archivage, vous devez définir certaines options, notamment spécifier si les messages instantanés ou les conférences doivent être archivés, si le mode critique est utilisé et les options de vidage. Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans la configuration de l’archivage de site ou de pool. Vous devez définir toutes les options appropriées avant d’activer l’archivage des communications internes ou externes. Pour plus d’informations, reportez-vous à [configurer les options d’archivage de Skype entreprise Server](configure-archiving-options.md). 
  
> [!NOTE]
> Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, Exchange stratégies de conservation inaltérable déterminent si l’archivage est activé pour les utilisateurs hébergés sur Exchange et que leurs boîtes aux lettres sont placées dans la conservation inaltérable. 
  
Pour plus d’informations sur le fonctionnement des stratégies d’archivage, y compris la hiérarchie des stratégies globales, de site et d’utilisateur, reportez-vous à la rubrique [planification de l’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md). Pour plus d’informations sur la gestion des stratégies après le déploiement, voir [gérer les stratégies d’archivage dans Skype entreprise Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Stratégie globale

Lorsque vous déployez vos serveurs frontaux, Skype entreprise Server crée une stratégie globale d’archivage. Par défaut, l’archivage est désactivé dans la stratégie globale. La stratégie globale contrôle l’activation de l’archivage pour les communications internes et externes pour votre déploiement complet, sauf si vous configurez des stratégies de site ou d’utilisateur qui remplacent la stratégie globale ou si vous utilisez l’intégration de Microsoft Exchange pour tout ou partie de vos utilisateurs. Si vous utilisez l’intégration de Microsoft Exchange, la stratégie global ne s’applique pas aux utilisateurs hébergés sur Exchange et ayant recours à des boîtes aux lettres en conservation inaltérable.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurer la politique globale de l’archivage pour les bases de données d’archivage de Skype entreprise Server

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie**d’archivage.
    
4. Dans la page **Stratégie d’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :
    
   - Dans **Nom**, si vous ne souhaitez pas utiliser le nom par défaut Global, spécifiez un nouveau nom pour la stratégie globale. 
    
   - Dans **Description**, entrez les informations relatives à la stratégie (par exemple, stratégie générale pour *divisionName* ).
    
   - Afin de contrôler l’archivage des communications internes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Afin de contrôler l’archivage des communications externes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
## <a name="site-policies"></a>Stratégies de site

Vous pouvez activer ou désactiver l’archivage pour des sites spécifiques en créant une stratégie d’archivage pour chacun de ces sites. Une stratégie de site remplace la stratégie globale, mais les stratégies utilisateur remplacent les stratégies de site. Les stratégies d’archivage ne s’appliquent que si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous utilisez l’intégration de Microsoft Exchange, mais que certains utilisateurs ne sont pas hébergés sur Exchange et que leurs boîtes aux lettres sont placées sur le blocage sur place.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Créer une stratégie d’archivage pour un site

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie**d’archivage.
    
    Pour plus d’informations sur le fonctionnement des stratégies d’archivage, y compris la hiérarchie des stratégies globales, de site et d’utilisateur, reportez-vous à la rubrique [planification de l’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Cliquez sur **Créer**, puis sur **Stratégie de site**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.
    
6. Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
   - Dans **Nom**, spécifiez le nom pour la stratégie de site. 
    
   - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de site pour Redmond).
    
   - Pour contrôler l’archivage des communications internes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour contrôler l’archivage des communications externes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
7. Cliquez sur **Valider**.
    
## <a name="user-policies"></a>Stratégies utilisateur

Vous pouvez activer ou désactiver l’archivage pour des utilisateurs spécifiques en créant et en configurant une stratégie d’archivage pour les utilisateurs, puis en appliquant la stratégie à des utilisateurs spécifiques ou à des groupes d’utilisateurs. Les stratégies utilisateur remplacent les stratégies globales ou de site. Les stratégies d’archivage ne s’appliquent que si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous utilisez l’intégration de Microsoft Exchange, mais que certains utilisateurs ne sont pas hébergés sur Exchange et que leurs boîtes aux lettres sont placées sur le blocage sur place.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurer une stratégie d’archivage pour les utilisateurs hébergés sur Skype entreprise Server

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie**d’archivage.
    
4. Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.
    
5. Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
   - Dans **Nom**, spécifiez le nom de la stratégie utilisateur. 
    
   - Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie utilisateur pour le service juridique).
    
   - Pour contrôler l’archivage des communications internes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour contrôler l’archivage des communications externes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
Une stratégie utilisateur ne s’applique qu’aux utilisateurs auxquels vous affectez la stratégie.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Appliquer une stratégie d’archivage de Skype entreprise Server à un utilisateur

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **modifier l’utilisateur de Skype entreprise Server** sous **stratégie**d’archivage, sélectionnez la stratégie de l’utilisateur d’archivage que vous voulez appliquer.
    
    > [!NOTE]
    > Les ** \<paramètres\> automatiques** appliquent les paramètres d’installation du serveur par défaut. Ces paramètres sont appliqués automatiquement par le serveur.
  
6. Cliquez sur **Valider**.
    

