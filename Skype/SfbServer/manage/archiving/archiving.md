---
title: Gérer l’archivage dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Résumé : Découvrez comment gérer l’archivage des Skype Entreprise Server.'
ms.openlocfilehash: bdb373bf723e586cbc7222cd2559b87f4c72381e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856791"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Gérer l’archivage dans Skype Entreprise Server

**Résumé :** Découvrez comment gérer l’archivage des Skype Entreprise Server.
  
Lorsque vous déployez l’archivage pour votre organisation, vous spécifiez la configuration initiale pendant le déploiement. Toutefois, il se peut que vous vouliez modifier la façon dont vous implémentez la prise en charge de l’archivage pour la gestion quotidienne ou pour répondre aux nouvelles exigences de votre organisation. Par exemple, vous devrez peut-être configurer la prise en charge de l’archivage différemment pour un site spécifique, un pool spécifique ou des utilisateurs spécifiques au sein de votre organisation. Pour les utilisateurs Skype Entreprise Server, vous devez créer et personnaliser les options de configuration d’archivage et les stratégies utilisateur. 
  
Avant de lire cette rubrique, assurez-vous que vous connaissez les informations de la rubrique Planifier l’archivage dans [Skype Entreprise Server](../../plan-your-deployment/archiving/archiving.md) et Déployer l’archivage [pour Skype Entreprise Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies Exchange contrôlent si l’archivage est activé pour les utilisateurs qui sont Exchange et dont les boîtes aux lettres sont mises en In-Place archive. Pour plus d’informations, voir [Plan for archiving in Skype Entreprise Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype Entreprise Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Options de configuration de l’archivage

Les options de configuration de l’archivage spécifient s’il faut :
  
- Activation ou désactivation de l’archivage
    
- Archiver les sessions de messagerie instantanée
    
- Archiver les sessions de conférence web
    
- Bloquer l’activité lorsque l’archivage n’est pas disponible
    
- Utiliser l’intégration Exchange des données
    
- Configurer le purgement et l’exportation des données
    
Ces options peuvent être définies au niveau global, du site ou du pool. Pour plus d’informations, [voir Gérer les options d’archivage dans Skype Entreprise Server](options.md).
  
## <a name="archiving-policies"></a>Stratégies d’archivage

Les stratégies d’archivage déterminent s’il faut archiver les données suivantes :
  
- Communications internes
    
- Communications externes
    
Ces stratégies peuvent être définies au niveau global, du site ou de l’utilisateur. Pour plus d’informations, [voir Gérer les stratégies d’archivage dans Skype Entreprise Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Gérer l’archivage à l’aide du Panneau de Windows PowerShell

Vous pouvez gérer l’archivage à l’aide du Panneau de Windows PowerShell. Le tableau suivant récapitule les cmdlets disponibles pour vous aider à gérer l’archivage. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, [voir Skype Entreprise Server Management Shell.](../management-shell.md) 


|**Applet de commande**|**Description**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exporte les enregistrements qui ont été stockés dans la base de données Skype Entreprise Server’archivage.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Retourne des informations sur les paramètres de configuration de l’archivage dans votre organisation.  <br/> |
|Get-CsArchivingPolicy  <br/> |Retourne des informations sur les stratégies d’archivage de votre organisation pour les communications internes et externes.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Affecte des stratégies d’archivage de session de messagerie instantanée à des utilisateurs ou à des ensembles d’utilisateurs. Ces stratégies vous donnent la possibilité d’archiver les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes, et/ou d’archiver toutes les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes et des partenaires extérieurs.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Purge manuellement les enregistrements de la base de données d’archivage.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crée un nouvel ensemble de paramètres de messagerie instantanée, qui peuvent être utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer les messages instantanés qui ne peuvent pas être archivés.  <br/> |
|New-CsArchivingPolicy  <br/> |Crée des stratégies d’archivage des sessions de messagerie instantanée. Ces stratégies permettent d’archiver toutes les sessions entre les utilisateurs internes et/ou d’archiver toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires externes.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Supprime la collection spécifiée de paramètres d’archivage utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer éventuellement les messages instantanés qui ne peuvent pas être archivés.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Supprime la stratégie d’archivage de messagerie instantanée spécifiée qui détermine si Skype Entreprise Server enregistre automatiquement toutes les sessions de messagerie instantanée qui ont lieu entre les utilisateurs internes et/ou toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires fédérés.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifie une collection existante d’options de configuration de l’archivage de la messagerie instantanée.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifie une stratégie d’archivage de messagerie instantanée existante. Une stratégie d’archivage vous permet d’archiver toutes les sessions de messagerie instantanée et les conférences qui ont lieu entre des utilisateurs internes ; vous pouvez également archiver des sessions qui ont lieu entre des utilisateurs internes et des partenaires fédérés.  <br/> |
|Set-CsArchivingServer  <br/> |Permet de spécifier un nouvel emplacement de base de données pour un ou plusieurs serveurs d’archivage.  <br/> |
   

