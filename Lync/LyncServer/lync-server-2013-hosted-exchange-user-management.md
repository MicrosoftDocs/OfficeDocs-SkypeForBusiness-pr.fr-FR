---
title: 'Lync Server 2013 : Gestion des utilisateurs Exchange hébergés'
TOCTitle: Gestion des utilisateurs Exchange hébergés
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399037(v=OCS.15)
ms:contentKeyID: 49299189
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des utilisateurs Exchange hébergés dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour fournir des services de messagerie vocale aux utilisateurs Lync Server 2013 dont les boîtes aux lettres sont situées sur un service Exchange hébergé, vous devez activer leur compte utilisateur pour la messagerie vocale hébergée.

> [!NOTE]  
> Pour qu’un utilisateur Lync Server 2013 puisse accéder à la messagerie vocale hébergée, une stratégie de messagerie vocale hébergée correspondant au compte utilisateur doit être déployée. Cette stratégie peut être déployée au niveau global, du site ou de chaque utilisateur à condition qu’elle s’applique à l’utilisateur que vous souhaitez activer. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-hosted-voice-mail-policies.md">Stratégies de messagerie vocale hébergées dans Lync Server 2013</a> (contenu éventuellement en anglais).

## L’attribut msExchUCVoiceMailSettings

Lync Server 2013 introduit un nouvel attribut d’utilisateur intitulé **msExchUCVoiceMailSettings**, créé lors de la préparation du schéma Active Directory Lync Server 2013. Cet attribut à valeurs multiples contient les paramètres de messagerie vocale partagés par Lync Server 2013 et par le service Exchange hébergé.

Le service Exchange hébergé peut dans certains cas définir la valeur de l’attribut msExchUCVoiceMailSettings lors du processus d’activation de la messagerie unifiée (UM) Exchange ou de transfert des boîtes aux lettres vers un serveur Exchange hébergé. Si cet attribut n’est pas défini par Exchange, l’administrateur Lync Server 2013 doit le définir en exécutant l’applet de commande Set-CsUser, comme décrit précédemment dans cette rubrique.

Les paires clé/valeur de l’attribut et leurs auteurs sont indiqués dans le tableau suivant.

### Les paires clé/valeur de l’attribut msExchUCVoiceMailSettings

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
<td><p>ExchangeHostedVoiceMail=1</p></td>
<td><p>Exchange</p></td>
<td><p>L’utilisateur a été activé pour accéder à la messagerie unifiée hébergée par Exchange Server. L’application de routage ExUM messagerie unifiée Exchange consultera les informations de routage de la stratégie de messagerie vocale hébergée de l’utilisateur.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail=0</p></td>
<td><p>Exchange</p></td>
<td><p>L’utilisateur a été désactivé pour accéder à la messagerie unifiée hébergée par Exchange Server.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail=1</p></td>
<td><p>Lync Server</p></td>
<td><p>L’utilisateur a été activé pour accéder à la messagerie unifiée hébergée par Lync Server 2013. L’application de routage ExUM Lync Server 2013 consultera les informations de routage de la stratégie de messagerie vocale hébergée de l’utilisateur.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail=0</p></td>
<td><p>Lync Server</p></td>
<td><p>L’utilisateur a été désactivé pour accéder à la messagerie unifiée hébergée par Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Si l’attribut comporte déjà des valeurs différentes des paires clé/valeur Lync Server 2013 (CSHostedVoiceMail=0 ou CSHostedVoiceMail=1), un message vous avertit que l’attribut peut être géré par une autre application. Par exemple, un avertissement s’affiche si la paire clé/valeur ExchangeHostedVoiceMail=0 ou ExchangeHostedVoiceMail=1 existe déjà. Dans ce cas, vous pouvez modifier la valeur en éditant Active Directory ou en exécutant l’applet de commande suivante pour appliquer une valeur nulle :<br />
Set-CsUser –identité utilisateur –HostedVoicemail $null

## Activation des utilisateurs pour la messagerie vocale hébergée

Pour acheminer les appels de messagerie vocale d’un utilisateur vers une messagerie unifiée (UM) Exchange, vous devez exécuter l’applet de commande Set-CsUser afin de définir la valeur du paramètre *HostedVoiceMail* . Ce paramètre indique également à Lync Server 2013 d’allumer l’indicateur « appeler la messagerie vocale ».

  - L’exemple suivant active le compte de Pilar Ackerman pour la messagerie vocale hébergée :
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    L’applet de commande vérifie qu’une stratégie de messagerie vocale hébergée (au niveau global, du site ou de chaque utilisateur) s’applique à cet utilisateur. Si aucune stratégie ne s’applique, l’applet de commande échoue.

  - L’exemple suivant désactive le compte de Pilar Ackerman pour la messagerie vocale hébergée :
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    L’applet de commande vérifie qu’aucune stratégie de messagerie vocale hébergée (au niveau global, du site ou de chaque utilisateur) ne s’applique à cet utilisateur. Si une stratégie s’applique, l’applet de commande échoue.

Pour plus d’informations sur l’utilisation de l’applet de commande Set-CsUser, reportez-vous à la documentation Lync Server Management Shell.

