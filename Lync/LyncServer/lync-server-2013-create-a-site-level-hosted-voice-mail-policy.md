---
title: 'Lync Server 2013 : création d’une stratégie de messagerie vocale hébergée au niveau du site'
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
ms.openlocfilehash: 6aeae2e533bd62cf1f3e24e7ceff69b870ebc7b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Créer une stratégie de messagerie vocale hébergée au niveau du site dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-24_

Une stratégie de *site* peut influer sur l’ensemble des utilisateurs hébergés sur le site pour lesquels la stratégie est définie. Si un utilisateur est configuré pour l’accès à la messagerie unifiée Exchange hébergé sans avoir reçu une stratégie par utilisateur, la stratégie de site s’applique. Si vous n’avez pas déployé de stratégie de site, la politique globale s’applique.

Pour plus d’informations sur la configuration des stratégies de site, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - [Nouveau-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>Pour créer une stratégie de messagerie vocale hébergée sur un site

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de nouvelle applet de CsHostedVoicemailPolicy pour créer la stratégie. Par exemple, exécutez :
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    Cet exemple crée une stratégie de messagerie vocale hébergée avec l’étendue du site et définit les paramètres suivants :
    
      - **Identity** spécifie un identificateur unique pour la stratégie, qui inclut l’étendue. Dans le cas d’une stratégie avec l’étendue du site, la valeur du paramètre Identity doit être spécifiée dans le `site:` * \<nom\>* du format, par exemple `site:Redmond`.
    
      - **Destination** spécifie le nom de domaine complet (FQDN) du service Exchange um hébergé. Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée et que la stratégie attribuée de l’utilisateur n’a pas de valeur de destination, l’activation échoue.
    
      - **Description** fournit des informations descriptives supplémentaires sur la stratégie.
    
      - **Organization** spécifie une liste séparée par des virgules des clients Exchange qui sont des utilisateurs de Lync Server 2013. Chaque client doit être spécifié en tant que nom de domaine complet (FQDN) du client sur le service de messagerie unifiée Exchange hébergé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

