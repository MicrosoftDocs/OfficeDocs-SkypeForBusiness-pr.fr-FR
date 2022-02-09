---
title: Configurer les options d’archivage pour Skype Entreprise Server
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
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer les options d’archivage initiales pour Skype Entreprise Server. Vous définissez initialement les configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement.'
ms.openlocfilehash: 953bf4a5a353001993e8aee51b5bd21ac8f377b5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396076"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Configurer les options d’archivage pour Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment configurer les options d’archivage initiales pour Skype Entreprise Server. Vous définissez initialement les configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement.
  
Pour configurer les configurations d’archivage initiales, utilisez Skype Entreprise Server panneau de configuration pour spécifier les éléments suivants :
  
- Configuration au niveau global créée par défaut lorsque vous déployez Skype Entreprise Server
    
- Configurations facultatives au niveau du site qui spécifient comment l’archivage est implémenté pour un site spécifique
    
- Configurations facultatives au niveau du pool qui spécifient comment l’archivage est implémenté pour un pool spécifique
    
Vous devez configurer les options suivantes :
  
- Activer ou désactiver l’archivage
    
- S’il faut archiver les sessions de messagerie instantanée
    
- S’il faut archiver les sessions de conférence web
    
- S’il faut bloquer l’activité lorsque l’archivage n’est pas disponible
    
- S’il faut utiliser Exchange’intégration
    
- Comment configurer la purge et l’exportation des données
    
> [!NOTE]
> Vous devez spécifier toutes les options appropriées avant d’activer l’archivage. 
  
Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir Planifier l’archivage [dans Skype Entreprise Server](../../plan-your-deployment/archiving/archiving.md). Pour plus d’informations sur la gestion des configurations après le déploiement à l’aide du Panneau de configuration ou de Windows PowerShell, voir Gérer les options d’archivage [dans Skype Entreprise Server](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Configurer les options d’archivage au niveau global

Lorsque vous ajoutez l’archivage à votre topologie et publiez la topologie, Skype Entreprise Server crée une configuration globale pour l’archivage. Par défaut, aucune option d’archivage n’est activée dans la configuration globale. La configuration globale contrôle les options activées pour l’ensemble de votre déploiement, sauf si vous avez installé des configurations de site ou de pool, qui remplacent la configuration globale.
  
Pour configurer les options d’archivage au niveau global :
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Dans la page **Configuration de l’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier le paramètre d’archivage - Global**, dans la zone de liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options suivantes :
    
   - **Désactiver l’archivage**
    
   - **Archiver les sessions de messagerie instantanée**
    
   - **Archiver les sessions de messagerie instantanée et de conférence web**
    
6. Dans la page **Modifier le paramètre d’archivage - Global** , vous pouvez également :
    
   - Pour bloquer toute activité lorsque l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
   - Pour utiliser Microsoft Exchange Server stocker les données d’archivage, cliquez sur la case à **cocher** Intégration Exchange Microsoft.
    
   - Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
    
   - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.
    
   - Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
7. Cliquez sur **Valider**.
    
## <a name="configure-site-level-archiving-options"></a>Configurer les options d’archivage au niveau du site

Vous pouvez spécifier des options d’archivage pour un site spécifique. Une configuration de site remplace la configuration globale, mais uniquement pour le site spécifié dans la configuration du site. 
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Dans la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du site**.
    
5. Dans **Sélectionner un site**, choisissez le site à configurer pour l’archivage.
    
6. Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :
    
   - Afin d’activer l’archivage uniquement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
   - Afin d’activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée / conférence Web**.
    
   - Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.
    
7. Dans **Créer un paramètre d’archivage**, procédez comme suit :
    
   - Pour bloquer toute activité quand l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
   - Pour utiliser Microsoft Exchange Server stocker les données d’archivage, cliquez sur la case à **cocher** Intégration Exchange Microsoft.
    
   - Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
    
   - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.
    
   - Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
8. Cliquez sur **Valider**.
    
## <a name="configure-pool-level-archiving-options"></a>Configurer les options d’archivage au niveau du pool

Vous pouvez spécifier des options d’archivage pour un pool spécifique. La configuration d’un pool remplace la configuration globale et la configuration d’un site, mais uniquement pour le pool spécifié dans la configuration du pool.
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Dans la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du pool**.
    
5. Dans **Sélectionner un service**, sélectionnez le pool à configurer pour l’archivage.
    
6. Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options d’archivage suivantes :
    
   - **Désactiver l’archivage**
    
   - **Archiver les sessions de messagerie instantanée**
    
   - **Archiver les sessions de messagerie instantanée et de conférence web**
    
7. Dans la page **Créer un paramètre d’archivage**, effectuez également l’opération suivante :
    
   - Pour bloquer toute activité lorsque l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
   - Pour utiliser Microsoft Exchange Server stocker les données d’archivage, cliquez sur la case à **cocher** Intégration Exchange Microsoft.
    
   - Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
    
   - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.
    
   - Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
8. Cliquez sur **Valider**.
    

