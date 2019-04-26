---
title: Configurer les options d’archivage pour Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer les options d’archivage initiales pour Skype pour Business Server. Vous définissez à l’origine des configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement.'
ms.openlocfilehash: 80501c01c4e05e0578685b42f8fb83b7faed6c59
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32236137"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Configurer les options d’archivage pour Skype pour Business Server
 
**Résumé :** Lisez cette rubrique pour savoir comment configurer les options d’archivage initiales pour Skype pour Business Server. Vous définissez à l’origine des configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement.
  
Pour configurer initiale de l’archivage des configurations, vous utilisez Skype pour Business Server Control Panel pour spécifier les éléments suivants :
  
- Configuration au niveau global qui est créée par défaut lorsque vous déployez Skype pour Business Server
    
- Configurations facultatives au niveau du site qui déterminent la mise en œuvre de l’archivage d’un site spécifique
    
- Configurations facultatives au niveau du pool qui spécifient comment l’archivage est implémenté pour un pool spécifique
    
Vous devez configurer les options pour définir les paramètres suivants :
  
- Activer ou désactiver l’archivage
    
- Archiver ou non les sessions de messagerie instantanée
    
- Archiver ou non les sessions de conférence Web
    
- Bloquer ou non l’activité lorsque l’archivage n’est pas disponible
    
- Utiliser ou non l’intégration d’Exchange
    
- Procédure de configuration de la purge et de l’exportation des données
    
> [!NOTE]
> Vous devez spécifier toutes les options appropriées avant d’activer l’archivage. 
  
Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment sur les options que vous pouvez spécifier et la hiérarchie des configurations, d’archivage voir [planifier l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md). Pour plus d’informations sur la gestion des configurations après le déploiement à l’aide du Panneau de configuration ou à l’aide de Windows PowerShell, voir [Gérer les options d’archivage dans Skype pour Business Server](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Configurer les options d’archivage au niveau global

Lorsque vous ajoutez l’archivage à votre topologie et que vous publiez la topologie, Skype pour Business Server crée une configuration globale pour l’archivage. Par défaut, aucune option d’archivage n’est activées dans la configuration globale. La configuration globale contrôle les options sont activées pour tout votre déploiement, sauf si vous définissez des configurations de site ou un pool, qui remplace la configuration globale.
  
Pour configurer les options d’archivage au niveau global
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Configuration de l’archivage**.
    
4. Sur la page **Configuration de l’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier le paramètre d’archivage - Global**, dans la zone de liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options suivantes :
    
   - **Désactiver l’archivage**
    
   - **Archiver les sessions de messagerie instantanée**
    
   - **Archiver les sessions de messagerie instantanée et de conférence web**
    
6. Également dans la page **Modifier un paramètre d’archivage - Global** , procédez comme suit :
    
   - Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.
    
   - Pour utiliser Microsoft Exchange Server pour stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .
    
   - Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
    
   - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
    
   - Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
7. Cliquez sur **Valider**.
    
## <a name="configure-site-level-archiving-options"></a>Configurer les options d’archivage au niveau du site

Vous pouvez préciser les options d’archivage d’un site spécifique. Une configuration de site ne remplace la configuration globale que pour le site spécifié dans la configuration du site. 
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Configuration de l’archivage**.
    
4. Sur la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du site**.
    
5. Dans **Sélectionner un site**, choisissez le site à configurer pour l’archivage.
    
6. Dans **Nouveau paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :
    
   - Afin d’activer l’archivage seulement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
   - Afin d’activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence Web**.
    
   - Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.
    
7. Par ailleurs, dans **Créer un paramètre d’archivage**, procédez comme suit :
    
   - Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
   - Pour utiliser Microsoft Exchange Server pour stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .
    
   - Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
    
   - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
    
   - Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
8. Cliquez sur **Valider**.
    
## <a name="configure-pool-level-archiving-options"></a>Configurer les options d’archivage au niveau du pool

Vous pouvez préciser les options d’archivage d’un pool spécifique. Une configuration de pool ne remplace la configuration globale et la configuration du site que pour le pool spécifié dans la configuration du pool.
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Configuration de l’archivage**.
    
4. Sur la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du pool**.
    
5. Dans **Sélectionner un service**, sélectionnez le pool à configurer pour l’archivage.
    
6. Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options d’archivage suivantes :
    
   - **Désactiver l’archivage**
    
   - **Archiver les sessions de messagerie instantanée**
    
   - **Archiver les sessions de messagerie instantanée et de conférence web**
    
7. Dans la page **Créer un paramètre d’archivage**, effectuez également l’opération suivante :
    
   - Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.
    
   - Pour utiliser Microsoft Exchange Server pour stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .
    
   - Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
    
   - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
    
   - Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
8. Cliquez sur **Valider**.
    

