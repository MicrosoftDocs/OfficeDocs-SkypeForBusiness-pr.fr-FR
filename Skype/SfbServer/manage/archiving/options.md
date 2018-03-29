---
title: Gestion des options d’archivage dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Résumé : Apprenez à configurer les options d’archivage de Skype pour Business Server 2015.'
ms.openlocfilehash: 29800fef7054cd0e82f203d2ad6ec1ed53251ca4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-options-in-skype-for-business-server-2015"></a>Gestion des options d’archivage dans Skype Entreprise Server 2015

**Résumé :** Apprenez à configurer les options d’archivage de Skype pour Business Server 2015.
  
Si l’archivage est initialement configuré au déploiement, vous pouvez modifier, ajouter et supprimer des configurations par la suite. Les options d’archivage déterminent : 
  
- l’activation ou la désactivation de l’archivage
    
- Archiver les sessions de messagerie instantanée
    
- Archiver les sessions de conférence Web
    
- Bloquer l’activité lorsque l’archivage n’est pas disponible
    
- Utiliser l’intégration à Exchange
    
- Configurer la purge et l’exportation des données
    
Vous pouvez préciser les options de configuration aux niveaux suivants :
  
- Configuration au niveau global qui est créée par défaut lorsque vous déployez Skype pour Business Server
    
- Configurations facultatives au niveau du site qui déterminent la mise en œuvre de l’archivage d’un site spécifique
    
- Configurations facultatives au niveau du pool qui spécifient comment l’archivage est implémentée pour un pool donné
    
Vous pouvez supprimer une configuration de site ou une configuration de pool, mais vous ne pouvez pas supprimer la configuration globale. Si vous supprimez la configuration globale, ses valeurs par défaut sont automatiquement rétablies. Pour plus d’informations sur la façon de configurations d’archivage sont mis en œuvre et la hiérarchie de l’archivage des configurations, reportez-vous à [planification d’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurer les options d’archivage à l’aide du panneau de configuration

Vous pouvez configurer les options d’archivage à l’aide du panneau de configuration comme suit :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Configuration d’archivage**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurer les options d’archivage à l’aide de Windows PowerShell

Vous pouvez également configurer les options d’archivage à l’aide des applets de commande de Windows PowerShell figurant dans le tableau ci-après. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, consultez [Skype pour Business Server 2015 Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Retourne des informations sur les paramètres de configuration d’archivage de votre organisation.  <br/> |
|Nouvelle-CsArchivingConfiguration  <br/> |Crée un nouveau jeu de paramètres pour la messagerie instantanée qui peuvent être utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer les messages instantanés qu’il n’est pas possible d’archiver.  <br/> |
|Supprimer-CsArchivingConfiguration  <br/> |Supprime la collection spécifiée de paramètres d’archivage utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer éventuellement tout message instantané ne pouvant pas être archivé.  <br/> |
|Ensemble-CsArchivingConfiguration  <br/> |Modifie une collection existante d’options de configuration d’archivage de la messagerie instantanée.  <br/> |