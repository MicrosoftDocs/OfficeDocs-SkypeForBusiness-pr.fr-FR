---
title: Exécution de compatibilité descendante pour la conversation permanente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b512d18449c881efd856674477a727cec137b64c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Exécution de compatibilité descendante pour la conversation permanente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Le point de terminaison Lync Server 2013, le point de terminaison serveur Chat permanent fournit un moyen de créer une URL simple qui pointe vers un pool de serveurs de chat permanent. Cette fonctionnalité est utile pour les clients hérités (serveur de conversation de groupe Microsoft Office Communications Server 2007 R2 ou Lync Server 2010, discussion de groupe), car les utilisateurs peuvent entrer une URL simple dans la configuration manuelle lors d’une tentative de pointage sur un ordinateur exécutant Lync 2013. Conversation permanente. Ce point de terminaison n’est pas utilisé par chat permanent et est requis uniquement pour les clients hérités. Cela est utile pour la période intermédiaire où les salles peuvent être migrées, mais les clients 2013 Lync n’ont pas été déployés au sein de l’organisation. Les utilisateurs exécutant une discussion de groupe Lync 2010 (client) peuvent toujours se connecter au serveur principal de chat serveur.

Vous n’avez pas besoin de créer plusieurs points de terminaison serveur de chat permanent; vous avez simplement besoin d’une seule liste de serveurs de chat permanent. Les administrateurs peuvent créer plusieurs points de terminaison (un par liste), mais les clients hérités peuvent être configurés pour se connecter à un seul pool à la fois. Dans le scénario classique ou standard, le déploiement hérité est un seul pool. Un nouveau déploiement migre généralement ce pool vers un nouveau serveur Lync Server 2013 et peut ajouter de nouveaux pools de serveurs de chat permanent supplémentaires.

Ce scénario standard suit généralement ce modèle:

  - Pour administrer les utilisateurs dotés d’un serveur Lync Server 2010, d’une liste de discussion de groupe et de vos clients de discussion de groupe Lync 2010, vous devez vous connecter à\<ce\>pool à l’aide d’un utilisateur connu (par défaut SIP: OCSChat @ nom_domaine. com ou similaire). Les utilisateurs utilisent les services de domaine Active Directory SIP et le service de recherche s’inscrit avec eux pour recevoir les demandes entrantes.

  - Par la suite, vous installez un serveur de chat permanent Lync Server 2013 et un pool de serveurs de chat permanent.

  - Lorsque les utilisateurs sont généralement hors ligne (par exemple, un week-end):
    
      - Désactivez Lync Server 2010, discussion de groupe.
    
      - Migrer les données de Lync Server 2010, pool de discussion de groupe vers le pool de serveurs Lync Server 2013 persistent.
    
      - Supprimez l’utilisateur connu des services de domaine Active Directory (AD FS).
    
      - Créer un *point de terminaison hérité* avec le même URI SIP que l’utilisateur connu précédemment supprimé.
    
      - Démarrez Lync Server 2013, serveurs de chat permanent.

  - Les utilisateurs se connectent de nouveau en utilisant leur discussion de groupe Lync 2010 et se connectent à leurs données sans avoir besoin de modifier une configuration.

  - Par la suite, vous pouvez désactiver la mise à niveau de Lync Server 2010, discussion de groupe. Par la suite, vous pouvez déployer Lync Server 2013, le serveur de chat permanent et installer de nouveaux pools de serveurs Lync Server 2013 permanents.

Pour plus d’informations sur la migration de Lync Server 2010, la discussion de groupe vers Lync Server 2013, le serveur de chat permanent, voir [migration de Lync server 2010, discussion de groupe ou conversation de groupe Microsoft Office Communications Server 2007 R2 vers Lync server 2013, serveur de chat permanent](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Pour procéder à la compatibilité descendante (pour créer un point de terminaison serveur Chat permanent qui pointe vers un pool de serveurs de chat permanent, qui peut être utilisé par les clients de pool de discussion de groupe existants):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Ensuite, configurez les clients de chat permanent pour qu’ils utilisent cette adresse SIP comme objet de contact. L’adresse SIP est créée à l’aide de l’applet de nouvelle applet de **CsPersistentChatEndpoint** pour un pool de serveurs de chat permanent spécifique.

Pour ajouter le point de terminaison serveur Chat permanent à l’aide de l’interface de ligne de commande Windows PowerShell, considérez l’exemple suivant. Dans le cas présent, vous configurez l’objet contact pour qu’il soit nommé «persistentchat» sur la topologie «contoso.com», où le nom de domaine complet (FQDN) du pool est «pcpool.contoso.com»:

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>Voir aussi


[Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de conversation permanente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

