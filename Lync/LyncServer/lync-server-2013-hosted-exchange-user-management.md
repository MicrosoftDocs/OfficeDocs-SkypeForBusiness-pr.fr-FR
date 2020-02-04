---
title: 'Lync Server 2013 : Gestion des utilisateurs Exchange hébergés'
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
ms.openlocfilehash: 23289399e4eee4a654b41f2978191a6329739b4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Gestion des utilisateurs Exchange hébergés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Pour fournir des services de messagerie vocale aux utilisateurs de Lync Server 2013 dont les boîtes aux lettres se trouvent sur un service Exchange hébergé, vous devez activer leurs comptes d’utilisateurs pour la messagerie vocale hébergée.

<div>


> [!NOTE]  
> Pour que l’utilisateur de 2013 la messagerie vocale hébergée puisse être activé, une stratégie de messagerie vocale hébergée qui s’applique au compte d’utilisateur correspondant doit être déployée. La stratégie peut être globale, de site ou par utilisateur dans le champ d’application, dans la mesure où elle s’applique à l’utilisateur que vous souhaitez activer. Pour plus d’informations, reportez-vous <A href="lync-server-2013-hosted-voice-mail-policies.md">à stratégies de messagerie vocale hébergées dans Lync Server 2013</A>.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>Attribut msExchUCVoiceMailSettings

Lync Server 2013 introduit un nouvel attribut utilisateur nommé **msExchUCVoiceMailSettings**, qui est créé dans le cadre de la préparation du schéma Active Directory de lync Server 2013. Cet attribut à plusieurs valeurs contient les paramètres de messagerie vocale partagés par Lync Server 2013 et le service Exchange hébergé.

Le service Exchange hébergé risque de définir la valeur de l’attribut msExchUCVoiceMailSettings dans le processus d’activation de la messagerie unifiée Exchange ou lors du processus de transfert de boîtes aux lettres sur un serveur Exchange hébergé. Si cet attribut n’est pas défini par Exchange, l’administrateur 2013 du serveur Lync doit le configurer en exécutant l’applet de commande Set-CsUser, comme décrit plus haut dans cette rubrique.

Les paires clé/valeur de l’attribut et leurs auteurs sont indiquées dans le tableau suivant.

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>Paires clé/valeur de l’attribut msExchUCVoiceMailSettings

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
<td><p>L’utilisateur a été activé pour l’accès à la messagerie unifiée hébergé par Exchange Server. L’application de routage de messagerie unifiée Exchange vérifie les détails de routage de la stratégie de messagerie vocale hébergée par l’utilisateur.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>L’utilisateur a été désactivé pour l’accès à la messagerie unifiée hébergé par Exchange Server.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>L’utilisateur a été activé pour l’accès à la messagerie unifiée hébergée par Lync Server 2013. L’application de routage de ExUM Lync Server 2013 vérifie la stratégie de messagerie vocale hébergée de l’utilisateur pour déterminer les détails de routage.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>L’utilisateur a été désactivé pour l’accès à la messagerie unifiée hébergée par Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Si l’attribut comporte déjà des valeurs autres que l’une des paires clé/valeur de Lync Server 2013 (CSHostedVoiceMail = 0 ou CSHostedVoiceMail = 1), un avertissement indique que l’attribut peut être géré par une autre application. Par exemple, un avertissement s’affiche si les paires clé/valeur ExchangeHostedVoiceMail = 0 ou ExchangeHostedVoiceMail = 1 sont déjà présentes. Dans ce cas, vous pouvez modifier la valeur en la modifiant dans Active Directory ou en exécutant l’applet de commande suivante pour définir la valeur sur null :<BR>Set-CsUser-Identity User-HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>Activation des utilisateurs pour la messagerie vocale hébergée

Pour permettre le routage des appels de messagerie vocale d’un utilisateur vers la messagerie unifiée Exchange hébergée, vous devez exécuter l’applet de demande Set-CsUser pour définir la valeur du paramètre *HostedVoiceMail* . Ce paramètre indique également à Lync Server 2013 d’allumer l’indicateur « appeler la messagerie vocale ».

  - Dans l’exemple suivant, le compte d’utilisateur de Pilar Arès est activé pour la messagerie vocale hébergée :
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    L’applet de passe vérifie qu’une stratégie de messagerie vocale hébergée (globale, de niveau de site ou par utilisateur) s’applique à cet utilisateur. S’il n’y a aucune stratégie, l’applet de passe échoue.

  - Dans l’exemple suivant, le compte d’utilisateur de la messagerie vocale hébergée Pilar Arès :
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    L’applet de passe vérifie qu’il n’y a aucune stratégie de messagerie vocale hébergée (globale, de niveau site ou par utilisateur). Si une stratégie s’applique, l’applet de demande échoue.

Pour plus d’informations sur l’utilisation de l’applet de connexion Set-CsUser, voir la documentation Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

