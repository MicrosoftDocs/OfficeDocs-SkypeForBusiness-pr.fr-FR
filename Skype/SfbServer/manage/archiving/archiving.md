---
title: Gestion de l’archivage dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Résumé : Découvrez comment gérer l’archivage de Skype entreprise Server.'
ms.openlocfilehash: 46b0937a00f289ad5383d3bb1a4acf890bf48390
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818996"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Gestion de l’archivage dans Skype entreprise Server

**Résumé :** Découvrez comment gérer l’archivage de Skype entreprise Server.
  
Quand vous déployez l’archivage pour votre organisation, vous devez spécifier la configuration initiale durant le déploiement. Cependant, vous pouvez être amené à modifier la façon dont vous implémentez la prise en charge de l’archivage pour la gestion quotidienne ou pour répondre aux nouvelles exigences de votre organisation. Par exemple, vous pouvez être amené à configurer une prise en charge distincte de l’archivage pour un site, un pool ou des utilisateurs spécifiques au sein de votre organisation. Pour les utilisateurs hébergés sur Skype entreprise Server, procédez ainsi en créant et en personnalisant les options de configuration de l’archivage et les stratégies utilisateur. 
  
Avant de lire ce sujet, assurez-vous que vous êtes familiarisé avec les informations fournies dans [plan pour l’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md) et [déploiement de l’archivage pour Skype entreprise Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Si vous avez activé l’intégration Microsoft Exchange pour votre déploiement, les stratégies Exchange vérifient que l’archivage est activé pour les utilisateurs hébergés sur Exchange et dont les boîtes aux lettres sont placées en conservation inaltérable. Pour plus d’informations, reportez-vous à la rubrique [planification de l’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md) et configuration de l' [intégration avec le stockage Exchange pour Skype entreprise Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Options de configuration de l’archivage

Les options de configuration l’archivage déterminent s’il faut :
  
- l’activation ou la désactivation de l’archivage
    
- Archiver les sessions de messagerie instantanée
    
- Archiver les sessions de conférence Web
    
- Bloquer l’activité lorsque l’archivage n’est pas disponible
    
- Utiliser l’intégration à Exchange
    
- Configurer la purge et l’exportation des données
    
Ces options peuvent être définies au niveau global, site ou pool. Pour plus d’informations, reportez-vous à [gérer les options d’archivage dans Skype entreprise Server](options.md).
  
## <a name="archiving-policies"></a>Stratégie d’archivage

Les stratégies d’archivage déterminent s’il convient d’archiver les éléments suivants :
  
- Communications internes
    
- Communications externes
    
Ces stratégies peuvent être définies au niveau global, site ou pool. Pour plus d’informations, reportez-vous à [gérer les stratégies d’archivage dans Skype entreprise Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Gérer l’archivage en utilisant le Panneau de configuration ou Windows PowerShell

Vous pouvez gérer l’archivage en utilisant le Panneau de configuration ou Windows PowerShell. Le tableau suivant récapitule les applets de commande disponibles pour vous aider à gérer l’archivage. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, reportez-vous à la rubrique [Skype entreprise Server Management Shell](../management-shell.md). 


|**Applet de commande**|**Description**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exporte les enregistrements stockés dans la base de données d’archivage de Skype entreprise Server.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Retourne des informations sur les paramètres de configuration d’archivage de votre organisation.  <br/> |
|Get-CsArchivingPolicy  <br/> |Renvoie des informations sur les stratégies d’archivage de votre organisation pour les communications internes et externes.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Affecte des stratégies d’archivage de session de messagerie instantanée à des utilisateurs ou à un groupe d’utilisateurs. Ces stratégies vous donnent la possibilité d’archiver les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes, et/ou d’archiver toutes les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes et des partenaires extérieurs.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Purge manuellement les enregistrements de la base de données d’archivage.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crée un nouveau jeu de paramètres pour la messagerie instantanée qui peuvent être utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer les messages instantanés qu’il n’est pas possible d’archiver.  <br/> |
|New-CsArchivingPolicy  <br/> |Crée des stratégies d’archivage des sessions de messagerie instantanée. Ces stratégies permettent d’archiver toutes les sessions entre les utilisateurs internes et/ou d’archiver toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires externes.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Supprime la collection spécifiée de paramètres d’archivage utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer éventuellement tout message instantané ne pouvant pas être archivé.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Supprime la stratégie d’archivage de messagerie instantanée spécifiée qui détermine si Skype entreprise Server enregistre automatiquement toutes les sessions de messagerie instantanée qui se produisent entre les utilisateurs internes et/ou toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires fédérés.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifie une collection existante d’options de configuration d’archivage de la messagerie instantanée.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifie une stratégie d’archivage de messagerie instantanée existante. Une stratégie d’archivage vous donne la possibilité d’archiver toutes les sessions et conférences de messagerie instantanée qui se produisent entre les utilisateurs internes ; vous pouvez également archiver des sessions qui interviennent entre des utilisateurs internes et des partenaires fédérés.  <br/> |
|Set-CsArchivingServer  <br/> |Permet de spécifier un nouvel emplacement de base de données pour un ou plusieurs serveurs d’archivage.  <br/> |
   

