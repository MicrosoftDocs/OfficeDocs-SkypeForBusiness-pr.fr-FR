---
title: Gérer un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Résumé: Découvrez comment gérer le serveur Chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: 17b9770d2cc3385eb797a1e868c7623f3f09a3ba
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279276"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Gérer un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé:** Découvrez comment gérer le serveur Chat permanent dans Skype entreprise Server 2015.
  
Lorsque vous configurez le serveur de chat permanent pour votre organisation, vous spécifiez la configuration initiale lors du déploiement. Toutefois, il peut arriver que vous souhaitiez modifier le mode de mise en œuvre d’une prise en charge du serveur de chat permanent. Par exemple, vous pouvez avoir besoin de configurer une prise en charge et des contrôles permanents pour une équipe ou un groupe spécifique au sein de votre organisation. Cette section fournit des informations et des procédures pour vous aider à personnaliser le déploiement de votre serveur Chat permanent. Pour plus d’informations sur les fonctionnalités que vous pouvez configurer pour le serveur de chat permanent, voir [planifier pour le serveur de chat permanent dans Skype entreprise server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Pour plus d’informations sur le déploiement d’un serveur de chat permanent, voir [déployer un serveur Chat permanent dans Skype entreprise server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique [voyage de Skype entreprise à Microsoft teams](/microsoftteams/journey-skypeforbusiness-teams). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 
  
Vous pouvez gérer le serveur Chat permanent en utilisant le panneau de configuration ou en utilisant des applets de commande Windows PowerShell. 
  
Pour utiliser le Panneau de configuration :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **conversation permanente**.
    
Le tableau suivant récapitule les applets de commande Windows PowerShell disponibles pour vous aider à gérer le serveur de chat permanent. Pour plus de détails sur la syntaxe, notamment tous les paramètres disponibles, voir [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crée une catégorie  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configure des paramètres pour une catégorie existante  <br/> |
|Get-CsPersistentChatCategory  <br/> |Récupère des informations sur les catégories  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Supprime une catégorie  <br/> |
|New-CsPersistentChatRoom  <br/> |Crée une salle de conversation  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configure des paramètres pour une salle existante ; affecter des utilisateurs et des groupes d’utilisateurs à la salle  <br/> |
|Get-CsPersistentChatRoom  <br/> |Récupère les informations sur les salles.  <br/> |
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
   

