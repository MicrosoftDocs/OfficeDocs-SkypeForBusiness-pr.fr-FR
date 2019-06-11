---
title: 'Lync Server 2013: création d’une stratégie de messagerie vocale hébergée par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d09638c28c1cbd2b068972aff169376508325885
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Créer une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-24_

Une stratégie *par utilisateur* peut affecter uniquement des utilisateurs, des groupes et des objets de contact individuels. Pour déployer une stratégie par utilisateur, vous devez affecter explicitement la stratégie à un ou plusieurs utilisateurs, groupes ou objets de contact. Pour plus d’informations, reportez-vous à [la section affectation d’une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).

Pour plus d’informations sur l’utilisation des stratégies de messagerie vocale hébergées par utilisateur, voir la documentation Lync Server Management Shell pour les applets de commande suivantes:

  - [Nouveau-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a>Pour créer une stratégie de messagerie vocale hébergée par utilisateur

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de nouvelle applet de CsHostedVoicemailPolicy pour créer la stratégie. Par exemple, exécutez :
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    L’exemple précédent crée une stratégie de messagerie vocale hébergée avec une étendue par utilisateur et définit les paramètres suivants:
    
      - **Identity** spécifie un identificateur unique pour la stratégie, qui inclut l’étendue. Dans le cas d’une stratégie avec une étendue par utilisateur, la valeur de ce paramètre est spécifiée sous la forme d’une chaîne simple, par exemple, exredmond.
    
      - **Destination** spécifie le nom de domaine complet (FQDN) du service Exchange um hébergé. Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée et que la stratégie attribuée de l’utilisateur n’a pas de valeur de destination, l’activation échoue.
    
      - **Description** fournit des informations descriptives supplémentaires sur la stratégie.
    
      - **Organization** spécifie une liste séparée par des virgules des clients Exchange qui sont des utilisateurs de Lync Server 2013. Chaque client doit être spécifié en tant que nom de domaine complet (FQDN) du client sur le service de messagerie unifiée Exchange hébergé.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Affecter une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

