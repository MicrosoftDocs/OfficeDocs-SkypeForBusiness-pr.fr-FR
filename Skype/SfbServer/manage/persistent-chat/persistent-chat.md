---
title: Gérer le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Résumé : Découvrez comment gérer le serveur de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 3fc0027d8984a3c4ea4249f0d44a2d21a4913a3a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860001"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Gérer le serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment gérer le serveur de conversation permanente dans Skype Entreprise Server 2015.
  
Lorsque vous définissez le serveur de conversation permanente pour votre organisation, vous spécifiez la configuration initiale pendant le déploiement. Toutefois, il peut se peut que vous vouliez modifier la façon dont vous implémentez la prise en charge du serveur de conversation permanente. Par exemple, vous devrez peut-être configurer différemment la prise en charge et les contrôles du serveur de conversation permanente pour une équipe ou un groupe spécifique au sein de votre organisation. Cette section fournit des informations et des procédures pour vous aider à personnaliser votre déploiement de serveur de conversation permanente. Pour plus d’informations sur les fonctionnalités que vous pouvez configurer pour le serveur de conversation permanente, voir [Plan for Persistent Chat Server in Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Pour plus d’informations sur le déploiement d’un serveur de conversation permanente, voir [Deploy Persistent Chat Server in Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 
  
Vous pouvez gérer le serveur de conversation permanente à l’aide du Panneau de Windows PowerShell cmdlets. 
  
Pour utiliser le Panneau de contrôle :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez **sur Conversation permanente.**
    
Le tableau suivant récapitule les cmdlets Windows PowerShell disponibles pour vous aider à gérer le serveur de conversation permanente. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, [voir Skype Entreprise Server 2015 Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crée une catégorie  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configure les paramètres d’une catégorie existante  <br/> |
|Get-CsPersistentChatCategory  <br/> |Récupère des informations sur les catégories  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Supprime une catégorie  <br/> |
|New-CsPersistentChatRoom  <br/> |Crée une salle de conversation  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configure les paramètres d’une salle existante ; affecter des utilisateurs et des groupes d’utilisateurs à la salle  <br/> |
|Get-CsPersistentChatRoom  <br/> |Récupère des informations sur les salles  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Effacer une salle ou des messages d’une salle  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Supprime une salle  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Supprime les messages d’une salle  <br/> |
|New-CsPersistentChatAddin  <br/> |Crée un nouveau add-in  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configure les paramètres d’un add-in existant  <br/> |
|Get-CsPersistentChatAddin  <br/> |Récupère des informations sur les modules complémentaires  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Supprime un add-in  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Modifie une collection existante de paramètres de configuration de conformité  <br/> |
|Export-CsPersistentChatData  <br/> |Exporte des données à partir d’une base de données de conversation permanente  <br/> |
|Import-CsPersistentChatData  <br/> |Importe les données exportées à partir d’une version précédente de Lync Server  <br/> |
   

