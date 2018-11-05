---
title: Exécution de compatibilité descendante pour la conversation permanente
TOCTitle: Exécution de compatibilité descendante pour la conversation permanente
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204901(v=OCS.15)
ms:contentKeyID: 49297216
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exécution de compatibilité descendante pour la conversation permanente

 

_**Dernière rubrique modifiée :** 2013-02-21_

Le point de terminaison du serveur de conversations permanentes de Lync Server 2013 permet de créer une simple URL qui pointe vers un pool de serveurs de conversations permanentes. Cela est utile pour les clients hérités ( Microsoft Office Communications Server 2007 R2serveur Group Chat ou Lync Server 2010, conversation de groupe), car les utilisateurs peuvent entrer une simple URL durant la configuration manuelle, quand ils tentent de faire pointer le client hérité vers un ordinateur exécutant Lync 2013, conversation permanente. Ce point de terminaison n’est pas utilisé par la conversation permanente. Il est nécessaire uniquement pour les clients hérités. Cela est utile pour la période intermédiaire où des salles peuvent être migrées alors que les clients Lync 2013 n’ont pas été déployés dans l’ensemble de l’organisation. Les utilisateurs qui exécutent Lync 2010Group Chat (client) peuvent toujours se connecter à serveur de conversations permanentesserveur principal.

Vous n’avez pas besoin de créer plusieurs points de terminaison serveur de conversations permanentes. Un seul suffit pour chaque pool de serveurs de conversations permanentes. Les administrateurs peuvent créer plusieurs points de terminaison (un par pool). Cependant, les clients hérités peuvent être configurés pour se connecter à un seul pool à la fois. Dans le scénario habituel ou standard, le déploiement hérité concerne un seul pool. En règle générale, un nouveau déploiement migre ce pool vers un nouveau serveur Lync Server 2013 et peut éventuellement ajouter des pools de serveurs de conversations permanentes supplémentaires.

Ce scénario standard suit généralement le modèle suivant :

  - Vous administrez les utilisateurs avec un pool Lync Server 2010, conversation de groupe. Vos clients Conversation de groupe Lync 2010 se connectent à ce pool à l’aide d’un utilisateur reconnu (soit l’utilisateur par défaut sip:ocschat@ *\<nom\_domaine\>* .com, soit un utilisateur similaire). Les utilisateurs sont des services de domaine Active Directory compatibles avec SIP. Par ailleurs, le service de recherche s’inscrit auprès d’eux pour recevoir les requêtes entrantes.

  - Vous installez ensuite un serveur de conversations permanentes et un pool de serveurs de conversations permanentesLync Server 2013.

  - Quand les utilisateurs sont généralement hors connexion (par exemple, le week-end) :
    
      - Désactivez Lync Server 2010, conversation de groupe.
    
      - Effectuez la migration des données du pool Lync Server 2010, conversation de groupe vers le pool de serveurs de conversations permanentesLync Server 2013.
    
      - Supprimez l’utilisateur reconnu des services de domaine Active Directory.
    
      - Créez un *point de terminaison hérité* avec le même URI SIP que celui de l’utilisateur reconnu supprimé précédemment.
    
      - Démarrez les serveurs de conversations permanentesLync Server 2013.

  - Les utilisateurs se reconnectent à l’aide de leur version de Conversation de groupe Lync 2010 (client) et se connectent à leurs données sans devoir modifier la configuration.

  - Plus tard, vous pourrez désaffecter Lync Server 2010, conversation de groupe, puis déployer le serveur de conversations permanentesLync Server 2013 et installer de nouveaux pools de serveurs de conversations permanentesLync Server 2013.

Pour plus d’informations sur la migration de Lync Server 2010, conversation de groupe vers un serveur de conversations permanentesLync Server 2013, reportez-vous à [Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de conversation permanente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Pour permettre la rétrocompatibilité (créer un point de terminaison de serveur de conversations permanentes qui pointe vers un pool de serveurs de conversations permanentes utilisable par les clients du pool Group Chat hérité) :

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Configurez ensuite les clients de conversation permanente afin d’utiliser cette adresse SIP comme objet contact. L’adresse SIP est créée à l’aide de l’applet de commande **New-CsPersistentChatEndpoint** pour un pool de serveurs de conversations permanentes spécifique.

Pour ajouter le point de terminaison du serveur de conversations permanentes à l’aide de l’interface de ligne de commande Windows PowerShell, suivez l’exemple ci-après. Dans le cas présent, vous configurez l’objet contact afin de le nommer « persistentchat » dans la topologie « contoso.com », où le nom de domaine complet du pool est « pcpool.contoso.com » :

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

## Voir aussi

#### Concepts

[Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de conversation permanente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

