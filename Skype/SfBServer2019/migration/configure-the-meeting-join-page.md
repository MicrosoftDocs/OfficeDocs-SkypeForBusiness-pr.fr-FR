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
ms.localizationpriority: medium
description: Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de réunion détecte le client déjà installé sur l’ordinateur de l’utilisateur. Si c’est le cas, ce client s’ouvre et se joint à la réunion. Si un client n’est pas installé, l’application Web s’ouvre par défaut.
ms.openlocfilehash: 8cba2a6ea0bc54eae6c30265c21d33d01ec951c0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617110"
---
# <a name="configure-the-meeting-join-page"></a>Configuration de la page de participation à une réunion

Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de réunion détecte le client déjà installé sur l’ordinateur de l’utilisateur. Si c’est le cas, ce client s’ouvre et se joint à la réunion. Si un client n’est pas installé, l’application Web s’ouvre par défaut.
  
Vous pouvez modifier le comportement de la page de rejoindre une réunion si vous souhaitez autoriser les utilisateurs à participer à des réunions. Ces options de configuration ont été supprimées du Panneau de configuration, mais vous les configurez à l’aide de l’cmdlet CsWebServiceConfiguration.
  
**Paramètres CsWebServiceConfiguration de la page de participation aux réunions**

|**Paramètre CsWebServiceConfiguration**|**Description**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Si la valeur est True, les utilisateurs qui rejoignent une réunion à l’aide d’une application cliente autre que Lync auront la possibilité de participer à la réunion. La valeur par défaut est False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Si la valeur est True, les autres options de rejoindre une conférence en ligne sont automatiquement étendues et affichées aux utilisateurs. Si la valeur est False (valeur par défaut), ces options seront disponibles, mais l’utilisateur devra afficher la liste des options pour lui-même.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Pour configurer la page de réunion à l’aide de Skype Entreprise Server 2019 Management Shell

1. Démarrez Skype Entreprise Server 2019 Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Microsoft **Skype Entreprise Server 2019,** puis sur Skype Entreprise Server Management Shell .
    
2. Exécutez la cmdlet suivante : 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Cette applet de commande renvoie les paramètres de configuration du service Web.
    
3. Exécutez la commande suivante, avec les paramètres définies sur True ou False, en fonction de vos préférences (pour plus d’informations sur les paramètres de cette cmdlet, voir la documentation de [Skype Entreprise Server Management Shell)](../../SfbServer/manage/management-shell.md) :
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


