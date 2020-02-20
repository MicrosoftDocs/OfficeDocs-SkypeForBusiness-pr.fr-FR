---
title: Exécuter la compatibilité descendante pour le serveur de conversation permanente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad689dace5e302cad8d41dff77dd575637b99ae6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Exécuter la compatibilité descendante pour le serveur de conversation permanente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Le point de terminaison Lync Server 2013, persistent Chat Server permet de créer une URL simple qui pointe vers un pool de serveurs de conversation permanente. Cette fonctionnalité est utile pour les clients hérités (serveur de conversation de groupe Microsoft Office Communications Server 2007 R2 ou Lync Server 2010, conversation de groupe), car les utilisateurs peuvent entrer une URL simple dans la configuration manuelle lorsqu’ils tentent de faire pointer le client hérité vers un ordinateur exécutant Lync 2013 Conversation permanente. Ce point de terminaison n’est pas utilisé par la conversation permanente et est requis uniquement pour les clients hérités. Cela est utile pour la période intermédiaire où les salles peuvent être migrées, mais les clients Lync 2013 n’ont pas été déployés au sein de l’organisation. Les utilisateurs exécutant Lync 2010 Group chat (client) peuvent toujours se connecter au serveur principal du serveur de conversation permanente.

Vous n’avez pas besoin de créer plusieurs points de terminaison de serveur de conversation permanente ; il vous suffit d’en avoir un pour chaque pool de serveurs de conversation permanente. Les administrateurs peuvent créer plusieurs points de terminaison (un par pool), mais les clients hérités peuvent être configurés pour se connecter à un seul pool à la fois. Dans le scénario classique ou standard, le déploiement hérité est un seul pool. Un nouveau déploiement migre généralement ce pool vers un nouveau Lync Server 2013 et peut ajouter des pools de serveurs de conversation permanente supplémentaires.

Ce scénario standard suit généralement ce modèle :

  - Vous administrez les utilisateurs avec un pool Lync Server 2010, Group chat et vos clients Lync 2010 Group chat se connectent à ce pool à l’aide d’un utilisateur connu (soit\<SIP\>par défaut : OCSChat@ nom_domaine. com, soit similaire). Les utilisateurs sont des services de domaine Active Directory compatibles SIP, et le service de recherche s’inscrit auprès de ces derniers pour recevoir des demandes entrantes.

  - Par la suite, vous installez un serveur de conversation permanente Lync Server 2013 et un pool de serveurs de conversation permanente.

  - Pendant un moment où les utilisateurs sont généralement hors connexion (par exemple, un week-end) :
    
      - Désactivez Lync Server 2010, Group chat.
    
      - Migrez les données du pool de conversation de groupe Lync Server 2010 vers le pool de serveurs Lync Server 2013 persistent chat.
    
      - Supprimez l’utilisateur connu des services de domaine Active Directory.
    
      - Créez un *point de terminaison hérité* avec le même URI SIP que l’utilisateur connu précédemment supprimé.
    
      - Démarrez les serveurs Lync Server 2013, persistent chat.

  - Les utilisateurs se connectent à l’aide de leur service de conversation de groupe Lync 2010 (client) et se connectent à leurs données sans avoir à modifier la configuration.

  - Par la suite, vous pouvez mettre hors service le Lync Server 2010, Group chat. Par la suite, vous pouvez déployer Lync Server 2013, le serveur de conversation permanente et installer les nouveaux pools de serveurs de conversation permanente Lync Server 2013.

Pour plus d’informations sur la migration de Lync Server 2010, Group chat vers Lync Server 2013, persistent Chat Server, voir [migration from Lync server 2010, Group chat ou Office Communications server 2007 R2 Group chat to Lync Server 2013, persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Pour exécuter la compatibilité descendante (pour créer un point de terminaison de serveur de conversation permanente qui pointe vers un pool de serveurs de conversation permanente, qui peut être utilisé par les clients de pool de conversation de groupe hérités) :

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Ensuite, configurez les clients de conversation permanente de sorte qu’ils utilisent cette adresse SIP comme objet contact. L’adresse SIP est créée avec la cmdlet **New-CsPersistentChatEndpoint** pour un pool de serveurs de conversation permanente spécifique.

Pour ajouter le point de terminaison du serveur de conversation permanente à l’aide de l’interface de ligne de commande Windows PowerShell, tenez compte de l’exemple suivant. Dans ce cas, vous configurez l’objet contact de sorte qu’il soit nommé « persistentchat » sur la topologie « contoso.com », où le nom de domaine complet (FQDN) du pool est « pcpool.contoso.com » :

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>Voir aussi


[Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, Serveur de conversation permanente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

