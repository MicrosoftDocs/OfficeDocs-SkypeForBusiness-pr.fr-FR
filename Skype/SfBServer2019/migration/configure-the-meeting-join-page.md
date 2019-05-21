---
title: Configuration de la page de participation à une réunion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation à une réunion détecte le client déjà installé sur l’ordinateur de l’utilisateur. Si un client est déjà installé, ce client ouvre et joint la réunion. Si un client n’est pas installé, l’application Web s’ouvre par défaut.
ms.openlocfilehash: c5f6cd5b1d04b54f8db9f82080bc8dbabefdc11e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298276"
---
# <a name="configure-the-meeting-join-page"></a>Configuration de la page de participation à une réunion

Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation à une réunion détecte le client déjà installé sur l’ordinateur de l’utilisateur. Si un client est déjà installé, ce client ouvre et joint la réunion. Si un client n’est pas installé, l’application Web s’ouvre par défaut.
  
Vous pouvez modifier le comportement de la page de participation à une réunion si vous voulez permettre aux utilisateurs de participer à des réunions. Ces options de configuration ont été supprimées du panneau de configuration, mais vous les configurez à l’aide de l’applet de commande CsWebServiceConfiguration.
  
**Paramètres d’CsWebServiceConfiguration de la page de participation à une réunion**

|**Paramètre CsWebServiceConfiguration**|**Description**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |S’il est défini sur true, les utilisateurs qui rejoignent une réunion à l’aide d’une application client autre que Lync seront en mesure de rejoindre la réunion. La valeur par défaut est False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Lorsque cette propriété est définie sur true, d’autres options permettant de participer à une conférence en ligne sont automatiquement développées et affichées aux utilisateurs. Lorsque ce paramètre est défini sur false (valeur par défaut), les options suivantes sont disponibles, mais l’utilisateur doit afficher la liste des options pour eux-mêmes.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Pour configurer la page de participation à une réunion à l’aide de Skype entreprise Server 2019 Management Shell

1. Démarrez Skype entreprise Server 2019 Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande suivante : 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    Ce cmdlet renvoie les paramètres de configuration de service Web.
    
3. Exécutez la commande suivante, avec les paramètres définis sur true ou false, en fonction de votre préférence (pour plus d’informations sur les paramètres de cette applet de commande, reportez-vous à la documentation de [Skype entreprise Server Management Shell](../../SfbServer/manage/management-shell.md) ):
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


