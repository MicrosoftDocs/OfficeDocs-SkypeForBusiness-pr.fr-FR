---
title: 'Lync Server 2013 : gestion des utilisateurs Exchange hébergés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16b2716bee52902f55160e770df36801d18f1b78
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Gestion des utilisateurs Exchange hébergés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Pour fournir des services de messagerie vocale pour les utilisateurs de Lync Server 2013 dont les boîtes aux lettres sont situées sur un service Exchange hébergé, vous devez activer leurs comptes d’utilisateur pour la messagerie vocale hébergée.

<div>


> [!NOTE]  
> Avant de pouvoir activer un utilisateur Lync Server 2013 pour la messagerie vocale hébergée, une stratégie de messagerie vocale hébergée qui s’applique au compte d’utilisateur correspondant doit être déployée. Cette stratégie peut être déployée au niveau global, du site ou de chaque utilisateur à condition qu’elle s’applique à l’utilisateur que vous souhaitez activer. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-hosted-voice-mail-policies.md">stratégies de messagerie vocale hébergée dans Lync Server 2013</A>.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>L’attribut msExchUCVoiceMailSettings

Lync Server 2013 introduit un nouvel attribut utilisateur nommé **msExchUCVoiceMailSettings**, qui est créé dans le cadre de la préparation du schéma Active Directory de lync Server 2013. Cet attribut à valeurs multiples contient les paramètres de messagerie vocale qui sont partagés par Lync Server 2013 et le service Exchange hébergé.

Le service Exchange hébergé peut dans certains cas définir la valeur de l’attribut msExchUCVoiceMailSettings lors du processus d’activation de la messagerie unifiée (UM) Exchange ou de transfert des boîtes aux lettres vers un serveur Exchange hébergé. Si cet attribut n’est pas défini par Exchange, l’administrateur Lync Server 2013 doit le définir en exécutant la cmdlet Set-CsUser, comme décrit plus haut dans cette rubrique.

Les paires clé/valeur de l’attribut et leurs auteurs sont indiqués dans le tableau suivant.

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>Les paires clé/valeur de l’attribut msExchUCVoiceMailSettings

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valeur</th>
<th>Auteur</th>
<th>Signification</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>L’utilisateur a été activé pour accéder à la messagerie unifiée hébergée par Exchange Server. L’application de routage de messagerie unifiée Exchange vérifie la stratégie de messagerie vocale hébergée de l’utilisateur pour les détails de routage.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>L’utilisateur a été désactivé pour accéder à la messagerie unifiée hébergée par Exchange Server.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>L’accès à la messagerie unifiée hébergée par Lync Server 2013 a été activé pour l’utilisateur. L’application de routage ExUM de Lync Server 2013 vérifie la stratégie de messagerie vocale hébergée de l’utilisateur pour les détails de routage.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>L’utilisateur a été désactivé pour l’accès à la messagerie unifiée hébergée par Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Si l’attribut possède déjà des valeurs autres que l’une des paires clé/valeur de Lync Server 2013 (CSHostedVoiceMail = 0 ou CSHostedVoiceMail = 1), un avertissement indique que l’attribut peut être géré par une autre application. Par exemple, un avertissement s’affiche si la paire clé/valeur ExchangeHostedVoiceMail=0 ou ExchangeHostedVoiceMail=1 existe déjà. Dans ce cas, vous pouvez modifier la valeur en éditant Active Directory ou en exécutant la cmdlet suivante pour appliquer une valeur nulle :<BR>Set-CsUser –identité utilisateur –HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>Activation des utilisateurs pour la messagerie vocale hébergée

Pour acheminer les appels de messagerie vocale d’un utilisateur vers une messagerie unifiée (UM) Exchange, vous devez exécuter la cmdlet Set-CsUser afin de définir la valeur du paramètre *HostedVoiceMail*. Ce paramètre signale également à Lync Server 2013 l’indicateur d’appel de messagerie vocale.

  - L’exemple suivant active le compte de Pilar Ackerman pour la messagerie vocale hébergée :
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    La cmdlet vérifie qu’une stratégie de messagerie vocale hébergée (au niveau global, du site ou de chaque utilisateur) s’applique à cet utilisateur. Si aucune stratégie ne s’applique, la cmdlet échoue.

  - L’exemple suivant désactive le compte de Pilar Ackerman pour la messagerie vocale hébergée :
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    La cmdlet vérifie qu’aucune stratégie de messagerie vocale hébergée (au niveau global, du site ou de chaque utilisateur) ne s’applique à cet utilisateur. Si une stratégie s’applique, la cmdlet échoue.

Pour plus d’informations sur l’utilisation de la cmdlet Set-CsUser, voir la documentation de Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

