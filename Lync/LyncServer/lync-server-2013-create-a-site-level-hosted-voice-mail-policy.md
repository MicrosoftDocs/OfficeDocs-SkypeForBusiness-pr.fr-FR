---
title: 'Lync Server 2013 : création d’une stratégie de messagerie vocale hébergée au niveau du site'
description: 'Lync Server 2013 : créez une stratégie de messagerie vocale hébergée au niveau du site.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd578359a8d20562e8887b61b86d53332e6f8d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578370"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Créer une stratégie de messagerie vocale hébergée au niveau du site dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-24_

Une stratégie de *site* peut avoir un impact sur tous les utilisateurs hébergés sur le site pour lequel la stratégie est définie. Si un utilisateur est configuré pour l’accès à la messagerie unifiée Exchange hébergée et qu’aucune stratégie par utilisateur n’a été attribuée, la stratégie de site s’applique. Si vous n’avez pas déployé une stratégie de site, la stratégie globale s’applique.

Pour plus d’informations sur la configuration des stratégies de site, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>Pour créer une stratégie de messagerie vocale hébergée sur un site

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsHostedVoicemailPolicy pour créer la stratégie. Par exemple, exécutez :
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    Cet exemple crée une stratégie de messagerie vocale hébergée avec l’étendue site et définit les paramètres suivants :
    
      - **Identity** spécifie un identificateur unique pour la stratégie qui englobe l’étendue. Pour une stratégie avec étendue de site, la valeur du paramètre Identity doit être spécifiée dans le format `site:` *\<name\>* , par exemple `site:Redmond` .
    
      - **Destination** spécifie le nom de domaine complet du service de messagerie unifiée Exchange hébergé. Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée alors que la stratégie affectée à l’utilisateur n’a pas de valeur Destination, l’activation échoue.
    
      - **Description** fournit des informations facultatives décrivant la stratégie.
    
      - **Organisation** spécifie une liste séparée par des virgules des clients Exchange hébergeant des utilisateurs de Lync Server 2013. Chaque locataire doit être spécifié avec son nom de domaine complet (FQDN) dans le service de messagerie unifiée Exchange hébergé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

