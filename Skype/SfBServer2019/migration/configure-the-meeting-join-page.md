---
title: Configuration de la page de participation à une réunion
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation aux réunions détecte le client qui est déjà installé sur l’ordinateur de l’utilisateur. Si c’est le cas, ce client s’ouvre et se joint à la réunion. Si un client n’est pas installé, l’application Web s’ouvre par défaut.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754024"
---
# <a name="configure-the-meeting-join-page"></a>Configuration de la page de participation à une réunion

Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation aux réunions détecte le client qui est déjà installé sur l’ordinateur de l’utilisateur. Si c’est le cas, ce client s’ouvre et se joint à la réunion. Si un client n’est pas installé, l’application Web s’ouvre par défaut.
  
Vous pouvez modifier le comportement de la page de participation à la réunion si vous souhaitez autoriser les utilisateurs à participer à des réunions. Ces options de configuration ont été supprimées du panneau de configuration, mais vous les configurez à l’aide de l’applet de commande CsWebServiceConfiguration.
  
**Paramètres CsWebServiceConfiguration de la page de participation aux réunions**

|**Paramètre CsWebServiceConfiguration**|**Description**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Si la valeur est true, les utilisateurs qui rejoignent une réunion à l’aide d’une application cliente autre que Lync auront la possibilité de participer à la réunion. La valeur par défaut est False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Lorsque la valeur est true, d’autres options de participation à une conférence en ligne sont automatiquement développées et affichées aux utilisateurs. Lorsqu’elle est définie sur false (valeur par défaut), ces options sont disponibles, mais l’utilisateur doit afficher la liste des options pour eux-mêmes.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Pour configurer la page de participation aux réunions à l’aide de Skype entreprise Server 2019 Management Shell

1. Démarrez Skype entreprise Server 2019 Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Skype entreprise Server 2019**, puis sur **Skype entreprise Server Management Shell**.
    
2. Exécutez la cmdlet suivante : 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Cette applet de commande renvoie les paramètres de configuration du service Web.
    
3. Exécutez la commande suivante, avec les paramètres définis sur true ou false, en fonction de vos préférences (pour plus d’informations sur les paramètres de cette cmdlet, voir la documentation de [Skype entreprise Server Management Shell](../../SfbServer/manage/management-shell.md) ) :
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


