---
title: Gérer un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Résumé : Apprenez à gérer le serveur de conversation permanents dans Skype pour Business Server 2015.'
ms.openlocfilehash: 294c6bcecbbfb57bb8d2a6a785cdf20775119510
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Gérer un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à gérer le serveur de conversation permanents dans Skype pour Business Server 2015.
  
Lorsque vous configurez persistant Chat Server pour votre organisation, vous spécifiez la configuration initiale pendant le déploiement. Toutefois, il peut arriver lorsque vous souhaitez modifier la façon dont vous implémentez la prise en charge du serveur de conversation persistant. Par exemple, vous devrez configurer la prise en charge du serveur de Chat persistant et contrôles différemment pour une équipe spécifique ou un groupe au sein de votre organisation. Cette section fournit des informations et des procédures pour vous aider à personnaliser votre déploiement de serveur de conversation persistant. Pour plus d’informations sur les fonctionnalités que vous pouvez configurer de serveur de conversation persistant, voir [planification de serveur Chat persistant dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Pour plus d’informations sur le déploiement du serveur de conversation persistant, consultez [Déploiement de serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
  
Vous pouvez gérer serveur de Chat persistant à l’aide du Panneau de configuration ou à l’aide des applets de commande Windows PowerShell. 
  
Pour utiliser le Panneau de configuration :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanent**.
    
Le tableau suivant résume les applets de commande Windows PowerShell disponibles pour vous aider à gérer le serveur de conversation persistant. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, consultez [Skype pour Business Server 2015 Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|Nouvelle-CsPersistentChatCategory  <br/> |Crée une catégorie  <br/> |
|Ensemble-CsPersistentChatCategory  <br/> |Configure des paramètres pour une catégorie existante  <br/> |
|Get-CsPersistentChatCategory  <br/> |Récupère des informations sur les catégories  <br/> |
|Supprimer-CsPersistentChatCategory  <br/> |Supprime une catégorie  <br/> |
|Nouvelle-CsPersistentChatRoom  <br/> |Crée une salle de conversation  <br/> |
|Ensemble-CsPersistentChatRoom  <br/> |Configure des paramètres pour une salle existante ; affecter des utilisateurs et des groupes d’utilisateurs à la salle  <br/> |
|Get-CsPersistentChatRoom  <br/> |Extrait des informations à propos de salles  <br/> |
|CsPersistentChatRoom-clair  <br/> |Efface une salle et les messages d’une salle  <br/> |
|Supprimer-CsPersistentChatRoom  <br/> |Supprime une salle  <br/> |
|Supprimer-CsPersistentChatMessage  <br/> |Supprime les messages d’une salle  <br/> |
|Nouvelle-CsPersistentChatAddin  <br/> |Crée un complément  <br/> |
|Ensemble-CsPersistentChatAddin  <br/> |Configure des paramètres pour un complément existant  <br/> |
|Get-CsPersistentChatAddin  <br/> |Récupère des informations sur les compléments  <br/> |
|Supprimer-CsPersistentChatAddin  <br/> |Supprime un complément  <br/> |
|Ensemble-CsPersistentChatComplianceConfiguration  <br/> |Modifie une collection existante des paramètres de configuration de conformité  <br/> |
|Exportation-CsPersistentChatData  <br/> |Exporte les données d’une base de données de conversation permanente.  <br/> |
|Importation-CsPersistentChatData  <br/> |Importe les données qui avaient été exportées d’une version précédente de Lync Server  <br/> |
   

