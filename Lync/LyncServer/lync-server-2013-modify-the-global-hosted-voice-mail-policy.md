---
title: 'Lync Server 2013 : modification de la stratégie de messagerie vocale hébergée dans le monde entier'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e930e0b1f9a6e2d246a8011c59e2c92c75ba138d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a>Modifier la stratégie globale de messagerie vocale hébergée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-24_

La stratégie de messagerie vocale *globale* hébergée est installée avec Lync Server 2013. Vous pouvez le modifier en fonction de vos besoins, mais vous ne pouvez pas le renommer ou le supprimer. Pour modifier la stratégie globale, vous devez utiliser l’applet de passe Set-CsHostedVoicemailPolicy pour définir les paramètres sur les valeurs appropriées pour votre déploiement spécifique.

Pour plus d’informations sur l’applet [de connexion Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , voir la documentation Lync Server Management Shell.

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a>Pour modifier la stratégie de messagerie vocale hébergée dans le monde

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de cmdlet Set-CsHostedVoicemailPolicy pour définir les paramètres de stratégie globale pour votre environnement. Par exemple, exécutez :
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    Étant donné que cette commande ne spécifie pas le paramètre Identity de la stratégie, l’interface de ligne de commande Windows PowerShell définit les valeurs suivantes sur la stratégie de messagerie vocale hébergée dans le monde entier :
    
      - **Destination** spécifie le nom de domaine complet (FQDN) du service Exchange um hébergé. Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée et que la stratégie attribuée de l’utilisateur n’a pas de valeur de destination, l’activation échoue.
    
      - **Organization** spécifie une liste séparée par des virgules des clients Exchange que les utilisateurs du serveur principal de Lync Server. Chaque client doit être spécifié en tant que nom de domaine complet (FQDN) du client sur le service de messagerie unifiée Exchange hébergé.
    
    <div>
    

    > [!NOTE]  
    > Dans l’applet de l’exemple précédent, la valeur « corp1.litwareinc.com » remplace une valeur éventuellement déjà présente dans le paramètre Organization. Par exemple, si la stratégie comporte déjà une liste d’organisations séparée par des virgules, la liste complète serait remplacée. Si vous souhaitez ajouter une organisation à la liste au lieu de remplacer la liste entière, exécutez une commande similaire à ce qui suit.

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

