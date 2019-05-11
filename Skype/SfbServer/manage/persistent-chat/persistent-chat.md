---
title: Gérer un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Résumé : Découvrez comment gérer les serveurs de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: 27405be6d209089c670aa117838e959bae64d9e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910220"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Gérer un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment gérer des serveurs de conversation permanente dans Skype pour Business Server 2015.
  
Lorsque vous configurez le serveur de conversation permanente pour votre organisation, vous spécifiez la configuration initiale au cours du déploiement. Toutefois, il peut arriver lorsque vous souhaitez modifier la façon dont vous implémentez la prise en charge des serveurs de conversation permanente. Par exemple, vous devrez peut-être configurer la prise en charge des serveurs de conversation permanente et contrôles différemment pour une équipe spécifique ou un groupe au sein de votre organisation. Cette section fournit des informations et des procédures pour vous aider à personnaliser votre déploiement de serveurs de conversation permanente. Pour plus d’informations sur les fonctions et fonctionnalités que vous pouvez configurer pour le serveur de conversation permanente, voir [Plan for Persistent Chat Server dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Pour plus d’informations sur le déploiement des serveurs de conversation permanente, voir [Déployer un serveur de conversation permanente dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 
  
Vous pouvez gérer des serveurs de conversation permanente à l’aide du Panneau de configuration ou à l’aide des applets de commande Windows PowerShell. 
  
Pour utiliser le Panneau de configuration :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**.
    
Le tableau suivant récapitule les applets de commande Windows PowerShell disponibles pour vous aider à gérer les serveurs de conversation permanente. Pour plus de détails sur la syntaxe, notamment tous les paramètres disponibles, voir [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crée une catégorie  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configure des paramètres pour une catégorie existante  <br/> |
|Get-CsPersistentChatCategory  <br/> |Récupère des informations sur les catégories  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Supprime une catégorie  <br/> |
|New-CsPersistentChatRoom  <br/> |Crée une salle de conversation  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configure des paramètres pour une salle existante ; affecter des utilisateurs et des groupes d’utilisateurs à la salle  <br/> |
|Get-CsPersistentChatRoom  <br/> |Récupère des informations sur les salles  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Efface une salle et les messages d’une salle  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Supprime une salle  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Supprime les messages d’une salle  <br/> |
|New-CsPersistentChatAddin  <br/> |Crée un complément  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configure des paramètres pour un complément existant  <br/> |
|Get-CsPersistentChatAddin  <br/> |Récupère des informations sur les compléments  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Supprime un complément  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Modifie une collection existante des paramètres de configuration de conformité  <br/> |
|Export-CsPersistentChatData  <br/> |Exporte les données d’une base de données de conversation permanente.  <br/> |
|Import-CsPersistentChatData  <br/> |Importe les données qui avaient été exportées d’une version précédente de Lync Server  <br/> |
   

