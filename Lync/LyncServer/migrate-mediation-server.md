---
title: Migration du serveur de médiation
TOCTitle: Migration du serveur de médiation
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205173(v=OCS.15)
ms:contentKeyID: 49298536
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration du serveur de médiation

 

_**Dernière rubrique modifiée :** 2012-09-28_

Votre serveur de médiation est fusionné dans votre topologie pilote Lync Server 2013 lorsque vous exécutez l’Assistant Fusion. Cependant, vous configurez le serveur de médiation Lync Server 2013 une fois que tous les utilisateurs ont migré car un pool Office Communications Server 2007 R2 ne peut pas communiquer avec un serveur de médiation Lync Server 2013. Pendant la migration côte à côte, le pool Lync Server 2013 communique avec le serveur de médiation Office Communications Server 2007 R2.

Lorsque vous configurez votre serveur de médiation Lync Server 2013, vous devez également mettre à niveau ou remplacer vos passerelles Office Communications Server 2007 R2. Les passerelles Office Communications Server 2007 R2 ne prennent pas en charge le serveur de médiation Lync Server 2013. Vous devez déployer des passerelles certifiées pour Lync Server 2013 et les associer au serveur de médiation Lync Server 2013. Cette étape est préalablement requise pour pouvoir mettre complètement hors service votre déploiement Office Communications Server 2007 R2.

Les rubriques de cette section décrivent les tâches de configuration à exécuter une fois que vous avez effectué votre migration du serveur de médiation Lync Server 2013. La transition du serveur de médiation colocalisé vers un serveur de médiation autonome est une tâche facultative.

  - [Configuration du serveur de médiation](configure-mediation-server.md)

  - [Modification des itinéraires de communications vocales pour l’utilisation du nouveau serveur de médiation Lync Server 2013](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Transition d’un serveur de médiation colocalisé vers un serveur de médiation autonome (facultatif)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

