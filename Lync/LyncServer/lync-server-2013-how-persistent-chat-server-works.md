---
title: 'Lync Server 2013 : fonctionnement du serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d919d7c9d955355a45ebf3c05391204ca919a3fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528171"
---
# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>Fonctionnement du serveur de conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-21_

Lync Server 2013, serveur de conversation permanente vous permet de participer à des conversations en plusieurs rubriques, qui sont conservées au fil du temps. Le serveur de conversation permanente peut aider votre organisation à effectuer les opérations suivantes :

  - améliorer la communication entre les équipes géographiquement dispersées et multifonctionnelles ;

  - élargir la prise en compte des informations et la participation ;

  - améliorer la communication dans l’ensemble de votre organisation ;

  - réduire la surcharge d’informations ;

  - améliorer la prise en compte des informations ;

  - accroître la dissémination des connaissances et des informations importantes.

Vous pouvez déployer le serveur de conversation permanente comme un rôle facultatif avec Lync Server 2013. Les services de conversation permanente s’exécutent sur un pool dédié et un pool de serveurs de conversation permanente dépend d’un pool Lync Server pour acheminer les messages vers celui-ci. Les clients utilisent le protocole XCCOS (eXtensible Chat Communication Over SIP). Les serveurs frontaux Lync Server sont configurés pour acheminer le trafic vers un pool de serveurs de conversation permanente.

<div>

## <a name="high-level-architecture"></a>Architecture de haut niveau

Les diagrammes suivants fournissent des perspectives de haut niveau de l’architecture et des services du serveur de conversation permanente.

**Architecture de haut niveau du serveur de conversation permanente**

![Architecture de serveur de conversation permanente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Architecture de serveur de conversation permanente.")

**Services de haut niveau du serveur de conversation permanente**

![Composants de serveur de conversation permanente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Composants de serveur de conversation permanente.")

Deux services s’exécutent sur les serveurs frontaux du serveur de conversation permanente :

  - Conversation permanente (canal)

  - Conformité

<div>

## <a name="persistent-chat-channel-service"></a>Service de conversation permanente (canal)

Le service de conversation permanente (canal) est le service principal responsable du serveur de conversation permanente. Ce service offre les fonctions suivantes :

  - acceptation des messages entrants ;

  - Inscrit et répertorie les participants en ligne dans une salle de conversation permanente

  - retransmission des messages vers les abonnés à d’autres canaux ;

  - implémentation de la logique de gestion des canaux, d’invitation aux salles de conversation, de recherche et de notifications de nouveau contenu.

Le service de conversation permanente (canal) stocke et accède au contenu de la salle de conversation et à d’autres métadonnées système (règles d’autorisation, etc.) à l’aide de la Banque de conversation permanente. Ce service stocke les fichiers chargés dans les salles de conversation du magasin de fichiers de conversation permanente.

</div>

<div>

## <a name="compliance-service"></a>Service de conformité

Le service de conformité est un composant facultatif du serveur de conversation permanente et est responsable de l’archivage du contenu et des événements de conversation dans le magasin de conformité de la conversation permanente. Si votre organisation a des réglementations qui nécessitent l’archivage de l’activité de conversation permanente, vous pouvez déployer le service de conformité de conversation permanente facultatif. Le service de conformité est installé sur chaque serveur de conversation permanente d’un pool de conversations permanentes. Une fois configurée, la conformité du serveur de conversation permanente enregistre les activités de l’utilisateur, telles que la jonction et la fermeture des salles, ainsi que la publication et la lecture des messages. Le service de conformité stocke les fichiers qui doivent être archivés dans le magasin de fichiers de conformité de la conversation permanente.

</div>

<div>

## <a name="persistent-chat-web-services"></a>Services Web de conversation permanente

Sur les serveurs frontaux Lync Server, deux services exécutés dépendent des services IIS (Internet Information Services) et sont implémentés en tant que composants Web :

  - **Services Web de conversation permanente pour le chargement/téléchargement de fichiers** Responsable de la publication et de l’extraction de fichiers à partir de salles de conversation.

  - **Services Web de conversation permanente pour la gestion des salles de conversation** Chargé de fournir aux utilisateurs la possibilité de gérer leurs salles de conversation et de créer de nouvelles salles de conversation.

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>Comment puis-je commencer à utiliser le serveur de conversation permanente ?

Le serveur de conversation permanente est un rôle serveur facultatif au sein de l’infrastructure Lync Server 2013. Si vous installez le rôle de serveur de conversation permanente, tous les utilisateurs qui ont été activés par le biais d’une stratégie par un administrateur peuvent utiliser la conversation permanente avec le client Lync 2013.

Pour plus d’informations sur le déploiement du serveur de conversation permanente et sur la façon dont les utilisateurs peuvent tirer parti des fonctionnalités par le biais d’une stratégie, voir [Deploying persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Pour plus d’informations sur la configuration des paramètres de votre déploiement de serveur de conversation permanente, voir [Deploying persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) et [Managing Lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).

Pour plus d’informations sur la façon d’activer les utilisateurs par une stratégie de sorte qu’ils puissent utiliser la fonctionnalité de conversation permanente dans le client Lync 2013, consultez la rubrique [Deploying persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) et [Managing Lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).

Si vous avez déployé la conformité de la conversation permanente, reportez-vous à la rubrique [Managing Lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) pour plus d’informations sur la configuration des paramètres de conformité.

</div>

<div>

## <a name="persistent-chat-call-flows"></a>Flux d’appels de conversation permanente

Le client de conversation permanente communique avec le service de conversation permanente à l’aide de XCCOS. Les séquences suivantes décrivent le processus de connexion, ainsi qu’un scénario classique d’abonnement à une salle et de publication de messages.

<div>

## <a name="sign-in"></a>Connexion

Le diagramme de flux d’appels et les étapes suivants décrivent le processus de connexion.

**Flux d’appels de connexion au client de conversation permanente**

![Diagramme de flux d’appels de serveur de conversation permanente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagramme de flux d’appels de serveur de conversation permanente.")

1.  Le client de conversation permanente envoie d’abord un abonnement SIP pour récupérer le document de mise en service intrabande à partir du serveur. Ce document indique si la conversation permanente est activée ou désactivée pour l’utilisateur et la liste des URI SIP pour le pool de serveurs de conversation permanente.

2.  Le client de conversation permanente envoie un message d’INVITE SIP à l’URI SIP du serveur de conversation permanente qu’il a obtenu à l’étape précédente. La séquence INVITE est suivie de 200 OK et ACK, et le client de conversation permanente a ouvert une session SIP avec un point de terminaison de serveur de conversation permanente. Par conséquent, le client de conversation permanente communique avec le serveur de conversation permanente en envoyant des messages d’informations SIP contenant des messages de conversation ou des commandes demandant au serveur d’effectuer une action. Tous ces messages sont reconnus avec 200 OK ou le service 503 indisponible (en cas de charge importante sur le serveur). Si le client reçoit une réponse 503, il retentera le message. (Cet exemple n’inclut pas de réponse 503.) Si le serveur accepte le message ou la commande et envoie 200 OK, il fournit une réponse au client sous la forme d’un message INFO SIP distinct. Cette réponse inclut une référence à la commande d’origine.

3.  Le client de conversation permanente envoie un message d’informations SIP contenant la commande XCCOS **GetServerInfo** . Le serveur de conversation permanente répond avec un nouveau message d’informations SIP contenant des informations sur la configuration du service de conversation permanente.

4.  Le client de conversation permanente envoie un message d’informations SIP contenant la commande XCCOS **GetAssociations** . Le serveur de conversation permanente répond avec un nouveau message d’informations SIP contenant la liste des salles dont l’utilisateur est membre. Le client de conversation permanente répète la commande pour récupérer la liste des salles dont l’utilisateur est responsable.

5.  Le client de conversation permanente obtient la liste des salles suivies à partir du document « présence », où chaque salle de suivi est représentée par une catégorie « roomSetting ». L’accès à toutes les salles suivies se fait par le biais d’une commande unique SIP INFO qui contient la commande XCCOS **bjoin**, qui elle-même contient la liste d’URI des salles. La liste des salles suivies étant conservée sur le serveur, les clients des ordinateurs ont tous la même liste de salles suivies correspondant l’URI utilisateur spécifiée. Le client de conversation permanente conserve également la liste des salles ouvertes (si cette option est activée par l’utilisateur) dans le registre de l’ordinateur local, puis joint chacune de ces salles lors de la connexion en envoyant un message INFO SIP contenant la commande XCCOS **join** pour chaque salle ouverte. Cette liste étant conservée dans le registre, elle peut être différente sur deux clients de conversation permanente exécutés sur des ordinateurs différents.

6.  Pour chaque salle jointe, le client de conversation permanente envoie un message d’informations SIP contenant la commande XCCOS **bccontext** . Le serveur de conversation permanente répond avec un nouveau message d’informations SIP contenant le message de conversation le plus récent dans la salle.

7.  Le client de conversation permanente envoie un message d’informations SIP contenant une commande XCCOS **getinv** (Get invitation) pour demander les nouvelles invitations de salle que le client n’a pas encore vues. Dans un message d’informations SIP distinct, le serveur de conversation permanente renvoie une liste de ces salles.

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>S’inscrire à une salle et publier un message

Le diagramme de flux d’appels et les étapes suivants décrivent un scénario classique d’abonnement à une salle et de publication de messages.

**Flux d’appels de salle de conversation permanente et de publication de messages**

![Scénario d’abonnement à une salle et de publication de messages.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Scénario d’abonnement à une salle et de publication de messages.")

1.  À partir du client de conversation permanente, utilisateur1 clique sur **rejoindre une salle de conversation**, clique sur **Rechercher**, puis entre certains critères de recherche. Le client de conversation permanente envoie un message d’informations SIP contenant la commande XCCOS **chansrch** (recherche de salle), ainsi que les critères de recherche. Le serveur de conversation permanente interroge la base de données principale et les réponses dans un nouveau message d’informations SIP contenant une liste des salles disponibles qui répondent aux critères de recherche.

2.  L’utilisateur 1 sélectionne la salle de conversation qu’il souhaite rejoindre et clique sur **Suivre cette salle**. Le client de conversation permanente envoie un message d’information SIP à un serveur de conversation permanente contenant la commande XCCOS **join** et l’ID de la salle de conversation sélectionnée par l’utilisateur. Le serveur de conversation permanente répond avec un message d’informations SIP contenant les données de mise en service.

3.  Le client de conversation permanente envoie un message d’information SIP à un serveur de conversation permanente qui contient la commande XCCOS **bccontext** (contexte de messagerie instantanée). Le serveur de conversation permanente récupère l’historique de la conversation et le renvoie au client de conversation permanente dans un message d’informations SIP distinct. À ce stade, l’utilisateur se trouve dans la salle de conversation et est en mesure de participer.

4.  L’utilisateur 1 entre un nouveau message et clique sur **Envoyer**. Le client de conversation permanente envoie le message à la salle de conversation dans une commande SIP INFO XCCOS **grpchat** . Le serveur de conversation permanente stocke une copie de ce nouveau message dans la base de données principale de conversation permanente.

5.  Le serveur de conversation permanente envoie une copie distincte du message SIP INFO XCCOS **grpchat** à utilisateur2, qui a déjà accédé à la salle de conversation.

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>Flux d’appels de conformité de conversation permanente

Le serveur de conversation permanente utilise Message Queuing (également appelé MSMQ) et une base de données de conformité supplémentaire (mgccomp) pour traiter les données de conformité. À titre d’exemple de la façon dont les événements de conformité sont traités, la séquence d’événements suivante illustre le traitement d’un événement de publication de message.

1.  Un utilisateur publie un message dans une salle.

2.  Le serveur de conversation permanente place les informations relatives à l’événement dans une file d’attente Message Queuing privée.

3.  Le serveur de conformité de conversation permanente lit cet événement à partir de la file d’attente et le place dans la base de données mgccomp pour le traiter ultérieurement.

4.  Régulièrement, le serveur de conformité de conversation permanente traite un ensemble d’événements dans la base de données et les envoie à l’adaptateur de conformité de conversation permanente pour traitement.

5.  Si l’adaptateur traite correctement les données, le serveur de conformité de conversation permanente supprime les événements de la base de données mgccomp.

</div>

</div>

<span> </span>

</div>

</div>

</div>

