---
title: Fonctionnement d’un serveur de conversation permanente dans Lync Server 2013
TOCTitle: Fonctionnement d’un serveur de conversation permanente dans Lync Server 2013
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49891315
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Fonctionnement d’un serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-21_

Le serveur de conversations permanentes de Lync Server 2013 vous permet de participer à des conversations permanentes à plusieurs sur un sujet précis. Le serveur de conversations permanentes peut aider votre organisation à réaliser ce qui suit :

  - améliorer la communication entre les équipes géographiquement dispersées et multifonctionnelles ;

  - élargir la prise en compte des informations et la participation ;

  - améliorer la communication dans l’ensemble de votre organisation ;

  - réduire la surcharge d’informations ;

  - améliorer la prise en compte des informations ;

  - accroître la dissémination des connaissances et des informations importantes.

Vous pouvez déployer le serveur de conversations permanentes en tant que rôle facultatif en même temps que Lync Server 2013. Les services de conversation permanente s’exécutent sur un pool dédié et un pool de serveurs de conversations permanentes dépend d’un pool Lync Server pour lui acheminer les messages. Les clients utilisent le protocole XCCOS (eXtensible Chat Communication Over SIP). Les serveurs frontauxLync Server sont configurés pour acheminer le trafic vers un pool de serveurs de conversations permanentes.

## Architecture de haut niveau

Les diagrammes suivants offrent des perspectives de haut niveau des services et de l’architecture du serveur de conversations permanentes.

**Architecture de haut niveau du serveur de conversation permanente**

![Architecture du serveur de conversation permanente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Architecture du serveur de conversation permanente.")

**Services de haut niveau du serveur de conversation permanente**

![Composants du serveur de conversation permanente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Composants du serveur de conversation permanente.")

Deux services s’exécutent sur les serveurs frontaux du serveur de conversations permanentes :

  - Conversation permanente (canal)

  - Conformité

## Service de conversation permanente (canal)

Le service de conversation permanente (canal) est le service principal en charge du serveur de conversations permanentes. Ce service offre les fonctions suivantes :

  - acceptation des messages entrants ;

  - inscription et inventaire des participants en ligne dans une salle de conversation permanente ;

  - retransmission des messages vers les abonnés à d’autres canaux ;

  - implémentation de la logique de gestion des canaux, d’invitation aux salles de conversation, de recherche et de notifications de nouveau contenu.

Le service de conversation permanente (canal) stocke et accède au contenu des salles de conversation et à d’autres métadonnées système (règles d’autorisation, etc.) en utilisant le magasin de conversation permanente. Ce service stocke les fichiers téléchargés dans les salles de conversation dans le magasin de fichiers de conversation permanente.

## Service de conformité

Le service de conformité est un composant facultatif du serveur de conversations permanentes qui est chargé d’archiver le contenu et les événements de conversation dans le magasin de conformité de la conversation permanente. Si le règlement de votre organisation impose un archivage de l’activité de conversation permanente, vous pouvez déployer le service de conformité de conversation permanente facultatif. Ce service est installé sur chaque serveur de conversations permanentes d’un pool de conversation permanente. Quand elle est configurée, la conformité du serveur de conversations permanentes enregistre l’activité des utilisateurs à mesure qu’ils rejoignent et quittent les salles et qu’ils publient et lisent des messages. Le service de conformité stocke les fichiers qui ont besoin d’être archivés dans le magasin de fichiers de conformité de la conversation permanente.

## Services web de conversation permanente

Les serveurs frontauxLync Server intègrent deux services qui dépendent des services Internet (IIS). Ils s’exécutent et s’implémentent en tant que composants web :

  - Services web de **conversation permanente pour le téléchargement de fichiers** : ils sont chargés de la publication et de la récupération des fichiers dans les salles de conversation.

  - Services web de **conversation permanente pour la gestion des salles de conversation** : ils sont chargés d’offrir aux utilisateurs la possibilité de gérer leurs salles de conversation et d’en créer des nouvelles.

## Utilisation du serveur de conversations permanentes

Le serveur de conversations permanentes est un rôle de serveur facultatif au sein de l’infrastructure Lync Server 2013. Si vous installez le rôle de serveur de conversations permanentes, les utilisateurs qui ont été activés au moyen d’une stratégie par un administrateur peuvent utiliser la conversation permanente avec le client Lync 2013. Pour plus d’informations sur la façon de déployer le serveur de conversations permanentes et de permettre aux utilisateurs de tirer parti de ses fonctionnalités par le biais d’une stratégie, voir [Déploiement d’un serveur de conversation permanente dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Pour plus d’informations sur la façon de configurer les paramètres de déploiement de votre serveur de conversations permanentes, voir [Déploiement d’un serveur de conversation permanente dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) et [Gestion de Lync Server 2013, serveur de conversation permanente](managing-lync-server-2013-persistent-chat-server.md).

Pour plus d’informations sur la façon d’activer les utilisateurs par le biais d’une stratégie et ainsi leur permettre de tirer parti des fonctionnalités de conversation permanente dans le client Lync 2013, voir [Déploiement d’un serveur de conversation permanente dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) et [Gestion de Lync Server 2013, serveur de conversation permanente](managing-lync-server-2013-persistent-chat-server.md).

Si vous avez déployé la conformité de la conversation permanente, voir [Gestion de Lync Server 2013, serveur de conversation permanente](managing-lync-server-2013-persistent-chat-server.md) pour plus d’informations sur la façon de configurer les paramètres de conformité.

## Flux d’appels de la conversation permanente

Le client Lync communique avec le service de conversation permanente à l’aide du protocole XCCOS. Les séquences suivantes décrivent le processus de connexion, ainsi qu’un scénario classique d’abonnement à une salle et de publication de messages.

## Se connecter

La séquence suivante décrit le processus de connexion.

1.  Le client Lync envoie dans un premier temps un message SIP SUBSCRIBE pour récupérer le document de mise en service de la bande entrante auprès du serveur. Ce document indique si la conversation permanente est activée ou désactivée pour l’utilisateur et la liste des URI SIP du pool de serveurs de conversations permanentes.

2.  Le client Lync envoie un message SIP INVITE à l’URI SIP du serveur de conversations permanentes qu’il a obtenue à l’étape précédente. La séquence INVITE est suivie des réponses 200 OK et ACK. À cet instant, le client Lync a ouvert une session SIP avec un système d’extrémité de serveur de conversations permanentes. Par conséquent, le client communique avec le serveur de conversations permanentes en envoyant des messages SIP INFO qui contiennent des messages de conversation ou des messages demandant au serveur d’effectuer une action. En guise d’accusé de réception, tous ces messages reçoivent une réponse 200 OK ou 503 Service Unavailable (en cas de charge importante du serveur). Si le client reçoit une réponse 503, une nouvelle tentative d’envoi du message est opérée. (Cet exemple n’inclut pas de réponse 503.) Si le serveur accepte le message ou la commande et envoie la réponse 200 OK, il fournit une réponse au client sous forme de message SIP INFO distinct. Cette réponse comprend une référence à la commande d’origine.

3.  Le client Lync envoie un message SIP INFO qui contient la commande XCCOS **getserverinfo**. Le serveur de conversations permanentes répond par un nouveau message SIP INFO qui contient des informations sur la configuration du service de conversation permanente.

4.  Le client Lync envoie un message SIP INFO qui contient la commande XCCOS **getassociations**. Le serveur de conversations permanentes répond par un nouveau message SIP INFO qui contient la liste des salles dont l’utilisateur est membre. Le client Lync répète la commande pour récupérer la liste des salles dont l’utilisateur est responsable.

5.  Le client Lync obtient la liste des salles suivies à partir du document de présence, où chaque salle suivie est représentée par une catégorie « roomSetting ». L’accès à toutes les salles suivies se fait par le biais d’une commande unique SIP INFO qui contient la commande XCCOS **bjoin**, qui elle-même contient la liste d’URI des salles. La liste des salles suivies étant conservée sur le serveur, les clients des ordinateurs ont tous la même liste de salles suivies correspondant l’URI utilisateur spécifiée. Par ailleurs, chaque client Lync conserve la liste des salles ouvertes (si cette option est activée par l’utilisateur) dans le Registre de l’ordinateur local et accède à chacune de ces salles au moment de se connecter en envoyant un message SIP INFO qui contient la commande XCCOS **join** pour chaque salle ouverte. Étant donné que cette liste est conservée dans le Registre, elle peut être différente sur deux clients Lync s’exécutant sur des ordinateurs distincts.

6.  Pour chaque salle rejointe, le client Lync envoie un message SIP INFO qui contient la commande XCCOS **bccontext**. Le serveur de conversations permanentes répond par un nouveau message SIP INFO qui contient le message de conversation le plus récent de la salle.

7.  Le client Lync envoie un message SIP INFO qui contient une commande XCCOS **getinv** (c’est-à-dire, « get invitation ») pour demander les nouvelles invitations éventuelles que le client n’a pas encore obtenues. Dans un autre message SIP INFO, le serveur de conversations permanentes retourne la liste de ces salles.

## S’inscrire à une salle et publier un message

La séquence suivante décrit un scénario classique d’inscription à une salle et de publication de messages.

1.  À partir du client Lync, l’utilisateur 1 clique sur **Joindre une salle de conversation**, sur **Rechercher**, puis entre des critères de recherche. Le client envoie un message SIP INFO qui contient la commande XCCOS **chansrch** de recherche de salle avec les critères de recherche. Le serveur de conversations permanentes interroge la base de données principale et répond par un nouveau message SIP INFO qui contient la liste des salles disponibles répondant aux critères de recherche.

2.  L’utilisateur 1 sélectionne la salle de conversation qu’il souhaite rejoindre et clique sur **Suivre cette salle**. Le client envoie au serveur de conversations permanentes un message SIP INFO qui contient la commande XCCOS **join** et l’ID de la salle de conversation que l’utilisateur a sélectionnée. Le serveur de conversations permanentes répond par un message SIP INFO qui contient les données de mise en service.

3.  Le client Lync envoie au serveur de conversations permanentes un messageSIP INFO qui contient la commande XCCOS **bccontext** (« backchat context »). Le serveur de conversations permanentes récupère l’historique des conversations et le renvoie au client dans un message SIP INFO distinct. À ce stade, l’utilisateur se trouve dans la salle de conversation et est en mesure de participer.

4.  L’utilisateur 1 entre un nouveau message et clique sur **Envoyer**. Le client Lync publie le message dans la salle de conversation au moyen d’une commande SIP INFO XCCOS **grpchat**. Le serveur de conversations permanentes stocke une copie de ce nouveau message dans la base de données principale de conversation permanente.

5.  Le serveur de conversations permanentes envoie une copie du message SIP INFO XCCOS **grpchat** à l’utilisateur 2, qui se trouve déjà dans la salle de conversation.

## Flux d’appels de conformité de la conversation permanente

Pour traiter les données de conformité, le serveur de conversations permanentes utilise Message Queuing (également appelé MSMQ) et une base de données de conformité supplémentaire (mgccomp). À titre d’exemple de la façon dont les événements de conformité sont traités, la séquence d’événements suivante illustre le traitement d’un événement de publication de message.

1.  Un utilisateur publie un message dans une salle.

2.  Le serveur de conversations permanentes place les informations relatives à l’événement dans une file d’attente privée Message Queuing.

3.  Le serveur de conformité de la conversation permanente lit cet événement dans la file d’attente et le place dans la base de données mgccomp en vue d’un traitement ultérieur.

4.  Périodiquement, le serveur de conformité de la conversation permanente traite un ensemble d’événements dans la base de données et les envoie à l’adaptateur de compatibilité de la conversation permanente à des fins de traitement.

5.  Si l’adaptateur traite correctement les données, le serveur de conformité de la conversation permanente supprime les événements de la base de données mgccomp.

