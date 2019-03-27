---
title: Configuration de la page de participation à une réunion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Lorsqu’un utilisateur clique sur un lien de la réunion dans une demande de réunion, la réunion page de participation aux détecte que le client est déjà installé sur l’ordinateur de l’utilisateur. Si un client est déjà installé, que le client s’ouvre et rejoint la réunion. Si un client n’est pas installé, par défaut l’application Web s’ouvre.
ms.openlocfilehash: 88ae915318505efef6ae716a17217aaa1e7b12df
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879939"
---
# <a name="configure-the-meeting-join-page"></a>Configuration de la page de participation à une réunion

Lorsqu’un utilisateur clique sur un lien de la réunion dans une demande de réunion, la réunion page de participation aux détecte que le client est déjà installé sur l’ordinateur de l’utilisateur. Si un client est déjà installé, que le client s’ouvre et rejoint la réunion. Si un client n’est pas installé, par défaut l’application Web s’ouvre.
  
Vous pouvez modifier le comportement de la participation aux réunions de page si vous souhaitez autoriser les utilisateurs à participer à des réunions. Ces options de configuration ont été supprimées dans le panneau de configuration, mais les configurer à l’aide de l’applet de commande CsWebServiceConfiguration.
  
**Paramètres CsWebServiceConfiguration de la Page de participation aux réunions**

|**Paramètre CsWebServiceConfiguration**|**Description**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Si défini sur True, les utilisateurs qui rejoignent une réunion à l’aide d’une application cliente autre que Lync aura la possibilité de participer à la réunion. La valeur par défaut est False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Lorsque la valeur True, les options de substitution pour la participation à une conférence en ligne sera automatiquement développée et affichée aux utilisateurs. Lorsque la valeur False (valeur par défaut), ces options seront disponibles, mais l’utilisateur aura afficher la liste des options pour eux-mêmes.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Pour configurer la réunion page d’inscription à l’aide de Skype pour Business Server 2019 Management Shell

1. Démarrez le Skype pour Business Server 2019 Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Exécutez l’applet de commande suivante : 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    Cette applet de commande renvoie le site web de paramètres de configuration de service.
    
3. Exécutez la commande suivante, avec les paramètres dont la valeur est True ou False selon votre préférence (pour plus d’informations sur les paramètres de cette applet de commande, voir la documentation de [Skype pour Business Server Management Shell](../../SfbServer/manage/management-shell.md) ) :
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


