---
title: Configurer des stratégies d’archivage pour Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer des stratégies d’archivage initiales pour Skype Entreprise Server utilisateurs.'
ms.openlocfilehash: 6e50f40aa91a26af8833ec7f330b14a9354d6b8b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399428"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Configurer des stratégies d’archivage pour Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment configurer des stratégies d’archivage initiales pour Skype Entreprise Server utilisateurs.
  
Dans Skype Entreprise Server, vous utilisez des stratégies pour activer et désactiver l’archivage des communications internes et externes pour les utilisateurs qui sont Skype Entreprise Server. Les voici :
  
- Stratégie globale créée par défaut lorsque vous déployez Skype Entreprise Server
    
- Stratégies facultatives au niveau du site qui spécifient la façon dont l’archivage est implémenté pour un site spécifique
    
- Stratégies facultatives au niveau de l’utilisateur qui spécifient la façon dont l’archivage est implémenté pour des utilisateurs spécifiques
    
Vous définissez initialement les stratégies d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des stratégies après le déploiement. Dans Skype Entreprise Server de contrôle d’archivage, vous pouvez utiliser **la page Stratégie** d’archivage du  groupe Archivage et surveillance pour gérer les stratégies au niveau global, du site et de l’utilisateur.
  
> [!NOTE]
> Pour contrôler l’implémentation de l’archivage, vous devez spécifier des options, telles que l’archivage de la messagerie instantanée ou de la conférence, l’utilisation du mode critique et les options de  purge. Par défaut, aucune option n’est activée dans la configuration d’archivage globale ou dans toute configuration d’archivage de site ou de pool. Vous devez spécifier toutes les options appropriées avant d’activer l’archivage pour les communications internes ou externes. Pour plus d’informations, [voir Configure archiving options for Skype Entreprise Server](configure-archiving-options.md). 
  
> [!NOTE]
> Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de Exchange In-Place Hold contrôlent si l’archivage est activé pour les utilisateurs qui sont Exchange et dont les boîtes aux lettres sont mises en In-Place. 
  
Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie des stratégies globales, de site et utilisateur, voir Planifier l’archivage [dans Skype Entreprise Server](../../plan-your-deployment/archiving/archiving.md). Pour plus d’informations sur la gestion des stratégies après le déploiement, voir Gérer les stratégies [d’archivage dans Skype Entreprise Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Stratégie globale

Lorsque vous déployez vos serveurs frontux, Skype Entreprise Server crée une stratégie globale pour l’archivage. Par défaut, l’archivage est désactivé dans la stratégie globale. La stratégie globale contrôle si l’archivage est activé pour les communications internes et externes pour l’ensemble de votre déploiement, sauf si vous avez installé des stratégies de site ou d’utilisateur, qui remplacent la stratégie globale, ou si vous utilisez l’intégration de Microsoft Exchange pour une partie ou la totalité de vos utilisateurs. Si vous utilisez l’intégration microsoft Exchange, la stratégie globale ne s’applique pas aux utilisateurs qui sont Exchange et dont les boîtes aux lettres sont mises en In-Place en attente.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurer la stratégie globale pour l’archivage des bases Skype Entreprise Server d’archivage

1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.
    
4. Dans la page **Stratégie d’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :
    
   - Dans **Nom**, si vous ne souhaitez pas utiliser le nom par défaut Global, spécifiez un nouveau nom pour la stratégie globale. 
    
   - Dans **Description**, fournissez des informations sur la stratégie (par exemple, stratégie globale pour  *divisionName*  .
    
   - Afin de contrôler l’archivage des communications internes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Afin de contrôler l’archivage des communications externes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
## <a name="site-policies"></a>Stratégies de site

Vous pouvez activer ou désactiver l’archivage pour des sites spécifiques en créant une stratégie d’archivage pour chacun de ces sites. Une stratégie de site remplace la stratégie globale, mais les stratégies utilisateur remplacent les stratégies de site. Les stratégies d’archivage s’appliquent uniquement si vous n’utilisez pas l’intégration Microsoft Exchange ou, si vous utilisez l’intégration de Microsoft Exchange, mais que certains utilisateurs ne sont pas dossés sur Exchange et dont les boîtes aux lettres sont mises en In-Place.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Créer une stratégie d’archivage pour un site

1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.
    
    Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie des stratégies globales, de site et utilisateur, voir Planifier l’archivage [dans Skype Entreprise Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Cliquez sur **Nouveau**, puis sur **Stratégie de site**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.
    
6. Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
   - Dans **Nom**, spécifiez le nom pour la stratégie de site. 
    
   - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de site pour Redmond).
    
   - Pour contrôler l’archivage des communications internes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour contrôler l’archivage des communications externes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
7. Cliquez sur **Valider**.
    
## <a name="user-policies"></a>Stratégies utilisateur

Vous pouvez activer ou désactiver l’archivage pour des utilisateurs spécifiques en créant et en configurant une stratégie d’archivage pour les utilisateurs, puis en appliquant la stratégie à des utilisateurs ou groupes d’utilisateurs spécifiques. Les stratégies utilisateur remplacent les stratégies globales ou de site. Les stratégies d’archivage s’appliquent uniquement si vous n’utilisez pas l’intégration Microsoft Exchange ou, si vous utilisez l’intégration de Microsoft Exchange, mais que certains utilisateurs ne sont pas dossés sur Exchange et dont les boîtes aux lettres sont mises en In-Place.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurer une stratégie d’archivage pour les utilisateurs Skype Entreprise Server

1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.
    
4. Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.
    
5. Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
   - Dans **Nom**, spécifiez le nom de la stratégie utilisateur. 
    
   - Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie utilisateur pour le service juridique).
    
   - Pour contrôler l’archivage des communications internes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour contrôler l’archivage des communications externes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
Une stratégie utilisateur ne s’applique qu’aux utilisateurs auxquels vous affectez la stratégie.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Appliquer une stratégie Skype Entreprise Server’archivage à un utilisateur

1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier Skype Entreprise Server utilisateur sous** stratégie d’archivage **,** sélectionnez la stratégie utilisateur d’archivage à appliquer.
    
    > [!NOTE]
    > Les paramètres **\<Automatic\>** appliquent les paramètres d’installation du serveur par défaut. Ces paramètres sont appliqués automatiquement par le serveur.
  
6. Cliquez sur **Valider**.
    

