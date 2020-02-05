---
title: Configurer les options d’archivage de Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Résumé : cette rubrique vous explique comment configurer les options d’archivage initial pour Skype entreprise Server. Vous définissez initialement des configurations d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement.'
ms.openlocfilehash: f663b310d4c82594976f2f0fc99b8ddd9baf035f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769197"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Configurer les options d’archivage de Skype entreprise Server
 
**Résumé :** Pour plus d’informations sur la configuration des options d’archivage initial de Skype entreprise Server, reportez-vous à cette rubrique. Vous définissez initialement des configurations d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement.
  
Pour configurer les configurations d’archivage initiales, utilisez le panneau de configuration Skype entreprise Server pour spécifier les éléments suivants :
  
- Configuration de niveau global créée par défaut lors du déploiement de Skype entreprise Server
    
- Configurations facultatives au niveau du site qui déterminent la mise en œuvre de l’archivage d’un site spécifique
    
- Configurations facultatives de niveau de pool qui spécifient la façon dont l’archivage est implémenté pour un pool spécifique
    
Vous devez configurer les options pour définir les paramètres suivants :
  
- Activer ou désactiver l’archivage
    
- Archiver ou non les sessions de messagerie instantanée
    
- Archiver ou non les sessions de conférence Web
    
- Bloquer ou non l’activité lorsque l’archivage n’est pas disponible
    
- Utiliser ou non l’intégration d’Exchange
    
- Procédure de configuration de la purge et de l’exportation des données
    
> [!NOTE]
> Vous devez spécifier toutes les options appropriées avant d’activer l’archivage. 
  
Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, reportez-vous à la rubrique [planification de l’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md). Pour plus d’informations sur la gestion des configurations après le déploiement à l’aide du panneau de configuration ou de Windows PowerShell, reportez-vous à la rubrique [gérer les options d’archivage de Skype entreprise Server](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Configurer les options d’archivage au niveau global

Lorsque vous ajoutez l’archivage à votre topologie et que vous publiez la topologie, Skype entreprise Server crée une configuration globale pour l’archivage. Par défaut, aucune option d’archivage n’est activée dans la configuration globale. La configuration globale détermine quelles options sont activées pour votre déploiement complet, sauf si vous configurez des configurations de site ou de pool qui remplacent la configuration globale.
  
Pour configurer les options d’archivage au niveau global
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.
    
4. Sur la page **Configuration de l’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier le paramètre d’archivage - Global**, dans la zone de liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options suivantes :
    
   - **Désactiver l’archivage**
    
   - **Archiver les sessions de messagerie instantanée**
    
   - **Archiver les sessions de messagerie instantanée et de conférence web**
    
6. Par ailleurs, dans la page **modifier les paramètres d’archivage-général** , procédez comme suit :
    
   - Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.
    
   - Pour utiliser Microsoft Exchange Server pour stocker des données d’archivage, activez la case à cocher **intégration Microsoft Exchange** .
    
   - Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
    
   - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
    
   - Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
7. Cliquez sur **Valider**.
    
## <a name="configure-site-level-archiving-options"></a>Configurer les options d’archivage au niveau du site

Vous pouvez préciser les options d’archivage d’un site spécifique. Une configuration de site ne remplace la configuration globale que pour le site spécifié dans la configuration du site. 
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.
    
4. Sur la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du site**.
    
5. Dans **Sélectionner un site**, choisissez le site à configurer pour l’archivage.
    
6. Dans **Nouveau paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :
    
   - Afin d’activer l’archivage seulement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
   - Afin d’activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence Web**.
    
   - Afin de désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.
    
7. Par ailleurs, dans **Créer un paramètre d’archivage**, procédez comme suit :
    
   - Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
   - Pour utiliser Microsoft Exchange Server pour stocker des données d’archivage, activez la case à cocher **intégration Microsoft Exchange** .
    
   - Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
    
   - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
    
   - Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
8. Cliquez sur **Valider**.
    
## <a name="configure-pool-level-archiving-options"></a>Configurer les options d’archivage au niveau du pool

Vous pouvez préciser les options d’archivage d’un pool spécifique. Une configuration de pool ne remplace la configuration globale et la configuration du site que pour le pool spécifié dans la configuration du pool.
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.
    
4. Sur la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis sur **Configuration du pool**.
    
5. Dans **Sélectionner un service**, sélectionnez le pool à configurer pour l’archivage.
    
6. Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options d’archivage suivantes :
    
   - **Désactiver l’archivage**
    
   - **Archiver les sessions de messagerie instantanée**
    
   - **Archiver les sessions de messagerie instantanée et de conférence web**
    
7. Dans la page **Créer un paramètre d’archivage**, effectuez également l’opération suivante :
    
   - Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.
    
   - Pour utiliser Microsoft Exchange Server pour stocker des données d’archivage, activez la case à cocher **intégration Microsoft Exchange** .
    
   - Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
    
   - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
    
   - Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
8. Cliquez sur **Valider**.
    

