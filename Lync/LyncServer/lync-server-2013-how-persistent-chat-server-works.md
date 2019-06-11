---
title: 'Lync Server 2013: fonctionnement du serveur de chat permanent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bf6179e1ce24264c2079b3096fa9bb8c539ca1c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>Fonctionnement du serveur Chat permanent dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-21_

Lync Server 2013, Lync Chat Server vous permet de participer à des conversations à plusieurs sujets qui persistent dans le temps. Le serveur de chat permanent peut aider votre organisation à effectuer les opérations suivantes:

  - Amélioration de la communication entre les équipes géographiquement dispersées et celles à plusieurs fonctions

  - Élargissement de la sensibilisation et de la participation aux informations

  - Améliorer la communication avec votre organisation étendue

  - Réduire la surcharge d’information

  - Amélioration de la prise en charge des informations

  - Augmenter la dispersion des connaissances et informations importantes

Vous pouvez déployer le serveur de chat permanent en tant que rôle facultatif avec Lync Server 2013. Les services de chat permanent s’exécutent sur un pool dédié, et un pool de serveurs de chat permanent dépend d’un pool de serveurs Lync pour router des messages vers ce dernier. Les clients utilisent la communication de discussion eXtensible par SIP (XCCOS). Les serveurs front-end de Lync Server sont configurés pour acheminer le trafic vers un pool de serveurs de chat permanent.

<div>

## <a name="high-level-architecture"></a>Architecture de haut niveau

Les schémas suivants fournissent des perspectives de haut niveau de l’architecture et des services de chat permanent du serveur.

**Architecture de haut niveau du serveur de conversation permanente**

![Architecture serveur de chat permanent.] (images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Architecture serveur de chat permanent.")

**Services de haut niveau du serveur de conversation permanente**

![Composants serveur de chat permanent.] (images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Composants serveur de chat permanent.")

Deux services s’exécutent sur les serveurs front-end du serveur Chat permanent:

  - Conversation permanente (canal)

  - Conformément

<div>

## <a name="persistent-chat-channel-service"></a>Service de chat permanent (canal)

Le service de chat permanent (canal) est le principal service responsable du serveur de chat permanent. Ce service fournit les fonctions suivantes:

  - acceptation des messages entrants ;

  - inscription et listage des participants en ligne dans une salle de conversation permanente ;

  - retransmission des messages vers les abonnés à d’autres canaux ;

  - Implémente la logique pour la gestion des canaux, l’invitation de salle de conversation, la recherche et de nouvelles notifications de contenu

Le service de chat permanent (canal) stocke et accède au contenu des salles de conversation et aux autres métadonnées système (règles d’autorisation, etc.) à l’aide du magasin permanent de conversation. Ce service stocke les fichiers téléchargés dans des salles de conversation dans le magasin de fichiers de chat permanent.

</div>

<div>

## <a name="compliance-service"></a>Service de conformité

Le service de conformité est un composant facultatif de chat permanent qui est chargé de l’archivage du contenu et des événements de conversation dans le magasin de conformité des conversations permanentes. Si le règlement de votre organisation impose un archivage de l’activité de conversation permanente, vous pouvez déployer le service de conformité de conversation permanente facultatif. Le service de conformité est installé sur chaque serveur de chat permanent d’un pool de conversations permanentes. Dans le cadre de la configuration, la compatibilité avec le serveur Chat permanent enregistre les activités de l’utilisateur, telles que la participation et le départ des salles, et la publication et la lecture des messages. Le service de conformité stocke les fichiers qui doivent être archivés dans le magasin de fichiers de conformité des conversations permanentes.

</div>

<div>

## <a name="persistent-chat-web-services"></a>Services Web de chat permanent

Sur les serveurs front-end de Lync Server, deux services s’exécutent en fonction de Internet Information Services (IIS) et sont implémentés en tant que composants Web:

  - **Services Web de chat permanent pour le chargement et le téléchargement de fichiers** Responsable de la publication et de l’extraction de fichiers de salles de conversation.

  - **Services Web de chat permanent pour la gestion des salles de conversation** Responsable d’offrir aux utilisateurs la possibilité de gérer leurs salles de conversation et de créer des salles de conversation.

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>Comment puis-je commencer à utiliser le serveur de chat permanent?

Le serveur Chat permanent est un rôle serveur facultatif au sein de l’infrastructure 2013 de Lync Server. Si vous installez le rôle serveur Chat permanent, tous les utilisateurs qui ont été activés par l’intermédiaire de la stratégie par un administrateur peuvent utiliser la conversation permanente avec le client 2013 Lync.

Pour plus d’informations sur le déploiement d’un serveur de chat permanent et permettre aux utilisateurs de tirer parti des fonctionnalités d’une stratégie, voir [déploiement d’un serveur de chat permanent dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Pour plus d’informations sur la configuration des paramètres du déploiement de votre serveur Chat permanent, voir [déploiement d’un serveur de chat permanent dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) et [gestion de Lync Server 2013, serveur de chat permanent](managing-lync-server-2013-persistent-chat-server.md).

Pour plus d’informations sur la façon d’activer les utilisateurs par stratégie de telle sorte qu’ils puissent tirer parti de la fonctionnalité de conversation persistante dans le client Lync 2013, voir [déploiement d’un serveur de chat permanent dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) et [gestion de Lync Server 2013, serveur de chat permanent](managing-lync-server-2013-persistent-chat-server.md).

Pour plus d’informations sur la configuration des paramètres de conformité, reportez-vous à la section [gestion de Lync server 2013, serveur de chat permanent](managing-lync-server-2013-persistent-chat-server.md) .

</div>

<div>

## <a name="persistent-chat-call-flows"></a>Flux d’appels permanents de conversation

Le client de chat permanent communique avec le service de chat permanent à l’aide de XCCOS. Les séquences suivantes décrivent le processus de connexion et un scénario standard d’abonnement de salle et de publication de message.

<div>

## <a name="sign-in"></a>Connexion

Le diagramme de flux d’appels et les étapes suivants décrivent le processus de connexion.

**Flux d’appels de connexion permanent du client de conversation**

![Diagramme de flux d’appels de chat permanent du serveur.] (images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagramme de flux d’appels de chat permanent du serveur.")

1.  Le client de chat permanent envoie d’abord un abonnement SIP pour extraire le document de mise en service intrabande du serveur. Ce document indique si la conversation permanente est activée ou désactivée pour l’utilisateur et la liste des URI SIP pour le pool de serveurs de chat permanent.

2.  Le client de chat permanent envoie un message d’invitation SIP à l’URI SIP du serveur de chat permanent qu’il a obtenu lors de l’étape précédente. La séquence d’invitation est suivie de 200 OK et ACK, et le client chat permanent a ouvert une session SIP avec un point de terminaison de serveur Chat permanent. Par conséquent, le client de chat permanent communique avec le serveur de chat permanent en envoyant des messages d’informations SIP contenant des messages de discussion ou des commandes demandant au serveur d’effectuer une action. Tous ces messages sont reconnus par l’utilisation de 200 OK ou d' 503 Service indisponible (autrement dit, en cas de charge importante du serveur). Si le client reçoit une réponse 503, il tentera de réessayer le message. (Cet exemple n’inclut pas de réponse 503.) Si le serveur accepte le message ou la commande et envoie 200 OK, il fournit une réponse au client sous la forme d’un message d’INFO SIP distinct. Cette réponse inclut une référence à la commande d’origine.

3.  Le client de chat permanent envoie un message d’information SIP contenant la commande XCCOS **GetServerInfo** . Le serveur Chat permanent répond avec un nouveau message SIP INFO contenant des informations sur la configuration du service de chat permanent.

4.  Le client de chat permanent envoie un message d’information SIP contenant la commande XCCOS **GetAssociations** . Le serveur Chat permanent répond avec un nouveau message SIP INFO qui contient la liste des salles dont l’utilisateur est membre. Le client de chat permanent répète la commande pour récupérer la liste des salles dont il est le gestionnaire.

5.  Le client de chat permanent obtient la liste des salles suivies du document «présence», où chaque salle suivie est représentée par une catégorie «roomSetting». Toutes les salles suivies sont jointes à l’aide d’un seul message SIP INFO contenant la commande XCCOS **bPour y accéder** qui contient la liste des URI de la salle. Dans la mesure où la liste des salles suivies est conservée sur le serveur, tous les clients sur n’importe quel ordinateur disposent de la même liste de salles suivies pour l’URI de l’utilisateur spécifié. Le client de chat permanent conserve également la liste des salles ouvertes (si cette option est activée par l’utilisateur) dans le registre de l’ordinateur local et joint chacune de ces pièces lors de la connexion en envoyant un message SIP INFO contenant la commande XCCOS **join** de chaque salle ouverte. . Dans la mesure où cette liste est conservée dans le registre, elle peut être différente sur deux clients de chat permanent s’exécutant sur des ordinateurs différents.

6.  Pour chaque salle jointe, le client de chat permanent envoie un message d’information SIP contenant la commande XCCOS **bccontext** . Le serveur Chat permanent répond avec un nouveau message SIP INFO contenant le message de conversation le plus récent dans la salle.

7.  Le client de chat permanent envoie un message d’information SIP contenant une commande XCCOS **getinv** (qui est une invitation) pour demander toute nouvelle invitation de salle que le client n’a pas encore détectée. Dans un message des informations SIP distinctes, le serveur de chat permanent renvoie une liste de ces salles.

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>S’abonner à une salle et publier un message

Le schéma de flux d’appels et les étapes suivants décrivent un scénario type d’abonnement de salle et de publication de message.

**Flux d’abonnement d’une salle de conversation permanente et flux d’appels de publication de message**

![Scénario d’abonnement de salle et de publication de message.] (images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Scénario d’abonnement de salle et de publication de message.")

1.  À partir du client de chat permanent, User1 clique sur **rejoindre une salle de conversation**, clique sur **Rechercher**, puis saisit des critères de recherche. Le client de chat permanent envoie un message d’information SIP contenant la commande XCCOS **chansrch** (recherche de salle), ainsi que les critères de recherche. Le serveur Chat permanent interroge la base de données principale et les réponses dans un nouveau message SIP INFO contenant une liste des salles disponibles qui répondent aux critères de recherche.

2.  User1 sélectionne la salle de conversation à laquelle il souhaite participer, puis clique sur **suivre cette salle**. Le client de chat permanent envoie un message de chat permanent contenant la commande de **jointure** XCCOS et l’ID de la salle de conversation sélectionnée par l’utilisateur. Le serveur Chat permanent répond avec un message SIP INFO contenant les données de mise en service.

3.  Le client de chat permanent envoie un message de chat permanent contenant le message SIP ( **** contexte de conversation). Le serveur Chat permanent récupère l’historique de la discussion et la renvoie au client de chat permanent dans un message d’informations SIP distinct. À ce stade, l’utilisateur entre dans la salle de conversation et est prêt à participer.

4.  User1 entre un nouveau message, puis clique sur **Envoyer**. Le client chat permanent publie le message dans la salle de conversation à l’invite SIP INFO XCCOS **grpchat** . Le serveur Chat permanent enregistre une copie de ce nouveau message dans la base de données principale de conversation permanente.

5.  Serveur Chat permanent envoie une copie distincte du message SIP INFO XCCOS **grpchat** message à utilisateur2, qui a déjà entré la salle de conversation.

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>Flux d’appels permanents de conformité des conversations

Le serveur Chat permanent utilise Message Queuing (également connu sous le nom de MSMQ) ainsi qu’une base de données de conformité supplémentaire (mgccomp) pour traiter les données de conformité. Pour illustrer le traitement des événements de conformité, la séquence d’événements suivante décrit le traitement d’un événement de publication de message.

1.  Un utilisateur publie un message dans une salle.

2.  Serveur Chat permanent place les informations relatives à l’événement dans une file d’attente de Message Queuing privée.

3.  Le serveur de conformité des conversations permanent lit cet événement à partir de la file d’attente, puis le place dans la base de données mgccomp pour le traitement.

4.  Périodiquement, le serveur de conformité des conversations persistantes traite un ensemble d’événements dans la base de données et les envoie à l’adaptateur de conformité de la conversation permanente pour le traitement.

5.  Si la carte traite correctement les données, le serveur de conformité des conversations permanentes supprime les événements de la base de données mgccomp.

</div>

</div>

<span> </span>

</div>

</div>

</div>

