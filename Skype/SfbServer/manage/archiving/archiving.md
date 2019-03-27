---
title: Gérer l’archivage dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Résumé : Découvrez comment gérer l’archivage pour Skype pour Business Server.'
ms.openlocfilehash: 19d8d7eb6a2cd92bb4132d5dfe7703995b1056b9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875235"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Gérer l’archivage dans Skype pour Business Server

**Résumé :** Découvrez comment gérer l’archivage pour Skype pour Business Server.
  
Quand vous déployez l’archivage pour votre organisation, vous devez spécifier la configuration initiale durant le déploiement. Cependant, vous pouvez être amené à modifier la façon dont vous implémentez la prise en charge de l’archivage pour la gestion quotidienne ou pour répondre aux nouvelles exigences de votre organisation. Par exemple, vous pouvez être amené à configurer une prise en charge distincte de l’archivage pour un site, un pool ou des utilisateurs spécifiques au sein de votre organisation. Pour les utilisateurs hébergés sur Skype pour Business Server, cela par la création et la personnalisation des options de configuration d’archivage et les stratégies utilisateur. 
  
Avant de lire cette rubrique, assurez-vous que vous êtes familiarisé avec les informations de [planification pour l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md) et de [déployer l’archivage pour Skype pour Business Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Si vous avez activé l’intégration Microsoft Exchange pour votre déploiement, les stratégies Exchange vérifient que l’archivage est activé pour les utilisateurs hébergés sur Exchange et dont les boîtes aux lettres sont placées en conservation inaltérable. Pour plus d’informations, voir [planifier l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md) et [configurer l’intégration avec le stockage Exchange pour Skype pour Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Options de configuration de l’archivage

Les options de configuration l’archivage déterminent s’il faut :
  
- l’activation ou la désactivation de l’archivage
    
- Archiver les sessions de messagerie instantanée
    
- Archiver les sessions de conférence Web
    
- Bloquer l’activité lorsque l’archivage n’est pas disponible
    
- Utiliser l’intégration à Exchange
    
- Configurer la purge et l’exportation des données
    
Ces options peuvent être définies au niveau global, site ou pool. Pour plus d’informations, voir [Gérer les options d’archivage dans Skype pour Business Server](options.md).
  
## <a name="archiving-policies"></a>Stratégie d’archivage

Stratégies d’archivage de déterminent si vous souhaitez archiver les éléments suivants :
  
- Communications internes
    
- Communications externes
    
Ces stratégies peuvent être définies au niveau global, site ou pool. Pour plus d’informations, voir [Gérer les stratégies d’archivage de Skype pour Business Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Gérer l’archivage en utilisant le Panneau de configuration ou Windows PowerShell

Vous pouvez gérer l’archivage en utilisant le Panneau de configuration ou Windows PowerShell. Le tableau suivant récapitule les applets de commande disponibles pour vous aider à gérer l’archivage. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, voir [Skype pour Business Server Management Shell](../management-shell.md). 


|**Applet de commande**|**Description**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exporte les enregistrements qui ont été stockées dans le Skype pour la base de données d’archivage de serveur Business.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Retourne des informations sur les paramètres de configuration d’archivage de votre organisation.  <br/> |
|Get-CsArchivingPolicy  <br/> |Renvoie des informations sur les stratégies d’archivage de votre organisation pour les communications internes et externes.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Affecte des stratégies d’archivage de session de messagerie instantanée à des utilisateurs ou à un groupe d’utilisateurs. Ces stratégies vous donnent la possibilité d’archiver les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes, et/ou d’archiver toutes les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes et des partenaires extérieurs.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Purge manuellement les enregistrements de la base de données d’archivage.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crée un nouveau jeu de paramètres pour la messagerie instantanée qui peuvent être utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer les messages instantanés qu’il n’est pas possible d’archiver.  <br/> |
|New-CsArchivingPolicy  <br/> |Crée des stratégies d’archivage des sessions de messagerie instantanée. Ces stratégies permettent d’archiver toutes les sessions entre les utilisateurs internes et/ou d’archiver toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires externes.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Supprime la collection spécifiée de paramètres d’archivage utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer éventuellement tout message instantané ne pouvant pas être archivé.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Supprime le spécifié messagerie instantanée (MI) qui détermine si Skype pour Business Server doit enregistrer automatiquement toutes les sessions de messagerie instantanée qui ont lieu entre les utilisateurs internes et/ou toutes les sessions de messagerie instantanée entre utilisateurs internes et des partenaires fédérés stratégie d’archivage.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifie une collection existante d’options de configuration d’archivage de la messagerie instantanée.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifie une existante la messagerie instantanée (MI) stratégie d’archivage. Une stratégie d’archivage vous donne la possibilité d’archiver tous les sessions de messagerie instantanée et les conférences qui ont lieu entre les utilisateurs internes ; Vous pouvez également archiver les sessions qui ont lieu entre les utilisateurs internes et des partenaires fédérés.  <br/> |
|Set-CsArchivingServer  <br/> |Permet de spécifier un nouvel emplacement de base de données pour un ou plusieurs serveurs d’archivage.  <br/> |
   

