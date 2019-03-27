---
title: Configurer la réunion page de participation dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Résumé : Découvrez comment configurer la réunion page de participation dans Skype pour Business Server.'
ms.openlocfilehash: 4f737bdab0586cb342d1271f348cf765ae093c5c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875545"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configurer la réunion page de participation dans Skype pour Business Server
 
**Résumé :** Découvrez comment configurer la réunion page de participation dans Skype pour Business Server.
  
Lorsqu’un utilisateur clique sur un lien de la réunion dans une demande de réunion, la réunion page de participation aux détecte si un Skype pour client d’entreprise est déjà installé sur l’ordinateur de l’utilisateur. Si un client est déjà installé, le client s’ouvre et rejoint la réunion. Si un client n’est pas installé, par défaut le Skype pour les entreprises client s’ouvre. 
  
## <a name="configure-the-meeting-join-page"></a>Configuration de la page de participation à une réunion

Vous pouvez modifier le comportement de la participation aux réunions de page si vous souhaitez autoriser les utilisateurs à participer à des réunions avec d’autres versions du client. Ces options de configuration ont été supprimées de la Skype pour le panneau de configuration serveur Business, mais les configurer à l’aide de l’applet de commande Set-CsWebServiceConfiguration.
  
**Paramètres de participer à Set-CsWebServiceConfiguration de la Page de réunion**

|**Paramètre SET-CsWebServiceConfiguration**|**Description**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Ce paramètre est déconseillé pour une utilisation avec la version locale de Skype pour Business Server.  <br/> Si la valeur True, les utilisateurs à une réunion à l’aide d’une application cliente autre que Skype pour les entreprises auront la possibilité de participer à la réunion à l’aide de l’application cliente en cours. La valeur par défaut est False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Ce paramètre est déconseillé pour une utilisation avec la version locale de Skype pour Business Server.  <br/>  Si défini sur True, autres options pour participer à une conférence en ligne sont automatiquement développé et affichée aux utilisateurs. Si la valeur False (valeur par défaut), ces options seront disponibles, mais l’utilisateur aura afficher la liste des options pour eux-mêmes.  <br/> |
   

